# RigPulse Win11

> **Próximamente:** Aplicación visual de escritorio, gratuita, open-source y basada en evidencia para **auditar, diagnosticar, limpiar de forma segura y optimizar cualquier PC con Windows 11 — siempre bajo decisión total del usuario**.

---

## ¿Qué hace diferente a RigPulse Win11?

La mayoría de los "optimizadores" y *debloaters* de Windows aplican decenas de cambios ocultos a ciegas, mezclan mejoras reales con trucos placebo (*snake-oil*), rompen Windows Update o Microsoft Store y no permiten volver atrás con exactitud.

**RigPulse Win11** cambia el enfoque por completo:

- **App visual interactiva (Tú tienes el control absoluto):** Nada se ejecuta sin tu permiso. Desde la interfaz gráfica podrás revisar el diagnóstico completo de tu equipo por categorías, **elegir casilla por casilla qué quieres limpiar u optimizar y qué prefieres no tocar**, ver la explicación técnica (beneficio real vs. riesgo) de cada ajuste y ejecutar una simulación (*Dry Run*) antes de aplicar nada.
- **Adaptado a cada hardware:** Reconoce automáticamente si usas **Intel híbrido (P/E cores)**, **AMD Ryzen / X3D**, **NVIDIA** o **AMD Radeon**, SSD **NVMe** o **SATA**, evitando aplicar en un equipo ajustes pensados para otro distinto.
- **Independiente del idioma:** Funciona por igual en Windows 11 en español, inglés o cualquier idioma usando APIs CIM, XML, GUIDs y palabras clave de registro.

---

## 1. Qué Podrá Auditar y Optimizar

### Diagnóstico de Hardware y Configuración Real
- **Memoria RAM:** Comprueba canales (Dual/Single Channel) y si tu perfil **XMP / EXPO** está realmente activado o corriendo lento a velocidad base JEDEC.
- **Tarjeta Gráfica y PCIe:** Verifica si **Resizable BAR (`BAR1`)** está activo o apagado en BIOS, ancho de enlace PCIe, estado de **HAGS**, **VRR**, *Optimizaciones para juegos en ventana* (*Flip Model*), **MPO** (*Multi-Plane Overlay*) y soporte de **DirectStorage (`BypassIO`)**.
- **Almacenamiento y Salud SSD:** Detecta discos NVMe/SATA, desgaste, temperatura, alineación de particiones y estado de `TRIM`.
- **Seguridad sin compromisos:** Audita `Secure Boot`, `TPM`, `Windows Defender` y **VBS / HVCI (Aislamiento de núcleo)** mostrando siempre el equilibrio real entre seguridad, requisitos de *anti-cheats* y rendimiento.

### Optimización Real y Reversible
- **Energía y CPU (`powercfg`):** Clona tu plan de energía (sin modificar el original de fábrica) para corregir estados mínimos al 100 % en reposo, ajustar `EPP`, *Boost Mode* y *Core Parking* según la topología real de tu procesador.
- **Segundo Plano y Arranque:** Mide el tiempo exacto de inicio de Windows (`Event ID 100–103`) y muestra qué aplicaciones o drivers lo frenan; detecta servicios pesados de terceros (bases de datos, *updaters*, overlays, software RGB, audio virtual) para pasarlos a `Manual` sin romper funciones de Windows, y permite deshabilitar tareas programadas redundantes guardando su respaldo XML.
- **Red Cableada / Wi-Fi:** Evalúa ahorros de energía (`Green Ethernet` / `EEE`), moderación de interrupciones y `RSS` (actuando solo ante síntomas medibles, sin falsos trucos de ping).
- **Detector de "Snake-Oil" y Tweaks Dañinos:** Identifica ajustes placebo o perjudiciales aplicados por guías viejas de Internet (HPET forzado en `bcdedit`, archivo de paginación desactivado, limpiadores de *standby RAM*, deshabilitación de mitigaciones o servicios críticos) y permite revertirlos.

---

## 2. Qué Podrá Limpiar de Forma Segura (Por Niveles de Riesgo)

Cada bloque de limpieza muestra exactamente **cuántos MB/GB ocupa** y te deja decidir qué incluir:

1. **Nivel 1 — Limpieza Segura (Cero impacto funcional):**
   - Análisis real del almacén de componentes **`WinSxS`** (`DISM /AnalyzeComponentStore`, sin los números inflados del Explorador).
   - Caché de descargas antiguas de **Windows Update**, *Delivery Optimization* y `Windows.old` (superados los días de seguridad).
   - Archivos temporales viejos (> 7 días, saltando cualquier archivo en uso sin cerrar programas), reportes WER y volcados de memoria antiguos (conservando evidencia si hubo errores recientes).
   - Limpieza de **paquetes de drivers antiguos/duplicados en `DriverStore`** (`pnputil`), manteniendo siempre intacto el driver activo + 1 versión anterior de respaldo.

2. **Nivel 2 — Limpieza Opcional (Con aviso claro de trade-off):**
   - Cachés acumuladas de **shaders GPU** (`NVIDIA DXCache/GLCache`, `AMD DxCache`, `DirectX D3DSCache`) y cachés de launchers/apps (`Steam`, `Discord`, etc.), advirtiendo cuándo conviene limpiarlas y cuándo evitarlo para no recompilar shaders.
   - Ajuste inteligente de **`hiberfil.sys`** (modo reducido manteniendo *Inicio rápido*, o desactivado en PCs de escritorio para recuperar varios GB).
   - **Compresión transparente NTFS (`LZX`)** para juegos o apps pesados de uso poco frecuente (excluyendo automáticamente juegos que usen DirectStorage).

3. **Nivel 3 — Restos Huérfanos y Reporte de Espacio (Cuarentena + Privacidad):**
   - Detecta **carpetas huérfanas** de programas que ya desinstalaste y tareas/accesos rotos, moviéndolos primero a una **Cuarentena de 14 días** (restaurables en 1 clic si hicieran falta) antes de permitir la purga definitiva.
   - Puede detectar instalaciones sin uso y archivos grandes/duplicados **solo en las rutas que tú elijas**, sin leer documentos personales, sin descargar archivos en la nube de **OneDrive** y excluyendo siempre datos privados de navegadores.

---

## 3. Seguridad, Rollback y Medición `Antes vs. Después`

- **Simulación previa (`Dry Run`):** Antes de modificar nada, la app te muestra la vista previa exacta del plan.
- **Rollback LIFO Transaccional:** Toda modificación de registro, servicio, tarea, red o plan de energía guarda su estado previo exacto (incluyendo si una clave **no existía antes**, para eliminarla al revertir) en un manifiesto de reversión paso a paso.
- **Comprobación Real con Datos:** Mide espacio recuperado, huella de RAM/procesos en reposo, tiempo de arranque y métricas de rendimiento en juegos (`FPS promedio`, `1 % / 0,1 % low`, `frametime`, `GPUBusy` y temperatura) para verificar matemáticamente si cada cambio mejoró tu equipo.
- **Límites claros:** Nunca modifica parámetros internos de la BIOS (solo comprueba desde Windows si XMP o Resizable BAR están activos y te guía si hace falta activarlos manualmente).

---

## Estado del Proyecto

🚧 **En desarrollo / Arquitectura en validación.** El motor central PowerShell (auditoría estática modular, cuarentena y rollback transaccional) se encuentra en fase de pruebas privadas antes de construir la interfaz visual y lanzar la versión pública v1.0 para cualquier PC.
