# diagrama-uml

Clases principales para el diagrama UML:

Paquete

peso: float

dimensiones: string (o una clase aparte si quieres ser más detallado)

valorDeclarado: float

Cliente

nombre: string

dirección: string

teléfono: string

Envío

idEnvio: int

estado: string (ejemplo: "En tránsito", "Entregado", "Devuelto")

fechaSolicitud: Date

fechaEntrega: Date (opcional)

paquete: Paquete

cliente: Cliente

repartidor: Repartidor

Repartidor

idRepartidor: int

nombre: string

teléfono: string

Relaciones entre clases:

Un Cliente puede realizar muchos envíos (1 a muchos).

Un Envío está asociado a un solo Paquete.

Un Envío es gestionado por un solo Repartidor.

Un Repartidor puede gestionar muchos envíos.

Notación rápida para Visio:

Clases representadas como rectángulos con tres secciones: nombre, atributos y métodos (en este caso sólo atributos).

Relación 1..* entre Cliente y Envío.

Relación 1..1 entre Envío y Paquete.

Relación 1..* entre Repartidor y Envío.

Cliente
------------
- nombre: string
- dirección: string
- teléfono: string
------------
+ realizarEnvio()

1 ---------------------- * 
                        Envío
                        ------------
                        - idEnvio: int
                        - estado: string
                        - fechaSolicitud: Date
                        - fechaEntrega: Date
                        ------------
                        + actualizarEstado()

                        1 -------------- 1
                                         Paquete
                                         ------------
                                         - peso: float
                                         - dimensiones: string
                                         - valorDeclarado: float
                                         ------------

Repartidor
------------
- idRepartidor: int
- nombre: string
- teléfono: string
------------
1 --------------------- *
                        Envío
