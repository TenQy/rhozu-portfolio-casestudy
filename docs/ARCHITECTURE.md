
Detalles importantes sobre la arquitectura y decisiones del proyecto

---

## Stack

- **Astro**: Framework principal  
- **Sanity**: CMS headless - gestión del contenido sin modificar código
- **Tailwind CSS**: Estilos 
- **Vercel**: Hosting y deploy automáticos

### Por qué este stack

- **Astro sobre Next.js**: Astro esta diseñado específicamente para sitios con contenido estático. Genera HTML puro sin JavaScript innecesario, lo que mejora el rendimiento
- **Sanity sobre otros CMS**: el cliente necesita poder editar su contenido sin la necesidad de tocar código. Sanity Studio ofrece una interfaz limpia donde el cliente puede agregar, editar y eliminar posts, writeups y proyectos por su cuenta.
- **Vercel**: integración directa con GitHub y despliegue gratuito. Combinado con el webhook de Sanity, el sitio se actualiza cuando el cliente publica o edita contenido.

---

## Flujo de datos

1. Cliente edita contenido en Sanity Studio
2. Sanity dispara webhook a vercel
3. Vercel ejecuta build de Astro
4. Astro hace fetch a la API de Sanity vía GROQ
5. Se genera HTML estático
6. Sitio publicado con contenido nuevo

---

## Estructura de carpetas

Base sobre la cual se va a trabajar para organizar los archivos

src/  
├── components/ — componentes reutilizables de UI  
├── layouts/ — layouts base compartidos entre páginas  
├── lib/  
│ ├── sanity.ts — cliente de Sanity y configuración  
│ └── queries/ — queries GROQ separadas por tipo de contenido  
├── pages/ — rutas del sitio, una carpeta por sección  
└── styles/ — estilos globales

sanity/  
├── schemaTypes/  
│ ├── index.ts — junta todos los schemas en un array y se exporta a sanity.config.ts  
│ └── (un archivo .ts por cada tipo de contenido)  
├── sanity.config.ts — configuración de Sanity Studio  
└── sanity.cli.ts — configuración de la CLI (projectId, dataset)

---

## Decisiones técnicas 

- **Queries separadas de los componentes** — las queries GROQ viven en `src/lib/queries/` y no dentro de las páginas o componentes. Si Sanity cambia un campo, solo se toca el archivo de queries. Si cambia el diseño, solo se toca el componente.  
- **Tailwind con design tokens** — los colores, tipografía y espaciado se definen una sola vez en `tailwind.config.mjs`. Los componentes consumen tokens, nunca valores directos. Cambiar un color es modificar una sola línea.

---

## Campos derivados

Datos que no se almacenan en Sanity sino que se calculan en build time: 

- **readingTime** — calculado desde el campo `content` de writeups y posts. Se estima a 200 palabras por minuto excluyendo bloques de código. 
- **writeupCount** — conteo total de documentos de tipo `writeup`, mostrado en las stats del Hero. 
- **certCount** — conteo total de documentos de tipo `certification`, mostrado en las stats del Hero.
