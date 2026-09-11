<div align="center">

# 🌿 WebGIS GEE — Mato Grosso do Sul

### Análise espacial das emissões municipais de gases de efeito estufa

[![Python](https://img.shields.io/badge/Python-Data%20Processing-1B4332?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![GIS](https://img.shields.io/badge/GIS-WebGIS-2D6A4F?style=for-the-badge&logo=openstreetmap&logoColor=white)](#)
[![Folium](https://img.shields.io/badge/Folium-Interactive%20Maps-40916C?style=for-the-badge)](#)
[![Leaflet](https://img.shields.io/badge/Leaflet.js-Web%20Mapping-52B788?style=for-the-badge&logo=leaflet&logoColor=white)](https://leafletjs.com/)
[![SEEG](https://img.shields.io/badge/Data-SEEG-74C69D?style=for-the-badge)](#)

<br>

**WebGIS interativo para visualização e análise das emissões de GEE nos 79 municípios de Mato Grosso do Sul.**

🌎 **[Abrir WebGIS](https://souzavictoria973-pixel.github.io/webgis-gee-ms/)**

</div>

---

## 🌱 Sobre o projeto

Este projeto apresenta um **WebGIS para análise espacial das emissões de Gases de Efeito Estufa (GEE)** nos municípios de Mato Grosso do Sul.

A aplicação integra dados ambientais, populacionais e geográficos para transformar informações tabulares em um produto interativo de **inteligência geoespacial**.

O principal indicador analisado é:

> **Emissão per capita = Emissão total de GEE ÷ População municipal**

A visualização utiliza um mapa coroplético em tons de verde, permitindo identificar rapidamente diferenças espaciais entre os municípios.

---

## 🗺️ WebGIS

O sistema permite navegar pelos 79 municípios do estado e consultar informações individualmente.

### Principais funcionalidades

| Funcionalidade | Descrição |
|---|---|
| 🌿 **Mapa coroplético** | Municípios classificados pela emissão de GEE per capita |
| 🔎 **Busca municipal** | Localização rápida de qualquer município de MS |
| 🖱️ **Tooltip interativo** | Informações exibidas ao passar o mouse |
| 📊 **Painel municipal** | População, emissão total, per capita e ranking |
| 🏆 **Top 5** | Municípios com maiores emissões por habitante |
| 📈 **Comparação estadual** | Indica quanto o município está acima ou abaixo do indicador estadual |
| 📏 **Medição** | Ferramenta para medir áreas e distâncias |
| 🧭 **Coordenadas** | Exibição da posição do cursor |
| 🗺️ **Mini mapa** | Referência espacial durante a navegação |
| 🏠 **Home** | Retorno rápido à visualização de Mato Grosso do Sul |
| ⛶ **Fullscreen** | Visualização do WebGIS em tela cheia |
| ℹ️ **Sobre os dados** | Informações metodológicas e fontes |

---

## 📊 Indicadores

Para cada município são apresentados:

```text
População
        ↓
Emissão total de GEE
        ↓
Emissão por habitante
        ↓
Ranking estadual
        ↓
Comparação com Mato Grosso do Sul
