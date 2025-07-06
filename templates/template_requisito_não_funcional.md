# 🛡️ Template de Requisito Não Funcional

## 📋 Estrutura Básica

**[RNF##] Título do Requisito**

**Categoria:** [Performance/Usabilidade/Segurança/Disponibilidade/Compatibilidade/Manutenibilidade]  
**Descrição:** [Como o sistema deve se comportar]  
**Critério de Aceitação:** [Como medir/verificar]  
**Prioridade:** [Alta/Média/Baixa]

---

## 📝 Campos Adicionais (Opcional)

**ID:** RNF[número]  
**Módulo:** [área do sistema afetada]  
**Tipo:** [Qualidade/Restrição/Conformidade]  
**Impacto:** [Alto/Médio/Baixo]  
**Complexidade de Implementação:** [Alta/Média/Baixa]  

**Métricas:**
- [métrica 1]: [valor alvo]
- [métrica 2]: [valor alvo]

**Forma de Verificação:**
- [método de teste 1]
- [método de teste 2]

**Dependências:**
- [dependência técnica 1]
- [dependência de infraestrutura 2]

**Ferramentas Necessárias:**
- [ferramenta 1]
- [ferramenta 2]

---

## 🎨 Exemplos por Categoria

### ⚡ Performance

**[RNF001] Tempo de Resposta da API**

**Categoria:** Performance  
**Descrição:** As APIs do sistema devem responder às requisições em tempo adequado para garantir boa experiência do usuário.  
**Critério de Aceitação:** 95% das requisições devem ser processadas em menos de 2 segundos, considerando conexão 4G.  
**Prioridade:** Alta

**Métricas:**
- Tempo médio de resposta: < 1 segundo
- Tempo máximo de resposta: < 2 segundos
- Taxa de requisições atendidas em menos de 2s: ≥ 95%

**Forma de Verificação:**
- Testes de carga com JMeter
- Monitoramento em produção com New Relic
- Análise de logs de performance

### 🎨 Usabilidade

**[RNF002] Responsividade da Interface**

**Categoria:** Usabilidade  
**Descrição:** A interface do sistema deve ser responsiva e funcionar adequadamente em diferentes dispositivos e tamanhos de tela.  
**Critério de Aceitação:** Interface deve ser totalmente funcional em dispositivos de 320px a 1920px de largura.  
**Prioridade:** Alta

**Métricas:**
- Breakpoints suportados: mobile (320-768px), tablet (768-1024px), desktop (1024px+)
- Elementos não devem sobrepor ou quebrar layout
- Texto deve permanecer legível em todas as resoluções

**Forma de Verificação:**
- Testes manuais em diferentes dispositivos
- Ferramentas de desenvolvimento do navegador
- Testes automatizados com Cypress viewport

### 🔒 Segurança

**[RNF003] Criptografia de Dados Sensíveis**

**Categoria:** Segurança  
**Descrição:** Dados sensíveis dos usuários devem ser criptografados tanto em trânsito quanto em repouso.  
**Critério de Aceitação:** Senhas hash com bcrypt (salt rounds ≥ 12), comunicação via HTTPS, dados pessoais criptografados no banco.  
**Prioridade:** Alta

**Métricas:**
- 100% das comunicações via HTTPS
- Senhas nunca armazenadas em texto plano
- Dados PII criptografados com AES-256

**Forma de Verificação:**
- Auditoria de segurança do código
- Testes de penetração
- Verificação de certificados SSL

### 📈 Disponibilidade

**[RNF004] Uptime do Sistema**

**Categoria:** Disponibilidade  
**Descrição:** O sistema deve estar disponível para uso na maior parte do tempo, com janelas de manutenção planejadas.  
**Critério de Aceitação:** Sistema deve ter uptime de 99.5% considerando mês de 30 dias (downtime máximo de 3.6 horas/mês).  
**Prioridade:** Média

**Métricas:**
- Uptime mensal: ≥ 99.5%
- Tempo máximo de indisponibilidade não planejada: 2 horas consecutivas
- Tempo de recuperação após falha: < 15 minutos

**Forma de Verificação:**
- Monitoramento contínuo com Pingdom
- Logs de indisponibilidade
- Relatórios mensais de SLA

### 🌐 Compatibilidade

**[RNF005] Suporte a Navegadores**

**Categoria:** Compatibilidade  
**Descrição:** O sistema deve funcionar adequadamente nos principais navegadores utilizados pelo público-alvo.  
**Critério de Aceitação:** Funcionalidade completa no Chrome 90+, Firefox 88+, Safari 14+, Edge 90+. Degradação elegante em versões anteriores.  
**Prioridade:** Média

**Métricas:**
- Cobertura de navegadores: ≥ 95% dos usuários target
- Funcionalidades críticas funcionam em 100% dos navegadores suportados
- Degradação elegante sem quebras em navegadores mais antigos

### 🔧 Manutenibilidade

**[RNF006] Qualidade do Código**

**Categoria:** Manutenibilidade  
**Descrição:** O código deve seguir padrões de qualidade que facilitem manutenção e evolução do sistema.  
**Critério de Aceitação:** Cobertura de testes ≥ 80%, complexidade ciclomática ≤ 10, code review obrigatório, documentação atualizada.  
**Prioridade:** Média

**Métricas:**
- Cobertura de testes: ≥ 80%
- Complexidade ciclomática média: ≤ 10
- Código duplicado: < 5%
- Code review coverage: 100%

---

## 🔧 Dicas para Escrever Bons RNFs

### ✅ Características de um Bom RNF

**Mensurável:**
- Use números específicos: "menos de 2 segundos" em vez de "rápido"
- Defina métricas claras e verificáveis
- Estabeleça valores mínimos, médios e máximos

**Testável:**
- Especifique como será verificado
- Liste ferramentas necessárias para teste
- Defina cenários de teste específicos

**Realista:**
- Considere limitações técnicas e orçamentárias
- Balanceie qualidade com viabilidade
- Alinhe com objetivos do projeto

**Específico ao Contexto:**
- Considere o público-alvo do sistema
- Adapte aos recursos disponíveis
- Alinha com criticidade do sistema

### 📊 Categorias Principais de RNF

**Performance:**
- Tempo de resposta
- Throughput (requisições/segundo)
- Tempo de inicialização
- Uso de recursos (CPU, memória)

**Usabilidade:**
- Responsividade
- Acessibilidade
- Tempo de aprendizado
- Taxa de erro do usuário

**Segurança:**
- Autenticação
- Autorização
- Criptografia
- Auditoria

**Confiabilidade:**
- Disponibilidade (uptime)
- Taxa de falhas
- Tempo de recuperação
- Tolerância a falhas

**Compatibilidade:**
- Navegadores suportados
- Sistemas operacionais
- Dispositivos móveis
- Resoluções de tela

**Manutenibilidade:**
- Qualidade do código
- Documentação
- Facilidade de deploy
- Monitoramento

### ❌ Erros Comuns

**Muito vago:**
- ❌ "Sistema deve ser rápido"
- ✅ "API deve responder em menos de 2 segundos"

**Não mensurável:**
- ❌ "Interface deve ser bonita"
- ✅ "Interface deve seguir guidelines de Material Design"

**Impossível de testar:**
- ❌ "Sistema deve ser fácil de usar"
- ✅ "90% dos usuários devem conseguir completar tarefa X em menos de 3 minutos"

**Irrealista:**
- ❌ "Sistema deve ter 100% de uptime"
- ✅ "Sistema deve ter 99.5% de uptime mensal"

### 🎯 Template para Métricas

Use esta estrutura para definir métricas claras:

**Métrica:** [nome da métrica]  
**Valor Atual:** [baseline se existir]  
**Valor Alvo:** [objetivo a alcançar]  
**Valor Mínimo Aceitável:** [limite inferior]  
**Como Medir:** [ferramenta/método]  
**Frequência de Medição:** [quando medir]

### 🔄 Priorização de RNFs

**Alta Prioridade:**
- Impacta diretamente a experiência do usuário
- Relacionado à segurança de dados
- Obrigatório por regulamentação
- Crítico para funcionamento básico

**Média Prioridade:**
- Melhora significativamente a qualidade
- Facilita manutenção futura
- Diferencial competitivo
- Boas práticas da indústria

**Baixa Prioridade:**
- Nice to have
- Otimizações avançadas
- Funcionalidades de nicho
- Melhorias incrementais

### 📋 Checklist de Qualidade

Antes de finalizar um RNF, verifique:
- [ ] Título é claro e específico?
- [ ] Categoria está correta?
- [ ] Descrição é objetiva?
- [ ] Critério de aceitação é mensurável?
- [ ] Prioridade está definida?
- [ ] Métricas são específicas e alcançáveis?
- [ ] Forma de verificação está clara?
- [ ] Ferramentas necessárias estão disponíveis?
- [ ] É possível testar se foi implementado?
- [ ] Está alinhado com objetivos do projeto?