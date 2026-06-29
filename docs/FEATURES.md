
Descripción funcional de cada sección dentro del portfolio

---

## Navegación

Barra de navegación del portfolio

- Siempre visible, se esconde si el usuario deja de scrollear y vuelve a salir cuando detecta movimiento.
- Lo único que bajara junto con el contenido es la barra de navegación, los demás elementos del header (logo e icono para modificar el tema) se quedarán en la parte superior del sitio.
- Clic al logo e icono de home regresa al usuario a Hero Section
- La navegación será a las siguientes páginas en orden: About - Blog - Writeups - Projects

---

## Hero

Muestra información relevante sobre el usuario, incluye:

### Presentación

- Etiqueta llamativa `whoami` por encima de todo el contenido 
- Nombre, titulo y una breve descripción
- Botones de acción:
	- Download CV: Al dar clic se abre otra página mostrando el PDF de su CV
	- Contact Me: Botón que al dar clic te manda a la sección de contacto
	- Github Icon: Al dar clic abre otra pestaña con el perfil de github del usuario
	- In Icon: Al dar clic abre otra pestaña con el perfil de linkedin del usuario

### Avatar + Estadísticas

- Avatar del usuario
- Total de vulnerabilidades reportadas por el usuario
- Total de writeups y certificados en el sitio

---

## About

Página con información adicional sobre el usuario

- Muestra el avatar del usuario y una descripción más completa sobre el
- Muestra la experiencia del usuario, ordenada por más reciente
- Se muestran solamente los últimos tres trabajos agregados en la experiencia, y un botón de `See All` para mostrar los demás trabajos dentro de la misma página
- La experiencia se muestra en cards con el titulo, la empresa, el periodo y una descripción
- Muestra las skills del usuario agrupadas en cuatro categorías:
	- Offensive: Todas las aptitudes o conocimiento ofensivo del usuario
	- Tools: Todas las herramientas que sabe usar el usuario
	- Languages: Todos los lenguajes de programación que usa el usuario
	- Extra: Todas las aptitudes no relacionadas a pentesting del usuario
- Las aptitudes se muestran en forma de tags incluyendo un icono y el nombre
- Cada categoría tiene un icono por defecto por si la aptitud no tiene uno propio

---

## Certifications

Galería de certificados obtenidos por el usuario. 

- Muestra cards con imagen, título, academia y fecha 
- Al hacer hover en la card se muestra un texto que indica que al hacer clic te redirecciona al post relacionado con el certificado
- En la galería se muestran ordenados por fecha, mostrando los más recientes primero 
- En la landing se muestran solo los certificados seleccionados por el usuario
- Sólo se puede acceder a la galería desde el botón en la sección de la landing

---

## Writeups

Galería de writeups realizados por el usuario

- Muestra cards con plataforma, nivel, titulo, os, fecha, tecnologías usadas y tiempo de lectura
- El orden por defecto de los writeups es por fecha, mostrando los más recientes primero, de la misma manera en la landing, mostrando los tres más recientes
- El tiempo de lectura se obtiene por el contenido del writeup
- Buscador que filtra writeups por el titulo
- Filtros para cada detalle importante en el writeup:
	- Platform: Filtra por la plataforma de la máquina
	- Difficulty: Filtra por la dificultad de la máquina
	- OS: Filtra por el sistema operativo de la máquina 
	- Category: Filtra por la categoría de la máquina Ej. active directory, buffer overflow
- Los filtros deben de stackearse, si se tiene un filtro de platform y difficulty se filtran los writeups respetando ambos filtros
- El buscador respeta los filtros seleccionados
- Botón para reiniciar filtros, devuelve tanto el buscador cómo los filtros a su estado base

### Detalles del writeup

Página dedicada a cada writeup para ver todo su contenido / experiencia 

- Muestra una portada con todos los elementos de la card
- Botón que te redirecciona a la máquina dentro de la plataforma
- Contenido como archivo markdown ocupando la mayoría del espacio
- Barra lateral para navegar entre los títulos del contenido

---

### Blog

Galería de posts realizados por el usuario

- Muestra cards con un titulo, breve descripción, tipo de post y fecha 
- El orden por defecto de los blogs es por fecha mostrando los más recientes primeros, de la misma manera en la landing, mostrando los tres más recientes
- Filtros para el tipo de post:
	- All: Para mostrar todos
	- Certifications: Para mostrar los que hablen de la obtención de un certificado
	- Tutorials: Para mostrar los tutoriales
	- Opinions: Para mostrar los que son sobre una opinion

### Post

Página dedicada a cada post realizado 

- Muestra una portada 
- Contenido como archivo markdown ocupando la mayoría del espacio
- Barra lateral para navegar entre los títulos del contenido

---

## Projects

Galería de proyectos del usuario

- Muestra cards con nombre, breve descripción y tecnologías
- Al dar clic te redirecciona al repositorio del proyecto en github
- En la galería se muestran ordenados por fecha, mostrando los más recientes primeros
- En la landing se muestran los tres proyectos seleccionados por el usuario

---

## Contact 

Sección de contacto del usuario

- Muestra un titulo para la sección
- Una breve descripción de cómo trabaja el usuario
- Un botón mostrando el email + copiar
- Un botón de `Send Email` que redirecciona directamente a outlook u otra aplicación de mensajería 

---

## Footer

Funciona para dar un fin visual a las páginas del sitio y mostrar contacto nuevamente

- Muestra logo y nombre del usuario
- Muestra enlaces a Github y LinkedIn del usuario en forma de iconos

---

## Compartido

Elementos compartidos de las secciones

- Botón de `View All..` mostrado en las secciones de certifications, writeups, posts y projects que redirecciona a la galería indicada al dar clic
- Botón de `Show More` mostrado en las galerías de certifications, writeups, posts y projects que muestra más elementos dentro de la galería, incrementando de nueve en nueve