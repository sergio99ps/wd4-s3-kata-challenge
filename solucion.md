### KATA 1 - Contador de vocales

 

```jsx
/*
Crear una función que devuelva el número de vocales 
que tiene el string que le pasemos como parámetro.

Consideramos que el string solo tiene letras minúsculas y espacios.
*/

/* 
Lo primero que haremos será crear un array de vocales y crearemos una función que reciba el string y lo recorra. En cada iteración del bucle vamos comprobando si el caracter correspondiente del string está incluido dentro del array de vocales y si es así sumaremos 1 al contador que tenemos.
*/

let contadorVocales = (frase) => {
		const listadoVocales = ["a", "e", "i", "o", "u"];
    let contador = 0; //inicializamos el contador a 0
		let fraseMinusculas = frase.toLowerCase(); //ponemos la frase en minúsculas para poder comparar bien

		// recorremos cada uno de los caracteres del array
    for (let letra of fraseMinusculas ) {
        if (listadoVocales.includes(letra)) {
            contador = contador + 1;
        }
    }

    // devolvemos el resultado
    return contador;
}

let resultado = contadorVocales('Don Pepito'); //llamamos a la función
console.log(resultado); //pintamos por pantalla
```

  

### KATA 2 - Múltiplos de 3 y de 5

  

```jsx
/*
Si enumerásemos todos los números naturales por debajo de 10 que 
fuesen múltiplos de 3 y de 5 tendríamos el siguiente listado (3, 5, 6 y 9). 
La suma de estos múltiplos sería 23.

Crea un función que devuelva la suma de todos los múltiplos de 3 y 5 del 
número que le pasemos.

En caso de que el número sea múltiplo de ambos solo habrá que contarlo 
un vez.
*/

/*
Tendremos que hacer una función, que reciba el número hasta donde queramos sacar los múltiplos de 3 o de 5. Dentro de esta función recorreremos cada uno de esos números comprobando que si son multiplos de 3 y de 5 los sumemos dentro de nuetra variable que hemos definido para tal fin. Una vez recorramos todos devolveremos la suma total.
*/

let sumadorMultiplo = (numero) => {
  let sumatorioMultiplos = 0; //inicializamos el sumatorio a 0
  //recorremos los números del 1 al 50 (numero recibido) comprobando si son múltiplos
	for(let i = 1;i <= numero; i++){
		// si son múltiplos de 3 y 5 (el resto de dividirlos da 0) lo incluimos en el sumatorio
    if(i % 3 == 0 || i % 5 == 0){
      sumatorioMultiplos = sumatorioMultiplos + i;
    }
  }
	//devolvemos el sumatorio
  return sumatorioMultiplos;
}

let resultado = sumadorMultiplo(50); //llamamos a la función
console.log(resultado); //mostramos por pantalla

```

   

### KATA 3 - Encuentra el número que aparece un número impar de veces

 

```jsx
/*
Crea una función que reciba como argumento un array de números 
y devuelva aquel que aparecen únicamente un número impar de veces.

Ejemplos: 

  [1]         → Devuelve el número 1, ya que aparece una única vez
  [3,3,5]     → Devuelve el 5, ya que aparece 1 vez.
  [2,1,1,2,2] → Devuelve 2, ya que aparece 3 veces
*/

/*
En esta ocasión tendremos que crear una función, que reciba un array de numeros. Lo primero que tenemos que hacer es ordenarlos. La clave es buscar, recorriendo el array, cuando cambiamos de número, y para eso, tendremos que ir viendo si el siguiente número respecto al que nos toca recorrer es igual o no. Si no es igual sumaremos uno a nuestro contador, si es diferente veremos que tenemos en el contador y si ese contador es impar, ya tendremos el número que se repite un número impar de veces.
*/

let comprobarImpar = (listadoNumeros) => {
  let numeroImpar; //creamos la variable donde irá el número impar que encontremos
  let contador = 1; //inizializamos el contador de números iguales a 1 con el fin de ir incrementandolo si se encuentran más numeros iguales. Empezamos en 1 porque al ir comparando con el siguiente dentro del bucle, no llegaríamos a contar el último número igual.

	
  listadoNumeros.sort(); //ordenamos el array recibido
	
	//recorremos el array.
  for (let i = 0; i < listadoNumeros.length; i++){
		// Si el contenido de esta posición es igual que el de la siguiente sumamos uno a nuestro numero de veces que se repite un número dentro del array, si no pasamos a ver si el numero de veces que se ha repetido es impar
	  if(listadoNumeros[i] === listadoNumeros[i+1]){
      contador = contador + 1;
    } else {
      if( contador % 2 !== 0 ){
          numeroImpar = listadoNumeros[i];
      }
      contador = 1;
    }
  }
  return numeroImpar;
}

let resultado = comprobarImpar([2,3,3,3,1,1,2]); //llamamos a la función
console.log(resultado); //sacamos por pantalla

```

  

