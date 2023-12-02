# Reto #1 | 🎁 ¡Primer regalo repartido!
Recuerda que antes de ver la solución debes intentar resolver el ejercicio por tu cuenta [aquí](https://adventjs.dev/es/challenges/2023/1).
Puedes enviar la solución tantas veces como quieras... por intentarlo no pierdes nada 🤷‍♂️

<details>
  <summary>📚 INSTRUCCIONES DEL EJERCICIO</summary>

En la fábrica de juguetes del Polo Norte, cada juguete tiene un número de identificación único.
Sin embargo, debido a un error en la máquina de juguetes, algunos números se han asignado a más de un juguete.
¡Encuentra el primer número de identificación que se ha repetido, donde la segunda ocurrencia tenga el índice más pequeño!
En otras palabras, si hay más de un número repetido, debes devolver el número cuya segunda ocurrencia aparezca primero en la lista. Si no hay números repetidos, devuelve -1.

```js
const giftIds = [2, 1, 3, 5, 3, 2]
const firstRepeatedId = findFirstRepeated(giftIds)
console.log(firstRepeatedId) // 3
// Aunque el 2 y el 3 se repiten
// el 3 aparece primero por segunda vez

const giftIds2 = [1, 2, 3, 4]
const firstRepeatedId2 = findFirstRepeated(giftIds2)
console.log(firstRepeatedId2) // -1
// Es -1 ya que no se repite ningún número

const giftIds3 = [5, 1, 5, 1]
const firstRepeatedId3 = findFirstRepeated(giftIds3)
console.log(firstRepeatedId3) //
````
</details>

<details>
  <summary>📕SOLUCIÓN + EXPLICACIÓN</summary>

Como ha exxplicado Midu en directo, esta solución es una de las más acertadas (hay más soluciones), y el resultado puede variar.

```js
function findFirstRepeated(gifts) {
  const uniqueGifts = new Set();

  for (const id of gifts) {
    if (uniqueGifts.has(id)) { return id; }
    uniqueGifts.add(id);
  }
  return -1
}
```
1. Definimos la función (findFirstRepeated), tomando el parámetro (gifts)
2. Creamos un Set para almacenar los regalos únicos que se han encontrado. (Se podría haber usado también un Map)
3. Luego creamos un bucle del tipo for ... of
4. Por último, ponemos el `return -1`, ya que es lo que devuelve si no se ha encontrado uno.
</details>

Esperad que al principio mis explicaciones puedan ser un poco simples y poco trabajadas, pero... Tengo 25 días más para trabajar y progresar. Al fin y al cabo, esto que estoy haciendo te está ayudando tanto a ti como a mi.


