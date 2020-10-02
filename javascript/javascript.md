## Arrays

### indexOf()

A função desse método é retornar o índice do primeiro elemento que corresponder ao valor de entrada.
Se nada for encontrado será retornado -1.

*Sintaxe:*
O método aceita até dois argumentos sendo o primeiro obrigatório e o segundo opcional.

```jsx
myArray.indexOf(fistArg, secondArg);
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

### findIndex()

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

### find()

Enquanto o findIndex() retorna apenas o índice do elemento que passou pelo teste, o método find() retorna o elemento em si.

*Sintaxe:*
O método aceita até 3 argumentos sendo o primeiro obrigatório e os demais opcionais.

```jsx
myArray.find(callBackFunction(element, currentIndex, array, thisArg));
```

Veja mais detalhes sobre os argumentos na [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

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

