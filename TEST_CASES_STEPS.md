# Casos de Teste (Passo a Passo)

Aplicação: https://creative-sherbet-a51eac.netlify.app/

Formato: ID • Objetivo • Pré-condições • Passos • Dados de teste • Resultado esperado • Prioridade • Status • Evidência

---

ID: TC-001  
Objetivo: Cadastrar curso com dados válidos  
Pré-condições: Acesso à internet e página “Cadastrar curso” disponível  
Passos:  
1. Acessar a aplicação e clicar em “Cadastrar curso”.  
2. Preencher campos obrigatórios com dados válidos.  
3. Clicar em “Salvar”.  
Dados de teste: título “Curso de QA Básico”, descrição “Introdução a testes”, demais campos se existirem.  
Resultado esperado: Mensagem de sucesso e curso visível em “Listar cursos”.  
Prioridade: Crítica • Status: Não executado • Evidência: —

---

ID: TC-002  
Objetivo: Bloquear cadastro com campos obrigatórios vazios  
Pré-condições: Página “Cadastrar curso” disponível  
Passos:  
1. Acessar “Cadastrar curso”.  
2. Deixar campos obrigatórios em branco.  
3. Clicar em “Salvar”.  
Dados de teste: campos vazios.  
Resultado esperado: Mensagens de validação exibidas; nada salvo.  
Prioridade: Crítica • Status: Não executado • Evidência: —

---

ID: TC-003  
Objetivo: Impedir título duplicado  
Pré-condições: Um curso previamente cadastrado com título “Curso de QA Básico”.  
Passos:  
1. Cadastrar novamente usando o mesmo título.  
2. Tentar salvar.  
Dados de teste: título duplicado.  
Resultado esperado: Aviso de duplicidade; nada salvo.  
Prioridade: Alta • Status: Não executado • Evidência: —

---

ID: TC-004  
Objetivo: Validar limite de caracteres do título  
Pré-condições: Conhecer o limite suportado (ex.: 100 caracteres)  
Passos:  
1. Informar um título acima do limite.  
2. Tentar salvar.  
Dados de teste: string com N+1 caracteres.  
Resultado esperado: Mensagem de tamanho máximo; nada salvo.  
Prioridade: Média • Status: Não executado • Evidência: —

---

ID: TC-005  
Objetivo: Prevenir XSS em campos de texto  
Pré-condições: Página “Cadastrar curso” disponível  
Passos:  
1. Inserir valor contendo “<script>alert(1)</script>” em um campo de texto.  
2. Salvar.  
Dados de teste: string com tags de script.  
Resultado esperado: Valor sanitizado/bloqueado; nenhum script executa; mensagem apropriada.  
Prioridade: Média • Status: Não executado • Evidência: —

---

ID: TC-006  
Objetivo: Cancelar cadastro (se houver ação)  
Pré-condições: Botão/ação de “Cancelar” disponível  
Passos:  
1. Preencher parcialmente o formulário.  
2. Acionar “Cancelar”.  
Dados de teste: título preenchido parcialmente.  
Resultado esperado: Formulário limpo ou retorno à listagem sem salvar.  
Prioridade: Baixa • Status: Não executado • Evidência: —

---

ID: TC-007  
Objetivo: Exibir lista vazia com mensagem adequada  
Pré-condições: Nenhum curso cadastrado  
Passos:  
1. Acessar “Listar cursos”.  
Dados de teste: —  
Resultado esperado: Mensagem “Nenhum curso encontrado” (ou equivalente).  
Prioridade: Crítica • Status: Não executado • Evidência: —

---

ID: TC-008  
Objetivo: Exibir curso após cadastro  
Pré-condições: Ao menos um curso cadastrado com sucesso  
Passos:  
1. Acessar “Listar cursos”.  
Dados de teste: curso “Curso de QA Básico”.  
Resultado esperado: Curso aparece na lista com os campos corretos.  
Prioridade: Crítica • Status: Não executado • Evidência: —

---

ID: TC-009  
Objetivo: Verificar ordenação padrão (se aplicável)  
Pré-condições: Pelo menos três cursos com títulos distintos  
Passos:  
1. Acessar “Listar cursos”.  
Dados de teste: títulos A, B, C fora de ordem de criação.  
Resultado esperado: Lista em ordem alfabética por título (ou documentar a ordem real).  
Prioridade: Média • Status: Não executado • Evidência: —

---

ID: TC-010  
Objetivo: Persistência após atualizar a página  
Pré-condições: Cursos visíveis em listagem  
Passos:  
1. Atualizar a página (F5).  
Dados de teste: —  
Resultado esperado: Lista se mantém; nada se perde.  
Prioridade: Média • Status: Não executado • Evidência: —

---

ID: TC-011  
Objetivo: Tratar erro de rede ao salvar  
Pré-condições: Possibilidade de simular offline/falha de rede  
Passos:  
1. Ativar modo offline no navegador (ou simular falha).  
2. Tentar salvar um curso.  
Dados de teste: dados válidos.  
Resultado esperado: Mensagem de erro e possibilidade de nova tentativa.  
Prioridade: Alta • Status: Não executado • Evidência: —

---

ID: TC-012  
Objetivo: Responsividade básica (mobile)  
Pré-condições: Ferramentas de viewport mobile do navegador  
Passos:  
1. Acessar “Cadastrar” e “Listar” em viewport ~375x667.  
Dados de teste: —  
Resultado esperado: Layout ajustado, sem cortes/overflows.  
Prioridade: Média • Status: Não executado • Evidência: —

---

ID: TC-013  
Objetivo: Acessibilidade básica (foco/labels)  
Pré-condições: Navegação por teclado  
Passos:  
1. Percorrer os campos com TAB/SHIFT+TAB.  
2. Verificar labels e ordem lógica de foco.  
Dados de teste: —  
Resultado esperado: Labels presentes; foco previsível.  
Prioridade: Baixa • Status: Não executado • Evidência: —

