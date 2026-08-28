# Brinda — Assistente Virtual de RH (protótipo acadêmico)

Brinda é um protótipo acadêmico de chatbot de RH inspirado na Ambev, feito
para demonstrar a viabilidade de um projeto de faculdade. **Não é um canal
oficial de RH da Ambev** e não deve ser usado para atendimento real de
colaboradores.

O assistente responde dúvidas administrativas comuns (férias, benefícios,
ponto e jornada, afastamentos/licenças e documentos de admissão) com base
numa base de conhecimento fixa, e sempre encaminha para o RH humano em casos
sensíveis (saúde mental, desligamentos, avaliações de desempenho, salário,
dados pessoais sensíveis).

## Como funciona

É um único arquivo estático (`index.html`), sem servidor, sem chave de API
e sem chamadas de rede. A "inteligência" é um casamento de palavras-chave:
o texto digitado é comparado contra a base de conhecimento definida no
próprio JavaScript (constante `KNOWLEDGE_BASE`) e, se houver correspondência,
a resposta pré-escrita daquele tópico é exibida. Perguntas sensíveis
(`SENSITIVE_TOPICS`) são sempre encaminhadas para o RH humano, e perguntas
fora da base de conhecimento caem numa resposta padrão (`FALLBACK_REPLY`)
que também recomenda o RH humano.

Esse recorte é proposital: o objetivo desta etapa é validar o fluxo de
conversa, o tom das respostas e a cobertura das políticas — não plugar um
modelo de linguagem de verdade. Uma evolução natural seria trocar o
casamento de palavras-chave por uma chamada a um LLM (via um backend, para
não expor chave de API no navegador), mantendo a mesma interface e as mesmas
regras de encaminhamento para o RH humano.

## Como rodar

Não precisa de instalação. Basta abrir `index.html` num navegador (duplo
clique no arquivo, ou `python3 -m http.server` na pasta e acessar
`http://localhost:8000`).

## Aviso

Este projeto foi desenvolvido exclusivamente para fins acadêmicos. As
políticas de RH usadas na base de conhecimento são fictícias/condensadas e
não reproduzem documentos internos reais da Ambev.
