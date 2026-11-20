# Política de Privacidade — Husky Grid

[🇧🇷 Português](README.md) • [🇺🇸 English](PRIVACY.en.md)

Última atualização: Novembro de 2026.

Esta política de privacidade descreve como o **Husky Grid** lida com suas informações. Nosso compromisso fundamental é a **transparência**: o Husky Grid é uma ferramenta de produtividade e gerenciamento de sessões, não uma plataforma de coleta de dados.

---

## 1. Dados das Sessões e Jogos (100% Locais)

- **Zero Keylogger e Zero Interceptação de Senhas:** O Husky Grid não intercepta, não monitora, não salva e não envia para nenhum servidor remoto as senhas, logins ou ações que você digita dentro das sessões de jogos ou sites.
- **Isolamento e Armazenamento Local:** Cookies de autenticação, tokens de sessão web, dados em cache e armazenamento de navegador (`localStorage`) são gravados exclusivamente no seu próprio computador, na partição Chromium de cada conta.
- **Configurações e Layouts:** Os nomes das contas, preferências de grade (dockview), perfis criados e configurações do Eco Mode são armazenados localmente no seu computador através da biblioteca `electron-store`.

---

## 2. Comunicação com a Nuvem e Validação de Licença

O aplicativo só se conecta a servidores de controle do Husky Grid para finalidades técnicas específicas ligadas à autenticação e ao licenciamento:

### Dados Coletados no Login e Licença:
Quando você faz login com sua conta do Husky Grid para ativar o plano Pro (ou validar o plano Gratuito), os seguintes dados são transmitidos via conexão segura HTTPS:
1. **Credenciais de Acesso da Conta Husky Grid:** E-mail e senha da sua conta do Husky Grid (utilizados exclusivamente para autenticação na nossa API).
2. **Identificador Anônimo de Dispositivo (`DeviceId`):** Um hash criptográfico gerado a partir de atributos anônimos do sistema (como identificador do processador e hostname) para assegurar o cumprimento do limite de até 2 computadores ativos simultâneos por assinatura.
3. **Status da Assinatura:** Confirmação do plano contratado retornada pelo gateway de pagamento (Stripe), indicando se o plano ativo é Gratuito ou Pro.

### Armazenamento de Tokens:
Os tokens de autenticação retornados pelo nosso backend são armazenados em seu disco local de forma criptografada, utilizando as APIs de segurança nativas do seu sistema operacional (`safeStorage` do Electron / DPAPI no Windows / Keychain no macOS / Secret Service no Linux).

---

## 3. Telemetria e Rastreamento

- **Não coletamos telemetria invasiva de uso:** O Husky Grid não monitora quais abas você abre, quais itens adquire nos jogos ou o conteúdo das páginas acessadas.
- **Atualizações Automáticas:** Caso o serviço de verificação de atualizações esteja ativado, o aplicativo fará requisições ocasionais ao GitHub Releases para verificar se há versões mais recentes do instalador disponíveis. Nenhuma informação pessoal é enviada nessas consultas.

---

## 4. Conexões de Rede Efetuadas

O aplicativo Husky Grid realiza conexões de rede exclusivamente para:
1. Os domínios da internet que você escolher navegar ou jogar nas telas da grade.
2. O backend oficial de licença do Husky Grid (`https://husky-grid-backend.fly.dev` ou domínio oficial configurado).
3. A API pública do GitHub para checagem de novas versões na aba de Releases.

---

## 5. Exclusão de Dados

Para apagar completamente todos os dados locais associados ao Husky Grid:
- Basta desinstalar o aplicativo e remover a pasta de dados de usuário criada pelo Electron em seu sistema:
  - **No Windows:** `%APPDATA%\husky-grid`
  - **No Linux:** `~/.config/husky-grid`

---

## 6. Contato sobre Privacidade

Dúvidas ou solicitações sobre o tratamento de informações e termos de uso podem ser enviadas diretamente para:
- **E-mail:** `privacy@huskygrid.com`
- **Repositório oficial:** [EdwilsonCruz/Husky-Grid-Releases/issues](https://github.com/EdwilsonCruz/Husky-Grid-Releases/issues)
