# Avaliação e Métricas

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

---

## Exemplos de Cenários de Teste

### Teste 1: Progresso de meta financeira
- **Pergunta:** "Quanto falta para eu completar minha reserva de emergência?"
- **Resposta esperada:** O agente deve identificar que a meta é R$ 20.000 e o valor atual é R$ 10.000, informando que faltam R$ 10.000.
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 2: Consulta de gastos
- **Pergunta:** "Qual foi minha categoria com maior gasto recente?"
- **Resposta esperada:** O agente deve identificar moradia como maior categoria, totalizando R$ 1.380 (aluguel + conta de luz).
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Quem será o próximo campeão brasileiro de futebol?"
- **Resposta esperada:** Agente informa que só trata de finanças
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Qual a rentabilidade do Fundo Internacional Premium?"
- **Resposta esperada:** O agente deve informar que esse produto não consta na base de conhecimento e admitir que não possui essa informação.
- **Resultado:** [x] Correto  [ ] Incorreto

---

## Resultados

**O que funcionou bem:**
- O agente utilizou corretamente os dados da base de conhecimento, incluindo perfil do cliente, histórico financeiro e produtos disponíveis.
- As respostas foram coerentes com o perfil moderado e com os objetivos financeiros informados.
- Após ajustes no código e no contexto enviado ao modelo, o cálculo da reserva de emergência passou a considerar corretamente a meta cadastrada e o valor já acumulado.
- O comportamento de segurança foi aprimorado após alterações no System Prompt, permitindo respostas adequadas para perguntas fora do escopo financeiro.
- O AurumIA admitiu limitações quando determinada informação não estava disponível na base.
- As respostas apresentaram linguagem clara, objetiva e acessível ao usuário.
- A integração entre Python, Streamlit e Ollama funcionou corretamente durante os testes.

**O que pode melhorar:**
- Reduzir o tempo de resposta utilizando modelos mais leves ou integração futura com API externa da OpenAI.
- Melhorar a memória conversacional para manter contexto entre múltiplas interações.
- Aprimorar o layout visual da interface, com sidebar, histórico de mensagens e indicadores gráficos.
- Implementar filtros automáticos para tornar respostas ainda mais precisas.
- Evoluir para carregamento dinâmico dos dados em tempo real, sem depender de arquivos locais.
- Adicionar autenticação de usuário e camadas extras de segurança para uso corporativo.
-Refinar continuamente prompts e regras de negócio conforme novos testes de uso.

---

