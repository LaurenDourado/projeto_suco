# *Passo a Passo: Criação de uma Página Interativa de Frutas* 🍓🍊🥑
Tutorial sobre como criar uma página web interativa utilizando HTML, CSS e JavaScript. A página exibe frutas e seus respectivos refrigerantes, permitindo que o usuário navegue entre as opções.

Este guia será dividido em etapas, mostrando desde a criação da estrutura HTML, estilização com CSS, até a implementação da interação com JavaScript.

### Estrutura do Projeto 💻
HTML : Estrutura básica da página com os frascos de frutas.
CSS : Estilização da página e animação de transição entre as frutas.
JavaScript : Lógica para navegação entre as frutas e exibição de um alerta.
Passo 1: Estrutura HTML 🛠️
Primeiro, criamos uma estrutura HTML que contém cada fruta e o correspondente refrigerante.

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Document</title>
</head>
<body>
    <main>
        <section class="item ativo" style="--background:#EA3D41">
            <div class="titulo">morango</div>
            <img src="img/morango.png" alt="fruta" class="fruta">
            <img src="img/lataMorango.png" alt="refri" class="refri">
        </section>

        <section class="item" style="--background:#2D5643">
            <div class="titulo">abacate</div>
            <img src="img/abacate.png" alt="fruta" class="fruta">
            <img src="img/lataAbacate.png" alt="refri" class="refri">
        </section>

        <section class="item" style="--background:#E7A043">
            <div class="titulo">Laranja</div>
            <img src="img/laranja.png" alt="fruta" class="fruta">
            <img src="img/lataLAranja.png" alt="refri" class="refri">
        </section>

        <div class="seta">
            <button id="anterior"><</button>
            <button id="proximo" onclick="clicou()">></button>
        </div>
    </main>
</body>
<script src="script.js"></script>
</html>
Passo 2: Estilizando com CSS 🎨
Agora, vamos adicionar o estilo para os botões de frutas, os botões de navegação e as animações de transição. O CSS garante que os elementos sejam desejados corretamente na tela e que a navegação entre as frutas seja suave.

.item{
    display: none;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    overflow: hidden;
    background-color: var(--background);
}

.item.ativo{
    display: block;
}

.item .titulo{
    font-size: 12rem;
    color: #ffffff;
    font-family: system-ui, -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    font-weight: bold;
    text-align: center;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.item .fruta{
    width: 90%;
    position: absolute;
    top: 0;
    z-index: 3;
}

.item .refri{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    z-index: 2;
}

#anterior, #proximo{
    position: absolute;
    top: 50%;
    transform: translatey(-50%);
    width: 50px;
    height: 50px;
    background-color: #EEE9;
    border: 1px solid #EEE9;
    color: #EEE;
    font-size: x-large;
    font-family: monospace;
    cursor: pointer;
    z-index: 4;
    border-radius: 50%;
}

#anterior{
    left: 30px;
}

#proximo{
    right: 30px;
}
Passo 3: Interação com JavaScript 🚀
Com o JavaScript, vamos criar uma lógica para navegar entre as frutas. A função clicou()exibe um alerta, enquanto o restante do código pode ser atualizado para controlar a navegação entre os botões.

const clicou = () => {
    window.alert("Deu certo");
}
Passo 4: Funcionamento da Navegação 🔄
Na estrutura atual, a navegação entre as frutas e seus refrigerantes não está rompida. Para isso, você pode adicionar uma lógica que alterna entre os botões de frutas ao clicar nos botões "anterior" e "próximo". Aqui está um exemplo básico de como isso pode ser feito:

let indiceAtivo = 0;
const itens = document.querySelectorAll('.item');
const anterior = document.getElementById('anterior');
const proximo = document.getElementById('proximo');

const mostrarItem = (index) => {
    itens.forEach((item, i) => {
        item.classList.remove('ativo');
        if (i === index) {
            item.classList.add('ativo');
        }
    });
};

anterior.addEventListener('click', () => {
    indiceAtivo = (indiceAtivo > 0) ? indiceAtivo - 1 : itens.length - 1;
    mostrarItem(indiceAtivo);
});

proximo.addEventListener('click', () => {
    indiceAtivo = (indiceAtivo < itens.length - 1) ? indiceAtivo + 1 : 0;
    mostrarItem(indiceAtivo);
});

// Inicializando o primeiro item como ativo
mostrarItem(indiceAtivo);
Passo 5: Conclusão 🎉
Agora você tem uma página interativa com frutas e seus respectivos refrigerantes. Você pode expandir esse projeto com mais frutas, adicionar animações ou até mesmo incluir mais funcionalidades, como uma barra de progresso ou uma galeria de imagens.
