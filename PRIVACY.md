# Política de Privacidade — Husky Grid

[🇧🇷 Português](PRIVACY.md) • [🇺🇸 English](PRIVACY.en.md)

Última atualização: Novembro de 2026.

Esta política de privacidade descreve como o **Husky Grid** lida com suas informações. Nosso compromisso fundamental é a **transparência e a conformidade com a Lei Geral de Proteção de Dados (LGPD - Lei nº 13.709/2018)**: o Husky Grid é uma ferramenta de produtividade e gerenciamento de sessões, não uma plataforma de coleta de dados.

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
1. **Credenciais da Conta Husky Grid (E-mail e Senha):** Utilizados exclusivamente para autenticação na nossa API e identificação do seu plano.
2. **Identificador Anônimo de Dispositivo (`DeviceId`):** Um hash criptográfico gerado a partir de atributos anônimos do sistema (como identificador do processador e hostname) para assegurar o cumprimento do limite de até 2 computadores ativos simultâneos por assinatura.
3. **Status da Assinatura:** Confirmação do plano contratado retornada pelo gateway de pagamento (Stripe), indicando se o plano ativo é Gratuito ou Pro.

### Armazenamento de Tokens:
Os tokens de autenticação retornados pelo nosso backend são armazenados em seu disco local de forma criptografada, utilizando as APIs de segurança nativas do seu sistema operacional (`safeStorage` do Electron / DPAPI no Windows / Keychain no macOS / Secret Service no Linux).

---

## 3. Proteção de Dados, E-mail e Conformidade com a LGPD

Em estrito cumprimento à **Lei Geral de Proteção de Dados Pessoais (LGPD - Lei nº 13.709/2018)**:

- **Não Reutilização de E-mails e Dados Pessoais:** O endereço de e-mail cadastrado é utilizado única e exclusivamente para a finalidade técnica de autenticação de conta, controle de licença e avisos operacionais críticos (ex.: recuperação de senha). **Seu e-mail NUNCA será reutilizado, vendido, alugado, cedido ou compartilhado com terceiros ou anunciantes para envio de spam, marketing ou criação de perfis de usuário.**
- **Não Monetização de Dados:** Nós não comercializamos nem exploramos dados pessoais ou de navegação dos usuários sob hipótese alguma.
- **Princípio da Necessidade e Minimização:** Coletamos apenas os dados estritamente necessários para viabilizar a entrega e o funcionamento do serviço contratado.
- **Direitos do Titular (Art. 18 da LGPD):** Você tem total direito de:
  1. Confirmar a existência de tratamento de seus dados.
  2. Solicitar acesso, correção ou atualização do seu e-mail cadastrado.
  3. Solicitar a revogação de consentimento e a **eliminação definitiva** da sua conta e de todos os dados pessoais associados de nossos servidores de licença.

Para exercer qualquer um desses direitos, basta enviar um e-mail para `privacy@huskygrid.com`.

---

## 4. Telemetria e Rastreamento

- **Não coletamos telemetria invasiva de uso:** O Husky Grid não monitora quais abas você abre, quais itens adquire nos jogos ou o conteúdo das páginas acessadas.
- **Atualizações Automáticas:** Caso o serviço de verificação de atualizações esteja ativado, o aplicativo fará requisições ocasionais ao GitHub Releases para verificar se há versões mais recentes do instalador disponíveis. Nenhuma informação pessoal é enviada nessas consultas.

---

## 5. Conexões de Rede Efetuadas

O aplicativo Husky Grid realiza conexões de rede exclusivamente para:
1. Os domínios da internet que você escolher navegar ou jogar nas telas da grade.
2. O backend oficial de licença do Husky Grid (`https://husky-grid-backend.fly.dev` ou domínio oficial configurado).
3. A API pública do GitHub para checagem de novas versões na aba de Releases.

---

## 6. Exclusão de Dados

- **Dados Locais:** Para apagar completamente todos os dados locais associados ao Husky Grid, basta desinstalar o aplicativo e remover a pasta de dados de usuário:
  - **No Windows:** `%APPDATA%\husky-grid`
  - **No Linux:** `~/.config/husky-grid`
- **Dados da Conta/Nuvem:** Caso deseje a exclusão da sua conta e remoção permanente do seu e-mail de nossos bancos de dados, entre em contato pelo e-mail de privacidade abaixo.

---

## 7. Contato e Encarregado de Dados (DPO)

Dúvidas, solicitações ou requisições de titulares referentes à LGPD e proteção de dados podem ser encaminhadas diretamente para:
- **E-mail de Privacidade:** `privacy@huskygrid.com`
- **Repositório oficial:** [EdwilsonCruz/Husky-Grid-Releases/issues](https://github.com/EdwilsonCruz/Husky-Grid-Releases/issues)