### KATA 4 - Código secreto

```jsx
/*
Crea una función que reciba como parámetro un string y devuelva otro, 
remplazando las letras por su posición en el alfabeto.

Si algún caracter no se encuentra, simplemente lo ignoramos.
*/

/*
 Al igual que en el ejercicio de contar vocales, en este tendremos que crear un abecedario para poder comprobar en que posición se encentra cada letra. Lo que hacemos es recorrer el mensaje secreto y por cada caracter comprobamos la posición dentro de nuestro array de abecedario. Podríamos también haber hecho un string y comprobar la posición dentro del string.
*/

let crearCodigoSecreto = (frase) => {
	const abecedario = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','ñ','o','p','q','r','s','t','u','v','w','x','y','z']; //creamos el abecedario para comparar.
  let codigoSecreto = ''; //creamos una nueva variable que será nuestro código secreto.
	let fraseMinusculas = frase.toLowerCase(); //pasamos la frase a minusculas para que encuentre los caracteres.
	// recorremos la frase pasando caracteres a numeros al comprobar la posición en el array. Hay que tener en cuenta que la posición de los arrays empiezan en 0 por lo que tenemos que sumar uno.
	for (letra of fraseMinusculas){
		let numeroLetra = abecedario.indexOf(letra) + 1; //buscamos el número de la letra
		//si el número de letra es 0 ( -1 por no encontrar el caracter y el +1 que le sumamos) podemos cambiarla por ejemplo por un guión para indicar que es un caracter no encontrado.
		if(numeroLetra === 0){
			numeroLetra = '-';
		}
		codigoSecreto = codigoSecreto + ' ' + numeroLetra; //concatenamos a nuestro código secreto
	}
  
  return codigoSecreto;
}

let resultado = crearCodigoSecreto('Hola soy Edu'); //llamamos a la función
console.log(resultado);
```

  

### KATA 5 - Concatenar arrays

```jsx
/*
Crea una función que reciba una serie de arrays como argumentos 
y devuelva uno único ordenado.

Ejemplo: 
  Recibe: 
    ([['Cristiano', 'Messi'], ['Neymar', 'Mbappe', Benzema'], 
    ['Vinicius', 'Kane']])  
  Devuelve: 
    ['Benzema', 'Cristiano', 'Kane', 'Mbappe', 'Messi', 
    'Neymar', 'Vinicius']
*/

/*
	Tenemos una función que recibe un array que contiene arrays. Tendremos que recorrer el array padre e ir concatenando cada uno de los array que se encuentren dentro de este. Luego únicamente tendremos que ordenar el array creado.
*/

let concatenarArray = (listadoArrays) => {
  let listadoUnificado = [];
	//recorremos el array padre para concatenar los hijos
  listadoArrays.forEach( element => {
    listadoUnificado = listadoUnificado.concat(element);
  })
  return listadoUnificado.sort(); //devolvemos el nuevo array ya ordenado
}

let resultado = concatenarArray([ ['Cristiano', 'Messi'], ['Neymar', 'Mbappe', 'Benzema'] , ['Vinicius', 'Kane'] ]); //llamamos al a función
console.log(resultado);
```

 

### KATA 6 - Slice

 

