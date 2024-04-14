> [!IMPORTANT]
> Apuntes de grid layout

# GRID LAYOUT
El "Grid Layout" es un sistema de diseño `bidimensional` en CSS que permite crear diseños de manera más flexible y precisa que los sistemas de diseño anteriores, como Flexbox. Con Grid Layout, puedes dividir el espacio de la página en filas y columnas, y luego colocar los elementos en estas celdas de forma fácil y controlada.

```
    .container{
        background-color: bisque;
        border: 1px solid #000000;
        display: grid;  /* inicio del grid */
        grid-template-columns: 100px 100px;
    }

```

Esta propiedad ``` grid-template-columns: 100px 100px; ```, sirve para indicarle cuales seran las columna, con su respectivo tamaño, (Recordar que pueden ser n columnas)

### Unidad especial de medidad para el grid template columns

`1fr --> 100%` unidad especial para el grid layout

```
    ..{
        display: grid; 
        grid-template-columns: 1fr; /* 1fr --> 100% */
    }
```

A la hora de establecer las columnas se general automaticamente las filas, asi que para manejarlas se utiliza lo siguiente: 

```
    grid-template-rows: 30px 50px 70px;

```


>[!NOTE]
> si se quiere dejar en automatico pero se quiere establecer una medida de ancho se puede utilizar lo siguiente 

```
    grid-auto-rows: 20px;

```

otra curiosidad es un metodo que nos ayuda a repetir las veces necesarias para hacer las fracciones `repeat()`: 

```
    ...{
          grid-template-columns: repeat(3, 1fr);
    }

    repeat(n, lo que se quiera repetir n veces); 

```
otra que complementa esta propiedad es `mimax(min, si pasa del minimo`; 

>[!NOTE]
> Ejemplo de minmax() aplicacion en el caso de aside

## CSS
```
    div{
        display: grid;
        grid-template-columns: minmax(400px, 1fr) 5fr;
    }

    aside{
        border: 2px solid #000000;
        height: 100vh;
    }

    body{
        margin: 0;
    }
```

## HTML
```
    <div>
        <aside>
            <ul>
                <li>inicio</li>
                <li>nosotros</li>
                <li>configuraciones</li>
            </ul>
        </aside>
        <section>
            contenido de la pagina
        </section>
    </div>
```

# Ejemplo de maquetacion

Nuevas propiedades

* column-gap
* row-gap
* gap

el gap es para utilizar las dos al mismo tiempo

## HTML

```
    <body>
        <div>
            <img src="img/imgEjemplo1.jpg" alt="">
            <img src="img/imgEjemplo2.jpg" alt="">
            <img src="img/imgEjemplo3.jpg" alt="">
            <img src="img/imgEjemplo1.jpg" alt="">
            <img src="img/imgEjemplo2.jpg" alt="">
            <img src="img/imgEjemplo3.jpg" alt="">
            <img src="img/imgEjemplo1.jpg" alt="">
            <img src="img/imgEjemplo2.jpg" alt="">
            <img src="img/imgEjemplo3.jpg" alt="">
        </div>
    </body>

```

## CSS

```
    div{
        width: 500px;
        margin: auto;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        column-gap: 10px;
        row-gap: 10px;
    }

    img{
        width: 100%; 
        height: 100%;
        object-fit: cover;
    }

```

Ejemplo de reposive en grid sin media query:

``` 
    div{
        display: grid;
        grid-template-columns: repeat(
            auto-fill,
            minmax(200px, 1fr)
        );
        gap: 10px; 
        max-width: 620px;
    }

```

Ahora una de las cosas mas importantes, manejar la cuadricula a la personalidad: 

```
    .container div:nth-child(1){
        background-color: blueviolet;
        grid-column: 1 / 3;
        grid-row: 1 / 3;
    }
```

>[!NOTE]
> Las propiedades que permiten esta cualidad: 

*  grid-column: ;
*  grid-row: ; 

la forma en la que se le da un valor, es teniendo en cuenta el inicio y final que hay entre las columnas y filas

> indicar el inicio y final : `1 / 2` 

> indicar cuantas cendas o cuadriculas : `span 2` 
