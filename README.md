# 🎧 Player de Áudio — Estudo de JavaScript

Projeto desenvolvido como parte dos meus estudos de **JavaScript**, com o objetivo de praticar e consolidar os fundamentos da linguagem através da criação de uma página interativa de reprodução de áudio.

O projeto simula um **player de audiobook**, permitindo reproduzir, pausar e navegar entre diferentes capítulos.

O foco principal do desenvolvimento foi a **lógica JavaScript e a interação com os elementos HTML**, utilizando uma interface já estruturada para colocar em prática os conceitos básicos da linguagem.

## 🎯 Objetivo do Projeto

O objetivo foi transformar uma página HTML em uma aplicação interativa utilizando JavaScript.

Através do projeto, foram praticados conceitos fundamentais da linguagem, como:

* Declaração e manipulação de variáveis;
* Tipos de dados;
* Valores booleanos;
* Funções;
* Parâmetros e chamadas de funções;
* Estruturas condicionais (`if / else`);
* Operadores de comparação;
* Operadores de atribuição;
* Incremento e decremento;
* Manipulação do DOM;
* Seleção de elementos HTML;
* Alteração de propriedades de elementos;
* Manipulação de classes CSS;
* Eventos;
* Controle de estado da aplicação;
* Manipulação de áudio através da API do navegador.

## 🎵 Funcionamento

O player possui controles para:

* ▶️ Reproduzir o capítulo atual;
* ⏸️ Pausar o áudio;
* ⏮️ Voltar para o capítulo anterior;
* ⏭️ Avançar para o próximo capítulo;
* 🔄 Voltar ao primeiro capítulo após o último;
* 🔄 Ir para o último capítulo ao voltar antes do primeiro;
* 🎧 Avançar automaticamente quando o áudio termina.

A lógica é controlada por JavaScript, que mantém o capítulo atual e o estado de reprodução do áudio.

### Controle do estado

Uma variável booleana é utilizada para controlar se o áudio está sendo reproduzido:

```javascript
let taTocando = false;
```

Quando o usuário reproduz o áudio:

```javascript
taTocando = true;
```

E quando pausa:

```javascript
taTocando = false;
```

Isso permite que o mesmo botão tenha comportamentos diferentes dependendo do estado atual do player.

## 🧠 Fundamentos de JavaScript praticados

### 1. Variáveis

Foram utilizadas variáveis com `const` e `let` para armazenar elementos e informações que mudam durante a execução.

```javascript
const quantidadeCapitulos = 10;

let taTocando = false;
let capitulo = 1;
```

O projeto também demonstra a diferença entre valores que permanecem constantes e valores que podem ser alterados.

---

### 2. Tipos de dados

O projeto utiliza diferentes tipos de valores, principalmente:

* `String`
* `Number`
* `Boolean`

Exemplo:

```javascript
let taTocando = false;
let capitulo = 1;
const quantidadeCapitulos = 10;
```

---

### 3. Funções

A lógica foi organizada em funções responsáveis por diferentes comportamentos da aplicação.

```javascript
function tocarFaixa() {
  audio.play();
  taTocando = true;
}
```

Também foram utilizadas funções para:

* Reproduzir o áudio;
* Pausar o áudio;
* Alternar entre reproduzir e pausar;
* Avançar capítulo;
* Voltar capítulo.

Essa organização ajuda a separar responsabilidades dentro do código.

---

### 4. Estruturas condicionais

O projeto utiliza `if / else` para controlar diferentes situações.

Por exemplo, para verificar se o áudio está tocando:

```javascript
if (taTocando === true) {
  pausarFaixa();
} else {
  tocarFaixa();
}
```

Também são utilizadas condições para controlar a navegação entre capítulos.

---

### 5. Operadores

Foram utilizados operadores de comparação e atribuição para controlar a lógica da aplicação.

Exemplos:

```javascript
capitulo === 1
```

```javascript
capitulo < quantidadeCapitulos
```

```javascript
capitulo += 1
```

```javascript
capitulo -= 1
```

Esses operadores permitem controlar o fluxo de navegação dos capítulos.

---

### 6. Manipulação do DOM