```jsx
/* 
Crea una función que reciba un array de números, la posición inicial 
y final del nuevo array (opcional), y devuelva el nuevo array.

Ejemplo 1: ([1, 2, 3], 0, 1) // => [1]
Ejemplo 2: ([1, 2, 3], 1) // => [2,3]
*/ 

/*
Es un ejercicio para que comprobemos que pasa si no recibimos el último argumento de una función. Lo único que tenemos que hacer es un slice según los parámetros que reciba la función.
*/

let generarSubArray = (array, posicionInicial, posicionFinal) => {
	posicionFinal = posicionFinal || array.length; //indicamos que si la posición final no llega, que sea la del final del array.

  return array.slice(start, end); //devolvemos el corte del array.
}

let resultado = generarSubArray([1, 2, 3], 0, 1)); //llamamos a la función
console.log(resultado) 
```

 

### KATA 7 - Encuentra el número que vale lo mismo que su índice

 

```jsx
/* 
Crea una función que  reciba un array de números y 
devuelva los números que coinciden con su posición en el array.

Ejemplos:
  [1,2,5,3] → Devuelve [3] que se encuentra en la posición 3 del array
  [1,5,20,4,16,8,6] → Devuelve [6] que se encuentra en la posición 6 del array
  [10,1,20,3,16,8,10] → Devuelve [1,3] ya que ambos coinciden.
*/ 

/*
	Tendremos que recorrer el array que recibamos e ir comparando la posición con el contedido. Encaso de que coincida lo incluiremos en un array.
*/

let comprobarPosicionContenido = (array) => {
	let listadoNumerosCoincidentes = [];
	//utilizo el foreach incluyendo el índice pero también podéis usar un for normal
	array.forEach((element, index) => {
		if(element === index){
			listadoNumerosCoincidentes.push(element);
		}
	});
	//devuelvo el array de numeros coincidadentes
  return listadoNumerosCoincidentes;
}

let resultado = comprobarPosicionContenido([10,1,20,3,16,8,10]);
console.log(resultado);

```

  

### KATA 8 - Etiquetas de vehículos

 

```jsx
/* 
Tenemos una flota de vehículos y con las nuevas restricciones de 
movilidad en Madrid, nos piden que todos tengan etiqueta de contaminación.

Crea una función que reciba un array de objetos-coche y devuelva un 
nuevo array con los objetos-coche. Cada coche tendrá un nueva propiedad 
que sea etiqueta ( con valor ‘ECO’ en caso de que el coche sea híbrido y 
‘C’ en caso de que sea gasolina). 

Dentro de la flota de coches solo tenemos esas 2 opciones así que no hay 
que preocuparse por ninguna otra.

Ejemplo:
  Entrada: 
    [{id: 1, modelo: 'híbrido', matricula:'4565HLM' },
    {id: 2, modelo: 'gasolina', matricula:'5678MNL' },
    {id: 3, modelo: 'híbrido', matricula:'1111LLL' }]

  Salida:
  [{id: 1, modelo: ‘híbrido’, matricula:’4565HLM’, etiqueta:’ECO’},
  {id: 2, modelo: ‘gasolina’, matricula:’5678MNL’, etiqueta:’C’},
  {id: 3, modelo: ‘híbrido’, matricula:’1111LLL’, etiqueta:’ECO’ }].
*/ 

/*
Tendremos que recorrer el listado de objetos añadiendo la matricula validando que sea híbrido o gasolina.
*/

let coches = [{id: 1, modelo: 'híbrido', matricula:'4565HLM' },
				{id: 2, modelo: 'gasolina', matricula:'5678MNL' },
				{id: 3, modelo: 'híbrido', matricula:'1111LLL' }];

let anadirEtiqueta = (listadoCoches) => {
	let listadoCochesConEtiqueta = []; //creamos un nuevo array
  listadoCoches.forEach(element => {
		//creamos un objeto nuevo incluyendo la etiqueta (si no modificaremos el objeto global (probar a no crear un objeto nuevo, veréis que cambia el objeto coches). Veréis otras alternativas en la siguiente sesión :D )
		let cocheNuevo = {
			id: element.id,
			modelo: element.modelo,
			matricula: element.matricula,
			etiqueta: ''
		};
		//comprobamos si es gasolina o híbrido e incluimos la etiqueta
		if(element.modelo === 'gasolina'){
			cocheNuevo.etiqueta = 'C';
		} else{
			cocheNuevo.etiqueta = 'ECO';
		}
		//añadimos el objeto nuevo al array
		listadoCochesConEtiqueta.push(cocheNuevo);
	});

	return listadoCochesConEtiqueta;
}

let resultado = anadirEtiqueta(coches);
console.log(resultado);
```

 

