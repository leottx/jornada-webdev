# Arrays

## push()

O método push() insere um ou mais elementos ao FINAL de um array e retorna o novo tamanho do mesmo.

*Sintaxe:*
```jsx
myArray.push(newValue);
```

*Exemplo:*
```jsx
let otherArray = [12, 7, 9, 0], myArray = [3, 2, 56], count = myArray.push(...otherArray);

console.log(count);
// 7

console.log(myArray);
// [3, 2, 56, 12, 7, 9, 0]
```

## pop()
Ao contrário do metódo push(), o pop() remove e retorna o ÚLTIMO elemento de um array.

*Sintaxe:*
```jsx
myArray.pop();
```

*Exemplo:*
```jsx
let myArray = [[12, 3, 0], [-90, 4, 32], [25, 30, -5]];

console.log(myArray.pop());
// [25, 30, -5];
```

## shift()
O metódo shift() executa o comportamento oposto do método pop(), ou seja, remove e retorna o PRIMEIRO elemento de um array.

*Sintaxe:*
```jsx
myArray.shift();
```

*Exemplo:*
```jsx
let myArray = [[12, 3, 0], [-90, 4, 32], [25, 30, -5]];

console.log(myArray.shift());
// [12, 3, 0];
```

## unshift()
O metódo unshift() executa o comportamento oposto do método push(), ou seja, insere um ou mais elementos no ÍNICIO do array e retorna o tamanho do mesmo.

*Sintaxe:*
```jsx
myArray.unshift(newValue);
```

*Exemplo:*
```jsx
let otherArray = [12, 7, 9, 0], myArray = [3, 2, 56], count = myArray.unshift(...otherArray);

console.log(count);
// 7

console.log(myArray);
// [12, 7, 9, 0, 3, 2, 56]
```

## splice()
Diferente de todos os métodos anteriores que apenas possibilitavam inserir ou remover elementos do ínicio ou fim do array, o método splice() possibilita a manipulação dos elementos a partir de qualquer índice. O comportamento consiste em alterar o conteúdo do array original e retornar um novo array com o valores eventualmente removidos.

*Sintaxe:*
```jsx
myArray.splice(startIndex, removeAmount, newValue1, newValue2, ...);
```
O primeiro argumento é o único obrigatório e específica a partir de qual índice as mudanças no array devem acontecer. Já o segundo argumento determina quantos elementos serão removidos a partir de tal índice. Por último pode-se definir um ou mais argumentos que serão integrados a lista de elementos a partir do índice especificado pelo primeiro parâmetro.

*Exemplo:*
```jsx
let malePetNames = ['Bob', 'Charlie', 'Lili', 'Bella'];

let femalePetNames = malePetNames.splice(2, 2, 'Toby', 'Pluto');

console.log(malePetNames);
// ['Bob', 'Charlie', 'Toby', 'Pluto']

console.log(femalePetNames);
// ['Lili', 'Bella']
```

## indexOf()

A função desse método é retornar o índice do primeiro elemento que corresponder ao valor de entrada.
Se nada for encontrado será retornado -1.

*Sintaxe:*
O método aceita até dois argumentos sendo o primeiro obrigatório e o segundo opcional.

```jsx
myArray.indexOf(valueToFind, fromIndex);
```
O primeiro argumento corresponde ao valor que deseja-se buscar dentro do array, já o segundo dita a partir de qual índice a busca será iniciada.
Caso nenhum valor seja atribuido ao segundo parâmetro, o valor padrão é 0.

*Exemplo com apenas um argumento:*
```jsx
const countries = [`Brazil`, `Italy`, `Lebanon`, `China`];

let countryIndex = countries.indexOf(`Lebanon`);

console.log(countryIndex);
// 2
```
*Exemplo com dois argumentos:*
```jsx
const years = [1987, 1833, 1245, 2020, 1833];

console.log(years.indexOf(1833, 2));
// 1
```

## findIndex()

Embora analisando os nomes desses métodos possa-se presumir não haver diferença entre ambos, ela existe.

O findeIndex() é para situações em que deseja-se testar uma condição para cada elemento do array. O primeiro que passar, ou seja, produzir o valor booleano *true*, terá a respectiva posição retornada pelo método.

*Exemplo:*
```jsx
const users = [{
    fname: `Ana`,
    lname: `Rodrigues`,
    age: 18
}, {
    fname: `Jonas`,
    lname: `Silveira`,
    age: 45
}, {
    fname: `Gabriela`,
    lname: `Andrade`,
    age: 33
}];

console.log(users.findIndex((user) => user.fname.toLowerCase() === 'gabriela'));
// 2
```

## find()

