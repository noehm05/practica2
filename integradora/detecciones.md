# Detecciones SOLID

## 1. SRP – Responsabilidad Única

**Dónde:** En `GestorDeEstadias`, dentro de `RegistrarSalida()`.

**Por qué:** Vi que esta clase está haciendo varias cosas juntas: calcula el precio, guarda la estadía, muestra el ticket y manda el mensaje por WhatsApp. Por eso no tiene una sola responsabilidad y se puede separar mejor.

## 2. OCP – Abierto/Cerrado

**Dónde:** En el `switch` que está dentro de `RegistrarSalida()`.

**Por qué:** Para agregar otro tipo de vehículo tendría que entrar y modificar ese `switch`. La idea de OCP es poder agregar nuevas opciones sin tener que cambiar el código que ya está funcionando.

## 3. DIP – Inversión de Dependencias

**Dónde:** En `GestorDeEstadias`, cuando usa `new BaseDeDatosParqueo()` y `new WhatsAppDelEdificio()`.

**Por qué:** El gestor está dependiendo directamente de esas clases. Si después quisiera cambiar la forma de guardar los datos o enviar los mensajes, tendría que modificar el gestor. Sería mejor trabajar con interfaces o abstracciones.

