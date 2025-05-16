Bugs encontrados en sitio web:

Input:
permite ingresar letras, caracteres especiales y números mayores a 100

boton:
se presiona y no hace nada

alertas:
No muestra las alertas

mensajes: 
No muestra los mensajes indicados al ingresar un número


Bugs encontrados en codigo:

* variable "ATTEMPS" se encuentra en 5: solución se modifico a 10

* Logica invertida, indica que el usuario perdió cuando el número ingresado es el mismo que en número aleatorio, al igual que cuando los números son distintos indica que el usuario Adivino el número correcto --  Solución se intercambiaron los mensajes

* Método addEventListener() se encuentra mas escrito "addeventListener", por ese motivo no encontraba el intup gessSubmit: Solución se escibio correctamente

* La expresión "Math.random() * 10" devuelve un número decimal entre 0 y 10 (no se incluye el número 10), por lo tanto no cumple su función -- solución 
1 - se cambio el número 10 por el 100 = "Math.random() * 100"
2 - luego se añadio la función Math.floor que redondea hacia bajo el número decimal del resultado de "Math.random() * 100" = "Math.floor(Math.random() * 100)"
3 - La expresión "Math.floor(Math.random() * 100)" solo nos devuelve resultados entre 0 y 99, para solucionar esto, se añadio un + 1 al final de la expresión para asegurar que los rangos sean entre 1 y 100  =  "Math.floor(Math.random() * 100) + 1"




const lowOrHi = document.querySelector('lowOrHi') busca la etiqueta lowOrhi que no existe, se modifico para que busque la clase '.lowOrHi'

con esto se soluciono lo siguiente:

1 - input .guessField se limpia al presionar boton de "Ingresar número aleatorio"
