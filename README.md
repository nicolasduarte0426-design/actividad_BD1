# actividad_BD1
### Modelo conceptual
<img width="1063" height="677" alt="image" src="https://github.com/user-attachments/assets/759f3ef5-4138-40e9-821d-6f6c660e4af7" />
### Modelo logico
 <img width="793" height="455" alt="image" src="https://github.com/user-attachments/assets/98509156-d5b1-47cf-b211-38d6988defbc" />
 
## TABLAS
### Clientes
<img width="914" height="404" alt="image" src="https://github.com/user-attachments/assets/d1faa261-bfdb-48db-a7af-3eac633b7955" />

### Ventas
<img width="800" height="466" alt="image" src="https://github.com/user-attachments/assets/4774ee23-0f9b-4fc5-983d-15620555e652" />

### Productos
<img width="922" height="430" alt="image" src="https://github.com/user-attachments/assets/a885670d-9939-4832-9ee5-381b6e65883a" />

### Detalle ventas
<img width="433" height="345" alt="image" src="https://github.com/user-attachments/assets/b8d11be8-5b49-4a9b-86c6-34dac28cab87" />

## Consultas
#### Informacion de un producto vendido
SELECT 
    p.id_producto,
    p.nombre AS producto,
    p.marca,
    p.precio,
    dv.cantidad,
    dv.subtotal,
    v.id_venta,
    v.fecha,
    c.nombre AS cliente
FROM producto p
INNER JOIN detalle_venta dv ON p.id_producto = dv.id_producto
INNER JOIN ventas v ON dv.id_venta = v.id_venta
INNER JOIN cliente c ON v.id_cliente = c.id_cliente
WHERE p.id_producto = 1;

FROM producto INNER JOIN detalle_venta ON detalle_venta.id_producto = producto.id_producto
<img width="917" height="431" alt="image" src="https://github.com/user-attachments/assets/5fcf8171-db09-450a-8a0f-32f499536570" />

#### Clientes que han realizado ventas
SELECT cliente.nombre, cliente.correo, venta.fecha, venta.total
FROM cliente INNER JOIN venta ON venta.id_cliente = cliente.id_cliente
<img width="1030" height="450" alt="image" src="https://github.com/user-attachments/assets/91e1ccbd-1ede-42e0-ba1d-3fa96b023c3d" />

#### Listar prductos donde el precio este entre los 50.000 y 800.000
SELECT nombre, marca, precio
FROM producto
WHERE precio BETWEEN 50000 AND 800000;
<img width="1158" height="431" alt="image" src="https://github.com/user-attachments/assets/92696934-bdb9-4833-8a04-42a2b81ec1b6" />
