
# Reto #2 | 🏭 Ponemos en marcha la fábrica
Recuerda que antes de ver la solución debes intentar resolver el ejercicio por tu cuenta [aquí](https://adventjs.dev/es/challenges/2023/2).
Puedes enviar la solución tantas veces como quieras... por intentarlo no pierdes nada 🤷‍♂️

<details>
  <summary>📚 INSTRUCCIONES DEL EJERCICIO</summary>

En el taller de Santa, los elfos tienen una lista de regalos que desean fabricar y un conjunto limitado de materiales.
Los regalos son cadenas de texto y los materiales son caracteres. Tu tarea es escribir una función que, dada una lista de regalos y los materiales disponibles, devuelva una lista de los regalos que se pueden fabricar.
Un regalo se puede fabricar si contamos con todos los materiales necesarios para fabricarlo.

```js
const gifts = ['tren', 'oso', 'pelota']
const materials = 'tronesa'

manufacture(gifts, materials) // ["tren", "oso"]
// 'tren' SÍ porque sus letras están en 'tronesa'
// 'oso' SÍ porque sus letras están en 'tronesa'
// 'pelota' NO porque sus letras NO están en 'tronesa'

const gifts = ['juego', 'puzzle']
const materials = 'jlepuz'

manufacture(gifts, materials) // ["puzzle"]

const gifts = ['libro', 'ps5']
const materials = 'psli'

manufacture(gifts, materials) // []
````
</details>

<details>
  <summary>📕SOLUCIÓN + EXPLICACIÓN</summary>

Recuerda que no hay una unica solución.

```js
function manufacture(gifts, materials) {
  const result = [];

  for (const gift of gifts) {
    let canManufacture = true;
    
    for (const char of gift) {
      if (!materials.includes(char)) {
        canManufacture = false;
        break;
      }
    }

    if (canManufacture) {
      result.push(gift);
    }
  }

  return result;
}

```
1. Empezamos con la función `Manufracture`, que toma de referencia el número de regalos y los materiales.
2. Verificamos si el "carácter" está o no está presente
3. Luego, si `canManufacture` sigue siento `true` después de verificar, se agrega el resultado al final.
