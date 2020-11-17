# Javascript Samurai

![enter image description here](https://media.giphy.com/media/W30tviZ52FbdEbKnlb/giphy.gif)

Este repositório tem o objetivo de trazer habilidades para que você possa massacrar qualquer problema  usando Javascript, esta que é a linguagem mais hypada no momento. Podemos responsabilizar a gigante e maravilhosa comunidade por este feito, uma vez que o JS contém features (nativas ou construidas pela própria comunidade) para o uso desta ferramenta para mil e uma utilidades.

## Considerações inciais
Este repositório não tem o objetivo de introduzir conceitos de lógica de programação ou abrir um conceito histórico e evolutivo desta linguagem maravilhosa. Então se você está dando os primeiros passos no fantástico (e sadomasoquista risos) universo da programação, deixarei logo em seguida uma lista de conteúdos iniciais interessantes.

 - História do Javascript by FireShip
 - Lógica de programação by XXX

## Feijão com Arroz

### Variavel
Vamos iniciar com o conceito mais básico possível sobre códigos ao meu ver: A variável.  Alegoricamente, a variável é uma gaveta, onde se guarda informação. Até conseguimos deixar uma gaveta vazia, mas qual seria o propósito de construir uma gaveta se esta ficará vazia?
A nossa gaveta fica em um armário chamado memória interna, podendo ser acessada futuramente no código. 

> O Javascript é continuado oficialmente pela Mozilla, sendo atualizado em versões pela grupo open source EcmaScript. Sendo adicionado os modelos de variáveis let e const após o ECMAScript 6.

No Javascript existem 3 tipos de variaveis:

 - `var` nasceu juntamente com o JS, hoje em dia não é recomendado o uso.
 - `let` este tipo de variável é válida apenas no escopo do bloco no qual foi declarada (por exemplo em uma função ou em um loop), sendo possível ser subscrita
 - `const` especificamente este modelo de variável é na verdade uma "constante", sendo possível apenas ler ela após a escrita, não podendo ser subscrita.

### Exemplos de variáveis
Apenas por motivos cientifico, vamos dar uma olhada como é o funcionamento do modelo `var`

```js
if (true) {
  var x = 5
}
console.log(x)  // 5
```
Como pode ser visto, a variavel foi declarada no escopo do loop, e mesmo fora deste escopo é possível printar o seu valor.

Com o modelo `let` é diferente, onde é impossível acessar uma varíavel que não está no escopo no qual você se encontra:
```js
if (true) {
	let y = 5
}
console.log(y) // ReferenceError: y não está definido	
```
O modelo `const` como já informado tem o poder de declarar apenas uma vez o valor desta variável, e após isso ela permite apenas a leitura.
```js
const lanche = 'Burrito'
console.log(lanche) // Burrito

lanche = 'Big Mac' // TypeError: lanche é uma constante
```
### Tipos
O Javascript moderno considera sete tipos de dados, sendo seis primitivos:

 - **Boolean:** valores binários
 ```js
 true false
```
- **null:** palavra chave que indica valor nulo, importante salientar que o JS é case-sensitive, ou seja, letras maiusculas e minusculas são diferenciadas.
```js
null // yes
Null // no
NULL // no
```
- **undefined:** quando uma variavel é declarada porém não é preenchida com nenhum valor (gaveta vazia)
```js
let nome
console.log(nome) // undefined
```
- **Number:** valores numéricos, inteiros ou decimais
```js
const inteiro = 23
const decimal = 6.663
```
- **Strings:** valores textuais, sendo declarados com aspas.
```js
const nome = 'Leonardo'
const idade = '23' 
/* 
veja que é um valor numérico, porém declarado como uma
string, isso imposibilita operações matemáticas 
com o variável
*/
```

- **Symbol**: Dados cuja as instâncias são únicas e imutáveis.
```js
const recado = 'veremos isso futuramente...' 
```

O tipo qual não é chamado de primitivo é o Objeto, que podemos definir como uma variável incpetion, pois podemos inserir variáveis dentro de outra váriavel (esta que recebe os valores é o objeto)
```js
const usuario = {
	nome: "Leonardo",
	idade: 23,
	javascript: true,
	PHP: false,
	github: "https://github.com/coastleo",
	chave: 'valor'
}

console.log(usuario) // { nome: "Leonardo",  idade: 23,  javascript: true,  PHP: false,  github: "https://github.com/coastleo" }
console.log(usuario.nome) // Leonardo
console.log(usuario['nome']) // Leonardo
```

Os objetos nos possibilitam acessar seu conteudo integralmente ou apenas uma das chaves. 
