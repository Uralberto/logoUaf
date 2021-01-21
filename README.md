
# **logoUaf**

Proyecto de logo personal con el uso de la etiqueta *SVG* como contenedor de los cuatro elementos que lo conforman. Se listan a continuación con sus id.

- Anillo externo  (anilloExterno)
- Letra A (letra-A)
- Brazo letra U  (brazo-letra-U)
- Parte baja de la letra U  (parte-baja-letra-U)

Inicialmnte todos los elementos, salvo el anillo externo, tienen la misma animación. Se llama  *animacionLogoGeneral*. Hace que los elementos lleguen desde el exterior del contenedor a su posición final dentro de este.

Seguidamente, a cada elemento se aplica una animación diferente pero con un mismo propósito. Los desaparece inicialmente por un tiempo muy breve y luego surgen de nuevo, progresivamente. Para crear el efecto de pintado progresivo de los contornos de la formas  se usan las propiedades *stroke-dasharray* y *stroke-dashoffset*.  

El *stroke-dasharray*  define el patrón de rayas utilizado para pintar el contorno de la forma. El *stroke-dashoffset* es el espacio entre estas. Si el *stroke-dasharray* es igual a la longitud total del contorno de la forma, esta se verá continua. Por su parte, si el *stroke-dashoffset* es igual a la longitud total del contorno de la forma, esta no se verá. De manera que si una animación inicia con  *stroke-dashoffset*  igual a la longitud total del contorno de la forma y a su vez termina con un valor igual  cero, entonces se verá crecer progresivamente. 

El efecto de progresividad, en este proyecto,  termina al mismo tiempo en todos los elementos.

El método *getTotalLength()* de *javascript* permite obtener la longitud del  contorno de las formas. Dicho valor es considerado para el inicio de cada animación, es decir, el primer *keyframe*. Se aplica a la propiedad *stroke-dashoffset*. En el *keyframe* final se  asigna el valor de cero a la misma propiedad. Estos son los *keyframes* para *animacionLetraA*:

*keyframes animacionLetraA {
    from {
        stroke-dashoffset: 452px;
    }
    to {
        stroke-dashoffset: 0;
    }
}*

El valor 452px se obtiene con el método *getTotalLength()*, como ya se dijo.

Finalmente, se anima  la letra A (la insinua el triangulo azul) con un efecto de rotación. Empieza con la hipotenusa posicionada de manera manera horizontal, luego gira en sentido horario, por un segundo,  simulando un  movimiento similar a la  manecilla del segundero de un reloj. El efecto de rotación se logra insertando  el  *path*  de la letra A dentro de una etiqueta *g*. No funciona si la animación se aplica directamente al selector del *path*.







