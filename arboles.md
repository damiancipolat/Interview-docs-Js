## Arboles:

#### Arbol:
En ciencias de la computación y en informática, un árbol es un tipo abstracto de datos (TAD) ampliamente usado que imita la estructura jerárquica de un árbol, con un valor en la raíz y subárboles con un nodo padre, representado como un conjunto de nodos enlazados.

#### Arbol binario:
Es una estructura de datos en la cual cada nodo puede tener un hijo izquiero y derecho, no pueden tener más de dos hijos.
Si tiene como referencia a null ese nodo es una hoja.

![N|Solid](https://upload.wikimedia.org/wikipedia/commons/thumb/3/36/Binary_tree_%28oriented_digraph%29.png/192px-Binary_tree_%28oriented_digraph%29.png)

**Arbol espejado:**
Es un arbol binario es espejo con otro si tienen la misma forma pero en sentido inverso, simeticro como si fuera visto por un espejo.

```js

class Nodo{
 	String valor;
 	Nodo izq, der;
}

boolean espejos(Nodo x, Nodo y) {

 // Caso dos árboles vacíos
 if( x==null && y==null)
 return true;

 // Caso un árbol vacío
 if( x==null || y==null )
 return false;

 // Caso ningún árbol vacío
 return x.valor.equals(y.valor)&&espejos(x.izq, y.der)&& espejos(x.der, y.izq);

} 

```

### Busquedas basadas en arboles:

#### Busqueda binaria:
En ciencias de la computación y matemáticas, la búsqueda binaria, también conocida como búsqueda de intervalo medio1​ o búsqueda logarítmica,2​ es un algoritmo de búsqueda que encuentra la posición de un valor en un array **ordenado**.​ Compara el valor con el elemento en el medio del array, si no son iguales, la mitad en la cual el valor no puede estar es eliminada y la búsqueda continúa en la mitad restante hasta que el valor se encuentre.

#### Busqueda por fuerza bruta:

El código por fuerza bruta es bastante sencillo: Solo se recorre todo el arreglo y verificamos si la posición i es igual al dato que queremos buscar, el código anterior se puede mejorar simplemente agregandole una bandera, pero aun asi no es lo suficientemente bueno.

```js

   for(int i=0; i<Arreglo.length; i++)
           if(Arreglo[i] == elemento)
           System.out.println("\nElemento encontrado en la posicion: " + i);

```