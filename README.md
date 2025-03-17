# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Resposta: **Letra A**

O "var" permite declarar a variável fora do escopo, mas não atribui o seu valor, fazendo com que o "console.log(x)", consiga reconhecer a variável, mas não o número 5. Sendo assim, o resultado é indefinido (undefined). Já o "let" não declara a variável fora do escopo, fazendo com que o "console.log(y)", não consiga encontrar nada, dando como resultado um erro.

______
**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)


Resposta: **Letra A**

Da forma que está , qualquer valor que entrar em “a” terá como resposta "erro" pois só o “b” foi escrito de forma que a condição para ele seja ser igual a um valor. Utilizando o “ a === 0 || b ===0”, teriamos o resultado esperado que seria "Erro: número inválido" para ambas as variáveis. Sendo assim, a variável precisa ser atribuida a um valor, se não ocorrerá em erro.
______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.


Resposta: **Letra B**

O console.log chama a função “calcularPreco” a partir da variável “eletrônico”, porém o código possui uma função “break” então ele vai ler e retornar até a variável “vestuário”, pois é a última antes da função break, ou seja, o console.log irá retornar o valor da última variável antes da primeira função break  que tem o valor “200”
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24


Resposta: **Letra D**

Primeiro é definida uma variável lista chamada ‘numeros’ com os seguintes números dentro dela: let numeros = [1, 2, 3, 4, 5]. Depois, é criada uma variável resultado em que o valor dela é igual a lista de números. Mas com as seguintes modificações: mapear todos itens do número da array e multiplicar por 2, filtrar os números que são maiores que 5 e somar os números entre si para reduzir a um único valor ->
let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);
e depois tendo o valor impresso por console.log(resultado) que é igual a 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]


resposta: **letra C**

O método splice() permite modificar um array removendo elementos existentes e colocando novos no mesmo lugar, então o console.log() imprimi:  ["banana", "abacaxi", "manga", "laranja"], pois "maçã" e "uva" foram substituídos por "abacaxi" e "manga", mantendo os outros elementos do array iguais.
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Resposta: **Letra A**

A primeira afirmação está certa porque a herança em JavaScript permite que uma classe reutilize propriedades de outra classe, o que evita a duplicação de código.
A segunda afirmação também está certa, pois em JavaScript a herança é usada com a palavra-chave extends. Quando uma classe usa extends, ela herda todos os métodos e propriedades da classe pai. Como a segunda afirmação explica como a herança funciona, ela justifica a primeira afirmação. 
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.


Resposta: **Letra A**

A primeira afirmação está certa porque a classe Funcionario herda da classe Pessoa através do extends. Como as variaveis nome e idade são definidos no constructor de Pessoa, a subclasse Funcionario tem acesso a elas através de this.
A segunda afirmação também esta certa, pois a função apresentar() da classe Funcionario sobrescreve a função apresentar() da classe Pessoa, mas antes de imprimir seu próprio código, ele sobrescreve super.apresentar(), fazendo a classe pai ser executada antes de adicionar a nova funcionalidade, que é exibir o salário do funcionário.
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.


Resposta: **letra B**

A asserção é verdadeira, pois os objetos de diferentes tipos podem responder à mesma chamada da função de formas diferentes. Em JavaScript, isso acontece quando uma subclasse sobrescreve uma função da classe pai ou quando diferentes objetos possuem funções com o mesmo nome, mas objetivos diferentes.

A razão é falsa, pois se definirmos várias funções com o mesmo nome dentro de uma mesma classe, só a última definida será considerada, sobrescrevendo as anteriores. O polimorfismo em JavaScript é implementado por meio da sobrescrita de funções, e não por sobrecarga.
______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));

```

**Resolução**:
```javascript
function somaArray(numeros) {
    let soma = 0; // Correção: Variável soma precisa ser atribuida a um valor para não gerar erro na soma

    // Correçãoo: Adicionada a palavra-chave "let" para declarar "i", para ser definido corretamente como uma variável 
    for (let i = 0; i < numeros.length; i++) { // Correção: para variáveis com valores em numero se é usado método length e não size
        soma += 2 * numeros[i]; // Correção: Agora soma os valores em vez de iguala-los.
    }
    return soma;
}

console.log(somaArray([1, 2, 3, 4])); // valor impresso: 20

```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

Resposta:
```javascript
// Classe base Produto
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    // Método para calcular um desconto fixo de 10%
    calcularDesconto() {
        return this.preco * 0.9; // Aplica 10% de desconto
    }
}

// Classe Livro herdando de Produto
class Livro extends Produto {
    constructor(nome, preco, autor) {
        super(nome, preco); // Chama o construtor da classe Produto
        this.autor = autor;
    }

    // Sobrescrita do método calcularDesconto para aplicar 20% de desconto
    calcularDesconto() {
        return this.preco * 0.8; // Aplica 20% de desconto
    }
}

// Criando instâncias das classes
const produtoGenerico = new Produto("Smartphone", 1000);
console.log(`Preço do Produto com desconto: R$ ${produtoGenerico.calcularDesconto()}`);

const livro = new Livro("JavaScript Avançado", 150, "João Silva");
console.log(`Preço do Livro com desconto: R$ ${livro.calcularDesconto()}`);

```
Nesse contexto, a classe Livro herda da classe Produto, o que significa que a classe Livro pode acessar as variáveis nome e preco, bem como a função calcularDesconto(), definidos na classe Produto. A herança permite que a classe Livro reutilize e modifique o comportamento de funções sem precisar escrever todo o código novamente.
A modificação do método foi implentada utilizando a sobrescrita da função calcularDesconto da classe pai, mantendo a funcionalidade da função porém com objetivos diferentes, dependendo do tipo de produto.
