# Predição de Preços de Imóveis com Redes Neurais

Este repositório contém um projeto de Machine Learning focado na predição de preços de imóveis residenciais utilizando Redes Neurais Artificiais (RNAs). O projeto aborda o desafio 'House Prices - Advanced Regression Techniques' disponível na plataforma Kaggle, que consiste em estimar o valor de venda de casas com base em diversas características. O desenvolvimento foi realizado em Python, utilizando a biblioteca PyTorch para a construção e treinamento dos modelos de redes neurais.




## Visão Geral do Projeto

O objetivo principal deste projeto é aplicar Redes Neurais Artificiais para resolver um problema de regressão: a predição de preços de casas. O conjunto de dados utilizado é o popular dataset 'House Prices' do Kaggle, que contém uma vasta gama de características descritivas para cada imóvel, como área, número de quartos, qualidade dos materiais, localização, entre outros. O desafio reside em construir um modelo robusto que possa aprender as relações complexas entre essas características e o preço final de venda.




## Estrutura do Repositório

O repositório está organizado da seguinte forma:

- **`Redes_Neurais.ipynb`**: Este é o Jupyter Notebook principal que contém todo o código do projeto. Ele abrange desde a análise exploratória e pré-processamento dos dados até a construção, treinamento e avaliação dos modelos de redes neurais.
- **`Relatório Tecnico.pdf`**: Documento com analise e explicação de experimentos e do código.
- **`README.md`**: Este arquivo, que fornece uma visão geral do projeto, instruções de uso e outras informações relevantes.




## Conjunto de Dados

O conjunto de dados utilizado é o `House Prices - Advanced Regression Techniques` do Kaggle [1]. Ele é dividido em dois arquivos CSV:

- `train.csv`: Contém os dados de treinamento, incluindo a variável alvo `SalePrice` (preço de venda do imóvel).
- `test.csv`: Contém os dados de teste, sem a variável `SalePrice`, para submissão na plataforma Kaggle.

O dataset possui diversas características que descrevem aspectos dos imóveis, como:

- **Área**: Tamanho do lote, área construída, etc.
- **Configuração**: Número de quartos, banheiros, etc.
- **Qualidade**: Qualidade geral, qualidade de materiais, etc.
- **Localização**: Bairro, proximidade de serviços, etc.
- **Outros**: Ano de construção, ano de reforma, tipo de telhado, tipo de fundação, etc.

Para mais detalhes sobre as colunas e seus significados, consulte a aba 'Data' na página do desafio no Kaggle [1].




## Pré-processamento de Dados

O pré-processamento dos dados é uma etapa crucial para o bom desempenho dos modelos de redes neurais. As principais etapas realizadas neste projeto incluem:

- **Tratamento de Valores Ausentes**: Identificação e tratamento de colunas com valores nulos. Colunas com alta porcentagem de valores ausentes (acima de 20%) foram removidas, como `PoolQC`, `MiscFeature`, `Alley`, `Fence`, `FireplaceQu` e `LotFrontage`. Para outras colunas com menos valores ausentes, foram aplicadas estratégias de imputação adequadas.
- **Codificação de Variáveis Categóricas**: Variáveis categóricas (tipo `object` no Pandas) foram convertidas em representações numéricas adequadas para as redes neurais, utilizando técnicas como One-Hot Encoding.
- **Normalização/Escalonamento**: As características numéricas foram escalonadas para garantir que todas as features contribuam igualmente para o treinamento do modelo, evitando que features com maiores escalas dominem o processo de otimização.
- **Remoção de Outliers**: Análise e tratamento de outliers que poderiam impactar negativamente o treinamento do modelo.




## Modelo de Rede Neural

O modelo de rede neural foi construído utilizando a biblioteca PyTorch. A arquitetura da rede é composta por camadas densas (Fully Connected) com funções de ativação ReLU, e uma camada de saída linear para a predição do preço. A otimização do modelo é realizada utilizando o otimizador Adam, e a função de perda Mean Squared Error (MSE) é empregada para medir a diferença entre os preços previstos e os preços reais.

Os hiperparâmetros utilizados no treinamento são:

- **Épocas (EPOCHS)**: 500
- **Taxa de Aprendizagem (LEARNING_RATE)**: 0.001
- **Tamanho do Lote (BATCH_SIZE)**: 64
- **Dispositivo (DEVICE)**: 'cpu' (o código pode ser adaptado para 'cuda' se uma GPU estiver disponível)

Para garantir a reprodutibilidade dos resultados, foram definidas sementes (seeds) para as bibliotecas `random`, `numpy` e `torch`.




## Resultados e Avaliação

O desempenho do modelo é avaliado utilizando métricas de regressão, como o Erro Quadrático Médio (RMSE) ou o R-squared. Durante o desenvolvimento, o conjunto de treinamento foi dividido em subconjuntos de treino e validação para monitorar o desempenho do modelo e evitar overfitting. As previsões finais são geradas para o conjunto de teste e podem ser submetidas na plataforma Kaggle para avaliação.




## Como Executar

Para executar o projeto, siga os passos abaixo:

1.  **Clone o repositório:**

    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    cd seu-repositorio
    ```

2.  **Crie um ambiente virtual (opcional, mas recomendado):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: .\venv\Scripts\activate
    ```

3.  **Instale as dependências:**

    ```bash
    pip install pandas numpy matplotlib seaborn torch scikit-learn plotly tqdm
    ```

4.  **Baixe os dados:**
    Os arquivos `train.csv` e `test.csv` podem ser baixados diretamente da página do desafio no Kaggle [1]. Coloque-os na mesma pasta do notebook `Redes_Neurais.ipynb`.

5.  **Execute o Jupyter Notebook:**

    ```bash
    jupyter notebook Redes_Neurais.ipynb
    ```

    Abra o notebook no seu navegador e execute as células sequencialmente para ver o fluxo completo do projeto, desde o pré-processamento até a predição.




## Referências

[1] House Prices - Advanced Regression Techniques. Kaggle. Disponível em: [https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview)




## Autores

- TAMYRIS CABRAL GOMES ROCHA  
- MARCOS VINÍCIUS SILVA  



