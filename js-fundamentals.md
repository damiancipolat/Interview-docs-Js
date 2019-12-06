# JS FUNDAMENTALS:

## Events:
Definiciones, callback, promise, async, sync.

### Función de orden superior:
Son funciones que pueden aceptar como parametros otras funciones y hasta devolver funciones tambien como retorno.

Usados para programción asincronica, se ejecuta dicha función pasada como parametro, cuando se ejecuta la funcion a la cual se pasa,
la ventaja del asincronismo es que el hilo en el cual se ejecuta no se bloquea sino que continua ejecutandose y cuando se obtiene la respuesta de la función se la atiende.

### Callback:
Es una función de orden superior que recibe otra como parametro la cual es ejecutada cuando esta misma es invocada.

Ejemplo:

```js
//Se ejecuta la función que recibe el saludo luego de ejecutar la espera de 5 segundos.

const saludar = (nombre,onSaludo)=>{
  
  setTimeout(()=>{
    let saludo ='Hola '+nombre;
    onSaludo(saludo);
  },5000);

}

saludar('damian',(msj)=>{ 
  alert('Mensaje -> '+msj);
});
```

### Promises:
Es un objeto creado para manejar operaciones asincronicas, una promesa representa un valor que puede estar disponible
ahora, en el futuro o nunca.

```js

new Promise((resolver,rechazar)=>{
  ..... Función que resuelve ...

});

```

### Promise.all(iterable):
Devuelve una de dos promesas, una que se cumple cuando todas las promises se cumplen y una cuando hay alguna que no se cumpla.

#### Promise.race(iterable):
Devuelve una promesa que se cumple o rechaza tan pronto como una de las promesas del iterable se cumple o rechaza, con el valor o razón de esa promesa.

#### Promise.reject(reason):
Devuelve un objeto Promise que es rechazado con la razón dada.

#### Promise.resolve(value):
Devuelve un objeto Promise que es resuelto con el valor dado. Si el valor es un thenable (p.ej. tiene un método then), la promesa devuelta "seguirá" este thenable, adoptando su eventual estado; de lo contrario la promesa devuelta será cumplida con el valor. Generalmente, si se quiere saber si un valor es una promesa o no, se podría usar - Promise.resolve(value) y trabajar con el valor devuelto como una promesa.

```js

//Ejemplo simple de promise.
const saludar = (nombre)=>{
  
  return new Promise((resolve,reject)=>{

    try {

        setTimeout(()=>{

          let saludo ='Hola '+nombre;
          resolve(saludo);

        },5000);

      } catch(err){
          reject(err);
      }


  }); 

}

//Concatenar promises.
const testProm = (nombre,raiz)=>{
  
  return new Promise((resolve,reject)=>{

    try {

        setTimeout(()=>resolve(raiz),5000);

    } catch(err){
          reject(err);
    }


  }); 

}

//Armo una promise y encadeno las resuestas, se pasa la salida de un then al otro.
let p = testProm('damian',10).then((val)=>val+2).
                             .then((val)=>console.log('got',val))
                             .catch((err)=>console.log('error',err));

```

### GENERATORS:

A generator is a special type of function that can be entered and exited a number of times. 
You might hear people describe it as, “a function that can be paused”.

#### Creación:

```js

// standard function
function standardFunc() {

  console.log('The oscar for best picture goes to...');
  console.log('La La Land');
  console.log('There\'s been a mistake...')
  console.log('The best picture is MoonLight.');

}

// generator function
function* generatorFunc() {
  
 console.log('The oscar for best picture goes to...');
 console.log('La La Land');

 //Fija el pto de pausa de la función.
 yield 'WAIT!!!';

 console.log('There\'s been a mistake...')
 console.log('The best picture is MoonLight.');

}

//Traigo el generador.
const genFunc = generatorFunc();

//Ejecuto la función.
genFunc.next();

//Pauso la funcion.
genFunc.next();
```
