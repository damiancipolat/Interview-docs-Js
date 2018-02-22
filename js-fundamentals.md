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