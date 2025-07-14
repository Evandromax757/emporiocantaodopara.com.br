# Dashboard Completo - EVANDRO M1 VISION PRO

Este projeto é um **Dashboard Web** para monitoramento e visualização em tempo real de sinais e estatísticas do sistema **ROBOCAPTO**. Ele foi desenvolvido com HTML, CSS e JavaScript puro, possuindo uma interface moderna e responsiva, ideal para acompanhamento de operações automatizadas.

## Funcionalidades

- **Status Atual:** Exibe a mensagem do estado atual do robô/sistema.
- **Sinal Programado:** Mostra o tipo de sinal (COMPRA, VENDA ou NENHUM) e o horário programado.
- **Estatísticas:** Contabiliza total de sinais, acertos e a taxa de assertividade (%) das operações.
- **Sequência de Candles:** Informa a sequência atual de candles verdes e vermelhos.
- **Módulos Ativos:** Lista quais módulos estão ativos no momento.
- **Botão Pausar/Retomar Análise:** Permite pausar ou retomar a análise do robô diretamente pelo painel.

## Como Funciona

O dashboard faz requisições periódicas (a cada segundo) para um backend local (API em `http://127.0.0.1:5000`), buscando dados atualizados para exibição dos status, sinais e estatísticas.  
O botão "Pausar Análise" envia uma requisição para pausar ou retomar o funcionamento do backend.

> **Atenção:**  
> Para funcionamento total do dashboard, é necessário rodar o backend local que responda às rotas `/status` e `/toggle_pause` no endereço `http://127.0.0.1:5000`.

## Estrutura dos Dados Esperados

A API backend deve retornar um objeto JSON com a seguinte estrutura na rota `/status`:

```json
{
  "mensagem": "Texto de status...",
  "sinal_programado": "COMPRA | VENDA | NENHUM",
  "hora_sinal": "HH:MM",
  "estatisticas": {
    "total_sinais": 0,
    "total_acertos": 0
  },
  "sequencia_verde": 0,
  "sequencia_vermelha": 0,
  "modulos_ativos": ["nome_modulo1", "nome_modulo2"],
  "is_paused": false
}
```

## Personalização

- As cores e estilos do dashboard podem ser ajustados facilmente via CSS.
- Os ícones e textos são personalizáveis para o seu robô ou operação.

## Como Usar

1. **Coloque o arquivo `dashboard_completo.html` em uma pasta pública do seu servidor ou abra diretamente no navegador.**
2. **Garanta que o backend local está rodando e respondendo nas rotas esperadas.**

## Requisitos

- Navegador moderno (Google Chrome, Firefox, Edge, etc).
- Backend local rodando em `http://127.0.0.1:5000` com as rotas `/status` e `/toggle_pause`.

## Observações

- Este dashboard **não realiza operações diretamente**; ele apenas exibe informações vindas do backend.
- Para funcionamento externo (em outro computador ou hospedagem), ajuste o endereço da API na variável `API_URL` no script para apontar para o endereço correto do backend.

---

Desenvolvido por **Evandro**  
Para dúvidas ou sugestões, entre em contato!