### KATA 9 - Ordenación de un array según la propiedad

 

```jsx
/* 
Crea una función que reciba la lista de regalos de los reyes magos 
y la ordene según la propiedad elegida.

Ejemplo:		
  Entrada: 
      [ {nombre: 'Barbie', categoria: 'muñecas' }, {nombre: 'Lego', categoria:'construcción'}, {nombre: 'Fifa2023', categoria:'videojuego' }]

  Salida:
      [{nombre: ‘Barbie’, categoria: ‘muñecas’ },
      {nombre: ‘Fifa2023’, categoria:’videojuego’ }
      {nombre: ‘Lego’, categoria:’construcción’ }]
*/ 

/*
	En este ejercicio la idea es que os pegáseis un poco con el método sort.
	En la documentación (https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) podéis cotillear como trabajar con el
*/

let ordenSegunPropiedad = (listadoRegalos, propiedad) => {
	listadoRegalos.sort((a, b) => (a[propiedad] > b[propiedad]) ? 1 : -1);
  return listadoRegalos;
}

let resultado = ordenSegunPropiedad([ {nombre: 'Barbie', categoria: 'muñecas' }, {nombre: 'Lego', categoria:'construcción'}, {nombre: 'Fifa2023', categoria:'videojuego' }], 'nombre');
console.log(resultado);
```

 

### KATA 10 - Monopoli: ¿Quién tiene más dinero?

  

```jsx
/* 
Crea una función que reciba un listado de jugadores con el número de 
billetes de cada cantidad que tienen y devuelva el jugador con más dinero. 

No habrá más de un jugador que tenga el mayor número de billetes

Ejemplo:
 Entrada:
  [{nombre: 'Pedro', billetesDe5: 10, billetesDe10: 3, billetestDe50: 1 }, {nombre: 'Luis', billetesDe5: 10, billetesDe10: 1, billetestDe50: 2 }, {nombre: 'Gon', billetesDe5: 5, billetesDe10: 5, billetestDe50: 5 }]

  Salida:
    Gon
*/ 

/*
Para solucionar el problema recorremos el listado de personas. Tendremos que sacar el dinero que van teniendo. Guardaremos el primero en un objeto y lo iremos comparando con el resto para ver si tiene más o menos dinero, en caso de que tenga más dinero el siguiente, modificaremos el objeto. 
*/

let sacarPersonaConMasDinero = (jugadores) => {
	//creamos el objeto que nos servirá para guardar la persona con más dinero	
	let personaGanadora = {
				nombre: '',
				dinero: 0
	}
	//recorremos el array sacando el dinero total y comparándolo
	jugadores.forEach( jugador => {
	 //guardamos el dinero total del jugador
		let totalDinero = jugador.billetesDe5 * 5 + jugador.billetesDe10 * 10 + jugador.billetestDe50 * 50;
		//si el dinero es mayor que el que tenemos guardado en personaGanadora modificamos el objeto
		if(totalDinero > personaGanadora.dinero){
				personaGanadora.nombre = jugador.nombre;
				personaGanadora.dinero = totalDinero;
		}
	});

	return personaGanadora.nombre;

}

let resultado = sacarPersonaConMasDinero([{nombre: 'Pedro', billetesDe5: 10, billetesDe10: 3, billetestDe50: 1 }, {nombre: 'Luis', billetesDe5: 10, billetesDe10: 1, billetestDe50: 2 }, {nombre: 'Gon', billetesDe5: 5, billetesDe10: 5, billetestDe50: 5 }]);
console.log(resultado);
```

  

### KATA 11 - Mueve los 0 al final

  

