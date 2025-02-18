_Passo a Passo: Criação de uma Página Interativa de Frutas_ 🍓🍊🥑

Tutorial sobre como criar uma página web interativa utilizando HTML, CSS e JavaScript. A página exibe frutas e seus respectivos refrigerantes, permitindo que o usuário navegue entre as opções.

Este guia será dividido em etapas, mostrando desde a criação da estrutura HTML, estilização com CSS, até a implementação da interação com JavaScript.

## Estrutura do Projeto 💻

* **HTML**: Estrutura básica da página com os frascos de frutas.
* **CSS**: Estilização da página e animação de transição entre as frutas.
* **JavaScript**: Lógica para navegação entre as frutas e exibição de um alerta.

## Passo 1: Estrutura HTML 🛠️

Primeiro, criamos a estrutura HTML que contém contendo cada fruta e o correspondente refrigerante.

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Documento</title>
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
```

## Passo 2: Estilizando com CSS 🎨

Agora, vamos adicionar o estilo para os rótulos de frutas, os botões de navegação e as animações de transição. O CSS garante que os elementos estejam corretos na tela e que a navegação entre as frutas seja suave     `

``css
.item{
    display: none     ;


    posição: absoluta;
    topo: 0;
    esquerda: 0;
    estouro: oculto;
    cor de fundo: var(--fundo);
}

.item.ativo{
    display: bloco;
}

.item .titulo{
    tamanho da fonte: 12rem;
    cor: #ffffff;
    família da fonte: system-ui, -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    peso da fonte: negrito;
    alinhamento do texto: centralizado;
    posição: absoluta;
    topo: 50%;
    esquerda: 50%;
    transformar: traduzir(-50%, -50%);
}

.item .fruta{
    largura: 90%;
    posição: absoluta;
    topo: 0;
    z-index: 3;
}

.item .refri{
    posição: absoluta;
    topo: 50%;
    esquerda: 50%;
    transformar: traduzir(-50%, -50%);
    largura: 600px;
    índice z: 2;
}

#anterior, #proximo{
    posição: absoluta;
    topo: 50%;
    transformar: traduzir(-50%);
    largura: 50px;
    altura: 50px;
    cor de fundo: #EEE9;
    borda: 1px sólido #EEE9;
    cor: #EEE;
    tamanho da fonte: x-grande;
    família de fontes: monoespaçada;
    cursor: ponteiro;
    índice z: 4;
    raio da fronteira: 50%;
}

#anterior{
    esquerda: 30px;
}

#proximo{
    direita: 30px;
}
```

## Passo 3: Interação com JavaScript 🚀

Com o JavaScript, vamos criar uma lógica para navegar entre as frutas. A função `clicou()` exibe um alerta, enquanto o restante do código pode ser adaptado para controlar a navegação entre os rótulos.

```javascript
const clicou = () => {
    window.alert("Deu certo");
}
```

## Passo 4: Funcionamento da Navegação 🔄

Na estrutura atual, a navegação entre as frutas e seus refrigerantes não está rompida. Para isso, você pode adicionar uma lógica que alterna entre os botões de frutas ao clicar nos botões "anterior" e "próximo". Aqui está um exemplo básico de como isso pode ser feito:

```javascript
let indiceAtivo = 0;
const itens = document.querySelectorAll('.item');
const anterior = document.getElementById('anterior');
const próximo = document.getElementById('proximo');

const mostrarItem = (index) => {
    itens.forEach((item, i) => {
        item.classList.remove('ativo');
        if (i === índice) {
            item.classList.add('ativo');
        }
    });
};

anterior.addEventListener('click', () => {
    índiceAtivo = (indiceAtivo > 0) ? índiceAtivo - 1 : itens.length - 1;
    mostrarItem(indiceAtivo);
});

proximo.addEventListener('click', () => {
    índiceAtivo = (indiceAtivo < itens.length - 1) ? índiceAtivo + 1 : 0;
    mostrarItem(indiceAtivo);
});

// Inicializando o primeiro item como ativo
mostrarItem(indiceAtivo);
```

## Passo 5: Conclusão 🎉

Espero que goste e visite as massas disponíveis!
