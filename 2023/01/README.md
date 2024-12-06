# Reto #1 | 🎁 ¡Primer regalo repartido!
Recuerda que antes de ver la solución debes intentar resolver el ejercicio por tu cuenta [aquí](https://adventjs.dev/es/challenges/2024/1).
Puedes enviar la solución tantas veces como quieras... por intentarlo no pierdes nada 🤷‍♂️

<details>
  <summary>📚 INSTRUCCIONES DEL EJERCICIO</summary>

Santa Claus 🎅 ha recibido una lista de números mágicos que representan regalos 🎁, pero algunos de ellos están duplicados y deben ser eliminados para evitar confusiones. Además, los regalos deben ser ordenados en orden ascendente antes de entregárselos a los elfos.

Tu tarea es escribir una función que reciba una lista de números enteros (que pueden incluir duplicados) y devuelva una nueva lista sin duplicados, ordenada en orden ascendente.

```js
const gifts1 = [3, 1, 2, 3, 4, 2, 5]
const preparedGifts1 = prepareGifts(gifts1)
console.log(preparedGifts1) // [1, 2, 3, 4, 5]

const gifts2 = [6, 5, 5, 5, 5]
const preparedGifts2 = prepareGifts(gifts2)
console.log(preparedGifts2) // [5, 6]

const gifts3 = []
const preparedGifts3 = prepareGifts(gifts3)
console.log(preparedGifts3) // []
// No hay regalos, la lista queda vacía
````
</details>

<details>
  <summary>📕SOLUCIÓN + EXPLICACIÓN</summary>

- **MI SOLUCIÓN:**
```js
/**
 * @param {number[]} gifts - The array of gifts to prepare
 * @returns {number[]} An array with the prepared gifts
 */
function prepareGifts(gifts) {
  const tests = [
    { input: [3, 1, 2, 3, 4, 2, 5], expected: [1, 2, 3, 4, 5] },
    { input: [6, 5, 5, 5, 5], expected: [5, 6] },
    { input: [], expected: [] }
  ];

  tests.forEach(test => {
    const result = [...new Set(test.input)].sort((a, b) => a - b);
  });

  return [...new Set(gifts)].sort((a, b) => a - b);
}

```
1. Utilizamos `set` para eliminar los duplicados
2. (spread operator) para convertir un Set a un array
3. `sort()` para ordenar los valores numéricamente:
4. Por último, un `return` para devolver el resultado final.


3/5 estrellas <br>
1944 ops/s <br>
Complegidad cognitiva 4
- **EXPLICACIÓN DE MIDU:** (en el stream)
</details>