```jsx
/* 
Crea una función que reciba un listado y mueva todos los 0 al final, 
manteniendo el orden del resto de elementos.

Ejemplo:
   Entrada: [1,0,true,0,'hola', 5, 30, 'a']
   Salida: [1,true,’hola’, 5, 30, ‘a’,0,0]
*/ 

/*
Tendremos que recorrer el array y creando 2 arrays complementarios, uno para guardar los ceros y otros los que nos. Ya solo tendríamos que concatenar los dos arrays con el de los ceros al final
*/

let moverCeros = (array) =>  {
	let listaOrdenada = [];
  let listaCeros = []; //guardamos los valores que nos son ceros
  let listaNoCeros = []; //guardamos los que son ceros
	//vamos recorriendo y añadiendo al array correspondiente
  array.forEach(element => {
	 if(element === 0){
		 listaCeros.push(element);
	 } else {
		listaNoCeros.push(element);
	 }
	});
  
  //concatenamos
	listaOrdenada = listaOrdenada.concat(listaNoCeros);
  listaOrdenada = listaOrdenada.concat(listaCeros);
  return listaOrdenada;
};

let resultado = moverCeros ([1,0,true,0,'hola', 5, 30, 'a']);
console.log(resultado);

```

  

### KATA 12 - Encuentra el string único

 

```jsx
/* 
Crea una función que reciba un listado de strings y devuelva 
el string diferente al resto.

Serán strings sin espacios.

Ejemplo:

 Entrada: [ 'Aa', 'aaa', 'aaaaa', 'BbBb', 'Aaaa', 'AaAaAa', 'a' ]
 Salida : 'BbBb’

 Entrada: ['abc', 'acb', 'bac', 'foo', 'bca', 'cab', 'cba’]
 Salida : 'foo’
*/ 

/* UPDATE: Para dar más info y tener más claro el anunciado, tenemos
que buscar el array que tenga caracteres diferentes. 
Me he pasado de complejidad en este sorry, que no os explote el la cabeza si no os sale, es normal */

/* Este ejercicio tiene un poco más de complejidad así que vamos por partes:
	1) Ponemos en minúsculas
	2) Convertimos en array
	3) Ordenaremos esos arrays
	4) Quitamos duplicados
	5) Buscamos el que es diferente
*/

let buscarArrayDiferente = (listado) => {
  let posicionStringDiferente = 0;
  let arrayPreparadoParaBuscarDiferente = [];
  
  listado.forEach( element => {
    let stringMinusculas = element.toLowerCase(); // 1) Ponemos en minúsculas
    let array = stringMinusculas.split('');       // 2) Convertimos en array
    array.sort(); // 3) Ordenamos
    
    // 4) Quitamos duplicados
    let arraySinDuplicados = [];
    array.forEach( caracterArray => {
      if(arraySinDuplicados.includes(caracterArray) === false){
        arraySinDuplicados.push(caracterArray);
      }
    } );
    arrayPreparadoParaBuscarDiferente.push(arraySinDuplicados.join(''));
  });
    
  // 5) Buscamos el que es diferente
  arrayPreparadoParaBuscarDiferente.forEach( (elemento,index) => {
    if(arrayPreparadoParaBuscarDiferente.indexOf(elemento) === arrayPreparadoParaBuscarDiferente.lastIndexOf(elemento)){
      posicionStringDiferente = index;
    }
  });
  
  return listado[posicionStringDiferente];
}

let resultado = buscarArrayDiferente(['abc', 'acb', 'bac', 'foo', 'bca', 'cab', 'cba']);
console.log(resultado);
```

 

### KATA 13 - Tres en raya

```jsx
/* 
Crea una función que recibiendo un resultado del tablero del 3 en raya, 
indique si algún jugador ha ganado la partida. Asumimos que recibimos 
un tablero válido

    - 0 - Hueco en blanco
    - 1 - Jugador 1
    - 2 - Jugador 2

La función devolverá:
  - -1 si nadie ha ganado todavía y el tablero tiene huecos por rellenar
  - 1 si el jugador 1 ha ganado
  - 2 si el jugador 2 ha ganado
  - 0 nadie ha ganado

Ejemplo:
  Entrada:   	
  [  [ 0, 2, 1],
     [ 0, 1, 2],
     [ 2, 1, 0] ]

  Salida: -1
*/ 

/* 
La lógica para validar el 3 en raya es la siguiente:
	- Comprobar las filas
	- Comprobar las columnas
	- Comprobar las diagonales

Recibimos un array con 3 arrays que se estructura como un tablero:
		[  [ 0, 2, 1],
		   [ 0, 1, 2],
		   [ 2, 1, 0] ]
*/

let comprobarTresEnRaya = (tablero) => {
	let ganador = -1;
	
	//aprovechamos el bucle de 3 para comprobar filas y columnas
	for(let i = 0; i < 3; i++){
		//comprobamos filas
		if(tablero[i][0] === tablero[i][1] && tablero[i][0] === tablero[i][2]  && tablero[i][1] === tablero[i][2]){
				ganador = tablero[i][0];
		}
		//comprobamos columnas
		if(tablero[0][i] === tablero[1][i] && tablero[0][i] === tablero[2][i] && tablero[1][i] === tablero[2][i]){
				ganador = tablero[0][i];
		}
	}
	//comprobamos diagonales
	if(tablero[0][0] === tablero[1][1] === tablero[2][2]){
		ganador = tablero[0][0];
	}
  
	if(tablero[0][2] === tablero[1][1] === tablero[2][0]){
		ganador = tablero[0][2];
	}
	
	//comprobamos que si el resultado es 0, ponemos -1
	if(ganador <= 0){
		ganador = -1;
	}
	return ganador;
};

let resultado = comprobarTresEnRaya([[2, 2, 2],[0, 1, 2],[2, 1, 0]]);
console.log(resultado);
```

