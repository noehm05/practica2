# DIAGRAMA DE CLASES – PARQUEO TORRE CENTRAL

**Nombre:** Noelia Huanca M.  
**Materia:** Arquitectura de Software  
**Evaluación Integradora – Variante B**

```mermaid
classDiagram
direction LR

class Vehiculo {
    +placa : String
    +tipo : String
}

class Estadia {
    +idEstadia : int
    +fechaEntrada : DateTime
    +fechaSalida : DateTime
    +horas : int
    +total : decimal
    +calcularPago()
}

class EstadoEstadia {
    <<enumeration>>
    EnCurso
    PorPagar
    Pagada
    Anulada
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

class Tarifa {
    +tipoVehiculo : String
    +precioHora : decimal
}

class Aviso {
    +enviarAviso()
}

class ReporteMensual {
    +generarIngresosPorTipo()
}

Vehiculo "1" --> "0..*" Estadia : registra
Estadia --> EstadoEstadia : tiene
Estadia --> Tarifa : calcula
Portero --> Estadia : registra
Administrador --> Tarifa : ajusta
Administrador --> Estadia : anula
Administrador --> ReporteMensual : genera
Estadia --> Aviso : aviso >24h

note for ReporteMensual "NOELIA HUANCA MAMANI"
```

### Nota

Diagrama realizado a partir de los requerimientos del caso, identificando las clases, métodos y relaciones principales.

