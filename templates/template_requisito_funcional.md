# ⚙️ Template de Requisito Funcional

## 📋 Estrutura Básica

**[RF##] Título do Requisito**

**Descrição:** [O que o sistema deve fazer]  
**Atores:** [Quem interage com esta funcionalidade]  
**Pré-condições:** [O que deve estar verdadeiro antes]  

**Fluxo Principal:**
1. [Passo 1]
2. [Passo 2]
3. [Passo 3]

**Fluxos Alternativos:**
- [Cenário alternativo 1]
- [Cenário alternativo 2]

**Pós-condições:** [O que deve estar verdadeiro depois]  
**Prioridade:** [Must/Should/Could/Won't have]

---

## 📝 Campos Adicionais (Opcional)

**ID:** RF[número]  
**Módulo:** [área do sistema]  
**Complexidade:** [Alta/Média/Baixa]  
**Estimativa:** [horas ou story points]  
**User Stories Relacionadas:** [US001, US002, etc.]  

**Regras de Negócio:**
- RN[número]: [regra específica]
- RN[número]: [outra regra]

**Validações:**
- [validação de entrada 1]
- [validação de entrada 2]

**Exceções:**
- [erro específico 1] → [tratamento]
- [erro específico 2] → [tratamento]

---

## 🎨 Exemplo Preenchido

**[RF001] Cadastro de Gasto Compartilhado**

**Descrição:** O sistema deve permitir que usuários cadastrem gastos que serão divididos entre os membros de um grupo doméstico.

**Atores:** Usuário autenticado membro de um grupo  

**Pré-condições:** 
- Usuário deve estar logado no sistema
- Usuário deve pertencer a pelo menos um grupo
- Grupo deve ter pelo menos 2 membros

**Fluxo Principal:**
1. Usuário acessa a tela de "Novo Gasto"
2. Sistema exibe formulário com campos: valor, descrição, categoria, data, grupo
3. Usuário preenche os campos obrigatórios
4. Usuário clica em "Salvar Gasto"
5. Sistema valida os dados informados
6. Sistema calcula a divisão do valor entre os membros
7. Sistema salva o gasto na base de dados
8. Sistema envia notificação para outros membros do grupo
9. Sistema exibe mensagem de sucesso
10. Sistema redireciona para a lista de gastos do grupo

**Fluxos Alternativos:**
- **FA001 - Erro de validação:** Se dados inválidos, sistema exibe mensagens de erro específicas e mantém usuário na tela
- **FA002 - Grupo único:** Se usuário pertence a apenas um grupo, sistema pré-seleciona o grupo
- **FA003 - Falha na notificação:** Se erro ao enviar notificação, sistema salva o gasto mas exibe aviso sobre falha na notificação

**Pós-condições:** 
- Gasto salvo na base de dados
- Saldo dos membros do grupo atualizado
- Outros membros notificados (se possível)
- Histórico de atividades atualizado

**Prioridade:** Must have

**ID:** RF001  
**Módulo:** Gestão de Gastos  
**Complexidade:** Média  
**Estimativa:** 8 horas  
**User Stories Relacionadas:** US001, US003  

**Regras de Negócio:**
- RN001: Valor do gasto deve ser maior que R$ 0,01
- RN002: Data do gasto não pode ser superior a 30 dias no futuro
- RN003: Usuário só pode cadastrar gastos em grupos que participa
- RN004: Divisão é sempre igualitária entre todos os membros ativos

**Validações:**
- Valor: obrigatório, numérico, maior que 0
- Descrição: obrigatória, máximo 100 caracteres
- Data: obrigatória, formato válido, não futura além de 30 dias
- Categoria: obrigatória, deve existir no sistema
- Grupo: obrigatório, usuário deve ser membro

**Exceções:**
- Valor inválido → Exibir "Valor deve ser maior que R$ 0,01"
- Usuário não pertence ao grupo → Exibir "Você não tem permissão para adicionar gastos neste grupo"
- Falha na conexão → Salvar dados localmente e sincronizar quando conectar

---

## 🔧 Dicas para Escrever Bons Requisitos Funcionais

### ✅ Características de um Bom RF

**Claro e Específico:**
- Use linguagem simples e objetiva
- Evite ambiguidades ("sistema deve ser rápido" → "sistema deve responder em menos de 2 segundos")

**Completo:**
- Inclua todos os cenários possíveis
- Documente fluxos alternativos e exceções
- Considere validações e tratamento de erros

**Testável:**
- Critérios claros para verificar se foi implementado
- Cenários de teste evidentes
- Resultados esperados bem definidos

**Rastreável:**
- Conectado com user stories e casos de uso
- Referenciado em testes e código
- Versionado e controlado

### 📏 Níveis de Detalhamento

**Alto Nível (Épicos):**
- RF001: Sistema de autenticação
- RF002: Gestão de gastos compartilhados
- RF003: Relatórios financeiros

**Nível Médio (Features):**
- RF001.1: Login com email e senha
- RF001.2: Recuperação de senha
- RF001.3: Logout do sistema

**Baixo Nível (Detalhado):**
- RF001.1.1: Validação de formato de email
- RF001.1.2: Criptografia da senha
- RF001.1.3: Tentativas de login limitadas

### ❌ Erros Comuns

**Misturar funcional com não-funcional:**
- ❌ RF: "Sistema deve ser responsivo e permitir login"
- ✅ RF: "Sistema deve permitir login com email e senha"
- ✅ RNF: "Interface deve ser responsiva"

**Linguagem ambígua:**
- ❌ "Sistema deve processar dados rapidamente"
- ✅ "Sistema deve processar upload de arquivo em menos de 30 segundos"

**Muito genérico:**
- ❌ "Sistema deve gerenciar usuários"
- ✅ "Sistema deve permitir cadastro, edição, consulta e exclusão de usuários"

**Falta de tratamento de erros:**
- ❌ Só documentar o fluxo feliz
- ✅ Incluir validações, exceções e fluxos alternativos

### 🔄 Template para Fluxos Complexos

Para requisitos com múltiplos caminhos, use esta estrutura:

**Fluxo Principal:** [caminho ideal]
**Fluxos Alternativos:**
- FA001 - [cenário específico]: [passos alternativos]
- FA002 - [outro cenário]: [passos alternativos]
**Fluxos de Exceção:**
- FE001 - [erro específico]: [como tratar]
- FE002 - [outro erro]: [como tratar]

### 📊 Rastreabilidade

Mantenha conexões claras:
- **RF** ← conecta com → **User Stories**
- **RF** ← conecta com → **Casos de Teste**
- **RF** ← conecta com → **Código Implementado**
- **RF** ← conecta com → **Documentação Técnica**

### 🎯 Checklist de Qualidade

Antes de finalizar um RF, verifique:
- [ ] Título é claro e específico?
- [ ] Descrição é objetiva e completa?
- [ ] Atores estão bem definidos?
- [ ] Pré-condições são verificáveis?
- [ ] Fluxo principal está completo?
- [ ] Fluxos alternativos cobrem cenários importantes?
- [ ] Pós-condições são claras?
- [ ] Prioridade está definida?
- [ ] Regras de negócio estão explícitas?
- [ ] Validações estão documentadas?
- [ ] Tratamento de erros está especificado?
- [ ] É possível testar se foi implementado corretamente?