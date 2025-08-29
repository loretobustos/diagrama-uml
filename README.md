# diagrama-uml


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
