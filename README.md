# Rust desde 0

## Instalción

## Hola mundo

Creamos un archivo `main.rs` en el que estableceremos una función `main()` donde pondremos la macro para imprimir una linea en la consola.

```rs
fn main(){
    println!("Hola mundo");
}
```

## Variables y Constantes

Rust es un lenguaje con tipado estático, tiene que conoces el tipo de cada variable cuando se ejecuta la compilación. Habitualmente, no tendremos que declarar el tipo de datos, sino que el compilador puede deducir el tipo a partir del contexto.

Las variables, por defecto, son inmutables: no se puede cambiar su valor posteriormente.

Para declarar variables se usa la palabra reservada `let` del siguiente modo:

```rs
// Crea una variable x, de tipo entero (el tipo se establece solo)
let x = 5;
```

Aqui un ejemplo de como mostrariamos el valor de `x`.

```rs
fn main() {
    let x = 5;
    /* Para mostrar una variable en un string usamos {} y dentro el nombre
       de la variable      
    */
    println!("El valor de x es: {x}");
}
```

Si a nuestra variable `x` le intentamos cambiar el valor nos dara un error.

```rs
fn main() {
    let x = 5;
    // Aqui nos dara nun error de que la variable no es mutable.
    x = 3;
    println!("El valor de x es: {x}");
}
```

Si deseamos que una variable se pueda cambiar el valor posteriormente, se tiene que usar la palabra reservada `mut` entre `let` y el nombre de la variable, del siguiente modo:

```rs
    let mut x = 5;
```

Asi quedaria nuestro código:

```rs
fn main() {
    let mut x = 5;
    
    x = 3;
    println!("El valor de x es: {x}");
    // El valor de x es: 3
}
```

Probablemente al ver que las variables son inmutables recordaste el concepto de `constantes`.

En Rust, tambien existen y se definen del siguiente modo, usamos la palabra reservada `const`, el nombre de nuestra constante debe ir en mayusculas (esto es una convención que el compilador nos obliga seguir), a diferencia de las variables, aqui si tenemos que definir el tipo de dato y luego ya establecemos su valor, quedando de la siguiente forma:

```rs
fn main() {
    const PI: f64 = 3.1415;

    println!("Valor de PI: {PI}");
}
```

En las constantes tenemos que definir un valor literal, no podemos definir su valor dependiendo un resultado.

```rs
    // Esto da error
    const PI: f64 = 3.0 + 0.1415;

    // Esto esta bien
    const PI: f64 = 3.1415;
```

### Shadowing (redefiniendo variables)

Con este concepto de Rust, podemos volver a crear una misma variable, para poder asignarle un nuevo valor (incluso distinto).

```rs
let x = 5;
let x = "a";
```

Aqui un ejemplo:

```rs
fn main() {
    let x = 3;
    println!("X: {x}");

    let x = "Hola";
    println!("{x} mundo!");
}
```
