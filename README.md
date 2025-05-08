# Calculadora de Parámetros de Simulación KiCad

Este proyecto provee los parámetros esenciales para configurar un análisis transitorio en KiCad o otros programas de simulación de circuitos, basándose en:

* **Frecuencia** de la señal (Hz)
* **Número de ciclos** a visualizar

---

## Funcionalidad principal

1. **Entrada de datos**

   * Campo **Frecuencia (Hz)**: valor numérico de la frecuencia de la señal (por ejemplo, 60).
   * Campo **Ciclos a visualizar**: número de ciclos completos que deseas ver en la simulación.

2. **Cálculos internos**

   * Calcula el **período** $T = 1 / f$ de la señal.
   * Multiplica el período por el número de ciclos para obtener el **tiempo total** de simulación.
   * Divide el período en 100 puntos para definir el **Time step** (resolución temporal).
   * Convierte unidades para mostrar:

     * **Time step** en microsegundos (µs)
     * **Final time** en milisegundos (ms)
     * **Initial time** fijado a 0 (s)
     * **Max time step** igual al Time step, en µs

3. **Visualización de resultados**

   * Tras pulsar **Calcular**, se muestran los valores listos para copiar en la directiva SPICE de KiCad:

     ```spice
     .tran <Time step> <Final time> <Initial time> <Max time step>
     ```

---

¡Listo para mejorar tu flujo de trabajo de simulación en KiCad!