Enquanto o findIndex() retorna apenas o índice do elemento que passou pelo teste, o método find() retorna o elemento em si.

*Sintaxe:*
O método aceita até 2 argumentos sendo o primeiro obrigatório e o segundo opcional.

```jsx
myArray.find(callBackFunction(element, currentIndex, array), thisArg);
```

Veja mais detalhes sobre os argumentos na [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

*Exemplo:*
```jsx
const cityNames = [`Curitiba`, `Fortaleza`, `Manaus`, `Goiania`];

let city = function(cityNames, size) {
    return cityNames.find(function(city) {
        return city.toLowerCase().length > size;
    });
}
    
console.log(city(cityNames, 8));
// Fortaleza
```

## includes()

O método includes() é útil para situações em que é necessário verificar se dentro de um array existe um determinado valor. Assim que a primeira ocorrência do dado passado como argumento ocorrer, o valor booleano *true* é retornado. Caso nada seja localizado, o retorno será *false*.

*Sintaxe:*
```jsx
myArray.includes(valueToFind, fromIndex);
```
O primeiro parâmetro é obrigatório e corresponde ao valor que deseja-se buscar dentro do array, já o segundo é opcional e determina a partir de qual indíce a busca deve ser iniciada.
Se apenas o primeiro parâmetro receber um valor, o segundo adotará 0 por padrão.

*Exemplo com apenas 1 argumento:*
```jsx
const numbers = [12, 24, 3, 52, 6, 4];

console.log(numbers.includes(3));
// true
```

*Exemplo com 2 argumentos:*

```jsx
const numbers = [12, 24, 3, 52, 6, 4];

console.log(numbers.includes(3, 3));
// false
```

## filter()

Diferentemente dos métodos anteriores, o filter() possibilita testar uma condição para cada elemento de um array e obter como retorno um novo array contendo apenas os valores que passaram, ou seja, produziram *true*.

*Sintaxe:*
```jsx
let newArray = myArray.filter(callBackFunction(element, currentIndex, array), thisArg);
```
Assim como o método find(), o filter() possui dois parâmetros, sendo o primeiro obrigatório e o segundo opcional.
O primeiro argumento consiste em um função callBack responsável por testar uma condição para cada elemento do array.
Essa função possui três parâmetros. O primeiro é o valor que deseja-se buscar dentro do array e é o único obrigatório.

Veja mais detalhes sobre cada parâmetro na [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

*Exemplo:*
```jsx
const myPasswords = [`asl29@`, `1slp0`, `1234`, `spalwo%$`];

// Checando quais senhas são válidas. Apenas as que possuirem ao menos 6 caracteres deverão ser aprovadas.
const validPasswords = myPasswords.filter(function(password) {
    return password.length >= 6;
})

console.log(validPasswords);
// ['asl29@', 'spalwo%$']
```

## sort()

O método sort() tem por comportamento padrão a reordenação crescente dos elementos de um array e o retorno do mesmo ordenado. Vale mencionar que a reordenação é crescente e de acordo com o valor unicode de cada elemento.

Veja mais sobre o que são [Unicodes](https://en.wikipedia.org/wiki/List_of_Unicode_characters)

*Sintaxe:*
```jsx
ley newArray = myArray.sort([callBackFunction]);
```
O método sort() aceita um parâmetro opcional que é uma função para especificar alguma outra regra de ordenação. Se omitido, será adotado o padrão de ordenamento crescente de acordo com a pontução unicode de cada elemento.

*Exemplo sem o parâmetro:*
```jsx
const names = ['Leonardo', 'Ana', 'Amora', 'Lucas'];

console.log(names.sort());
// ['Amora', 'Ana', 'Leonardo', 'Lucas'];
```
*Exemplo com o parâmetro:*
```jsx
/* Reoordene a lista de tarefas. Todas as obrigações que já foram feitas,
ou seja, cuja propriedade status possui valor true, devem ser dispostas
ao final da lista e as que ainda não foram cumpridas no topo.*/

let todos = [{
    description: 'Clean my bedroom',
    status: true
}, {
    description: 'Buy cat food',
    status: false
}, {
    description: 'Exercise',
    status: true 
}, {
    description: 'Study for exams',
    status: false
}];

const sortTodos = function(todos) {
    todos.sort((a, b) => {
        if (!a.status && b.status) {
            return -1;
        } else if (a.status && !b.status) {
            return 1;
        } else {
            return 0;
        }
    });
}

sortTodos(todos);

console.log(todos);

/* 
[
  { description: 'Buy cat food', status: false },
  { description: 'Study for exams', status: false },
  { description: 'Clean my bedroom', status: true },
  { description: 'Exercise', status: true }
]
*/
```