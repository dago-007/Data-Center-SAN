# Reporte Ejecutivo: Modernización de Infraestructura SAN
**Objetivo:** Selección de almacenamiento de alto rendimiento para flujos de trabajo de video (4K/8K), edición no lineal y archivo histórico.

---

## 1. Análisis de Mercado: Comparativa de Fabricantes

Para el entorno de medios, la prioridad es **Throughput (Ancho de banda)** y **Latencia Determinista** (evitar *dropped frames*). A continuación, la comparativa técnica y operativa:

| Característica | **Pure Storage** (Recomendado) | **Dell Technologies** | **IBM** |
| :--- | :--- | :--- | :--- |
| **Producto Clave** | **FlashArray //X** (Bloque) y **FlashBlade** (Archivos/Rápido) | **PowerStore** (SAN) y **PowerScale/Isilon** (NAS) | **FlashSystem** (Bloque/SAN) |
| **Filosofía** | *Simplicidad y Evergreen:* All-Flash siempre. Sin configuraciones complejas. | *Portafolio Amplio:* Tienen una herramienta específica para cada cosa, pero integrarlas es complejo. | *Ingeniería Pura:* Densidad y compresión por hardware (FlashCore Modules). |
| **Rendimiento en Video** | **Excelente.** Latencia plana y predecible. Ideal para edición en tiempo real sin "hipos". | **Bueno.** PowerScale es el estándar en NAS, pero PowerStore (SAN) puede sufrir con deduplicación agresiva. | **Muy Bueno.** Alta velocidad bruta, aunque la interfaz de gestión es menos intuitiva. |
| **Modelo de Renovación** | **Evergreen//Forever:** Cambio de controladoras gratis cada 3 años. **Sin migración de datos.** | **Tradicional / Anytime Upgrade:** Históricamente requiere "Forklift Upgrades" (migraciones costosas). | **Tradicional:** Ciclos de 5-7 años, requiere migración al final de la vida útil. |
| **Punto Débil** | Inversión inicial (CAPEX) puede parecer más alta que una solución híbrida. | Complejidad de gestión. Soporte técnico fragmentado entre líneas de producto. | Soporte técnico burocrático. Curva de aprendizaje alta para administradores. |

---

## 2. Estrategia Financiera: El Caso de Negocio "Evergreen"

El mayor riesgo financiero en almacenamiento de video es la **"Trampa de la Renovación Tecnológica"** en el año 5.

### La Diferencia de Modelos

1.  **Modelo Legacy (Dell/IBM Tradicional):**
    * Se compra el equipo. En el año 4 o 5, el soporte se vuelve impagable.
    * Se obliga a comprar un equipo nuevo y **recomprar la capacidad (TB)** que ya se tenía.
    * Se desperdician recursos en migración de datos.

2.  **Modelo Pure Storage (Evergreen):**
    * Suscripción plana.
    * El hardware se actualiza (controladoras nuevas) incluido en la anualidad.
    * Los discos (Almacenamiento) se mantienen. **Nunca vuelves a comprar el mismo Terabyte.**
  

### Comparativa Financiera: Modelo Tradicional vs. Pure Evergreen

| Concepto Financiero | Modelo Tradicional (Dell/IBM Legacy) | Pure Storage (Evergreen//Forever) |
| :--- | :--- | :--- |
| **Ciclo de vida del Activo** | 3 a 5 años (luego es **obsoleto**). | **10+ años** (se renueva por partes). |
| **Evento de Renovación** (Año 3/4) | *"Forklift Upgrade"*: Comprar caja nueva + **Recomprar capacidad**. | *"Non-disruptive Upgrade"*: Cambio de cerebro, **mantienes la capacidad**. |
| **Costo de Migración de Datos** | **Alto** (Horas extra, consultores, riesgo de downtime). | **Cero** (La actualización ocurre con los datos en vivo). |
| **Riesgo de Performance** | El equipo se **degrada** con el tiempo. | El equipo se vuelve **más rápido** con el tiempo (nuevas controladoras). |
| **Predictibilidad del Gasto** | **Picos violentos** de CAPEX cada 5 años. | **Costo plano y predecible** (OPEX/Suscripción) a lo largo del tiempo. |

### Visualización del Flujo de Caja (TCO)

A continuación, se presenta la proyección de gastos comparando ambos modelos. Nótese el "pico" de gasto cada 3 años comprando el modelo tradicional con Dell o IBM. Mientras con PureStorage con el pago de la suscripcion "Forever" anualmente los cambios de controladoras mantienen el equipo "inmortal". 
*Básicamente, con Pure estoy comprando un activo que se revaloriza, no un pasivo que se deprecia a cero en menos de 5 años.

<img width="1200" height="600" alt="Code_Generated_Image" src="https://github.com/user-attachments/assets/bf8ba6d9-f69c-4f08-b0a5-af7ad5e95b98" />


