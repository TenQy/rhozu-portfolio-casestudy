
Tipos de contenido definidos en Sanity Studio

---

## Global Config

Singleton - Configuración de datos globales del sitio, consumidos por Hero, NavBar y Footer principalmente

- **name** `string` not null - Nombre del usuario, requerido para Hero y Footer
- **email** `string` not null - Correo del usuario, requerido para Hero y Footer
- **github** `url` not null - Enlace al github del usuario, requerido para Hero y Footer
- **linkedin** `url` not null - Enlace al linkedin del usuario, requerido para Hero y Footer
- **logo** `image` not null - Logo del usuario, requerido para Header y Footer
- **avatar** `image` not null - Avatar del usuario, requerido para Hero y About

La configuración global del schema sirve para variables o información que se repite o se va a repetir en al menos dos lugares distintos dentro del portfolio.

---

## Hero Section

Singleton - Información visible en el apartado principal del portfolio

- **title** `string` not null - Titulo del usuario 
- **description** `text` not null - Descripción breve del usuario
- **cv** `file` not null - PDF con el CV del usuario
- **vulns** `number` not null - Vulnerabilidades reportadas por el usuario

Aunque el hero section también incluya Nombre o Avatar, estos se guardan en la configuración global para evitar repetirlos.

---

## About Section

Singleton - Información visible dentro de la página de 'Sobre mí' del usuario

- **description** `text` not null - Sobre mí del usuario
- **experience** `array of object` nullable - Lista de experiencias laborales
	- **title** `string` not null - Titulo del puesto
	- **company** `string` not null - Nombre de la empresa
	- **period** `string` not null - Periodo del empleo
	- **description** `text` not null - Descripción del puesto
- **skills** `array of object` not null - Lista de habilidades del usuario
	- **name** `string` not null - Nombre de la habilidad
	- **category** `string list` not null - Categoría de la habilidad
		- Opciones: `offensive` `tools` `language` `extra`

La experiencia del usuario es una lista de objetos ya que se busca poder agregar distintos trabajos que ha tenido y cada uno requiere su propia información.

Las skills requieren de una categoría para que se agrupen bien en la UI. La opción de extra es para aptitudes no relacionadas con las demás pero que pueden ser importantes Ej. Inglés B1.

---

## Certifications 

Document type - Elemento con información para agregar, editar y eliminar certificados dentro del portfolio 

- **title** `string` not null - Titulo del certificado
- **image** `image` not null - Imagen del certificado
- **date** `date` not null - Fecha del certificado
- **academyUrl** `url` not null - Enlace al certificado dentro de la academia
- **academy** `string` not null - Nombre de la asociación/academia del certificado
- **relatedPost** `reference -> Post` nullable - Post relacionado con la experiencia del certificado
- **featured** `boolean` not null default false - Flag para saber si mostrar en landing o no

En la landing se muestran los tres certificados más valiosos, el usuario deberá poder modificar cuales quiere que se muestren activando el campo featured.

---

## Writeups 

Document type - Elemento con información para agregar, editar y eliminar writeups dentro del portfolio

- **platform** `string list` not null - Plataforma dónde se realizó la máquina
	- Opciones: `HackTheBox` `TryHackMe`
- **level** `string list` not null - Nivel de la máquina realizada
	- Opciones: `Easy` `Medium` `Hard` `Insane`
- **title** `string` not null - Titulo de la máquina 
- **os** `string list` not null - Sistema operativo de la máquina
	- Opciones: `Windows` `Linux`
- **date** `date` not null - Fecha de la máquina
- **techniques** `array of string` not null - Técnicas y tecnologías utilizadas Ej. `XSS` `LFI`
- **slug** `slug` not null - Enlace a los detalles del writeup
- **cover** `image` not null - Imagen con los detalles del writeup
- **platformUrl** `url` not null - Enlace a la máquina dentro de la plataforma
- **content** `portableText` not null - Archivo md con el contenido de lo realizado

---

## Posts 

Document type - Elemento con información para agregar, editar y eliminar posts dentro del portfolio

- **title** `string` not null - Titulo del post
- **description** `text` not null - Breve descripción del post
- **category** `string list` nullable - Tipo de post
	- Opciones: `Certification` `Opinion` `Tutorial`
- **cover** `image` not null - Portada del post 
- **content** `portableText` not null - Contenido del Post
- **slug** `slug` not null - Enlace al post

---

## Projects

Document type - Elemento con información para agregar, editar y eliminar proyectos dentro del portfolio

- **title** `string` not null - Titulo del proyecto
- **description** `text` not null - Descripción del proyecto
- **technologies** `array of string` not null - Tecnologías usadas Ej. `Python` 
- **repository** `url` not null - Enlace al repositorio del proyecto
- **featured** `boolean` not null default false - Flag para saber si mostrar proyecto en la landing

---

## Contact Section

Singleton - Resumen de contacto 

- **title** `string` not null - Titulo de la sección
- **description** `text` not null - Breve descripción de cómo trabaja el usuario

El email se obtiene de la configuración global para evitar duplicados
