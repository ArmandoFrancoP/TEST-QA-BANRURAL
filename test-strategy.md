HALLAZGOS PRUEBAS SITIO WEB:

* Input:
    permite ingresar letras, caracteres especiales, espacios, números decimales, nÚmeros menores a 1 y  mayores a 100

* botÓn:
    Se presiona y no realiza ninguna acción

* alertas:
    No muestra las alertas

* mensajes: 
    No muestra los mensajes indicados al ingresar un número


****************************************************************************************************************************************

ERRORES ENCONTRADOS Y SUS SOlUCIONES

* Error: variable "ATTEMPS" se encuentra con valor de 5.
  Solución: se modificó a 10

* Error: Lógica invertida, indica que el usuario perdió cuando el número ingresado es el mismo que en número aleatorio, al igual que cuando los números son distintos   indica que el usuario Adivino el número correcto 
  Solución: se intercambiaron los mensajes

* Error: Método addEventListener() se encuentra mas escrito "addeventListener", por ese motivo no encontraba el intup gessSubmit
  Solución se escribió correctamente

* Error: La expresión "Math.random() * 10" devuelve un número decimal entre 0 y 10 (no se incluye el número 10), por lo tanto no cumple su función
  Solución:
    1 - se cambió el número 10 por el 100 = "Math.random() * 100"
    2 - luego se añadió la función Math.floor que redondea hacia bajo el número decimal del resultado de "Math.random() * 100" = "Math.floor(Math.random() * 100)"
    3 - La expresión "Math.floor(Math.random() * 100)" solo nos devuelve resultados entre 0 y 99, para solucionar esto, se añadió un + 1 al final de la expresión para asegurar que los rangos sean entre 1 y 100  =  "Math.floor(Math.random() * 100) + 1"

* Error:  const lowOrHi = document.querySelector('lowOrHi') busca la etiqueta lowOrhi que no existe
  Solución: se modificó para que busque la clase '.lowOrHi'


* Error: Se podía ingresar cualquier tipo de carácter y los tomaba como intentos validos
  Solución:  Se agregó la siguiente validación:

            if (!Number.isInteger(Number(userGuess)) || userGuess < 1 || userGuess > 100) { // valida el número ingresado
            alert("Por favor, ingresa un número entero entre 1 y 100.");  / muestra la alerta
            guessField.value = '';  // limpia el input
            guessField.focus();    // deja el cursor sobre el input
            return;
            }


****************************************************************************************************************************************

PLAN DE PRUEBAS

Casos de Prueba – Proyecto “Adivina tu número”

* Prueba 1: Ingreso de número válido
Objetivo: Verificar que el juego muestra el mensaje de éxito cuando el usuario adivina el número.

Entradas: Número exacto a adivinar.

Pasos:
    - Ingresar número
    - Presionar botón "Ingresar el número aleatorio"
    - Repetir hasta adivinar el número

Resultado esperado:
Se muestra el mensaje en color verde:
"Felicitaciones! adivinaste el número!"
El juego se desactiva y aparece el botón para reiniciar.

Resultado:  Exitoso/Fallido


* Prueba 2: Ingreso de número incorrecto
Objetivo: Verificar el comportamiento cuando el usuario se equivoca.

Entradas: Número incorrecto.

Pasos:
    - Ingresar número
    - Presionar botón "Ingresar el número aleatorio"

Resultado esperado:
Se muestra el mensaje "Incorrecto! El número es mayor!" o "Incorrecto! El número es menor!" en color negro.

Resultado:  Exitoso/Fallido


* Prueba 3: Fallo tras 10 intentos
Objetivo: Verificar que el juego termina después de 10 intentos incorrectos.

Entradas: 10 números incorrectos.

Pasos:
    - Ingresar número
    - Presionar botón "Ingresar el número aleatorio"
    - * Repetir 10 veces

Resultado esperado:
Se muestra el mensaje en color rojo: "!!!Pérdistes!!!"
El juego se desactiva y aparece el botón para reiniciar.

Resultado:  Exitoso/Fallido


* Prueba 4: Ingreso de texto o caracteres no válidos
Objetivo: Verificar que el sistema bloquea entradas que no sean números enteros.

Entradas: "rgd", "1.5", "#", ""

Pasos:
    - Ingresar caracteres indicados
    - Presionar botón "Ingresar el número aleatorio"


Resultado esperado:
Aparece una alerta: "Por favor, ingresa un número entero entre 1 y 100."
No se cuenta como intento.

Resultado:  Exitoso/Fallido


* Prueba 5: Ingreso de número fuera de rango
Objetivo: Verificar que no se aceptan números fuera del rango 1–100.

Entradas: 0, -5, 150, 999

Pasos:
    - Ingresar números indicados
    - Presionar botón "Ingresar el número aleatorio"

Resultado esperado:
Aparece una alerta: "Por favor, ingresa un número entero entre 1 y 100."
No se cuenta como intento.

Resultado:  Exitoso/Fallido


* Prueba 6: Reiniciar el juego
Objetivo: Verificar que el juego se reinicia correctamente al presionar el botón "Comienza un nuevo juego".

Pasos:
Jugar hasta adivinar o perder.
Presionar el botón para reiniciar.
Resultado esperado:
Se limpian los campos.
Se genera un nuevo número aleatorio.
Se pueden ingresar nuevos intentos.
Resultado:  Exitoso/Fallido


* Prueba 7: Registro visual de intentos anteriores
Objetivo: Verificar que los números ingresados anteriormente se muestran correctamente.

Acciones: Ingresar varios números.

Pasos:
    - Ingresar número
    - Presionar botón "Ingresar el número aleatorio"
    - Visualizar número ingresado

Resultado esperado:
Se muestra el historial:
"Número aleatorio anterior: 1 55 8..."

Resultado:  Exitoso/Fallido