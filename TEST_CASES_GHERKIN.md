# Cenários de Teste (Gherkin)

Aplicação: https://creative-sherbet-a51eac.netlify.app/

Observação: Quando um comportamento não existir na aplicação (ex.: ordenação), marcar o cenário como N/A.

## Cadastro de Curso

@critico @cadastro
Cenário: Cadastrar curso com dados válidos
  DADO que estou na página "Cadastrar curso"
  QUANDO preencho todos os campos obrigatórios com dados válidos
  E clico em "Salvar"
  ENTÃO vejo uma mensagem de sucesso
  E o curso é exibido na "Lista de cursos"

@critico @validacao
Cenário: Impedir cadastro com campos obrigatórios vazios
  DADO que estou na página "Cadastrar curso"
  QUANDO deixo campos obrigatórios em branco
  E tento salvar
  ENTÃO vejo mensagens de validação claras em cada campo faltante
  E o curso não é salvo

@alto @duplicidade
Cenário: Impedir cadastro de curso com título duplicado
  DADO que já existe um curso com o mesmo título
  QUANDO tento cadastrar um novo curso reutilizando o título existente
  ENTÃO vejo uma mensagem informando duplicidade
  E o cadastro não é permitido

@medio @limite
Cenário: Validar limite de caracteres do título
  DADO que estou na página "Cadastrar curso"
  QUANDO informo um título acima do limite suportado
  ENTÃO vejo uma mensagem de validação sobre o tamanho máximo
  E o cadastro não é permitido

@medio @seguranca
Cenário: Bloquear inserção de script em campos de texto
  DADO que estou na página "Cadastrar curso"
  QUANDO informo caracteres com potencial de script (ex.: <script>)
  ENTÃO o valor é sanitizado ou bloqueado
  E nenhuma execução de script ocorre

@baixo @cancelar
Cenário: Cancelar cadastro (se houver ação de cancelar)
  DADO que estou preenchendo o formulário
  QUANDO aciono "Cancelar"
  ENTÃO o formulário é limpo ou retorno à listagem sem salvar

## Listagem de Cursos

@critico @listagem
Cenário: Exibir lista vazia com mensagem adequada
  DADO que não há cursos cadastrados
  QUANDO acesso "Listar cursos"
  ENTÃO vejo uma mensagem indicando que não há cursos

@critico @listagem
Cenário: Exibir curso após cadastro
  DADO que acabei de cadastrar um curso com sucesso
  QUANDO acesso "Listar cursos"
  ENTÃO o curso recém-cadastrado aparece na lista

@medio @ordenacao
Cenário: Ordenar cursos alfabeticamente por título (se aplicável)
  DADO que existem cursos com títulos distintos
  QUANDO visualizo a lista
  ENTÃO a ordem padrão é alfabética por título

@medio @persistencia
Cenário: Manter cursos após atualizar a página
  DADO que existem cursos listados
  QUANDO atualizo/recargo a página
  ENTÃO os cursos permanecem visíveis (dados persistidos)

@baixo @paginacao
Cenário: Paginar lista com muitos cursos (se aplicável)
  DADO que existem muitos cursos cadastrados
  QUANDO acesso "Listar cursos"
  ENTÃO a paginação é exibida e funciona corretamente

## Resiliência e UX

@alto @erro-rede
Cenário: Tratar erro de rede ao salvar
  DADO que estou tentando cadastrar um curso
  QUANDO ocorre falha de rede na submissão
  ENTÃO uma mensagem de erro é exibida
  E posso tentar novamente sem perder os dados

@medio @responsividade
Cenário: Verificar responsividade em dispositivos móveis
  DADO que acesso a aplicação em viewport móvel
  QUANDO navego por “Cadastrar” e “Listar”
  ENTÃO os elementos se ajustam e permanecem utilizáveis

@baixo @acessibilidade
Cenário: Acessibilidade básica (foco e labels)
  DADO que navego via teclado
  QUANDO foco cada campo do formulário
  ENTÃO a ordem de foco é lógica e todos os campos têm rótulos

