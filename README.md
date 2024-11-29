# Poo-Reto-2: Diagrama UML
Para la solución de este reto, decidí plantear los componentes de un restaurante, y las relaciones existentes entre estos, incluyendo a los empleados y a los clientes. A continuación el diagrama: 

```mermaid
classDiagram
    Empleado "1" --> "n" Orden: Recibe
    Cliente "1" --> "n" Orden: Pide
    Empleado "1" --> "n" Plato: Prepara/Entrega
    Empleado "1" --> Mesa: Asigna
    Mesa --* Restaurante
    Plato --* Restaurante
    Orden --* Restaurante
    class Restaurante {
        -String Orden
        -String Plato
        -String Cliente
        -String Menu
        -String Mesa

        +abrirRestaurante()
        +cerrarRestaurante()
    }
    class Orden {
        -Int NumeroOrden
        -Date Fechas
        -String Estado

        +agregarPlato(plato:Plato)
        +calcularTotal()
    }

    class Plato {
        -String Plato
        -Double Precio
        -String Descripcion
        -String Categoria 

        +mostrarDetalles()
    }

    class Cliente {
        -String Nombre
        -String Telefono
        -String Email

        +hacerReserva()
        +realizarOrden()
    }

    class Empleado {
        -String Name
        -String idEmpleado
        -String Rol 

        +tomarOrden()
        +servirPlato()
    }

    class Mesa {
        -String NumeroMesa
        -Int Capacidad
        -String Estado

        +asignarMesa(cliente: Cliente)
        +liberarMesa() 
    }
```

