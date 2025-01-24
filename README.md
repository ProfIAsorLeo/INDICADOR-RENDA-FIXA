# Indicador Quantitativo de Renda Fixa: Tome Decisões Inteligentes

Este projeto desenvolve um indicador quantitativo para auxiliar na tomada de decisão de investimentos em títulos de renda fixa brasileiros, com foco inicial em títulos públicos do Tesouro Direto (NTNs, LTNs e LFTs).

## Objetivo

Objetivo: Fornecer sinais claros de compra, venda ou manutenção para títulos públicos do Tesouro Direto, auxiliando investidores a identificar as melhores oportunidades e otimizar seus retornos.

## Metodologia

O indicador combina as seguintes informações:

*   **IPCA (Índice Nacional de Preços ao Consumidor Amplo):** Índice de inflação oficial do Brasil ([fonte](https://www3.bcb.gov.br/sgspub/)).
    *   Dados sintéticos utilizados temporariamente.
*   **Selic (Taxa Básica de Juros):** Taxa de juros básica da economia brasileira ([fonte](https://www3.bcb.gov.br/sgspub/)).
    *   Dados sintéticos utilizados temporariamente.
*   **Expectativas do Mercado (Relatório Focus):** Expectativas do mercado para o IPCA e a Selic ([fonte](https://olinda.bcb.gov.br/olinda/servico/Expectativas/versao/v1/odata/)).
*   **Curva de Juros Futuros (DI):** Taxas de juros negociadas no mercado futuro de DI para diferentes prazos de vencimento ([fonte](https://www.anbima.com.br/)) (coleta manual da ANBIMA, temporariamente).
*   **Taxa Neutra de Juros:** Taxa de juros real que, em teoria, não estimula nem contrai a economia.
    *   Três abordagens: estimativa do BCB, taxa FED + 7% e taxa FED + 5%.

**Indicadores Técnicos:**

*   Médias Móveis Exponenciais (MMEs): Para identificar tendências de curto e longo prazo.
*   MACD (Moving Average Convergence Divergence): Para confirmar tendências e identificar pontos de reversão.
*   IFR (Índice de Força Relativa): Para identificar condições de sobrecompra e sobrevenda (a ser implementado).
*   Estocástico: Para identificar condições de sobrecompra e sobrevenda (a ser implementado).
*   Pontos de Pivô: Para identificar níveis de suporte e resistência (a ser implementado).

## Estado Atual do Projeto

O projeto está em fase de desenvolvimento. Atualmente, o indicador:

*   Calcula MMEs e MACD para IPCA e Selic (com dados sintéticos).
*   Define tendências com base no MACD.
*   Integra as expectativas do mercado (Focus) para IPCA e Selic.
*   Gera um sinal de compra/venda/manter com base em uma lógica temporária e simplificada, focada em títulos pós-fixados.

**Limitações Atuais:**

*   Utiliza dados sintéticos para IPCA e Selic, o que limita a precisão do indicador.
*   Ainda não incorpora a curva de juros futuros (DI), a taxa neutra e os pontos de pivô na lógica do indicador.
*   A regra de decisão é simplificada e precisa de refinamento.

## Próximos Passos

1.  Obter dados reais da Curva de Juros (DI).
2.  Integrar a Curva de Juros e a Taxa Neutra na lógica do indicador.
3.  Calcular Spreads, Variações da Curva e Pontos de Pivô.
4.  Refinar a Regra de Decisão.
5.  Implementar IFR e Estocástico.
6.  Definir as Features para o Machine Learning.
7.  Escolher e Treinar um Modelo de Machine Learning.
8.  Testar e Validar o Indicador.
9.  Desenvolver a Interface (Node.js e React).
10. Integrar com a API da Nelogica (ProfitDLL).

## Como Executar o Projeto

1.  Clone o repositório: `git clone [link para o repositório]`
2.  Instale as dependências: `pip install -r requirements.txt`
3.  Execute o script principal: `python main.py`
4.  Acesse a interface web: `[endereço da interface web]`

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues, enviar pull requests ou entrar em contato para discutir ideias e melhorias.

## Autor

[Seu Nome Completo]([link para seu perfil do GitHub])

## Licença

[MIT](https://choosealicense.com/licenses/mit/)

Projeto de ferramenta para indicador em renda fixa. 
indicador-renda-fixa/
├── dados/
│   ├── ipca.csv
│   ├── selic.csv
│   └── curva_juros.csv
├── src/
│   ├── coleta_dados.py
│   ├── indicadores.py
│   └── logica_decisao.py
├── interface/
│   ├── backend/
│   │   └── server.js
│   └── frontend/
│       └── app.jsx
├── docs/
│   └── documentacao.md
└── README.md
