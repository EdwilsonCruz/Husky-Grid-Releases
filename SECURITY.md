# Política de Segurança — Husky Grid

[🇧🇷 Português](SECURITY.md) • [🇺🇸 English](SECURITY.en.md)

Este documento estabelece as diretrizes de segurança, a arquitetura de isolamento de processos e a política de reporte responsável de vulnerabilidades do **Husky Grid**.

---

## 1. Arquitetura de Segurança do Aplicativo

O Husky Grid foi projetado do zero com base no princípio do menor privilégio (*least privilege*) e no isolamento estrito entre o shell do sistema operacional e as páginas web executadas nas grades.

### Isolamento de Partições Chromium
- Cada conta ou jogo executado no Husky Grid recebe uma partição independente (`persist:husky-account-${accountId}`).
- Os cookies, armazenamento local (`localStorage`, `sessionStorage`), IndexedDB e cache de cada partição são totalmente segregados pelo motor Chromium.
- Uma sessão não tem visibilidade nem acesso ao armazenamento ou estado de outra sessão na mesma janela.

### Shell Security e Política de Navegação
- **Content Security Policy (CSP):** Em produção, o shell do aplicativo adota uma política rigorosa de CSP (`script-src 'self'`), impedindo a execução de scripts em linha (*inline*) não autorizados.
- **Bloqueio de Permissões Nativas:** Todas as permissões de hardware sensíveis — incluindo câmera, microfone, geolocalização e acesso a dispositivos USB/Bluetooth — são sumariamente rejeitadas por padrão (`denyPermissions`).
- **Navegação Segura:** Requisições para abertura de novas janelas (`setWindowOpenHandler`) são negadas dentro do aplicativo; links externos confiáveis são delegados exclusivamente ao navegador padrão do sistema operacional (`shell.openExternal`).
- **Prevenção de WebViews não autorizadas:** O evento `will-attach-webview` é bloqueado para impedir a injeção não autorizada de WebViews.

---

## 2. Integridade de Binários e Verificação SHA-256

Para proteger os usuários contra pacotes corrompidos ou ataques no trânsito de rede (*man-in-the-middle*), cada versão disponibilizada na aba [Releases](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases) inclui um manifesto oficial com hashes criptográficos: `SHA256SUMS.txt`.

### Como verificar no Windows (PowerShell)
```powershell
Get-FileHash .\Husky-Grid-Setup-*.exe -Algorithm SHA256
```

### Como verificar no Linux (Bash)
```bash
sha256sum Husky-Grid-*.AppImage
# ou para pacotes .deb:
sha256sum husky-grid_*_amd64.deb
```

Compare a saída com o hash publicado no `SHA256SUMS.txt`. Caso os valores divirjam, **não execute o instalador** e reporte a anomalia imediatamente.

---

## 3. Alertas do Sistema Operacional (Windows SmartScreen e Linux)

O instalador para Windows é gerado via electron-builder (formato NSIS). Em softwares novos e independentes distribuídos fora de lojas de aplicativos fechadas, o Windows Defender SmartScreen pode emitir uma mensagem informando que o fornecedor é desconhecido.

- Esse aviso é decorrente de algoritmos baseados em reputação histórica e telemetria acumulada da Microsoft, não significando a presença de código malicioso.
- Recomendamos sempre confrontar o hash do executável com o arquivo `SHA256SUMS.txt` oficial antes de clicar em *"Mais informações" → "Executar assim mesmo"*.

---

## 4. Divulgação Responsável de Vulnerabilidades (Vulnerability Reporting)

Se você identificar qualquer falha de segurança, brecha de isolamento ou vulnerabilidade no Husky Grid, solicitamos que nos informe de maneira ética e confidencial antes de qualquer divulgação pública:

1. **Canal de contato:** envie um e-mail com detalhes técnicos para `security@huskygrid.com.br` (ou `support@huskygrid.com.br`, ou abra um [Security Advisory privado no GitHub](https://github.com/EdwilsonCruz/Husky-Grid-Releases/security/advisories)).
2. **O que incluir no relatório:**
   - Descrição detalhada da vulnerabilidade.
   - Versão do Husky Grid testada e sistema operacional.
   - Prova de conceito (PoC) ou passo a passo para reproduzir o problema.
   - Impacto estimado (ex.: escalonamento de privilégios, vazamento de partição).
3. **Nosso compromisso:**
   - Confirmaremos o recebimento do relatório em até 48 horas úteis.
   - Avaliaremos a gravidade e manteremos comunicação constante sobre o progresso da correção.
   - Créditos serão atribuídos ao pesquisador caso este autorize a menção nas notas de versão (*Release Notes*).
