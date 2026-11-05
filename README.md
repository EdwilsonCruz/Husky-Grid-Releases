# Husky Grid — Downloads

Este repositório reúne os instaladores oficiais e as notas de versão do Husky Grid. Ele é dedicado à distribuição do aplicativo; **o código-fonte não é publicado aqui**.

## Baixar e instalar

1. Abra [Releases](https://github.com/EdwilsonCruz/Husky-Grid-Releases/releases).
2. Escolha a versão mais recente e leia as notas antes de atualizar.
3. Em **Assets**, baixe o instalador correspondente ao seu sistema operacional.
4. Execute o instalador e siga as instruções exibidas.

Os formatos disponíveis podem variar por versão e plataforma. Baixe arquivos somente desta página oficial.

## Verificar o download no Windows

Cada release inclui `SHA256SUMS.txt` para conferir se o instalador baixado corresponde ao arquivo publicado:

```powershell
Get-FileHash .\NOME-DO-INSTALADOR.exe -Algorithm SHA256
```

Compare o valor `Hash` com a linha do mesmo arquivo em `SHA256SUMS.txt`. Se os valores forem diferentes, não instale o arquivo; baixe-o novamente e confira mais uma vez.

O checksum ajuda a detectar um arquivo incompleto ou alterado, mas, sozinho, não comprova quem publicou o arquivo.

## Atualizações

As notas de cada release descrevem as mudanças disponíveis. Quando a verificação de atualizações estiver habilitada na versão instalada, use o aviso do próprio aplicativo e confira a versão e os detalhes nesta página.

## Código-fonte

Este repositório contém apenas os materiais de distribuição da aplicação e suas informações de release. Os instaladores são publicados como arquivos para download; o código-fonte do Husky Grid não está incluído.

## Problemas

Ao relatar um problema, informe a versão instalada, o sistema operacional e os passos para reproduzi-lo. **Não inclua senhas, tokens ou outros dados privados.**
