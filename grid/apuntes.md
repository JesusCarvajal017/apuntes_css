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
































