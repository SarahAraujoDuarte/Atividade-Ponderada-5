# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```

let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro -> A execução do código não será possível pois na primeira linha,o var x = 5 está definida após o console.log(x), gerando undefined após a execução. O let por ser definido em blocos e segue a leitura de apenas o que está definido após e/ou a partir dele, assim, ao executar o código, o comando console.log(y) não consegue encontrar o let y = 10 gerando uma mensagem de erro. 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0) -> A melhor solução seria adicionar '===' ao 'a' pois o mesmo não foi definido corretamente de forma que o código possa seguir com a comparação dos valores informados para dar o retorno correto no momento da execução. 

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

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

b) O código imprime 200. -> O código foi desenvolvido para imprimir o valor de "eletrônico" porém como não foi iserido o 'break' após 'preco', foi realizada a leitura e impresso o valor do próximo elemento, no caso "vestuário". 

c) O código imprime 50.

d) O código gera um erro.

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

d) 24 -> A saída do código é '24' pois 'numeros.map(x => x * 2)' realiza a multiplicação de todos os números por dois. O comando seguinte, filtra os resultados de todos que forem maiores que 5, e o comano final 'reduce((a, b) => a + b, 0);' fica responsável por seguir com a soma dos elementos separados anteriormente. Por fim, 'console.log(resultado)' realiza a impressão do valor final. 
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"] -> O comando 'lista.splice' no código apresentado está sendo resposável pela substituição dos termos "maçã" e "uva" por "abacaxi" e "manga". Resultando na responsta selecionada. 

d) ["banana", "maçã", "uva", "abacaxi", "manga"]
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira. -> As duas afirmações estão corretas pois conforme indicado nas afirmações, utilizamos a herança para compartilhar métodos e propriedades entre classes em JavaScript e a forma como realizamos essa implementação é a partir do 'extends'

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.
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

a) I e II são verdadeiras. -> As afirmações selecionadas estão corretas pois, conforme indicado no código a classe 'Funcionario' está herdando de 'Pessoa' podendo assim ter acesso aos atributos inclusos anteriormente sendo nome e idade. Já a segunda afimação está correta pois o 'super' define a classe posterior como pai. 

A afirmação III está incorreta em JavaScript é possível implementar uma herança de forma que o código seja funcional, pois o mesmo suporta tal ação.  

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa. -  A asserção está correta porque ao implementar o polimorfismo conseguimos com que objetos distintos respondam a mesma mensagem de diferentes formas. Já o conceito apresentado em razão é falso pois JavaScript não suporta o método de sobrecarga. 

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {
//A variável soma não foi definida, sendo necessária ser implementada como: 
    let soma = 0;

    for (i = 0; i < numeros.size; i++) { //O correto é: let i = 0; Assim, evitamos que i seja tratado como uma variável global. Size está incorreto para a definição do tamanho da variável, a propriedade correta nesse caso seria: .length 
        soma = 2*numeros[i]; //A forma mais correta de seguir com a soma na formula seria definindo a da seguinte forma: soma += 2* numeros [];
    }
    return soma; 
}
console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript

class Produto {
    constructor(nome, preco) {
      this.nome = nome;
      this.preco = preco;
    }
  
    calcularDesconto() {
       return this.preco * 0.90;
    }
  }
  //Nesse contexto, a herança está sendo utilizada no livro definindo-o como uma variação do produto. Assim funcionando de forma que está adicionndo na classe os mesmos atributos, mas sobrescrevendo o método para o novo valor do desconto. 

  class Livro extends Produto {
    constructor(nome, preco) {
      super(nome, preco);
      this.preco = preco;
    }
  
    calcularDesconto() {
        return this.preco * 0.80;
    }
  }

  let produto = new Produto("Livro: Coisas Obvias Sobre o Amor - Elayne Baeta", 70);
  console.log(`Preço com desconto (Produto): R$ ${produto.calcularDesconto()}`); 

  let livro = new Livro("", 70);
  console.log(`Preço com desconto (Livro): R$ ${livro.calcularDesconto()}`)