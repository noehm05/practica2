# Detecciones SOLID

## 1. SRP – Responsabilidad Única

**Dónde:** En la clase `GestorDeEstadias`, dentro de `RegistrarSalida()`.

**Por qué:** La clase tiene varias responsabilidades: calcula la tarifa, guarda la estadía, muestra el ticket y envía el mensaje por WhatsApp. Esto rompe SRP porque una clase debería encargarse de una sola responsabilidad principal.

---

## 2. OCP – Abierto/Cerrado

**Dónde:** En el `switch` de `RegistrarSalida()`, donde se definen las tarifas de cada tipo de vehículo.

**Por qué:** Si se quiere agregar otro tipo de vehículo, es necesario modificar el `switch`. Esto rompe OCP porque el sistema debería permitir agregar nuevos comportamientos sin modificar el código que ya funciona.

---

## 3. DIP – Inversión de Dependencias

**Dónde:** En `GestorDeEstadias`, al utilizar directamente `new BaseDeDatosParqueo()` y `new WhatsAppDelEdificio()`.

**Por qué:** El gestor depende directamente de clases concretas. Esto genera un acoplamiento fuerte. Lo correcto sería depender de abstracciones o interfaces para poder cambiar esas implementaciones con mayor facilidad.
