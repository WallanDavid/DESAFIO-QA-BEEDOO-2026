# DESAFIO-QA-BEEDOO-2026

Aplicação sob teste: https://creative-sherbet-a51eac.netlify.app/

Repositório público: https://github.com/WallanDavid/DESAFIO-QA-BEEDOO-2026

## Objetivo da aplicação
- Permitir o cadastro de cursos e a visualização/listagem dos cursos cadastrados.
- Oferecer uma interface simples com os fluxos “Cadastrar curso” e “Listar cursos”.

## Principais fluxos disponíveis
- Acessar “Cadastrar curso” a partir da navegação principal.
- Preencher os campos do curso e confirmar o envio (salvar).
- Acessar “Listar cursos” e visualizar os itens cadastrados.
- Verificar se o curso recém-cadastrado aparece na lista.

## Pontos críticos para teste
- Validações de campos obrigatórios (ex.: nome/título do curso).
- Regras de formatação/tamanho máximo dos campos.
- Prevenção de duplicidade de cursos (títulos iguais).
- Mensagens de erro/feedback ao usuário (sucesso e falha).
- Persistência dos dados (após atualizar a página).
- Ordenação/filtragem/paginação (se presentes).
- Comportamento com lista vazia e com muitos itens.
- Responsividade e acessibilidade básicas.
- Tratamento de comportamentos inesperados (ex.: falha de rede).

## Cenários e casos de teste
- Planilha no Google Sheets (preencha o link público): ADICIONAR_LINK_AQUI
- Alternativamente, os casos estão versionados neste repositório:
  - TEST_CASES_GHERKIN.md
  - TEST_CASES_STEPS.md
  - TEST_CASES.csv (template pronto para importação no Google Sheets)

## Execução dos testes
- Testes executados manualmente na aplicação hospedada.
- Para cada caso, registrar:
  - Resultado: Aprovado/Reprovado/Não executado
  - Evidências: prints ou gravação de tela
- Evidências (Google Drive/pasta compartilhada): ADICIONAR_LINK_DRIVE_AQUI

### Critérios de aceite (exemplos)
- Cadastro com dados válidos salva e exibe o curso na listagem.
- Campos obrigatórios bloqueiam o envio e mostram mensagens claras.
- Lista vazia exibe mensagem adequada; lista com itens exibe todos os cursos.
- Dados permanecem após atualizar a página (se houver persistência).

## Registro de bugs
- Registre os defeitos encontrados em: BUGS.md
- Para cada bug, inclua:
  - Título
  - Passos para reproduzir
  - Resultado atual
  - Resultado esperado
  - Severidade/Impacto

## Observações
- Caso a aplicação não apresente alguns recursos (ex.: ordenação), os casos correspondentes devem ser marcados como N/A.
- Este repositório contém os artefatos necessários para avaliação: descrição, casos de teste, template de planilha e modelo de bugs.

