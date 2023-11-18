¡Llega el turno de practicar todo lo aprendido esta semana! 

En esta ocasión, vamos a focalizarnos exclusivamente en Javascript, para seguir asentando las bases de todo lo aprendido, así que vamos a enfrentarnos a una competición de Katas.

**¿Qué es una kata?** 

La idea de una kata es un ejercicio corto que nos ayuda a aprender funcionalidades o conceptos, vamos, lo que hemos ido haciendo a lo largo de esta semana.

¿Estáis preparados para afrontar el reto?


### KATA 1 - Contador de vocales


```jsx
/*
		Crear una función que devuelva el número de vocales 
		que tiene el string que le pasemos como parámetro.

		Consideramos que el string solo tiene letras minúsculas y espacios.
*/
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
```


### KATA 4 - Código secreto


```jsx
/*
		Crea una función que reciba como parámetro un string y devuelva otro, 
		remplazando las letras por su posición en el alfabeto.

		Si algún caracter no se encuentra, simplemente lo ignoramos.
*/
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
```

 
### KATA 6 - Slice


```jsx
/* 
		Crea una función que reciba un array de números, la posición inicial 
		y final del nuevo array (opcional), y devuelva el nuevo array.
		
		Ejemplo 1: ([1, 2, 3], 0, 1) // => [1]
		Ejemplo 2: ([1, 2, 3], 1) // => [2,3]
*/ 
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
				[{id: 1, modelo: ‘híbrido’, matricula:’4565HLM’ },
				{id: 2, modelo: ‘gasolina’, matricula:’5678MNL’ },
				{id: 3, modelo: ‘híbrido’, matricula:’1111LLL’ }] 

			Salida:
			[{id: 1, modelo: ‘híbrido’, matricula:’4565HLM’, etiqueta:’ECO’},
			{id: 2, modelo: ‘gasolina’, matricula:’5678MNL’, etiqueta:’C’},
			{id: 3, modelo: ‘híbrido’, matricula:’1111LLL’, etiqueta:’ECO’ }].
*/ 
```
 

### KATA 9 - Ordenación de un array según la propiedad
 

```jsx
/* 
		Crea una función que reciba la lista de regalos de los reyes magos 
		y la ordene según la propiedad elegida.
		
		Ejemplo:		
			Entrada: 
					([{nombre: ‘Barbie’, categoria: ‘muñecas’ },
					{nombre: ‘Lego’, categoria:’construcción’ },
					{nombre: ‘Fifa2023’, categoria:’videojuego’ }], ‘nombre’);
			
			Salida:
					[{nombre: ‘Barbie’, categoria: ‘muñecas’ },
					{nombre: ‘Fifa2023’, categoria:’videojuego’ }
					{nombre: ‘Lego’, categoria:’construcción’ }]
*/ 
```
 

### KATA 10 - Monopoli: ¿Quién tiene más dinero?
  

```jsx
/* 
		Crea una función que reciba un listado de jugadores con el número de 
		billetes de cada cantidad que tienen y devuelva el jugador con más dinero. 

		No habrá más de un jugador que tenga el mayor número de billetes

		Ejemplo:
	   Entrada:
			[{nombre: ‘Pedro’, billetesDe5: 10, billetesDe10: 3, billetestDe50: 1 },
			{nombre: ‘Luis’, billetesDe5: 10, billetesDe10: 1, billetestDe50: 2 },
				{nombre: ‘Gon’, , billetesDe5: 5, billetesDe10: 5, billetestDe50: 5 },];
		
			Salida:
				Gon
*/ 
```
  

### KATA 11 - Mueve los 0 al final
  

```jsx
/* 
	Crea una función que reciba un listado y mueva todos los 0 al final, 
	manteniendo el orden del resto de elementos.

	Ejemplo:
	   Entrada: [1,0,true,0,’hola’, 5, 30, ‘a’]
	   Salida: [1,true,’hola’, 5, 30, ‘a’,0,0]
*/ 
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
```
