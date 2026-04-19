# FinGuard AI

Este é o meu projeto final para a trilha de IA da DIO. Ele une um Assistente de Voz em Python com uma base de conhecimento especializada em finanças.

## Objetivo do Projeto
Criar uma interface segura e clara que ajude usuários a entenderem investimentos e riscos bancários, utilizando IA Generativa ancorada em fontes oficiais.

## Documentação do Agente
Nome: FinGuard Assistant.

Tom de voz: Profissional, calmo e educativo.

Regra de Ouro: Nunca dar recomendações diretas de compra, mas sim explicar os conceitos e riscos com base nas fontes carregadas.


## Etapas do Projeto
### Etapa 1:
1 - O projeto começou com a estruturação de um novo repositório e seu READEME.md

### Etapa 2:
2.1 - Fontes de Dados Curadas
A base de conhecimento consiste em 10 documentos estratégicos que cobrem desde a filosofia clássica de investimentos até regulamentações técnicas atuais:

Teoria de Investimento: O Investidor Inteligente e Fórmulas de Benjamin Graham.

Dados Governamentais: Relatórios do Banco Central (Focus e Estabilidade Financeira) e Tesouro Nacional.

Segurança Institucional: Manuais do FGC e Glossários da B3.

Inovação e Tecnologia: Whitepapers sobre Open Finance e Redes Neurais para crédito.

2.2 - Estratégia de Grounding
Diferente de IAs convencionais, este agente utiliza a técnica de Ancoragem (Grounding). Isso significa que, antes de responder ao usuário, a IA consulta obrigatoriamente a biblioteca digital carregada, garantindo que:

As taxas citadas (SELIC, IPCA) estejam alinhadas com os relatórios oficiais.

As explicações de riscos sigam as normas vigentes do FGC.

O tom educativo seja mantido, evitando promessas de lucros rápidos.

2.3 - Link de Acesso ao Ambiente de Conhecimento
https://notebooklm.google.com/notebook/1bc64106-7e95-4037-b743-a31693c13380

### Etapa 3
3.1 - System Prompt (Diretriz de Identidade)
Para garantir que a IA atue como um assistente financeiro profissional, utilizamos a seguinte instrução base:

"Você é o FinGuard AI, um assistente educativo especializado em mercado financeiro brasileiro. Suas respostas devem ser baseadas estritamente na base de conhecimento carregada. Seja profissional, didático e sempre destaque os riscos envolvidos em qualquer operação financeira. Nunca forneça recomendações diretas de investimento."

3.2 - Prompts Estratégicos e "Cicatrizes"
Documentamos o processo de tentativa e erro (Troubleshooting) para chegar ao resultado ideal. O mercado valoriza saber como você resolveu os problemas da IA.

Prompts Estratégicos e "Cicatrizes"

| Estratégia | Prompt de Teste | Resultado / Ajuste (Cicatriz) |
| :--- | :--- | :--- |
| **Definição** | "O que Graham diz sobre risco?" | **Cicatriz:** A IA deu uma resposta genérica. **Ajuste:** Especifiquei que deveria citar a 'Margem de Segurança' do livro carregado. |
| **Comparação** | "Qual a diferença entre CDB e Tesouro?" | **Cicatriz:** A resposta omitiu o FGC. **Ajuste:** Forcei o agente a sempre verificar a proteção do FGC ao falar de bancos. |
| **UX/Clareza** | "Explique a SELIC para um iniciante." | **Resultado:** Excelente. A IA usou a analogia da 'temperatura do dinheiro' para facilitar o entendimento. |

### Etapa 4: Aplicação Funcional
4.1 - Arquitetura da Solução
A aplicação foi construída sobre um pipeline de três camadas, garantindo que o usuário tenha uma interação natural com dados técnicos complexos:

Camada de Interface (Python): Utiliza o código desenvolvido para captar a voz/texto do usuário.

Camada de Inteligência (NotebookLM): Processa a requisição consultando a base de conhecimento de 10 fontes (Grounding).

Camada de Saída (UX): Retorna uma resposta sintetizada, didática e segura, focada em educação financeira.

4.2 - Funcionalidades de Relacionamento
Para cumprir o desafio de "Experiência Digital", foram implementadas as seguintes lógicas:

Persistência de Contexto: A IA mantém o histórico da conversa, permitindo que o usuário faça perguntas de acompanhamento (ex: "E quanto a esse título, Graham aprovaria?").

FAQ Dinâmica: Explicações sobre CDB, SELIC e FGC geradas em tempo real, sem respostas pré-programadas e rígidas.

Mitigação de Alucinações: Filtro de segurança que impede a IA de recomendar ações específicas, limitando-se a explicar os conceitos fundamentados nas fontes.

### Etapa 5: Metodologia de Validação e Simulação de Voz
Como o ambiente do Google Colab opera em servidores remotos (Cloud), o acesso direto ao hardware local (microfone e alto-falante) é restrito por questões de segurança dos navegadores. Para este projeto, a validação da experiência de voz foi pensada em duas camadas:

5.1 - Validação Lógica (Ambiente Cloud)
No presente notebook, simulamos a interface de voz através de:

Entrada via Texto: Substituindo o gatilho de áudio para validar a Persistência de Contexto e a assertividade das respostas baseadas na curadoria de dados.

Processamento de Linguagem Natural (NLP): Testamos se as palavras-chave (ex: "Selic", "Graham", "FGC") ativam os fluxos de conhecimento corretos sem alucinações.

5.2 - Arquitetura para Ambiente Local (Edge Computing)
O código foi estruturado com as bibliotecas SpeechRecognition e pyttsx3, permitindo que, ao ser executado em uma IDE local (como VS Code ou PyCharm), o sistema realize:

Calibração de Ruído: Uso do método adjust_for_ambient_noise para garantir que o assistente ignore sons externos e foque na voz do usuário.

Síntese de Voz (TTS): Transformação das respostas técnicas em áudio claro, facilitando a acessibilidade e o relacionamento financeiro.

5.3 - Instalação das bibliotecas necessárias
pip install SpeechRecognition pyttsx3 gTTS pygame

### Etapa 6: Pitch - FinGuard AI
6.1. O Problema
No cenário atual, investidores iniciantes enfrentam dois grandes desafios: a complexidade técnica dos produtos bancários e o risco de obter informações imprecisas (alucinações) ao utilizar IAs generativas comuns para consultas financeiras.

6.2. A Solução (FinGuard AI)
O FinGuard AI é uma experiência digital de relacionamento financeiro que une a praticidade da Interface de Voz com o rigor da Curadoria Técnica.

Diferencial: Diferente de modelos abertos, nossa IA é ancorada (Grounding) em uma biblioteca digital de 10 fontes oficiais, incluindo Benjamin Graham e relatórios do Banco Central.

UX/UI: O sistema oferece um fluxo natural de conversação, permitindo que o usuário aprenda conceitos complexos (como Selic e Margem de Segurança) de forma simples, rápida e, acima de tudo, confiável.

6.3. Conclusão e Entrega
Este projeto demonstra a viabilidade de utilizar ferramentas de IA Generativa (NotebookLM + Python) para criar soluções de Customer Experience de alto valor agregado, priorizando a integridade da informação e a acessibilidade através da voz.

## Tecnologias Utilizadas
* **Python**: Lógica do assistente e processamento de voz.
* **Google NotebookLM**: Base de conhecimento e curadoria de dados.
* **Engenharia de Prompts**: Refinamento das respostas da IA.
