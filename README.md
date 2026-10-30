# 🛰️ Rastreador da Estação Espacial Internacional (ISS)

Aplicação web simples e responsiva para monitorar a posição da **Estação Espacial Internacional (ISS)** em tempo real no mapa interativo, utilizando HTML, CSS, JavaScript e a biblioteca Leaflet.

---

## 🚀 Funcionalidades

- **Rastreamento em Tempo Real:** Atualização automática das coordenadas geográfica da ISS a cada 5 segundos.
- **Mapa Interativo:** Exibição do marcador com o ícone da ISS sobre o mapa do *OpenStreetMap* via Leaflet.js.
- **Transição Suave:** Animação de movimento do marcador e centralização de câmera a cada nova atualização de coordenadas.
- **Interface Responsiva:** Design limpo com cabeçalho contendo latitude, longitude e horário da última atualização.

---

## 🛠️ Tecnologias Utilizadas

- **HTML5 & CSS3:** Estruturação da página e estilização moderna com Flexbox.
- **JavaScript (ES6+):** Consumo de API assíncrona (`fetch` / `async/await`) e manipulação de DOM.
- **[Leaflet.js](https://leafletjs.com/):** Biblioteca open-source para renderização de mapas interativos.
- **[OpenStreetMap](https://www.openstreetmap.org/):** Provedor das camadas do mapa (*tiles*).
- **[Where the ISS at? API](https://wheretheiss.at/w/developer):** API REST gratuita utilizada para obter a posição exata da ISS.

---

## 📂 Estrutura do Projeto

O projeto é mantido inteiramente em um único arquivo de execução:

```
.
└── index.html   # Contém a estrutura HTML, estilos CSS e scripts JS
```

---

## 🔧 Como Executar

Não é necessária a instalação de dependências ou Node.js para rodar este projeto.

1. Faça o download ou clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   ```
2. Abra o arquivo `index.html` diretamente em seu navegador web preferido (Google Chrome, Firefox, Edge, Safari, etc.).

---

## 🔍 Explicação Técnica do Código

### 1. Chamada de API (`Where the ISS at?`)
O script realiza requisições para o endpoint `https://api.wheretheiss.at/v1/satellites/25544` utilizando `fetch`. A API retorna dados JSON contendo `latitude` e `longitude` atuais da estação.

### 2. Fluxo da Aplicação (`fetchISSPosition`)
- **Primeiro Carregamento (`isFirstLoad = true`):**
  - Cria o marcador da ISS no mapa com um ícone customizado em formato SVG.
  - Exibe um balão informativo (*popup*) sobre a ISS.
  - Centraliza o mapa diretamente na posição atual.
- **Atualizações Recorrentes (`setInterval`):**
  - Executa a função `fetchISSPosition()` a cada 5.000 ms (5 segundos).
  - Atualiza as coordenadas do marcador existente via `issMarker.setLatLng()`.
  - Move suavemente a câmera do mapa com `map.panTo()`.

---

## 📝 Licença

Este projeto está sob a licença [MIT](https://opensource.org/licenses/MIT). Sinta-se à vontade para utilizar, modificar e distribuir!