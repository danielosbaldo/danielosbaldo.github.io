---
layout: post
title: State React
description: iNTENTARE EXPLICAR LO QUE ES EL ESTADO EN REACT COMO UTILIZARLO Y NOTAS IMPORTANTES SOBRE EL
---
Notas Sobre State En React

el estado de reactr es de lo mas complicado de entender de react

State(estado) es un objeto plano de javascript que se usa para registrar y reaccionar a los eventos de usuario, cada componente basado en una clase que definimos tiene su propio objeto de estado cuando el estado de un componente cambie el componente inmediatamanete se re renderea esto tambien para tosod sus hijos se forzan a re renderiar:

antes de usar estado(state) adentro de un componente primero hay que inicializar el objeto de estado
para hacerlo hay que declarar la propiedad estado a un objeto pleno de javascript(plain javascript object) adentro de el metodo constructor de la clase
 
```javascript
class SearchBar extends Component {
    constructor(props ) { //todas las clases javascript tienen una funcion especial llamada constructor esta es la primera y unica funcion llamada automaticamente cuando una nueva instancia de la clase se crea, puedes imaginarte en relidad esta funcion es llamada todo el timepo porque se llama cuando se crea una nueva instancia de la clase, la funcion de constructor es recerbada para hacer configuraciones en nuestra clase como inicializar variables, inicializar estado y ese tipo de cosas
        super(props); // Coponent tiene su propia funcion constructora, cuando definimos un metodo que ya esta definido en la clase padre la cual es component, podemos  llamar ese methodo padre en la calse padre llamando SUPER. Super llama la clase padre de el metodo que extendemos o metodo padre  
        this.state = { term: ''}; // cuando usamo state lo inicializamos creando un objeto nuevo y asignandozelo a This.State, el objeto que pasemos tambien tendra propiedades que queremos registrar en el state(estado), en este ejemplo queremos registrar la propiedad term de el estado(state) usamos Term por referirnos a termino de busqueda que es lo que pretende hacer esta clase cuando un usuario ingrese datos en un input queremos registrar lo que escrive en el This.state
    } //asi se inicializa el estado
                                   
    render() {
        return <input onChange={ event => this.setState({ term: event.target.value })} />;
    }

}

export default SearchBar;
```

para actualizar un estado no se utiliza this nunca nucna debemos manipular estate fuera del constructor con this, se usa this.setState para actualizarlo ej>
```javascript
    render() {
        return <input onChange={ event => this.setState({ term: event.target.value })} />;
    }
```