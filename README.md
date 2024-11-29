# Coordenadas das Escolas do Brasil

Este repositório contém um arquivo demonstrando a obtenção das coordenadas geográficas das Escolas do Brasil, tendo como fonte de dados o [Catálogo de Escolas do INEP](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/inep-data/catalogo-de-escolas), via linguagem de programação `Python` através da técnica de *web scraping*.

## Motivação

A criação deste repositório foi motivada pela necessidade de analisar espacialmente dados escolares e pela demanda de outros profissionais no que se refere a geolocalização das escolas (ver [este link](https://groups.google.com/g/qgisbrasil/c/m3fCa5B1jDk)). Atualmente (2024), o INEP disponibiliza apenas os endereços das escolas por meio dos microdados do Censo Escolar. Entretanto, abordagens de georeferenciamento não são eficazes devido ao alto nível de erros.

Como solução alternativa, as coordenadas geográficas podem ser obtidas através da técnica de *web scraping*, dado que o Catálogo de Escolas é um website com interface de BI para consultas que informa metadados das escolas, incluindo coordenadas geográficas. O Catálogo de Escolas possibilita consultar os metadados das escolas via filtros, como o código INEP da escola.

## Web scraping

Sendo uma página HTML com JavaScript, o Catálogo de Escolas exige o uso de soluções como `selenium`, via linguagem de programação, para gerenciamento robotizado do navegador de internet e posterior raspagem de dados. Aqui aplicamos o procedimento usando a linguagem `Python` e a biblioteca `selenium`, mas o processo é replicável em outras linguagens/frameworks.

Os **requisitos** são:

- Python 3.12.4 ou superior
- Mozila Firefox 100.0 ou superior

**Passo a passo** para reprodução (exemplo com código INEP da escola `42002079`):

1. Baixar repositório

```
git clone https://github.com/schoulten/coordenadas_escolas_br.git
```

2. Abrir o arquivo `webscraping.ipynb` (recomendado utilizar o `VS Code`)
3. Executar as células de código

Obs. 1: As coordenadas da escola `42002079` estarão disponíveis no objeto `coordenadas` (penúltima célula de código).
Obs. 2: Altere o código da escola na seção "Dados de entrada".
Obs. 3: configure um ambiente virual previamente (`venv`, `poetry`, etc.).
Obs. 4: adapte o código para iterar sobre uma lista de códigos de escolas.