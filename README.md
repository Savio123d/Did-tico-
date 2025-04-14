# Projetos JavaScript 

---

## HTML - Comandos Importantes

### `onmouseover`, `onmouseout`, `onclick`
- **Função:** Disparam ações ao interagir com elementos da página (passar o mouse, clicar, etc).
- **Exemplo explicado:**
  ```html
  <img src="desligada.avif"
       onmouseover="ligarLampada()"  <!-- Quando passar o mouse -->
       onmouseout="desligarLampada()" <!-- Quando tirar o mouse -->
       onclick="quebrarLampada()">   <!-- Quando clicar na imagem -->
  ```

### `id`, `class`, `input`, `button`, `p`
- `id`: Identifica um único elemento na página.
- `class`: Aplica estilos a múltiplos elementos com a mesma classe.
- `input`: Permite entrada de dados pelo usuário.
- `button`: Cria botões clicáveis para executar ações.
- `p`: Define um parágrafo de texto.
- **Exemplo:**
  ```html
  <input type="text" id="entrada" placeholder="Digite algo">
  <button onclick="mostrarMensagem()">Clique</button>
  <p id="saida"></p>
  ```

### `script`, `link`, `style`
- `<script>`: Insere código JavaScript direto ou externo.
- `<link>`: Conecta um arquivo CSS externo ao HTML.
- `<style>`: Aplica CSS diretamente dentro do HTML.

---

## CSS - Estilizando Elementos

### Cores, tamanhos e espaçamentos
```css
body {
  background-color: #f2f2f2; /* Cor de fundo */
  color: black;              /* Cor do texto */
  padding: 10px;             /* Espaço interno */
  margin: 0;                 /* Remove espaço externo */
}
```

### Bordas e cantos arredondados
```css
.caixa {
  border: 1px solid #333;   /* Borda fina com cor */
  border-radius: 8px;       /* Arredonda os cantos */
  padding: 10px;
}
```

### Flexbox - Layout Responsivo
```css
.container {
  display: flex;                   /* Ativa o modo Flex */
  justify-content: center;        /* Alinha horizontalmente */
  align-items: center;            /* Alinha verticalmente */
  height: 100vh;                  /* Altura total da tela */
}
```

### Pseudoclasses (interação com mouse)
```css
button:hover {
  background-color: blue; /* Muda a cor ao passar o mouse */
  color: white;
}

button:active {
  transform: scale(0.98);  /* Efeito ao clicar */
}
```

### Estilização de botões e layout (exemplo estilo "Raspadinha")
```css
body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: #f5f5dc;
  font-family: Arial;
  margin: 0;
}

button {
  cursor: pointer;
  border: none;
  border-radius: 5px;
  font-size: 18px;
  padding: 10px 20px;
  margin: 10px;
  transition: all 0.2s ease;
}

button a {
  text-decoration: none;
  color: inherit;
}

.yes {
  background-color: green;
  color: white;
  margin-right: 100px;
}

.nao {
  background-color: red;
  color: white;
  position: absolute;
  top: 0;
  left: 0;
}
```

---

## JavaScript - Funcionalidades

### Selecionar e modificar elementos HTML
```js
let titulo = document.getElementById("titulo"); // Seleciona elemento com id="titulo"
titulo.innerHTML = "Novo texto";               // Altera conteúdo interno
imagem.setAttribute("src", "ligada.avif");     // Altera atributo da imagem
```

### Eventos e interações com botões
```js
botao.addEventListener("click", imprimir); // Ao clicar no botão, executa a função

function imprimir() {
  resposta.innerText = "Perdeu playboy";
}
```

### Manipulação de formulários com input
```js
function mostrarMensagem() {
  let entrada = document.getElementById("entrada").value;
  document.getElementById("saida").innerText = "Você digitou: " + entrada;
}
```

### Botão que foge do cursor (efeito divertido)
```js
function moveButton() {
  let button = document.getElementById("nao");
  let x = Math.random() * (window.innerWidth - button.clientWidth);
  let y = Math.random() * (window.innerHeight - button.clientHeight);
  button.style.left = x + "px";
  button.style.top = y + "px";
}
```

### Interação com o usuário
```js
let nome = prompt("Digite seu nome:");
alert("Olá, " + nome);
```

### Variáveis e constantes
```js
let idade = 25;   // Pode mudar
const PI = 3.14;  // Valor fixo, constante
```

### Condições (if / else)
```js
if (nota >= 7) {
  alert("Aprovado");
} else {
  alert("Reprovado");
}
```

### Laços (loops) e arrays (listas)
```js
let lista = ["Ana", "Bruno", "Carlos"];

for (let i = 0; i < lista.length; i++) {
  console.log(lista[i]);
}

lista.push("Daniela"); // Adiciona no final da lista
```

### Conversão de valores
```js
let numero = parseFloat("12.5"); // Transforma string em número
```

---

## Exemplo Prático: Lista de Itens
```js
const botao = document.getElementById('add');
const entrada = document.getElementById('entrada');
const lista = document.getElementById('lista');
const items = [];

botao.addEventListener('click', function () {
  let valor = entrada.value;
  items.push(valor);
  atualizar();
});

function atualizar() {
  lista.innerHTML = "";
  for (let item of items) {
    let li = document.createElement("li");
    li.textContent = item;
    lista.appendChild(li);
  }
}
```

## Exemplo: Remover Itens da Lista
```js
const convidados = [];
const nome = document.getElementById('nome');
const botao = document.getElementById('add');
const lista = document.getElementById('listaConvidados');

botao.addEventListener("click", function() {
  convidados.push(nome.value);
  nome.value = "";
  atualizarLista();
});

function atualizarLista() {
  lista.innerHTML = "";
  for (let i = 0; i < convidados.length; i++) {
    const li = document.createElement("li");
    li.textContent = convidados[i];
    li.onclick = function() {
      convidados.splice(i, 1); // Remove ao clicar no item
      atualizarLista();
    };
    lista.appendChild(li);
  }
}
```

## Exemplo: Calculadora Simples
```js
function add() {
  let num1 = parseFloat(document.getElementById("num1").value);
  let num2 = parseFloat(document.getElementById("num2").value);
  document.getElementById("result").innerText = "Resultado: " + (num1 + num2);
}

function subtract() {
  let num1 = parseFloat(document.getElementById("num1").value);
  let num2 = parseFloat(document.getElementById("num2").value);
  document.getElementById("result").innerText = "Resultado: " + (num1 - num2);
}

function multiply() {
  let num1 = parseFloat(document.getElementById("num1").value);
  let num2 = parseFloat(document.getElementById("num2").value);
  document.getElementById("result").innerText = "Resultado: " + (num1 * num2);
}

function divide() {
  let num1 = parseFloat(document.getElementById("num1").value);
  let num2 = parseFloat(document.getElementById("num2").value);
  if (num2 === 0) {
    document.getElementById("result").innerText = "Erro: divisão por zero";
  } else {
    document.getElementById("result").innerText = "Resultado: " + (num1 / num2);
  }
}
```

### HTML para a calculadora
```html
<input type="text" id="num1" placeholder="Primeiro número">
<input type="text" id="num2" placeholder="Segundo número">
<button onclick="add()">+</button>
<button onclick="subtract()">-</button>
<button onclick="multiply()">*</button>
<button onclick="divide()">/</button>
<p id="result">Resultado: </p>
```

---
