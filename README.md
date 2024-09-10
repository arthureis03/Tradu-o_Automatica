# Estudo de Caso: Tradução Automática com RNNs

Este projeto implementa um modelo de tradução automática utilizando Redes Neurais Recorrentes (RNNs) com base no livro "Dive into Deep Learning". A implementação segue os passos descritos na seção 9.5, incluindo o download e pré-processamento de dados, tokenização, construção de vocabulário e treinamento do modelo. 

## Descrição Geral

Neste estudo de caso, utilizamos um conjunto de dados bilíngue de sentenças em francês e inglês. O objetivo é treinar um modelo capaz de traduzir sentenças do inglês para o francês.

## Perguntas e Respostas

### 1. Como o argumento `num_examples` na função `load_data_nmt` afeta os tamanhos do vocabulário do idioma de origem e do idioma de destino?

O argumento `num_examples` determina o número de exemplos usados para construir os vocabulários de origem e destino. Quando aumentamos `num_examples`, mais exemplos são incluídos, o que geralmente resulta em um vocabulário maior, pois mais palavras únicas são capturadas no processo. Isso pode melhorar a precisão do modelo ao traduzir, pois ele tem acesso a um vocabulário mais amplo. No entanto, isso também pode aumentar a complexidade e o tempo de treinamento.

Por outro lado, ao diminuir `num_examples`, menos exemplos são utilizados, o que resulta em um vocabulário menor. Isso simplifica o modelo e pode reduzir o tempo de treinamento, mas também pode limitar a capacidade do modelo de lidar com uma variedade maior de palavras e expressões, possivelmente afetando a qualidade da tradução.

### 2. A tokenização em nível de palavra é uma boa ideia para idiomas como chinês e japonês, que não têm indicadores de limite de palavras?

Não, a tokenização em nível de palavra não é ideal para idiomas como chinês e japonês, que não possuem espaços ou outros delimitadores claros entre palavras. Nestes idiomas, as palavras não são separadas por espaços, tornando difícil identificar os limites das palavras através de métodos de tokenização baseados em espaços.

Nesses casos, a tokenização em nível de caractere ou o uso de algoritmos de segmentação específicos são preferíveis. Esses métodos permitem capturar as unidades semânticas de forma mais precisa, considerando as nuances e a complexidade do idioma, resultando em uma representação mais adequada para tarefas de Processamento de Linguagem Natural (PLN).

## Estrutura do Código

- **Preprocessamento:** Inclui funções para limpeza e formatação do texto.
- **Tokenização:** Segmentação das sentenças em tokens, com opção de limitar o número de exemplos processados.
- **Vocabulário:** Construção de vocabulários para os idiomas de origem e destino, com base nos tokens.
- **Treinamento:** Configuração e treinamento do modelo de tradução usando RNNs.
