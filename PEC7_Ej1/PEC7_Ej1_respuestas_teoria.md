> ### PEC7_Ej1
>
> #### a) ¿Qué es y cómo funciona el elemento RouterOutlet?
>
> RouterOutlet es una etiqueta especial en Angular que sirve para mostrar los componentes hijos de un componente. Por defecto todos los componentes son hijos del componente AppComponent, por lo que si incluímos esta etiqueta dentro de la vista de AppComponent, se renderizará cada uno de los componentes del routing dependiendo de la página en la que nos encontremos.
>
> #### b) ¿Para qué se utilizan las directivas routerLink y routerLinkActive? ¿Existen más directivas relacionadas con el router?
>
> RouterLink: Cuando se aplica a un elemento en una plantilla, convierte ese elemento en un enlace que inicia la navegación a una ruta. La navegación abre uno o más componentes enrutados en una o más ubicaciones router-outlet en la página.
>
> RouterLinkActive: Realiza un seguimiento de si la ruta vinculada de un elemento está actualmente activa y le permite especificar una o más clases de CSS para agregar al elemento cuando la ruta vinculada está activa.
>
> Las directivas que existen para @angular/router son RouterLink, RouterLinkActive, RouterLinkWithHref y RouterOutlet.
>
> #### c) ¿Qué diferencias hay entre los servicios Router y ActivatedRoute? ¿Qué funcionalidades tiene cada uno de estos servicios? Describe algunos de los métodos más importantes por los que están compuestos.
>
> Router: Un servicio que proporciona navegación entre vistas y capacidades de manipulación de URL.
>
> - initialNavigation(): Configura el oyente de cambio de ubicación y realiza la navegación inicial.
>
> - getCurrentNavigation(): Devuelve el objeto de navegación actual cuando el enrutador está navegando y nulo cuando está inactivo.
>
> - navigateByUrl(): Navega a una vista utilizando una ruta de ruta absoluta.
>
> ActivatedRoute: Brinda acceso a información sobre una ruta asociada a un componente que se carga en un tomacorriente. Úselo para atravesar el árbol RouterState y extraer información de los nodos.
>
> - toString()
>
> #### d) ¿Qué son las Route Guards? ¿Cómo se usan las guardas en Angular? Describe todas las guardas que existen en Angular (consulta para ello la documentación oficial de Angular)
>
> Las route guards de navegación de Angular permiten otorgar o quitar el acceso a ciertas partes de la navegación. El guard CanDeactivate, por ejemplo, incluso permite evitar que un usuario deje accidentalmente un componente con cambios sin guardar.
>
> Las route guards se implementan con mayor frecuencia como clases que implementan la interfaz de la route guard necesaria.
>
> - CanActivate: Controla si se puede activar una ruta.
>
> - CanActivateChild: Controla si se pueden activar los hijos de una ruta.
>
> - CanLoad: Controla si una ruta puede incluso cargarse. Esto se vuelve útil para los módulos de funciones que tienen carga diferida. Ni siquiera se cargarán si el guard devuelve falso.
>
> - CanDeactivate: Controla si el usuario puede salir de una ruta. Esta protección no impide que el usuario cierre la pestaña del navegador o navegue a una dirección diferente. Solo evita acciones desde la propia aplicación.
>
> #### e) ¿Qué es la carga Lazy de los módulos de Angular? ¿Cómo se configura en Angular la carga Lazy? ( https://angular.io/guide/lazy-loading-ngmodules )
>
> De forma predeterminada, los NgModules se cargan rapidamente, lo que significa que tan pronto como se carga la aplicación, también lo hacen todos los NgModules, sean o no inmediatamente necesarios. Para aplicaciones grandes con muchas rutas, es bueno utilizar la carga lazy o lazy loading, un patrón de diseño que carga NgModules según sea necesario. El lazy loading ayuda a mantener los tamaños de paquetes iniciales más pequeños, lo que a su vez ayuda a reducir los tiempos de carga.
>
> Hay dos pasos principales para configurar un módulo con carga diferida:
>
> 1. En los archivos RoutingModule de los distintos módulos añadir la ruta al componente.
>
> 2. Dentro del archivo AppRoutingModule, usar loadChildren (en lugar de componente) para configurar las rutas a los distintos módulos de la aplicación.
>
> #### f) ¿Qué es/para qué son útiles los middlewares en el contexto de node.js? ¿Dónde estás usando middlewares en nuestra aplicación?
>
> Las funciones de middleware son funciones que tienen acceso al objeto de solicitud (req), el objeto de respuesta (res) y la función next de middleware en el ciclo de solicitud-respuesta de la aplicación. La función next de middleware se indica comúnmente mediante una variable llamada next.
>
> Ejemplo de funcion middleware:
>
> - Middleware de autenticación
Supongamos que tenemos cinco rutas getUsers,getDetails,updateDetails,isLoggedIn,isLoggedOut. Cada ruta debe autenticarse si el usuario no está autenticado, entonces no puede llamar a las rutas mencionadas anteriormente, por lo que cada llamada GET, POST requiere autenticación. En este caso, creamos un middleware de autenticación.
>
> Este ejemplo sería a nivel de aplicación, pero tenemos middlewares tambien a nivel de router, manejo de errores, o middlewares de terceros.
