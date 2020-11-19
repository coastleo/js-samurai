# Javascript Samurai

![enter image description here](https://media.giphy.com/media/W30tviZ52FbdEbKnlb/giphy.gif)

Este repositório tem o objetivo de trazer habilidades para que você possa massacrar qualquer problema  usando Javascript, esta que é a linguagem mais hypada no momento. Podemos responsabilizar a gigante e maravilhosa comunidade por este feito, uma vez que o JS contém features (nativas ou construidas pela própria comunidade) para o uso desta ferramenta para mil e uma utilidades.

## Considerações inciais
Este repositório não tem o objetivo de introduzir conceitos de lógica de programação ou abrir um conceito histórico e evolutivo desta linguagem maravilhosa. Então se você está dando os primeiros passos no fantástico (e sadomasoquista risos) universo da programação, deixarei logo em seguida uma lista de conteúdos iniciais interessantes.

 - [História do Javascript by FireShip](https://fireship.io/courses/javascript/intro-history/)
 - [Lógica de programação by 10 minutes Tech](https://www.youtube.com/watch?v=9zOo4JkZgSI)

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
null
Null
NULL
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

#### Operadores
Os operadores são representados por símbolos matemáticos, que tem o poder de produzir algum resultado baseado em dois ou mais valores (ou variáveis). 

|Operador| Utilidade |  Simbolos|   Exemplo  |
|--|--|--|--|
| **Adição** | Usado para somar dois números ou juntar duas strings.  | `+` | `6 + 9`  ou `"Java" + "Script"` |
|**Subtração, multiplição, divisão**|Fazem exatamente o que você espera que eles façam na matemática básica.|`-`, `*`, `/`|`9 - 3`, `9 * 3` , `9 / 3`|
| **Atribuição** | Ela escreve um valor em uma variável. | `=` | `let variavel = "valor"` |
| **Operador de igualdade** | Faz um teste para ver se dois valores são iguais, retornando um resultado true/false (booleano). | `===` | `7 === 6 // false` `6 === 6 // true` |
| **Negação, não igual** | Retorna o valor lógico oposto do sinal; transforma um true em um false, etc. Quando usado junto com o operador de igualdade, o operador de negação testa se os valores são diferentes. |`!`, `!==`  | `!(7 === 6) // true` `6 !== 6 // false`  |

> A negação resulta o valor contrário do boolean do operador de igualde, ou seja, se o valor do operador de igualde retorna true, a negação será false e vice versa. Já o Não igual é o contrário do valor de operação de igualde: `let variavelA`NÃO é igual a `let variavelB`

#### Conversão de tipos de Dados
Em expressões envolvendo valores numérico e string com o operador +, JavaScript converte valores numérico para strings. Por exemplo:
```js
x = "A resposta é " + 42 // "A resposta é 42"
y = 42 + " é a resposta" // "42 é a resposta"
```
Nas declarações envolvendo outros operadores, JavaScript não converte valores numérico para strings. Por exemplo:
```js
"37" - 7 // 30
"37" + 7 // "377" 
```
Já para converter um valor de String para númerico existem duas possibilidades, transforma-lo em numero inteiro ou decimal. Outro método para que isso aconteça é colocar o operador `+` na frente de um valor de String.
```js
parseInt() // converte para inteiro
parseFloat() // converte para decimal
"1.1" + "1.1" = "1.11.1"
(+"1.1") + (+"1.1") = 2.2   
/* Os parênteses foram usados para deixar mais legível o código, 
ele não é requirido.
*/
```

### Strings 
Como visto anteriormente, strings são uma tipagem de dado na qual o valor sempre é textual. No JavaScript existem alguns métodos para a manipulação deste tipo de dados especíificos.

#### length
Este método é utilizado quando é necessário saber a quandidade de caractetes e espaços em branco.

```js
let string = 'Aprendendo Javascript'
string.length // 21
```

#### toUpperCase e toLowerCase
Para transformar toda a sentença em letras mínusculas, é necessário usar o método toLowerCase, já para transforma-lo em maiusculo usamos o toUpperCase

```js
string.toLowerCase // aprendendo javascript
string.toUpperCase // APRENDENDO JAVASCRIPT
```

#### indexOf
Para encontrar o index, ou seja, encontrar qual é o número relativo a posição de terminado conjunto de caracteres, usamos o indexOf.

```js
string.indexOf('Javascript') // 11
```
> Caso seja informado algum cojunto ou caracter que existe em mais de uma posição, é retornado apenas a primeira vez que ele aparece no texto


#### replace
Este método tem o propósito de substituir determinado conjunto de caracteres A encontrado no texto em um conjunto B.

```js
let stringReplaced = string.replace('Javascript', 'Typescript')
console.log(stringReplaced) // Aprendendo Typescript
```

#### slice
Para recortar um pedaço da string, é usado o método slice, no qual retira o texto a partir de um index inicial e final informado.
```js
let linguagem = string.slice(11, 21) // Javascript
```
#### trim
O método trim serve para retirar os espaços em branco no ínicio ou no final da string. Desta vez não é necessário informar nada como parametro.

```js
let stringTrim = '      Aprendendo Javascript              '
stringTrim.tim() // Aprendendo Javascript
```
