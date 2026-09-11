<div align="center">

<h1>🌿 WebGIS GEE — Mato Grosso do Sul</h1>

<h3>Análise espacial das emissões municipais de gases de efeito estufa</h3>

<p>
WebGIS interativo para visualização e análise das emissões de GEE
nos 79 municípios de Mato Grosso do Sul.
</p>

<p>
<a href="https://souzavictoria973-pixel.github.io/webgis-gee-ms/">
🌎 <b>Abrir WebGIS</b>
</a>
</p>

<p>
<img src="https://img.shields.io/badge/Python-1B4332?style=for-the-badge&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/WebGIS-2D6A4F?style=for-the-badge">
<img src="https://img.shields.io/badge/Folium-40916C?style=for-the-badge">
<img src="https://img.shields.io/badge/Leaflet.js-52B788?style=for-the-badge&logo=leaflet&logoColor=white">
<img src="https://img.shields.io/badge/SEEG-74C69D?style=for-the-badge">
</p>

</div>

---

## 🌱 Sobre o projeto

Este projeto apresenta um **WebGIS para análise espacial das emissões de Gases de Efeito Estufa (GEE)** nos municípios de Mato Grosso do Sul.

A aplicação integra dados ambientais, populacionais e geográficos para transformar informações tabulares em um produto interativo de **inteligência geoespacial**.

O principal indicador apresentado no mapa é:

> **Emissão per capita = Emissão total municipal de GEE ÷ População municipal**

A visualização utiliza um mapa coroplético em tons de verde, permitindo comparar espacialmente os municípios e identificar aqueles com maiores e menores valores de emissão por habitante.

---

## 🗺️ Funcionalidades

- 🌿 Mapa coroplético dos 79 municípios de Mato Grosso do Sul
- 🔎 Busca por município
- 🖱️ Tooltip com indicadores ao passar o mouse
- 📊 Painel municipal com informações detalhadas
- 👥 População municipal
- 🌎 Emissão total de GEE
- 📈 Emissão per capita
- 🏆 Ranking estadual
- 📉 Comparação com o indicador estadual
- 📏 Ferramenta de medição de distância e área
- 🧭 Exibição de coordenadas
- 🗺️ Mini mapa
- 🏠 Botão de retorno à visualização estadual
- ⛶ Modo tela cheia
- ℹ️ Painel com metodologia e fontes
- 🌐 Publicação via GitHub Pages

---

## 🌎 Origem dos dados e rastreabilidade

A construção deste WebGIS utiliza diferentes fontes públicas e oficiais.

Cada base possui uma função específica dentro da análise.

### 🌱 Emissões de gases de efeito estufa

Os dados municipais de emissões de GEE são provenientes do:

**SEEG — Sistema de Estimativas de Emissões e Remoções de Gases de Efeito Estufa**

Plataforma:

https://plataforma.seeg.eco.br/

O SEEG disponibiliza estimativas de emissões e remoções de gases de efeito estufa no Brasil, permitindo análises por diferentes recortes territoriais, setores e períodos.

Neste projeto, os dados do SEEG deram origem à variável:

`emissao`

Essa variável representa a emissão total municipal utilizada tanto na análise espacial quanto no cálculo da emissão por habitante.

---

### 🗺️ Malha territorial dos municípios

Os limites geográficos dos municípios de Mato Grosso do Sul foram obtidos através dos serviços do:

**IBGE — Instituto Brasileiro de Geografia e Estatística**

A geometria municipal foi obtida diretamente pela **API de Malhas do IBGE**, em formato GeoJSON.

Endpoint utilizado:

`https://servicodados.ibge.gov.br/api/v2/malhas/50/?resolucao=5&formato=application/vnd.geo+json&qualidade=2`

Parâmetros utilizados:

- `50` = código da Unidade da Federação Mato Grosso do Sul;
- `resolucao=5` = nível municipal;
- `GeoJSON` = formato geográfico utilizado na aplicação WebGIS.

As geometrias retornadas pela API são utilizadas diretamente pelo Folium e pelo Leaflet para representar os municípios no mapa.

---

### 🔢 Códigos oficiais dos municípios

Para realizar a ligação entre os dados tabulares e os polígonos municipais, foram utilizados os **códigos oficiais do IBGE**.

Os nomes e códigos dos municípios foram obtidos através da:

**API de Localidades do IBGE**

Endpoint utilizado:

`https://servicodados.ibge.gov.br/api/v1/localidades/estados/50/municipios`

A API retorna informações como:

- código do município;
- nome;
- unidade da federação;
- região geográfica imediata;
- região geográfica intermediária.

O identificador municipal foi armazenado no projeto como:

`codigo_ibge`

Esse código é utilizado como chave de integração entre os dados tabulares e as geometrias.

O uso do código oficial do IBGE reduz problemas relacionados a:

- diferenças de grafia;
- acentuação;
- abreviações;
- nomes semelhantes.

---

### 👥 População municipal

Os dados populacionais foram utilizados para normalizar as emissões e gerar o indicador de emissão por habitante.

A variável utilizada no projeto é:

`populacao`

A fonte populacional deve ser registrada com o mesmo nível de rastreabilidade das demais bases.

**Fonte da população:** preencher com a base utilizada  
**Ano de referência:** preencher  
**Data de acesso:** preencher

Essa informação é importante para garantir a reprodutibilidade da análise.

---

## 🧮 Indicador de emissão per capita

O indicador apresentado no mapa foi calculado durante o processamento dos dados.

A fórmula utilizada foi:

**Emissão per capita = Emissão total municipal de GEE ÷ População municipal**

No projeto, o indicador foi armazenado na variável:

`por_habitante`

A unidade utilizada é:

`tCO₂e/hab`

Onde:

- `tCO₂e` = toneladas de dióxido de carbono equivalente;
- `hab` = habitante.

---

## 📊 Indicadores apresentados

Para cada município, o WebGIS apresenta:

- população;
- emissão total de GEE;
- emissão per capita;
- ranking estadual;
- comparação com o indicador estadual.

O ranking é calculado em ordem decrescente de emissão por habitante.

A comparação estadual indica quanto o valor municipal está acima ou abaixo do indicador per capita calculado para Mato Grosso do Sul.

---

## 🔗 Fluxo de integração dos dados

```text
SEEG
│
└── Emissões municipais
        │
        ├──────────────┐
        │              │
        ▼              ▼
     emissão        população
        │              │
        └──────┬───────┘
               │
               ▼
       Emissão per capita
               │
               ▼
      Código IBGE municipal
               │
               ▼
       API Localidades IBGE
               │
               ▼
        Malha GeoJSON IBGE
               │
               ▼
              JOIN
               │
               ▼
        Folium + Leaflet
               │
               ▼
       🌿 WebGIS interativo
