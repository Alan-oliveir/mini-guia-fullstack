# 📖 Template de User Story

## 🎯 Estrutura Básica

**Como** [tipo de usuário/persona],  
**Quero** [ação ou funcionalidade],  
**Para** [benefício ou resultado desejado].

**Critérios de Aceitação:**
- [ ] [critério 1]
- [ ] [critério 2]
- [ ] [critério 3]

**Definição de Pronto:**
- [ ] Funcionalidade desenvolvida
- [ ] Testes unitários criados
- [ ] Code review aprovado
- [ ] Documentação atualizada

---

## 📋 Campos Adicionais (Opcional)

**ID:** US[número]  
**Épico:** [nome do épico relacionado]  
**Prioridade:** [Must/Should/Could/Won't have]  
**Estimativa:** [story points ou horas]  
**Sprint:** [número da sprint]  
**Responsável:** [nome da pessoa]  

**Dependências:**
- [ ] [dependência 1]
- [ ] [dependência 2]

**Notas Técnicas:**
- [observação técnica importante]
- [limitação conhecida]

---

## 🎨 Exemplo Preenchido

**Como** Maria (usuária casada),  
**Quero** cadastrar um gasto compartilhado,  
**Para** que meu marido veja quanto gastei e possamos dividir a conta.

**Critérios de Aceitação:**
- [ ] Usuário pode inserir valor, descrição e categoria do gasto
- [ ] Sistema calcula automaticamente quanto cada pessoa deve pagar
- [ ] Outros membros do grupo recebem notificação do novo gasto
- [ ] Gasto aparece no histórico do grupo

**Definição de Pronto:**
- [ ] Interface de cadastro criada
- [ ] API de criação de gastos implementada
- [ ] Testes unitários para cálculo de divisão
- [ ] Integração frontend-backend testada
- [ ] Sistema de notificação funcionando
- [ ] Documentação da API atualizada

**ID:** US001  
**Épico:** Gestão de Gastos Compartilhados  
**Prioridade:** Must have  
**Estimativa:** 5 story points  
**Sprint:** Sprint 1  
**Responsável:** João (Frontend) + Maria (Backend)  

**Dependências:**
- [ ] Sistema de autenticação deve estar pronto
- [ ] Modelo de dados dos grupos deve estar definido

**Notas Técnicas:**
- Considerar diferentes moedas no futuro
- Validar campos obrigatórios no frontend e backend

---

## 🔧 Dicas para Escrever Boas User Stories

### ✅ Características de uma Boa User Story

**Independent (Independente):**
- Pode ser desenvolvida sem depender de outras stories
- Se há dependência, documente claramente

**Negotiable (Negociável):**
- Detalhes podem ser discutidos e ajustados
- Não é um contrato rígido

**Valuable (Valiosa):**
- Entrega valor para o usuário final
- Resolve um problema real

**Estimable (Estimável):**
- Equipe consegue estimar o esforço necessário
- Nem muito grande nem muito pequena

**Small (Pequena):**
- Pode ser concluída em uma sprint
- Se muito grande, quebrar em stories menores

**Testable (Testável):**
- Critérios de aceitação claros
- Possível verificar se está funcionando

### 📏 Tamanhos de Story

**Pequena (1-2 story points):**
- Ajustes simples de interface
- Correções de bugs
- Validações básicas

**Média (3-5 story points):**
- Funcionalidades novas simples
- Integrações diretas
- Telas com CRUD básico

**Grande (8+ story points):**
- Funcionalidades complexas
- Integrações com múltiplos sistemas
- **⚠️ Considere quebrar em stories menores**

### ❌ Erros Comuns

**Muito técnica:**
- ❌ "Como desenvolvedor, quero refatorar o código..."
- ✅ "Como usuário, quero que o app carregue mais rápido..."

**Muito vaga:**
- ❌ "Como usuário, quero usar o sistema..."
- ✅ "Como usuário, quero fazer login para acessar meus dados..."

**Sem benefício claro:**
- ❌ "Como usuário, quero ver uma lista de produtos."
- ✅ "Como usuário, quero ver uma lista de produtos para escolher o que comprar."

**Muito grande:**
- ❌ "Como usuário, quero um sistema completo de e-commerce..."
- ✅ Quebrar em: cadastro, carrinho, pagamento, etc.

### 🎯 Template para Quebrar Stories Grandes

Se sua story é muito grande, use este processo:

1. **Identifique os passos:** Liste todas as ações necessárias
2. **Agrupe por valor:** Quais passos entregam valor independente?
3. **Crie stories menores:** Uma para cada grupo de valor
4. **Defina ordem:** Qual story deve ser feita primeiro?

**Exemplo:**
Story grande: "Sistema de e-commerce completo"

Stories menores:
- "Cadastrar produtos no catálogo"
- "Adicionar produtos ao carrinho"
- "Finalizar compra com cartão"
- "Acompanhar status do pedido"