### KATA 14 - Validador sudokus

 

```jsx
/* 
Crea una función que reciba el tablero del sudoku y devuelva true/false en función de si es válido o no:

validarSolucion([
  [5, 3, 4, 6, 7, 8, 9, 1, 2],
  [6, 7, 2, 1, 9, 5, 3, 4, 8],
  [1, 9, 8, 3, 4, 2, 5, 6, 7],
  [8, 5, 9, 7, 6, 1, 4, 2, 3],
  [4, 2, 6, 8, 5, 3, 7, 9, 1],
  [7, 1, 3, 9, 2, 4, 8, 5, 6],
  [9, 6, 1, 5, 3, 7, 2, 8, 4],
  [2, 8, 7, 4, 1, 9, 6, 3, 5],
  [3, 4, 5, 2, 8, 6, 1, 7, 9]
]); // => true
*/

/*
Este ejercicio se complica,para que podáis comparar si habéis entrado en codewars, podría ser un nivel 4 o algo similar por lo que es bastante complejo. Echar un ojo a como vamos validando filas, columnas y cajas de 3x3.
*/

// Función para validar sudoku
let validarSudoku = (board) => {
   let solucion = true;
   for (let i = 0; i < 9; i++) {
        for (let j = 0; j < 9; j++) {
            const value = board[i][j];
                if (!validarFila(board, i, j, value) || !validarColumna(board, i, j, value) | !validBox(board, i, j, value)) {
                    solucion = false;
                }
            
        }
    }
    return solucion;
};

// Función para validar fila
let validarFila = (board, row, col, value) => {
    let solucion = true;
    for (let j = 0; j < 8; j++) {
        if (j !== col) {
            if (board[row][j] === value) {
                solucion = false;
            }
        }
    }
    
    return solucion;
}

// Función para validar columna
let validarColumna = (board, row, col, value) => {
    let solucion = true;
    for (let i = 0; i < 8; i++) {
        if (i !== row) {
            if (board[i][col] === value) {
                solucion = false; 
            }
        }
    }
    
    return solucion;
}

// Función para validar caja
let validBox = (board, row, col, value) => {
    let solucion = true;
    const startRow = row - (row % 3), startCol = col - (col % 3);
    for (let i = startRow; i < startRow + 3; i++) {
        for (let j = startCol; j < startCol + 3; j++) {
            if (i !== row && j !== col) {
                if (board[i][j] === value) {
                    solucion = false;
                }
            }
        }
    }
    return solucion;
}

const sudoku = [
  [5, 3, 4, 6, 7, 8, 9, 1, 2],
  [6, 7, 2, 1, 9, 5, 3, 4, 8],
  [1, 9, 8, 3, 4, 2, 5, 6, 7],
  [8, 5, 9, 7, 6, 1, 4, 2, 3],
  [4, 2, 6, 8, 5, 3, 7, 9, 1],
  [7, 1, 3, 9, 2, 4, 8, 5, 6],
  [9, 6, 1, 5, 3, 7, 2, 8, 4],
  [2, 8, 7, 4, 1, 9, 6, 3, 5],
  [3, 4, 5, 2, 8, 6, 1, 7, 9]
];

let resultado = validarSudoku(sudoku);
console.log(resultado);
```
