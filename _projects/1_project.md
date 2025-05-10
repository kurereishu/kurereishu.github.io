---
layout: page
title: Sistema de ventas
description: Un sistema de ventas en Java con MySQL
img: assets/img/producto_Sis_Ventas.jpg
importance: 1
category: work
related_publications: false #MUESTRA EN EL PIE DE LA PÁGINA REFERENCIAS
---

El proyecto usa tablas de MySQL para almacenar datos de ventas, productos y clientes. El sistema permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en la base de datos. Las tablas se crearon de la siguiente manera:

    
    CREATE DATABASE dbjavamysql;
    USE dbjavamysql;

    CREATE TABLE tb_usuario(
        idUsuario int(11) AUTO_INCREMENT PRIMARY KEY,
        nombre varchar(30) NOT NULL,
        apellido varchar(30) NOT NULL,
        usuario varchar(15) NOT NULL,
        password varchar(15) NOT NULL,
        telefono varchar(15) NOT NULL,
        estado int(1) NOT NULL
    );

    Insertar datos en tabla usuarios para el login
    INSERT INTO tb_usuario(nombre, apellido, usuario, password, telefono, estado)
    VALUES("nombre", "apellido", "usuarioLogin", "password","telefono",1);

    CREATE TABLE tb_cliente(
        idCliente int(11) AUTO_INCREMENT PRIMARY KEY,
        nombre varchar(30) NOT NULL,
        apellido varchar(30) NOT NULL,
        cedula varchar(15) NOT NULL,
        telefono varchar(15) NOT NULL,
        direccion varchar(100) NOT NULL,
        estado int(1) NOT NULL
    );

    CREATE TABLE tb_categoria(
        idCategoria int(11) AUTO_INCREMENT PRIMARY KEY,
        descripcion varchar(200) NOT NULL,
        estado int(1) NOT NULL
    );

    CREATE TABLE tb_producto(
        idProducto int(11) AUTO_INCREMENT PRIMARY KEY,
        nombre varchar(100) NOT NULL,
        cantidad int(11) NOT NULL,
        precio double(10,2) NOT NULL,
        descripcion varchar(200) NOT NULL,
        porcentajeIva int(2) NOT NULL,
        idCategoria int(11) NOT NULL,
        estado int(1) NOT NULL,
        FOREIGN KEY (idCategoria) REFERENCES tb_categoria(idCategoria)
    );

    CREATE TABLE tb_cabecera_venta(
        idCabeceraVenta int(11) AUTO_INCREMENT PRIMARY KEY,
        idCliente int(11) NOT NULL,
        valorPagar double(10,2) NOT NULL,
        fechaVenta date NOT NULL,
        estado int(1) NOT NULL,
        FOREIGN KEY (idCliente) REFERENCES tb_cliente(idCliente)
    );

    CREATE TABLE tb_detalle_venta(
        idDetalleVenta int(11) AUTO_INCREMENT PRIMARY KEY, 
        idCabeceraVenta int(11) NOT NULL,
        idProducto int(11) NOT NULL,
        cantidad int(11) NOT NULL,
        precioUnitario double(10,2) NOT NULL,
        subtotal double(10,2) NOT NULL,
        
        iva double(10,2) NOT NULL,
        totalPagar double(10,2) NOT NULL,
        estado int(1) NOT NULL,
        FOREIGN KEY (idCabeceraVenta) REFERENCES tb_cabecera_venta(idCabeceraVenta),
        FOREIGN KEY (idProducto) REFERENCES tb_producto(idProducto)
    );
    

Este sistema de ventas está desarollado en Java y además emplea MySQL como base de datos que permite almacenarla información de productos, clientes y facturas. La interfaz gráfica está diseñada con el propósito de facilitar la gestión de las ventas lo que permite a los usuarios añadir, actualizar y eliminar categorías, productos, clientes además de calcular totales y el registro de las ventas cuenta con la generación de una factura en formato PDF.


<!--- 
Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---
--->

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/login_Sis_Ventas.jpg" title="Sistema de Ventas" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/categ_Sis_Ventas.jpg" title="Sistema de Ventas" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/producto_Sis_Ventas.jpg" title="Sistema de Ventas" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Sus componentes principales a destacar son la interfaz gráfica "GUI" con pestañas, campos de entrada, selección y búsqueda
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/categ_Sis_Ventas.jpg" title="Categoría" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Categorias del sistema de ventas
</div>

La pestaña de cateogorías permite almacenar y gestionar las categorías de los productos, así como la creación de nuevas categorías mismas que van a interactuar con los productos y para la creación de las facturas.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/producto_Sis_Ventas.jpg" title="Producto" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    productos del sistema de ventas
</div>

La pestaña de productos nos permite almacenar y gestionar los productos mismos que van a interactuar con las categorías y para la creación de las facturas.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cli_Sis_Ventas.jpg" title="Cliente" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/fact_Sis_Ventas.jpg" title="Factura" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Productos del sistema de ventas y factura generada
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cli_Sis_Ventas.jpg" title="Cliente" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    clientes del sistema de ventas
</div>

La pestaña de clientes nos permite almacenar y gestionar los clientes mismos que van a interactuar con los productos y la creación de las facturas.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/factura_Sis_Ventas.jpg" title="Factura" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    factura del sistema de ventas
</div>

La pestaña de facturas nos permite almacenar y gestionar las facturas mismas que van a interactuar con los productos y el cliente para obtener la factura en PDF.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/fact_Sis_Ventas.jpg" title="Factura PDF" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    factura del sistema de ventas en PDF
</div>

El sistema de ventas desarollado en Java y utilizando MySQL nos ofrece una solución robusta y eficiente para la gestión de ventas además de la integración de Java para la lógica de negocio y MySQL para el almacenamiento de datos nos proporciona una plataforma confiable y escalabre para el crecimiento futuro del negocio.

<!--- 
{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
--->
