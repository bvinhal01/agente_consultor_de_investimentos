# Vinci - Mentor e Estratégista Financeiro Racional

> Agente de IA Generativa Local (Ollama + Streamlit) com inteligência analítica de dupla rota: ensina conceitos financeiros do zero para leigos e calcula alocações de ativos seguras e matemáticas para investidores iniciados, blindando-os contra vieses emocionais.

---

## O Que é o Vinci?

O Vinci é um ecossistema de orientação financeira focado em dois perfis de usuários. Ele identifica a maturidade do cliente e bifurca sua inteligência em dois motores distintos:

### 📑 1/3: O Motor de Triagem e Diagnóstico (Onboarding)
*   **Identificação de Maturidade:** Avalia o nível de conhecimento técnico e estabilidade financeira do usuário.
*   **Análise de Saúde Financeira:** Varre o histórico de transações (`transacoes.csv`) para diagnosticar a capacidade de poupança e calcular o tamanho ideal da **Reserva de Emergência** antes de qualquer passo de investimento.

### 📚 2/3: A Rota Educacional Didática (Foco: Leigo / Thiago)
*   **Tradução de "Economês":** Explica conceitos como Inflação, Selic e CDI usando metáforas cotidianas baseadas na realidade do usuário.
*   **Engenharia Educativa:** Ensina os pilares de proteção do dinheiro sem empurrar produtos, garantindo que o usuário entenda o *porquê* de cada movimento.

### 📈 3/3: O Motor de Alocação Racional (Foco: Iniciado / Mariana)
*   **Cálculo Baseado em Prazos:** Cruza os objetivos do cliente (Curto, Médio e Longo Prazo) com a liquidez dos ativos.
*   **Mitigação de Risco e Volatilidade:** Implementa uma matriz racional de alocação (Renda Fixa Pós, IPCA e Renda Variável) baseada na tolerância emocional e matemática a perdas.
*   **Geração de Carteira Teórica:** Desenha o balizamento percentual ideal para o momento macroeconômico, agindo como um escudo contra a ganância e dicas quentes de mercado.

---

## Arquitetura do Sistema

O Vinci isola a camada visual da lógica analítica, rodando 100% offline para garantir privacidade total dos dados do usuário.

``mermaid
flowchart TD
    A[Usuário] --> B[Interface Streamlit]
    B --> C[Lógica de Negócio / Pandas & Python]
    C --> D[Ollama - LLM Local gpt-oss]
    D --> E[Base de Conhecimento / Mocks JSON & CSV]
    E --> D
    D --> C
    C --> F[Dashboard Visual + Resposta do Chat]

### 3. Prompts do Agente

Documente os prompts que definem o comportamento do seu agente:

- **System Prompt:** Instruções gerais de comportamento e restrições
- **Exemplos de Interação:** Cenários de uso com entrada e saída esperada
- **Tratamento de Edge Cases:** Como o agente lida com situações limite

 **Template:** [`docs/03-prompts.md`](./docs/03-prompts.md)

---

### 4. Aplicação Funcional

Desenvolva um **protótipo funcional** do seu agente:

- Chatbot interativo (sugestão: Streamlit, Gradio ou similar)
- Integração com LLM (via API ou modelo local)
- Conexão com a base de conhecimento

 **Pasta:** [`src/`](./src/)

---

### 5. Avaliação e Métricas

Descreva como você avalia a qualidade do seu agente:

**Métricas Sugeridas:**
- Precisão/assertividade das respostas
- Taxa de respostas seguras (sem alucinações)
- Coerência com o perfil do cliente

 **Template:** [`docs/04-metricas.md`](./docs/04-metricas.md)

---

### 6. Pitch

Grave um **pitch de 3 minutos** (estilo elevador) apresentando:

- Qual problema seu agente resolve?
- Como ele funciona na prática?
- Por que essa solução é inovadora?

 **Template:** [`docs/05-pitch.md`](./docs/05-pitch.md)

---

## Ferramentas Sugeridas

Todas as ferramentas abaixo possuem versões gratuitas:

| Categoria | Ferramentas |
|-----------|-------------|
| **LLMs** | [ChatGPT](https://chat.openai.com/), [Copilot](https://copilot.microsoft.com/), [Gemini](https://gemini.google.com/), [Claude](https://claude.ai/), [Ollama](https://ollama.ai/) |
| **Desenvolvimento** | [Streamlit](https://streamlit.io/), [Gradio](https://www.gradio.app/), [Google Colab](https://colab.research.google.com/) |
| **Orquestração** | [LangChain](https://www.langchain.com/), [LangFlow](https://www.langflow.org/), [CrewAI](https://www.crewai.com/) |
| **Diagramas** | [Mermaid](https://mermaid.js.org/), [Draw.io](https://app.diagrams.net/), [Excalidraw](https://excalidraw.com/) |

---

## Estrutura do Repositório

```
📁 lab-agente-financeiro/
│
├── 📄 README.md
│
├── 📁 data/                          # Dados mockados para o agente
│   ├── historico_atendimento.csv     # Histórico de atendimentos (CSV)
│   ├── perfil_investidor.json        # Perfil do cliente (JSON)
│   ├── produtos_financeiros.json     # Produtos disponíveis (JSON)
│   └── transacoes.csv                # Histórico de transações (CSV)
│
├── 📁 docs/                          # Documentação do projeto
│   ├── 01-documentacao-agente.md     # Caso de uso e arquitetura
│   ├── 02-base-conhecimento.md       # Estratégia de dados
│   ├── 03-prompts.md                 # Engenharia de prompts
│   ├── 04-metricas.md                # Avaliação e métricas
│   └── 05-pitch.md                   # Roteiro do pitch
│
├── 📁 src/                           # Código da aplicação
│   └── app.py                        # (exemplo de estrutura)
│
├── 📁 assets/                        # Imagens e diagramas
│   └── ...
│
└── 📁 examples/                      # Referências e exemplos
    └── README.md
```

---

## Dicas Finais

1. **Comece pelo prompt:** Um bom system prompt é a base de um agente eficaz
2. **Use os dados mockados:** Eles garantem consistência e evitam problemas com dados sensíveis
3. **Foque na segurança:** No setor financeiro, evitar alucinações é crítico
4. **Teste cenários reais:** Simule perguntas que um cliente faria de verdade
5. **Seja direto no pitch:** 3 minutos passam rápido, vá ao ponto
