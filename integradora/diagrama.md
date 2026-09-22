# DIAGRAMA DE CLASES – PARQUEO TORRE CENTRAL

**Nombre:** Noelia Huanca M.  
**Materia:** Arquitectura de Software  
**Evaluación Integradora – Variante B**

```mermaid
classDiagram
direction TB

class Vehiculo {
    +placa : String
    +tipo : String
}

class Estadia {
    +fechaEntrada : DateTime
    +fechaSalida : DateTime
    +horas : int
    +total : decimal
    +calcularTotal()
    +cambiarEstado()
}

class EstadoEstadia {
    <<enumeration>>
    EnCurso
    PorPagar
    Pagada
    Anulada
}

class Tarifa {
    +precioHora : decimal
}

class Portero {
    +registrarEntrada()
    +registrarSalida()
}

class Administrador {
    +ajustarTarifa()
    +anularEstadia()
    +generarReporte()
}

class Aviso {
    +enviarAviso()
}

class ReporteMensual {
    +generarIngresosPorTipo()
}

Vehiculo "1" --> "0..*" Estadia : tiene
Estadia --> EstadoEstadia : estado
Estadia --> Tarifa : usa

Portero --> Estadia : registra
Administrador --> Tarifa : ajusta
Administrador --> Estadia : anula
Administrador --> ReporteMensual : genera

Estadia --> Aviso : mas de 24 horas

note for Vehiculo "Noelia Huanca M."
```

### Nota

Diagrama realizado a partir de los requerimientos del caso, identificando las clases, métodos y relaciones principales.

