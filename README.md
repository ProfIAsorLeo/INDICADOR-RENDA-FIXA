# Indicador de Investimentos em Renda Fixa

Este projeto desenvolve um indicador quantitativo para auxiliar na tomada de decisão de investimentos em títulos de renda fixa brasileiros, com foco inicial em títulos públicos do Tesouro Direto (NTNs, LTNs e LFTs).

## Objetivo

O objetivo é criar uma ferramenta que forneça sinais de **compra**, **venda** ou **manutenção** para esses títulos, baseado na análise de dados macroeconômicos, financeiros e de indicadores técnicos.

## Metodologia

O indicador combina as seguintes informações:

*   **IPCA (Índice Nacional de Preços ao Consumidor Amplo):**  Índice de inflação oficial do Brasil (dados sintéticos, temporariamente).
*   **Selic (Taxa Básica de Juros):**  Taxa de juros básica da economia brasileira (dados sintéticos, temporariamente).
*   **Expectativas do Mercado (Relatório Focus):**  Expectativas do mercado para o IPCA e a Selic (coletadas via API do Banco Central).
*   **Curva de Juros Futuros (DI):**  Taxas de juros negociadas no mercado futuro de DI para diferentes prazos de vencimento (coleta manual da ANBIMA, temporariamente).
*   **Taxa Neutra de Juros:**  Taxa de juros real que, em teoria, não estimula nem contrai a economia (3 abordagens: estimativa do BCB, taxa FED + 7% e taxa FED + 5%).

O indicador utiliza os seguintes indicadores técnicos:

*   **Médias Móveis Exponenciais (MMEs):**  Para identificar tendências.
*   **MACD (Moving Average Convergence Divergence):**  Para identificar tendências e pontos de reversão.
*   **IFR (Índice de Força Relativa):**  Para identificar condições de sobrecompra e sobrevenda (a ser implementado).
*   **Estocástico:**  Para identificar condições de sobrecompra e sobrevenda (a ser implementado).
*   **Pontos de Pivô:** Para identificar níveis de suporte e resistência (a ser implementado).

## Estado Atual do Projeto

O projeto está em fase de desenvolvimento.  Atualmente, o indicador:

*   Calcula MMEs e MACD para IPCA e Selic (com dados sintéticos).
*   Define tendências com base no MACD.
*   Integra as expectativas do mercado (Focus) para IPCA e Selic.
*   Gera um sinal de compra/venda/manter com base em uma lógica temporária e simplificada, focada em títulos pós-fixados.

**Limitações Atuais:**

*   Utiliza dados sintéticos para IPCA e Selic, o que limita a precisão do indicador.
*   Ainda não incorpora a curva de juros futuros (DI), a taxa neutra e os pontos de pivô na lógica do indicador.
*   A regra de decisão é simplificada e precisa de refinamento.

## Próximos Passos

1.  **Obter dados reais da Curva de Juros (DI):**  Implementar a coleta manual via planilha do Google Sheets e buscar uma fonte automatizada (API da ANBIMA, B3 ou fontes pagas).
2.  **Integrar a Curva de Juros e a Taxa Neutra:**  Adicionar os dados da curva de juros e da taxa neutra ao DataFrame e refinar a lógica do indicador.
3.  **Calcular Spreads, Variações da Curva e Pontos de Pivô:** Implementar o cálculo desses indicadores.
4.  **Refinar a Regra de Decisão:**  Desenvolver uma regra de decisão mais completa, considerando a curva de juros, a taxa neutra e os pontos de pivô.
5.  **Implementar IFR e Estocástico.**
6.  **Definir as Features para o Machine Learning:** Selecionar as variáveis de entrada para o modelo de machine learning.
7.  **Escolher e Treinar um Modelo de Machine Learning:**  Selecionar um algoritmo e treinar um modelo para prever os sinais do indicador.
8.  **Testar e Validar o Indicador:**  Avaliar o desempenho do indicador com dados históricos (quando disponíveis) e ajustar a lógica/modelo conforme necessário.
9.  **Desenvolver a Interface (Node.js e React):**  Criar uma interface web amigável para o indicador.
10. **Integrar com a API da Nelogica (ProfitDLL):** Automatizar a coleta de dados e, possivelmente, a execução de ordens.

## Como Executar o Projeto

1.  Instale as dependências: `pip install pandas numpy requests`.
2.  Faça o upload dos arquivos CSV (gerados automaticamente ou manualmente) para o ambiente do Colab.
3.  Execute as células do notebook na ordem correta.

## Contribuições

Contribuições são bem-vindas!  Sinta-se à vontade para abrir issues, enviar pull requests ou entrar em contato para discutir ideias e melhorias.

## Autor

[Seu Nome e Link para o seu perfil do GitHub]

---

**Lembre-se de:**

*   **Substituir as informações entre colchetes `[]` pelas informações do seu projeto.**
*   **Adicionar o link para o seu repositório do GitHub no final do README.**
*   **Manter o README atualizado à medida que o projeto evolui.**

**Com a documentação atualizada e o README criado, você estará pronto para criar o repositório no GitHub e compartilhar o seu projeto!**

Me avise se tiver mais dúvidas ou precisar de ajuda com a documentação.

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
