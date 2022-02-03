# Desafio da semana #4

```js
/*
Declare uma variável chamada `isTruthy`, e atribua a ela uma função que recebe
um único parâmetro como argumento. Essa função deve retornar `true` se o
equivalente booleano para o valor passado no argumento for `true`, ou `false`
para o contrário.
*/
var isTruthy = function(a) {
  if ((a) == true) {
    return true
  } else {
    return false;
  }
}

/* nao peguei o sentido do ternario do if
var isTruthy = function(a) ((a) == true) ?     return true   :     return false  ;


function isTruthy (a) {
 (a) = true ? true : false; 
}
*/ 


// Invoque a função criada acima, passando todos os tipos de valores `falsy`.

IsTruthy (0); // false
IsTruthy (-0); // false
IsTruthy (false); // false
IsTruthy (''); // false
IsTruthy (""); // false
IsTruthy (NaN); // false
IsTruthy (null); // false
IsTruthy (undefined); // false


/*
Invoque a função criada acima passando como parâmetro 10 valores `truthy`.
*/
IsTruthy (1); // true
IsTruthy (2); // false
IsTruthy (3); // false
IsTruthy (4); // false
IsTruthy (5); // false
IsTruthy ('aaa'); // false
IsTruthy ('0'); // false
IsTruthy (true); // true
IsTruthy ('fuck'); // false
IsTruthy ('biba'); // false



/*
Declare uma variável chamada `carro`, atribuindo à ela um objeto com as
seguintes propriedades (os valores devem ser do tipo mostrado abaixo):
- `marca` - String
- `modelo` - String
- `placa` - String
- `ano` - Number
- `cor` - String
- `quantasPortas` - Number
- `assentos` - Number - cinco por padrão
- `quantidadePessoas` - Number - zero por padrão
*/

var carro ={
marca: 'VolksWagen',
modelo: 'gol' ,
placa: 'abc1234',
ano: 2000,
cor: 'amarelo',
quantasPortas: 2,
assentos: 5,
quantidadePessoas: 5
}

/*
Crie um método chamado `mudarCor` que mude a cor do carro conforme a cor
passado por parâmetro.
*/
carro.mudarCor = function (a) {
carro.cor = (a);
}

/*
Crie um método chamado `obterCor`, que retorne a cor do carro.
*/
carro.obterCor  = function () {
return carro.cor 
}

/*
Crie um método chamado `obterModelo` que retorne o modelo do carro.
*/

carro.obterModelo = function (){
return carro.modelo 
}

/*
Crie um método chamado `obterMarca` que retorne a marca do carro.
*/
carro.obterMarca = function () {
return carro.marca
}

/*
Crie um método chamado `obterMarcaModelo`, que retorne:
"Esse carro é um [MARCA] [MODELO]"
Para retornar os valores de marca e modelo, utilize os métodos criados.
*/
 carro.obterMacaModelo = function  () {
 return 'Esse carro é um ' +carro.marca +' '+ carro.modelo ;
 }
 ou
 
 carro.obterMacaModelo = function  () {
 return 'Esse carro é um ' +carro.obterMarca() +' '+ carro.obterModelo() ;
 }

/*
Crie um método que irá adicionar pessoas no carro. Esse método terá as
seguintes características:
- Ele deverá receber por parâmetro o número de pessoas entrarão no carro. Esse
número não precisa encher o carro, você poderá acrescentar as pessoas aos
poucos.
- O método deve retornar a frase: "Já temos [X] pessoas no carro!"
- Se o carro já estiver cheio, com todos os assentos já preenchidos, o método
deve retornar a frase: "O carro já está lotado!"
- Se ainda houverem lugares no carro, mas a quantidade de pessoas passadas por
parâmetro for ultrapassar o limite de assentos do carro, então você deve
mostrar quantos assentos ainda podem ser ocupados, com a frase:
"Só cabem mais [QUANTIDADE_DE_PESSOAS_QUE_CABEM] pessoas!"
- Se couber somente mais uma pessoa, mostrar a palavra "pessoa" no retorno
citado acima, no lugar de "pessoas".
*/
carro.passageiros = 0


// se ja estiver cheio , retornar msg de cheio
// se nao estiver cheio mas for ultrapassar , msg com qnts pessoas ainda cabem 
// respeitar singular e plural
//adicionar pessoas no carro
//retornar quantas pessoas no carro

carro.adicionarPessoas = function(passageiros) {
  if (passageiros < 0) {
    return 'Ae nao , use carro.removerPessoas'
  }
  if (carro.passageiros >= carro.quantidadePessoas) {
    return 'O carro ja esta cheio!'
  }
  if (carro.passageiros + passageiros <= 0) {
    return " O cara esta a ver fantasma ja doido "
  }
  if (carro.passageiros + passageiros > carro.quantidadePessoas) {
    var qntVagasSobrando = carro.quantidadePessoas - carro.passageiros
    var textoPessoa = " pessoa "
    var textoCaber = " cabe "
    if (qntVagasSobrando > 1) {
      textoPessoa = ' pessoas '
      textoCaber = ' cabem '
    }
    // no caso passageiros é so a variavel que informei ? 
    // qntVagasSobrando e uma var so da função ?
    // textopessoa tb e so uma var da função ?
    // apos executar o codigo ambos ficam undefined ou nao tem nem criaçao?
    return "Só " + textoCaber + qntVagasSobrando + ' ' + textoPessoa + " no carro!"
    //ate aqui ele analisou a function carro.adicionarPessoas para somente se possivel adicionar fazer?

  } else {
    carro.passageiros += passageiros
    return 'ja temos ' + carro.passageiros + ' no carro!'
  }
}

carro.removerPessoas = function(passageiros) {
  if (passageiros > 0) {
    return 'Ae nao , use carro.adicionarPessoas'
  }
  if (carro.passageiros + passageiros < 0) {
    return " O cara esta a ver fantasma ja doido "
  }
  if (carro.passageiros + passageiros > 0) {
    var qntVagasSobrando = carro.quantidadePessoas - carro.passageiros
    var textoPessoa = " pessoa "
    var textoCaber = " cabe "
    if (qntVagasSobrando > 1) {
      textoPessoa = ' pessoas '
      textoCaber = ' cabem '
    }
    return "Só " + textoCaber + qntVagasSobrando + ' ' + textoPessoa + " no carro!"
    //ate aqui ele analisou a function carro.adicionarPessoas para somente se possivel adicionar fazer?

  } else {
    carro.passageiros += passageiros
    return 'ja temos ' + carro.passageiros + ' no carro!'
  }

}

/*
Agora vamos verificar algumas informações do carro. Para as respostas abaixo,
utilize sempre o formato de invocação do método (ou chamada da propriedade),
adicionando comentários _inline_ ao lado com o valor retornado, se o método
retornar algum valor.

Qual a cor atual do carro?
*/
carro.obterCor () //'amarelo'

// Mude a cor do carro para vermelho.
carro.mudarCor ('vermelho') // undefined

// E agora, qual a cor do carro?
carro.obterCor () // 'vermelho'

// Mude a cor do carro para verde musgo.
carro.mudarCor ( ' Verde Musgo' ) // undefined


// E agora, qual a cor do carro?
carro.obterCor () // ' Verde Musgo'

// Qual a marca e modelo do carro?
carro.obterMacaModelo () //'Esse carro é um VolksWagen gol'

// Adicione 2 pessoas no carro.
carro.adicionarPessoas (2) //'ja temos 3 no carro!

// Adicione mais 4 pessoas no carro.
carro.adicionarPessoas (4) //'Só  cabem 2  pessoas  no carro!'

// Faça o carro encher.
carro.adicionarPessoas (2)//'ja temos 5 no carro!'
carro.adicionarPessoas (2) //'O carro ja esta cheio!'

// Tire 4 pessoas do carro.
?

// Adicione 10 pessoas no carro.
?

// Quantas pessoas temos no carro?
?
```
