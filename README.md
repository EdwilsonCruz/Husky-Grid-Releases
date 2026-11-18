<div align="center">

# Husky Grid

**Gerenciador de múltiplas sessões em grade com isolamento completo e Eco Mode.**

[![Última Versão](https://img.shields.io/github/v/release/EdwilsonCruz/Husky-Grid-Releases?label=Vers%C3%A3o&color=6366f1&style=for-the-badge)](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/EdwilsonCruz/Husky-Grid-Releases/total?label=Downloads&color=10b981&style=for-the-badge)](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases)
[![Plataforma](https://img.shields.io/badge/Plataforma-Windows%20x64-0078D6?style=for-the-badge&logo=windows)](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases/latest)
[![Licença](https://img.shields.io/badge/Licen%C3%A7a-Propriet%C3%A1ria-475569?style=for-the-badge)](#-licen%C3%A7a-e-c%C3%B3digo-fonte)

[Baixar Última Versão](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases/latest) •
[Recursos](#-principais-recursos) •
[Instalação](#-instala%C3%A7%C3%A3o) •
[Verificar Download](#-verifica%C3%A7%C3%A3o-de-integridade-sha-256) •
[Reportar Problema](https://github.com/EdwilsonCruz/Husky-Grid-Releases/issues)

</div>

---

## Sobre o projeto

O **Husky Grid** é um aplicativo desktop desenvolvido para abrir, organizar e monitorar múltiplas contas e sessões web simultaneamente em uma única janela em grade — ideal para jogos *idle* de navegador (como **Huntera**) e qualquer aplicação web que exija múltiplas contas abertas ao mesmo tempo.

Este repositório é dedicado exclusivamente à **distribuição oficial de instaladores e notas de versão** do Husky Grid.

---

## Principais recursos

- **Sessões 100% isoladas:** cada conta roda em sua própria partição Chromium (cookies, cache e login totalmente independentes).
- **Grade flexível:** divida, redimensione, agrupe e reorganize painéis livremente com salvamento automático de layout.
- **Eco Mode:** reduz o consumo de CPU e a taxa de quadros (FPS) em sessões fora de foco, economizando recursos sem derrubar a conexão.
- **Catálogo de receitas:** configurações prontas para jogos suportados e opção de receita genérica para qualquer URL.
- **Atualizações automáticas:** receba novas versões e melhorias diretamente pelo aplicativo.
- **Plano Gratuito e Planos Pro:** comece gratuitamente com até **4 sessões simultâneas** ou faça upgrade para expandir o limite de telas e dispositivos.

---

## Instalação

1. Acesse a página de [**Última Versão (Latest Release)**](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases/latest).
2. Leia as notas da versão (*Release Notes*) para conferir novidades e correções.
3. Na seção **Assets**, baixe o instalador correspondente ao seu sistema (ex.: `Husky-Grid-Setup-x.y.z.exe`).
4. Execute o instalador e siga as instruções na tela.

> [!NOTE]
> **Aviso do Windows SmartScreen:** em versões recém-publicadas, o Windows pode exibir o alerta *"O Windows protegeu o computador"*. Caso confie na origem oficial deste repositório, clique em **Mais informações** → **Executar assim mesmo**. Recomendamos sempre validar o hash `SHA-256` abaixo antes de instalar.

### Requisitos mínimos (Windows)

| Item | Requisito |
| :--- | :--- |
| **Sistema Operacional** | Windows 10 ou Windows 11 (64-bit / x64) |
| **Memória RAM** | 2 GB (recomendado 8 GB+ para múltiplas sessões simultâneas) |
| **Armazenamento** | ~300 MB livres em disco |
| **Conexão** | Acesso à internet para carregamento das sessões e validação de licença |

---

## Verificação de integridade (SHA-256)

Cada release acompanha um arquivo `SHA256SUMS.txt` para confirmar que o instalador baixado não foi corrompido nem alterado.

No **PowerShell** (Windows), execute na pasta onde o instalador foi salvo:

```powershell
Get-FileHash .\Husky-Grid-Setup-x.y.z.exe -Algorithm SHA256
```

Compare o valor exibido na coluna `Hash` com a linha correspondente dentro de `SHA256SUMS.txt`:
- **Iguais:** o arquivo está íntegro.
- **Diferentes:** **não execute** o instalador; baixe novamente a partir da página oficial de [Releases](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases).

---

## Atualizações

O Husky Grid verifica atualizações automaticamente quando habilitado. Você também pode acompanhar o histórico completo de mudanças diretamente na aba [**Releases**](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases).

---

## Suporte e reporte de problemas

Encontrou algum bug ou comportamento inesperado? Abra uma [**Issue**](https://github.com/EdwilsonCruz/Husky-Grid-Releases/issues) informando:

1. **Versão instalada** do Husky Grid (ex.: `v0.1.0`).
2. **Sistema operacional** (ex.: Windows 11 x64).
3. **Passo a passo** para reproduzir o problema.
4. **Prints ou mensagens de erro**, se aplicável.

> [!CAUTION]
> **Nunca compartilhe dados sensíveis:** não inclua senhas, tokens de acesso, chaves de licença ou arquivos de sessão/perfil em issues públicas.

---

## Licença e código-fonte

Copyright © 2026 **Edwilson Cruz**. Todos os direitos reservados.

O Husky Grid é um software comercial de código fechado (**licença proprietária / EULA**). Este repositório hospeda apenas os binários oficiais de instalação e notas de versão; o código-fonte não é distribuído aqui.
