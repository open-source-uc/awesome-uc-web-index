# awesome-uc-web-index
Index to display projects on awesome-uc

Este repo tiene como finalidad la actualización dinámica de la página: [awesome.osuc.dev](https://awesome.osuc.dev)

Se manejan las siguientes categorías y sub-categorías:

```txt
awesome-uc/
├── Proyectos/
│   ├── Aplicaciones y Software/        # Apps web, móviles, extensiones (ej: directUC)
│   └── Herramientas de Dev/         # Scripts, APIs, scrapers, librerías
│
├── Social/
│   ├── Comunidades Digitales/       # Servidores de Discord, Telegram, Slack (Gaming, Grupos de alumnos, etc)
│   ├── Organizaciones/              # Centros de Alumnos, Iniciativas Estudiantiles
│   └── Recreación y Eventos/        # Hackathons, ferias, clubes de hobbies (eventos recurrentes)
│
└── Documentos/
    ├── Apuntes y Material/          # Wikis, Centrales de Apuntes
    └── Plantillas (Templates)/      # LaTeX, Beamer, informes de práctica
```

Cada categoría debe cumplir con un json personalizado, para más detalles se puede ver las plantillas de información en `./templates`.

Esta es la estructura del índice:

```txt

awesome-uc-data/
├── projects/
│   ├── web/
│   │   └── direct-uc/
│   │       ├── metadata.json       <-- Datos específicos del proyecto
│   │       └── media/              <-- Logo o screenshots
│   └── tools/
│       └── ucalendar/
│           └── metadata.json
├── social/
│   └── comunidades/
│       └── open-source-uc.json     <-- Aquí pueden ser solo archivos JSON directos
└── docs/
    └── IIC2233/
        ├── metadata.json
        └── resources/
            └── preview.webp

```

## Especificación de Metadatos: Awesome UC

Este documento define la estructura de los archivos `metadata.json` para las tres categorías principales del repositorio. 

---

### 1. Proyectos (`projects`)

Recursos de software, hardware o herramientas funcionales.

| Campo | Tipo | Estado | Descripción |
| :--- | :--- | :--- | :--- |
| `name` | String | **Obligatorio** | Nombre oficial del proyecto. |
| `authors` | Array | **Obligatorio** | Lista de creadores (Nombre o @usuario de GitHub). |
| `description` | String | **Obligatorio** | Explicación breve de la utilidad del proyecto. |
| `repo` | String | **Obligatorio*** | URL del repositorio (obligatorio si no hay `url`). |
| `url` | String | **Obligatorio*** | URL de la landing page o demo (obligatorio si no hay `repo`). |
| `download` | String | **Opcional** | Link directo a descarga (ej. Chrome Store, APK, Release). |
| `image` | String | **Opcional** | Nombre del archivo en `media/`. Si es `null`, se usa la imagen de GH. |

#### Plantilla JSON:
```json
{
  "name": "Nombre del Proyecto",
  "authors": ["@user1", "Nombre Real"],
  "description": "Descripción del proyecto.",
  "repo": "https://github.com/user/repo",
  "url": "https://proyecto.com",
  "download": null,
  "image": "logo.png"
}
```

---

### 2. Social (`social`)

Comunidades, grupos de estudio y organizaciones.

| Campo | Tipo | Estado | Descripción |
| :--- | :--- | :--- | :--- |
| `name` | String | **Obligatorio** | Nombre de la comunidad o grupo. |
| `authors` | Array | **Obligatorio** | Administradores o responsables. |
| `description` | String | **Obligatorio** | Propósito del grupo y reglas de acceso. |
| `url` | String | **Obligatorio*** | Link de invitación o sitio web (obligatorio si no hay `repo`). |
| `repo` | String | **Obligatorio*** | Link al repo si la comunidad es abierta (obligatorio si no hay `url`). |
| `download` | String | **Opcional** | Enlace a recursos adicionales. |
| `image` | String | **Opcional** | Logo o banner personalizado del grupo. |

#### Plantilla JSON:
```json
{
  "name": "Comunidad Ejemplo",
  "authors": ["Admin"],
  "description": "Espacio para compartir recursos.",
  "url": "https://discord.gg/ejemplo",
  "repo": null,
  "download": null,
  "image": null
}
```

---

### 3. Documentos (`docs`)

Apuntes, plantillas y guías de estudio.

| Campo | Tipo | Estado | Descripción |
| :--- | :--- | :--- | :--- |
| `name` | String | **Obligatorio** | Título del documento o material. |
| `authors` | Array | **Obligatorio** | Creadores del contenido. |
| `description` | String | **Obligatorio** | Resumen del contenido (ej. "Apuntes de Cálculo I"). |
| `repo` | String | **Obligatorio*** | URL del repositorio (obligatorio si no hay `url`). |
| `url` | String | **Obligatorio*** | URL de visualización (obligatorio si no hay `repo`). |
| `resource_image`| String | **Obligatorio** | Nombre del archivo **.webp** ubicado en la carpeta `/resources/`. |
| `download` | String | **Opcional** | Link directo de descarga del archivo. |

#### Plantilla JSON:
```json
{
  "name": "Apunte de Programación",
  "authors": ["@estudianteUC"],
  "description": "Resumen completo del curso IIC1103.",
  "repo": "https://github.com/user/apuntes",
  "url": "https://notion.so/apunte-ejemplo",
  "resource_image": "preview-apunte.webp",
  "download": "https://github.com/user/apuntes/archive/main.zip"
}
```
