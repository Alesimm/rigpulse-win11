# RigPulse Win11

> **Próximamente:** Suite modular, gratuita, transparente y basada en evidencia para **auditar, diagnosticar, limpiar de forma segura y optimizar cualquier PC con Windows 11**.

---

## ¿Qué será este proyecto?

La mayoría de los "optimizadores" de Windows en Internet aplican trucos genéricos a ciegas (*snake-oil*), rompen Windows Update o Microsoft Store y no permiten volver atrás con exactitud.

**RigPulse Win11** nace como un proyecto **open-source** enfocado en ingeniería real para cualquier usuario y cualquier configuración de hardware (Intel / AMD, NVIDIA / AMD Radeon, portátiles o escritorio):

1. **Auditoría 100 % Solo Lectura primero (`Evidence-First`):**
   - Analiza hardware, perfil XMP/EXPO de RAM, Resizable BAR, plan de energía, salud de SSD/NVMe y TRIM, tiempos reales de arranque, servicios de terceros, programas de inicio, drivers obsoletos, postura de seguridad (VBS/HVCI) y espacio recuperable.
   - Independiente del idioma de Windows (español, inglés, etc.) usando XML, GUIDs y APIs CIM nativas.
2. **Cero trucos placebo (`Zero Snake-Oil`):**
   - Detecta ajustes dañinos o obsoletos heredados de guías antiguas (como forzar HPET, desactivar el archivo de paginación o limpiar la *standby list*).
   - Solo propone cambios justificados según el hardware detectado en cada equipo.
3. **Limpieza Segura con Cuarentena de 14 Días:**
   - Clasifica el espacio recuperable por niveles de riesgo (`WinSxS`, temporales, `DriverStore` antiguo, cachés de shaders, carpetas huérfanas de programas desinstalados).
   - Nunca toca carpetas personales ni descarga placeholders de la nube (OneDrive).
4. **Reversibilidad Total (`Rollback-First`):**
   - Todo cambio de configuración guarda el estado previo exacto (incluyendo si una clave del registro no existía) en un manifiesto LIFO para poder deshacerlo al instante.
5. **Verificación Matemática `Antes vs. Después`:**
   - Mide el impacto real en espacio libre, huella en reposo, tiempo de arranque y estabilidad de *frametime* (`FPS promedio`, `1 % low`).

---

## Estado del Repositorio

🚧 **En preparación.** La arquitectura central se está validando en entorno controlado antes de publicar la versión universal v1.0 para todo público.
