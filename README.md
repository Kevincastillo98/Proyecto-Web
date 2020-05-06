![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/Logo2.png)

# Diseño del sistema CompraFut 

**Objetivo:** Desarrollar un sistema de compra online de camisetas deportivas, implementando
tecnologías web.

**Investigación del usuario:** El sistema se diseñó específicamente para una pequeña empresa dedicada a
la venta de camisetas de futbol soccer,dicha empresa cuenta con una cartera de clientes que frecuenta la
tienda, sin embargo se desea escalar de forma virtual para tener mayor alcance y así darse a conocer en
más lugares.
Dos de los objetivos principales de la empresa al implementar el sistema es el brindarle un servicio de
calidad a los usuarios y comodidad al usuario, ya que la empresa está enfocada a todo tipo de personas
y por lo cual se necesita ofrecer un servicio que se fácil de usar.
Para poder implementar el sistema, el cliente nos proporcionó algunos de los requerimientos más
importantes y que se implementarán a la brevedad.
Los requerimientos del usuario se en listarán a continuación:

- El sistema deberá de contar con un **registro de usuarios**,ya que solo las personas registradas podrán
hacer pedidos o compras en la página.
- Deberá de contener una galería de **productos disponibles y posibles descuentos.**
- Es recomendable que la página cuente con **historial de compras pasadas** ya que muchos clientes
suelen comprar ciertos artículos de forma regular.
- **Gestionar los artículos comprados** para tener registro de los artículos que se venden de forma
online.
- **Canasta de compra** esto ayudará a los usuarios a verificar los productos que desea comprar,así como
el total a pagar.

**Solución tecnológica:** El usuario desea que el sitio sea dinámico, que sea fácil de mantener y que
pueda desarrollarse en poco tiempo, por lo cual se optó por ser desarrollado con un framework de
python llamado `flask`.
Flask es un microframework que permite maquetar de forma rápida proyectos web,bajo el patrón
MVC(Modelo-vista-controlador), así que para gestionar el modelo se implementa una base de datos
relacional, en este caso se usará sqlite ya que este gestor de base de datos nos permitirá manejar
archivos multimedia, además de que es una base de datos muy ligera y portable, para la vista es
necesario implementar HTML y CSS y por último el controlador será python, el cual nos permitirá
darle funcionalidad a nuestra página. Otra característica fundamental del sistema es que este será un
sistema dinámico ya que los productos y costos cambiarán constantemente,por lo que el sistema tendrá
que ser fácil de gestionar.

**Definición del contenido:** El principal atractivo del sitio serán los productos que se ofertan y los
descuentos o promociones que se encuentren vigentes, por lo que siempre se pondrá como prioridad los
productos que cuentan con descuentos y que son más comprados.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/Camisa.png)

**Arquitectura de la información e interacción:** Si el usuario ingresa a la página web,este se
encontrará con el catálogo de productos que se encuentran disponibles en la tienda, sin embargo si este
trata de agaragar algún producto a la canasta, este le mostrará un error, ya que es necesario primero
registrarse o iniciar sesión para poder comprar en la tienda.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/ErroRegistrar.png)

Así que si el usuario desea comprar en la tienda, primero debe de registrarse y si cuenta con una cuenta,
este deberá de iniciar sesión.
En caso de no tener cuenta, registrase:

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/Registrar.png)
![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/DatosRegistro.png)

Si el usuario ya se registró y cuenta con un usuario y contraseña, entonces ya podrá ingresar al sistema,
simplemente dando click en la pestaña `Ingresar`.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/Ingresar.png)

Al ingresar el usuario verá el catálogo de artículos disponibles,el sitio cuenta con playeras de
diferentes paises,clubes,ligas o incluso por costo, por lo que podemos filtrar nuestros resultados
mediante la opción `filtrar por`.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/Filtrar.png)

El usuario podrá comprar una o más playeras del catálogo disponible.
Si el usuario desea agregar algún articulo a la canasta de compra, solo basta con seleccionar el número
de playeras a comprar, de lo contrario si no se especifica el número de playeras, el sistema le dirá que
no puede agregar el articulo a la canasta de compras:

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/EligeCamisa.png)

Si el usuario agrega el número de playeras a comprar y además da click en “Agregar al carrito”,este
será enviado a la canasta de compras:

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/SeleccionaCamisa.png)

En el carrito de compras podemos ver el número de artículos que seleccionamos,así como el precio
unitario y el total a pagar, en este apartado podemos ver 3 opciones.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/CarritoCompras.png)

1. **Realizar cambios:** Esta opción nos permitirá hacer cambios en los artículos seleccionados,aquí
podemos modificar el número de artículos a comprar o eliminarlo de la canasta de compras.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/CambiosCarrito.png)

2. **Continuar comprando:** Esta opción nos redireccionará al menú donde se encuentra el catálogo de
compras y deshace las compras que hicimos.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/VistaGeneral.png)

3. **Verificar:** Esta opción permitirá agregar nuestra compra al historial.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/Historial.png)

Por último tenemos la opción de **historial de compras** , en cual almacenará las compras verificadas y
que nos ayudarán a volver a hacer un pedido sin tener que regresar a catálogo de compras, esta opción
es recomendada para las personas que suelen comprar uno o varios artículos de forma recurrente,para
hacer uso del historial, basta en dar click a la opción de `Tus compras` que se encuentra en la parte
superior de la página,luego podemos dar click en la opción comprar de nuevo.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/ImagenesRepo/Historial.png)

**Diseño y manejo de los Datos:** El esquema generado de la base de datos cuenta con 3 tablas, la
primera hace referencia al usuario, la cual almacena los datos de contacto y de registro en la
plataforma,la tabla compra almacena las posibles transacciones que haga el usuario y por último la
tabla playera almacenará los detalles del producto y que servirá como inventario.

![](https://github.com/Kevincastillo98/Proyecto-Web/blob/master/Esquemas/esquema.png)

**Innovación:** Esta sistema está diseñado con el fin de poderse expandir y agregar más funcionalidades
que a la larga ayudaran en el crecimiento de la empresa,además de que muy pocas micro-empresas
cuentan con un servicio de compras y apartado online.

**Generación de contenido:** Este sistema se puede auto gestionar, ya que está diseñado con el fin de
poder escalar de forma proporcional al número de usuarios, el mantenimiento tanto de base de datos
como de implementación de nuevas funcionalidades serán gestionadas por su servidor `Kevin Castillo
Roa.`

**Futuras implementaciones:** Por cuestiones de seguridad no se han implementado métodos de pago,
como lo son tarjetas de crédito o débito, sin embargo esta será una de las funcionalidades a agregar en
la siguiente versión del sistema, la gestión de tallas o personalización de playeras aún no está
disponible en la tienda, sin embargo se estima que pronto se agregue esta función y por último el
implementar un servicio de analítica de datos que permita eficientisar el proceso de venta de productos.

