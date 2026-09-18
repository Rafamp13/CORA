# CORA 3.1.0

**Cora • Kiba Sound Studios™**

> Seu som. Seu servidor. Sua sessão.

Cora é o código-base do Melodix preparado com branding textual da Cora para compilação por GitHub Actions e execução na Discloud.

## Comandos

A embalagem não adiciona comandos nem altera a lógica de reprodução. Os comandos disponíveis são os que existem no código-fonte incluído em `src`.

Entre os comandos documentados pela base estão:

- `/play`
- `/search`
- `/queue`
- `/skip`
- `/pause`
- `/resume`
- `/stop`
- `/history`

## Configuração

Use `.env.example` como referência para as variáveis de ambiente necessárias. Não coloque o token do Discord no GitHub.

## Build automático

O workflow em `.github/workflows/build.yml`:

1. executa em `ubuntu-latest`;
2. instala Go 1.26;
3. aplica apenas substituições de branding textual definidas no workflow;
4. compila para Linux amd64 com `CGO_ENABLED=0`;
5. monta o pacote de deploy;
6. publica o artifact **CORA**.

O binário gerado é `cora-discord`.

## Estrutura do artifact

```text
CORA/
├── discloud.config
├── .env.example
├── README.md
├── cora-discord
└── data/
    └── .gitkeep
```

## O que este workflow NÃO faz

- não renomeia packages Go;
- não altera `module` ou import paths;
- não altera lógica de reprodução;
- não cria comandos novos;
- não modifica integrações de áudio;
- não converte automaticamente variáveis de ambiente ou identificadores técnicos;
- não substitui recursos gráficos binários.

Se algum nome técnico `Melodix` precisar ser alterado fora das strings visíveis, isso deve ser revisado manualmente para evitar quebrar imports, módulos, testes ou compatibilidade.

## Licença e origem

Preserve os arquivos de licença e avisos de copyright presentes em `src`.
