# Diseño y Nuevos Medios → Clase 12 

### Miércoles 29 de mayo → PHP → Personal Home Page o Pre HTML Process.

Lo que distingue a PHP de Javascript es que el código del primero es ejecutado del lado del servidor, generando HTML y enviándolo al cliente. El cliente recibirá el resultado de ejecutar el script, aunque no se sabrá el código subyacente que era. 


#### 2. Variables

Recordemos que, en programación, una variable está formada por un espacio en el sistema de almacenaje (memoria principal del computador) y un identificador asociado a dicho espacio. Este espacio contendrá una cantidad conocida o desconocida de datos, que pueden ir variando en la medida que el programa se ejecuta (y esta es la razón del nombre).

Así como en [JavaScript](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-06#2-variables), en PHP tampoco es necesario indicar el tipo de variable con un prefijo especial. A todo tipo de variable le antecede de un símbolo monetario `$`, para luego poner la asignación, valor y fin de la instrucción.  

Una variable a la que se le asigna un único número como contenido:

`$a = 1;`

Una variable a la que se le asigna un "string" como contenido:

`$a = "uno";`

Una variable a la que se le asigna un "array" como contenido:

`$a = array("uno", "dos", "tres","cuatro");`

Por ahora, no revisaremos los objetos en PHP. Pero vamos a profundizar en los "arrays" y "arrays dentro de arrays dentro de arrays…"

Profundicemos con un ejemplo:

`$inception = array("el sueño en la van",array("el sueño en el hotel",array("el sueño en la nieve",array("el sueño en la ciudad abandonada"))))`

La información legible en `$inception` es:
```
Array
(
    [0] => el sueño en la van
    [1] => Array
        (
            [0] => el sueño en el hotel
            [1] => Array
                (
                    [0] => el sueño en la nieve
                    [1] => Array
                        (
                            [0] => el sueño en la ciudad abandonada
                        )

                )

        )

)
```
Si queremos que nos entregue, por ejemplo, el sueño más profundo (el sueño en la ciudad abandonada), tenemos que ir a por `$inception[1][1][1][0]`.

Modifiquemos el ejemplo. Podemos escribir el arreglo de inception de otra manera:

`$inception = array("primero"=>"el sueño en la van","segundo"=>"el sueño en el hotel","tercero"=>"el sueño en la nieve","cuarto"=>"el sueño en la ciudad abandonada")`

Ahora la información legible dentro de la variable es:

```
Array
(
    [primero] => el sueño en la van
    [segundo] => el sueño en el hotel
    [tercero] => el sueño en la nieve
    [cuarto] => el sueño en la ciudad abandonada
)
```

En esta caso, si queremos que nos entregue el sueño más profundo (el sueño en la ciudad abandonada), le tenemos que solicitar un `$inception["cuarto"]`.

#### 3. Funciones

Este lenguaje nos ofrece [diversas funciones](https://www.php.net/manual/en/funcref.php) que se ejecutan del lado del servidor. Con ellas podríamos:

- imprimir el resultado de una consulta `<?php echo(…)?>` o `<?php print(…)?>`
- incluir partes de unos archivos en otros `<?php include(…)?>`
- obtener la fecha del servidor `<?php date(…)?>`
- obtener [información desde formularios](https://www.php.net/manual/es/tutorial.forms.php) `<?php $_POST[…]?>` 
- detectar la página que se está vistando, obtener la IP de quien visita la página, etc. 