Um dos principais objetivos do projeto foi aprender como o JavaScript pode acessar e modificar elementos HTML.

Para isso, foi utilizado:

```javascript
document.getElementById()
```

Exemplo:

```javascript
const nomeCapitulo = document.getElementById("capitulo");
```

Dessa forma, o JavaScript consegue acessar elementos da página e interagir com eles.

---

### 7. Alteração de conteúdo HTML

O nome do capítulo é atualizado dinamicamente através do JavaScript:

```javascript
nomeCapitulo.innerText = "Capítulo " + capitulo;
```

Isso demonstra como o JavaScript pode alterar o conteúdo de elementos HTML durante a execução da aplicação.

---

### 8. Manipulação de propriedades

O código altera dinamicamente a fonte do elemento de áudio:

```javascript
audio.src = "/audios/" + capitulo + ".mp3";
```

Assim, ao mudar de capítulo, o arquivo de áudio correspondente também é alterado.

---

### 9. Manipulação de classes CSS

O JavaScript também interage com o CSS através do `classList`.

Ao iniciar a reprodução:

```javascript
botaoPlayPause.classList.add("tocando");
```

Ao pausar:

```javascript
botaoPlayPause.classList.remove("tocando");
```

Isso permite alterar visualmente o botão de acordo com o estado do player.

---

### 10. Eventos

O projeto utiliza `addEventListener()` para detectar ações do usuário.

```javascript
botaoPlayPause.addEventListener("click", tocarOuPausarFaixa);
```

Também é utilizado o evento `ended` do elemento de áudio:

```javascript
audio.addEventListener("ended", proximoCapitulo);
```

Nesse caso, quando o áudio termina, o JavaScript executa automaticamente a função responsável por avançar para o próximo capítulo.

---

### 11. Controle de fluxo

A navegação entre os capítulos utiliza lógica para determinar quando avançar normalmente e quando voltar para o início.

```javascript
if (capitulo < quantidadeCapitulos) {
  capitulo += 1;
} else {
  capitulo = 1;
}
```

Isso cria um ciclo:

```text
Capítulo 1
   ↓
Capítulo 2
   ↓
...
   ↓
Capítulo 10
   ↓
Capítulo 1
```

O mesmo conceito é aplicado na navegação para capítulos anteriores.

## 🛠️ Tecnologias utilizadas

* **HTML5** — Estrutura da página
* **CSS3** — Estilização da interface
* **JavaScript** — Lógica e interatividade
* **HTML5 Audio API** — Reprodução e controle dos arquivos de áudio

## 📂 Estrutura do Projeto

```text
projeto/
│
├── index.html
├── style.css
├── script.js
│
└── audios/
    ├── 1.mp3
    ├── 2.mp3
    ├── 3.mp3
    ├── ...
    └── 10.mp3
```

## ▶️ Como executar

Como o projeto utiliza HTML, CSS e JavaScript puro, não é necessário instalar frameworks ou bibliotecas externas.

1. Clone o repositório:

```bash
git clone URL_DO_REPOSITORIO
```

2. Entre na pasta do projeto:

```bash
cd nome-do-projeto
```

3. Abra o arquivo `index.html` no navegador.

Também é possível utilizar a extensão **Live Server** no VS Code para executar o projeto localmente.

## 📚 Aprendizado

Este projeto foi desenvolvido como um exercício prático para **consolidar os fundamentos de JavaScript**.

Mais do que criar um player de áudio, o objetivo foi entender como os conceitos básicos da linguagem podem ser combinados para criar uma aplicação interativa.

O projeto ajudou a praticar o fluxo:

```text
Ação do usuário
       ↓
Evento JavaScript
       ↓
Função
       ↓
Lógica / Condição
       ↓
Alteração do estado
       ↓
Atualização da página
```

Esse tipo de exercício serviu como base para compreender melhor a utilização do JavaScript no desenvolvimento Front-end.

## 👨‍💻 Autor

**Guilherme Casseb**

Estudante de programação com foco em desenvolvimento **Back-end, APIs e automação**, utilizando projetos práticos para desenvolver e consolidar conhecimentos em programação.

---

⭐ Projeto desenvolvido para fins de **estudo e prática de JavaScript**.
