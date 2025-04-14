# Projetos JavaScript 

---

## Como usar este README no GitHub

1. **Abra o projeto com Git.**
2. Crie o arquivo `README.md` (se ainda não existir):
   ```bash
   touch README.md
   ```
3. Copie e cole este conteúdo no `README.md`.
4. Salve o arquivo.
5. Suba para o GitHub com os comandos:
   ```bash
   git add README.md
   git commit -m "Adiciona README para estudo"
   git push origin main
   ```
6. O README aparecerá na página inicial do seu repositório.

---

## HTML - Comandos Importantes

### `onmouseover`, `onmouseout`, `onclick`
- **Função:** Executam ações ao interagir com elementos.
- **Exemplo:**
  ```html
  <img src="desligada.avif" onmouseover="ligarLampada()" onmouseout="desligarLampada()" onclick="quebrarLampada()">
  ```

### `id` e `class`
- **Função:** Identificam e aplicam estilos aos elementos.
- **Exemplo:**
  ```html
  <div id="resultado" class="caixa"></div>
  ```

### `script`, `link`, `style`
- `<script>`: Insere código JavaScript.
- `<link>`: Conecta um arquivo CSS externo.
- `<style>`: Insere CSS diretamente no HTML.

---

## CSS - Estilizando Elementos

### Cores, tamanhos e espaçamentos
- **`background-color`**: Define a cor de fundo de um elemento.
- **`color`**: Define a cor do texto.
- **`font-size`**: Define o tamanho da fonte.
- **`padding`**: Espaço interno entre o conteúdo e a borda do elemento.
- **`margin`**: Espaço externo entre o elemento e outros elementos.

**Exemplo:**
```css
body {
  background-color: #f2f2f2; /* cor de fundo */
  color: black;              /* cor do texto */
  padding: 10px;             /* espaço interno */
  margin: 0;                 /* remove espaço externo padrão */
}
```

### Bordas e arredondamento
- **`border`**: Cria uma borda ao redor do elemento.
- **`border-radius`**: Arredonda os cantos da borda.

**Exemplo:**
```css
.caixa {
  border: 1px solid #333;
  border-radius: 8px;
  padding: 10px;
}
```

### Flexbox - Layout Responsivo
- **`display: flex`**: Define o container como flexível.
- **`justify-content`**: Alinha os itens horizontalmente (start, center, space-between, etc).
- **`align-items`**: Alinha os itens verticalmente.

**Exemplo:**
```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

### Pseudoclasses e interações
- **`:hover`**: Aplica estilo ao passar o mouse sobre o elemento.
- **`:active`**: Aplica estilo ao clicar.

**Exemplo:**
```css
button:hover {
  background-color: blue;
  color: white;
}

button:active {
  transform: scale(0.98);
}
```

### Estilização de botões e centralização (exemplo Raspadinha)
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

### Dica rápida:
- Utilize o DevTools (F12) para testar e alterar estilos rapidamente.
- Sempre salve alterações no `.css` e recarregue a página para ver os resultados.

### Cores, tamanhos e espaçamentos
- **Comandos:** `background-color`, `color`, `font-size`, `padding`, `margin`
- **Exemplo:**
  ```css
  body {
    background-color: #f2f2f2;
    color: black;
    padding: 10px;
  }
  ```

### Flexbox
- **Comandos:** `display`, `flex`, `justify-content`, `align-items`
- **Exemplo:**
  ```css
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  ```

### Pseudoclasses
- **Comandos:** `:hover`, `:active`
- **Exemplo:**
  ```css
  button:hover {
    background-color: blue;
  }
  ```

### Estilo com Botões e Layout Centralizado (Raspadinha)
```css
body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: #f5f5dc;
  font-family: Arial;
}

button {
  cursor: pointer;
  border: none;
  border-radius: 5px;
  font-size: 18px;
  padding: 10px 20px;
  margin: 10px;
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
}
```

---

## JavaScript - Funcionalidades

### Selecionar e modificar elementos
```js
let titulo = document.getElementById("titulo")
imagem.setAttribute("src", "ligada.avif")
resultado.innerHTML = "Bem-vindo!"
```

### Eventos e Interações
```js
botao.addEventListener("click", imprimir);

botao.addEventListener("mousemove", function () {
  resposta.innerText = "Você clicou né boiola";
});

botao.addEventListener("mouseout", function () {
  resposta.innerText = "Você passou em mim";
});

botao.addEventListener("mousemove", function () {
  evento.innerHTML = `<h1>Você foi invadido</h1>`;
});

function imprimir() {
  resposta.innerText = "Perdeu playboy";
}
```

### Botão que foge (move aleatoriamente)
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

### Variáveis
```js
let idade = 25;
const PI = 3.14;
```

### Condições
```js
if (nota >= 7) {
  alert("Aprovado");
} else {
  alert("Reprovado");
}
```

### Laços e arrays
```js
for (let i = 0; i < lista.length; i++) {
  console.log(lista[i]);
}

nomes.push("Carlos");
```

### Conversão de valores
```js
let numero = parseFloat("12.5");
```

---

## Exemplo: Lista Simples
```js
const botao = document.getElementById('add');
const entrada = document.getElementById('entrada');
const lista = document.getElementById('lista');
const items = [];

botao.addEventListener('click', function () {
  let ValorInput = entrada.value;
  items.push(ValorInput);
  atualizar();
});

function atualizar() {
  lista.innerHTML = null;
  for (let x = 0; x < items.length; x++) {
    let li = document.createElement("li");
    li.textContent = items[x];
    lista.appendChild(li);
  }
}
```

---

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
      convidados.splice(i, 1);
      atualizarLista();
    };
    lista.appendChild(li);
  }
}
```

---

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
    document.getElementById("result").innerText = "Não é possível dividir por zero!";
  } else {
    document.getElementById("result").innerText = "Resultado: " + (num1 / num2);
  }
}
```

### HTML da Calculadora
```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora Simples</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="calculator">
    <input type="text" id="num1" placeholder="Digite o primeiro número">
    <input type="text" id="num2" placeholder="Digite o segundo número">
    <button onclick="add()">+</button>
    <button onclick="subtract()">-</button>
    <button onclick="multiply()">*</button>
    <button onclick="divide()">/</button>
    <p id="result">Resultado: </p>
  </div>
  <script src="script.js"></script>
</body>
</html>
```

---
