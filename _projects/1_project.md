---
layout: page
title: Sistema de ventas
description: Un sistema de ventas en Java con MySQL
img: assets/img/producto_Sis_Ventas.jpg
importance: 1
category: work
related_publications: true
---

Este sistema de ventas está desarollado en Java y además emplea MySQL como base de datos que permite almacenarla información de productos, clientes y facturas. La interfaz gráfica está diseñada con el propósito de facilitar la gestión de las ventas lo que permite a los usuarios añadir, actualizar y eliminar categorías, productos, clientes además de calcular totales y el registro de las ventas cuenta con la generación de una factura en formato PDF.


<!--- 
Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:
--->
    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/login_Sis_Ventas.jpg" title="Sistema de Ventas" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/categoria_Sis_Ventas.jpg" title="Sistema de Ventas" class="img-fluid rounded z-depth-1" %}
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
        {% include figure.liquid loading="eager" path="assets/img/categoria_Sis_Ventas.jpg" title="Categoría" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Categorias del sistema de ventas
</div>

La pestaña de cateogorías permite almacenar y gestionar las categorías de los productos, así como la creación de nuevas categorías mismas que van a interactuar con los productos y para la creación de las facturas.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/producto_Sis_Ventas.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

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
