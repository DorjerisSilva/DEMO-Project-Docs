# Esquema de Base de Datos - LEXI: Aprende sin límites

_¿Cuáles son las entidades principales y relaciones en tu modelo de datos?_

---

## Diagrama ER

```mermaid
erDiagram
  USUARIO {
    int id
    string nombre
    string correo
    string idioma_nativo
    string nivel_actual
  }
  LECCION {
    int id
    string idioma
    string nivel
    string titulo
    string contenido
  }
  PROGRESO {
    int id
    int usuario_id
    int leccion_id
    string estado "completada | en progreso"
    datetime fecha_ultimo_acceso
  }
  USUARIO ||--o{ PROGRESO : tiene
  LECCION ||--o{ PROGRESO : es_parte
```
<small>(Diagrama adaptado para LEXI. Agrega más entidades según crezca el proyecto.)</small>

---

## Descripción

En LEXI, la entidad principal es el USUARIO, quien puede acceder a múltiples LECCIONES de diferentes idiomas y niveles. El PROGRESO registra qué lecciones ha iniciado o completado cada usuario, permitiendo personalizar la experiencia y sincronizar el avance entre dispositivos. Por ejemplo, una estudiante puede comenzar una lección de inglés nivel básico y continuarla más tarde desde otro dispositivo, manteniendo su progreso actualizado. Esta estructura soporta funcionalidades como acceso offline, retroalimentación inmediata y adaptación al nivel del usuario, alineadas con las historias de usuario y requerimientos del proyecto.

<small>Agrega más entidades y relaciones a medida que tu proyecto crezca.</small>
