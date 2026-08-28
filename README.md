# Brinda — Assistente Virtual de RH (protótipo acadêmico)

Brinda é um protótipo acadêmico de chatbot de RH inspirado na Ambev, feito para
um projeto de faculdade. **Não é um canal oficial de RH da Ambev** e não deve
ser usado para atendimento real de colaboradores.

O assistente responde dúvidas administrativas comuns (férias, benefícios,
ponto e jornada, afastamentos/licenças e documentos de admissão) com base em
uma base de conhecimento fixa embutida no servidor, e sempre encaminha para o
RH humano em casos sensíveis (saúde mental, desligamentos, avaliações de
desempenho, salário, dados pessoais sensíveis).

## Arquitetura

- `index.html` — interface de chat (estática, sem lógica de negócio).
- `server.js` — backend Express que guarda o system prompt/base de
  conhecimento e faz a chamada à API da Anthropic usando a chave de API
  armazenada apenas no servidor (via variável de ambiente).

O frontend nunca fala diretamente com a API da Anthropic. Toda chamada passa
por `POST /api/chat` no próprio servidor, para que a chave de API e o prompt
de sistema nunca sejam expostos no navegador.

## Como rodar localmente

```bash
npm install
cp .env.example .env   # edite e coloque sua ANTHROPIC_API_KEY
npm start
```

Acesse `http://localhost:3000`.

## Aviso

Este projeto foi desenvolvido exclusivamente para fins acadêmicos. As
políticas de RH usadas na base de conhecimento são fictícias/condensadas e
não reproduzem documentos internos reais da Ambev.
