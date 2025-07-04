# ✨ Criador Mágico de Animações com IA

Este é um projeto de front-end que permite aos usuários gerar animações CSS simplesmente descrevendo o que desejam em uma caixa de texto. A aplicação envia a descrição para um serviço de backend (via webhook N8N) que utiliza IA para gerar o código HTML e CSS correspondente, exibindo o resultado e o código em tempo real.

## 🚀 Funcionalidades

- **Interface Simples**: Um campo de texto para o usuário descrever a animação desejada.
- **Geração por IA**: Integração com um backend de IA para interpretar o texto e criar o código.
- **Visualização em Tempo Real**: Exibe a animação gerada instantaneamente.
- **Exibição de Código**: Mostra o código CSS gerado para que o usuário possa copiá-lo e utilizá-lo em outros projetos.

## 🛠️ Como Funciona

1.  **Entrada do Usuário**: O usuário digita uma descrição no campo de texto (ex: "Uma caixa que gira e muda de cor").
2.  **Requisição**: Ao clicar no botão "Criar Mágica ✨", o JavaScript captura o texto e envia uma requisição `POST` para um webhook pré-configurado do N8N.
3.  **Processamento no Backend**: O N8N recebe a requisição, processa o texto (provavelmente utilizando um modelo de linguagem como o GPT) e gera uma resposta em formato JSON contendo:
    - `preview`: O código HTML do elemento a ser animado.
    - `code`: O código CSS da animação para ser exibido.
    - `style`: As regras CSS (incluindo `@keyframes`) que precisam ser injetadas na página para a animação funcionar.
4.  **Exibição no Frontend**: O JavaScript recebe a resposta, interpreta o JSON e atualiza a página dinamicamente:
    - O HTML do `preview` é inserido na área de resultado.
    - O `code` CSS é exibido na área de código.
    - As regras de `style` são adicionadas ao `<head>` do documento, ativando a animação.

## 💻 Tecnologias Utilizadas

- **HTML5**: Estrutura da página web.
- **CSS3**: Estilização da interface e das animações geradas.
- **JavaScript (ES6+)**: Manipulação do DOM, interatividade e comunicação com a API (`fetch`, `async/await`).
- **N8N**: Plataforma de automação usada como backend para se conectar ao serviço de IA.

## 📂 Estrutura dos Arquivos

```
├── index.html
├── styles.css
└── scripts.js
```

- **`index.html`**: Contém a estrutura principal da página, incluindo as áreas para exibição do código e do resultado, além do campo de entrada e do botão.
- **`styles.css`**: Define a aparência visual de todos os elementos da página, utilizando Flexbox para o layout.
- **`scripts.js`**: Responsável por toda a lógica da aplicação, incluindo o evento de clique do botão e a comunicação com o webhook.

## 🏃 Como Executar

1.  **Backend**: Certifique-se de que o webhook do N8N (`https://rodrialmeida.app.n8n.cloud/webhook/animacao-csss`) está ativo e funcionando corretamente.
2.  **Frontend**:
    - Clone ou baixe este repositório.
    - Abra o arquivo `index.html` em qualquer navegador web moderno (como Chrome, Firefox, etc.).
3.  **Uso**:
    - Digite a descrição da animação que você deseja.
    - Clique no botão "Criar Mágica ✨" e aguarde o resultado.

---

*Este projeto é uma excelente demonstração de como integrar um frontend simples com serviços de IA poderosos para criar ferramentas criativas e funcionais.*