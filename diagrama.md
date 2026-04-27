```mermaidd
classDiagram
    class Producto {
        +int Id
        +string Nombre
        +decimal Precio
        +int Stock
        +int StockMinimo
    }

    class DetalleVenta {
        +Producto Producto
        +int Cantidad
        +decimal Subtotal
    }

    class Venta {
        +int Id
        +DateTime Fecha
        +List~DetalleVenta~ Detalles
        +decimal Total
    }

    class Datos {
        +List~Producto~ Productos
        +List~Venta~ Ventas
        +int siguienteIdProducto
        +int siguienteIdVenta
    }

    class Program {
        +void Main()
        +void MenuProductos()
        +void MenuVentas()
        +void MostrarProductos()
        +void AgregarProducto()
        +void EditarProducto()
        +void EliminarProducto()
        +void VerificarStock()
        +void RegistrarVenta()
        +void MostrarVentas()
        +bool RestarStock(int, int)
    }

    Datos "1" *-- "n" Producto : gestiona
    Datos "1" *-- "n" Venta : registra
    Venta "1" *-- "n" DetalleVenta : contiene
    DetalleVenta "n" --> "1" Producto : referencia
```
