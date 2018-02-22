## Factory pattern

```js
//Simularia la clase abstracta
class Triangulo{
  
  constructor(a,b,c){

    this.lado_1 = a;
    this.lado_2 = b;
    this.lado_3 = c;

  }

}

//Clases que la extienden
class Escaleno extends Triangulo{
  
  constructor(a,b,c){}{
    super(a,b,c);
    this.nombre = 'escaleno';
  }

  getNombre(){
    return this.nombre;
  }

}

class Equilatero extends Triangulo{
  
  constructor(a,b,c){}{
    super(a,b,c);
    this.nombre = 'equilatero';
  }

  getNombre(){
    return this.nombre;
  }

}

class Isoceles extends Triangulo{
  
  constructor(a,b,c){}{
    super(a,b,c);
    this.nombre = 'isoceles';
  }

  getNombre(){
    return this.nombre;
  }

}

//Factory
class TrinanguloFactory{
  
  build(a,b,c){

    if (a==b==c)
      return new Equilatero(a,b,c);

    if (a!=b!=c)
      return new Isoceles(a,b,c);

    if (a>=b>=c)
      return new Escaleno(a,b,c);      

  }

}

//Prueba.
let triangulo = new TrinanguloFactory().build(1,1,1);
console.log(triangulo.getNombre());
```

## Singleton Pattern

```js
//Nativamente en ES6 podemos crear un singleton usando modules.
class Contadores{
  
  constructor(){
    this.pares   = 0;
    this.impares = 0; 
  }

  getCounters(){

    return {"pares":this.pares,"impares":this.impares};

  }

  addPar(){
    this.pares++;
  }

  addImpar(){
    this.impares++;
  }

}

module.export = new Contadores();

//Prueba.
let contador = require('./contadores.js');

contador.addPar();
contador.addPar();
contador.addPar();
contador.addImpar();

console.log(contador.getCounters());
```

## Decorator Pattern

```js
//Creamos la clase base.
class Greetings{
  
  hello(){
    return 'hello';
  }

  bye(){
    return 'bye';
  }

}

//Clase que extiende dinamicamente comportamiento.
class GreetingsDecorator{
    
  constructor(component){
    this.component = component;
  }

  hello(){
    return this.component.hello()+' how are you?';
  }

  bye(){
    return this.component.bye()+' see you next time';
  }

  crazy(){
    return this.component.bye()+this.component.hello();
  }

}

//Prueba.
let saludos = new GreetingsDecorator(new Greetings());

console.log(saludos.hello());
console.log(saludos.bye());
```

## Adapter Pattern

```js
//Interfaz vieja.
class shipping_Old{

  calcTax(zipStart, zipEnd, weight){
        return "$49.75";
  }

}

//Interfaz nueva.
class shipping_New{
  
  constructor(start,end,weight){
    this.zipStart   = start;
    this.zipEnd     = end;
    this.weight     = weight;
    this.additional = 0;
  }

  setAdditional(add){
    this.additional = add;
  }

  calcTax(){
    return (this.zipStart+this.zipEnd)*this.weight+this.additional;
  }

}

//La clase adaptadora nos permite trabajar usando la clase vieja como si fuera la nueva.
class shippAdapter{
  
  constructor(adaptable){
    this.zipStart   = start;
    this.zipEnd     = end;
    this.weight     = weight;
    this.additional = 0;
    this.adaptable  = null;
  }

  setAdaptable(obj){
    this.adaptable = obj;
  }

  setAdditional(add){
    this.add = add;
  }

  calcTax(){
    return this.adaptable.calcTax(this.zipStart, this.zipEnd, this.weight)+this.additional;
  }

}

//Prueba.

//Nuevo
let shipNew = new shipping_New(1,1,3);
shipNew.setAdditional(5);

console.log(ship.calcTax());

//Viejo como nuevo.
let shipAdapt = new shippAdapter(1,1,3);
shipAdapt.setAdaptable(new shipping_Old());
shipAdapt.setAdditional(5);

console.log(ship.calcTax());
```

## Strategy Pattern
```js
class alumnHard{

  constructor(){
    this.iq = 90;
    this.studyPower = 100;
  }

  studyStat(){
    return this.iq+this.studyPower;
  }

}

class alumnLazy{
  constructor(){
    this.iq = 20;
    this.studyPower = 50;
    this.funLevelr  = 90;
  }

  studyStat(){
    return (this.iq+this.studyPower)-this.funLevel;
  }
}

class test{  
  constructor(){
    this.alumn = null;
  }

  setAlumn(alumn){
    this.alumn = alumn;
  }

  make(){
    this.alumn.study();
  }
}

let mathTest = new test();

mathTest.setAlumn(new alumnLazy());
mathTest.make();

mathTest.setAlumn(new alumnHard());
mathTest.make();
```

## Middleware Pattern
