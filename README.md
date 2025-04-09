# Reporte Técnico de Errores 404 y Soft 404
#Contexto General: ¿Qué son, por qué ocurren y cómo corregirlos?

# 1. Error 404 (Página no encontrada)

## Qué es: Este error ocurre cuando un usuario intenta acceder a una página que no existe. El servidor responde con el código 404, lo que indica que la página no se encuentra.

Por qué ocurre: Sucede cuando se elimina una página o se cambia su URL sin redirigir correctamente a los usuarios a una página similar.

## Cómo corregirlo:

Redirigir la URL eliminada o modificada a una página relevante (por ejemplo, una categoría similar o la página de inicio) usando redirecciones 301.

Actualizar los enlaces internos que apuntan a esa página rota.

## Cómo evitarlo:

Antes de eliminar o cambiar una página, asegúrate de configurar una redirección 301.

Revisa regularmente las URLs de tu sitio web para detectar y corregir páginas rotas.

# 2. Soft 404 (Página que parece no existir, pero responde como si sí existiera)

Qué es: Aunque la página muestra un mensaje de error (como "Página no encontrada"), el servidor responde con un código 200 (lo que indica que la página sí existe). Esto confunde tanto a los usuarios como a Google.

Por qué ocurre: Suele suceder cuando se crean páginas de error personalizadas que devuelven un código 200, pero no tienen contenido útil, como cuando se elimina una página sin configurarla correctamente para mostrar un error 404.

## Cómo corregirlo:

Asegúrate de que las páginas eliminadas o que no existen devuelvan un código 404 real.

Si es necesario, crea una página de error 404 personalizada que sea clara para el usuario.

Cómo evitarlo:

Verifica que las páginas de error estén configuradas correctamente para devolver un código 404.

No permitas que páginas de error sean indexadas por los motores de búsqueda.

# 3. Redirecciones 300 (Redirección)

## Qué es: Los códigos 300 indican que la página solicitada ha sido redirigida a otra. Esto puede ser una redirección permanente (301) o temporal (302).

Por qué ocurre: Las redirecciones se utilizan cuando una página ha cambiado de dirección, pero puede que no siempre se configuren correctamente.

## Cómo corregirlo:

Verifica que las redirecciones estén configuradas correctamente y que los usuarios sean enviados a páginas relevantes.

Si una redirección lleva a una página de error, corrige la ruta de destino.

## Cómo evitarlo:

Asegúrate de que las redirecciones estén configuradas adecuadamente para enviar a los usuarios a páginas relevantes.

Revisa que las redirecciones no lleven a páginas de error o contenido irrelevante.










# Auditoría de Errores 404 y Soft 404 - C&A (www.cyamoda.com)

## Objetivo
El objetivo de esta auditoría ha sido identificar y corregir los **errores 404** y **soft 404** en el sitio web de C&A, así como las causas posibles de estos errores y teniendo como objetivo,  mejorar la salud técnica del sitio y asegurando una experiencia de usuario óptima. A través de esta acción, buscamos también **optimizar el rastreo y la indexación** de las páginas más relevantes para fortalecer el SEO y garantizar la mejor visibilidad posible en los motores de búsqueda.

---

## 1. Auditoría Inicial Realizada en Google Search Console

Se exportaron los **informes de errores 404** directamente desde Google Search Console, que representan las URLs que **Google aún está intentando rastrear**, pero que no existen o ya han sido modificadas sin una redirección adecuada. Este paso fue clave para identificar **más de 500 URLs rotas** dentro de la plataforma.

### Acciones Realizadas:
- Identificación de páginas **no encontradas (404)** en el sitio web.
- Análisis de las URLs afectadas para comprender si había contenido relevante que aún debiera ser indexado.
- Verificación de las **URLs de redirección** mal configuradas que terminaban redirigiendo a 404.

---

## 2. Validación y Auditoría Técnica con Screaming Frog

Se llevó a cabo un **rastreo técnico detallado** utilizando **Screaming Frog SEO Spider**, con el objetivo de confirmar si las URLs rotas detectadas en Google Search Console también aparecían en el análisis y verificar la situación actual de cada enlace.

### Acciones Realizadas:
- Barrido completo para rastrear todas las URLs, incluyendo aquellas con errores 404 y soft 404.
- Detección de **redirecciones incorrectas** (3xx) que provocaban un **soft 404**.
- Verificación de que el sitio respondiera correctamente a las URLs válidas (código 200).

---

## 3. Resultados Encontrados: Errores 404 y Soft 404

### Errores 404 (Directos)
Se identificaron una serie de URLs que **devuelven un error 404** directo al ser accedidas. Este tipo de error es crítico ya que genera una **mala experiencia de usuario** y perjudica la **indexación por parte de Google**.

### Errores Soft 404
También encontramos varios casos de **soft 404**, donde las páginas devuelven un **código 200** pero visualmente muestran un mensaje de error o una página vacía, lo que confunde a los motores de búsqueda.

---

### Acciones emprendidas
Realizamos un match entre las URLs con errores 404 y 404 soft de Search Console vs URLs con errores desplegados a raíz de un crawl en Screaming Frog por Metodo List Mode, para analizar específicamente la lista que despliega Search Console y se encontraron datos interesantes. 

# Errores 404 GSC vs Screaming Frog
Resumen del análisis en Screaming Frog:

Total URLs auditadas: 1,000

Redirecciones (3xx): 258 → ⚠️ Estas URLs terminan en una página 404, lo que indica una redirección rota o mal configurada.

Errores 404 directos (4xx): 741 → Estas URLs no existen o ya están caídas, y están indexadas o enlazadas aún.

Completadas (200): 1 sola... lo cual confirma que la mayoría ya no llevan a ningún lado útil.

![image](https://github.com/user-attachments/assets/bade13a9-e56b-4925-be27-a4fd5d0d9d58)

Detalle de URLs: https://docs.google.com/spreadsheets/d/10dwomwzu4VMZvZ1zUUynnpt1ND4eB2V8/edit?usp=sharing&ouid=113874886446922366610&rtpof=true&sd=true


# Errores 404 Soft GSC vs Screaming Frog

Interpretación profesional

2XX - Páginas que devuelven código 200
Estas son páginas que técnicamente devuelven "éxito", pero Google las clasificó como Soft 404 porque:

El contenido es muy pobre o inexistente.

Devuelven un mensaje como “página no encontrada” pero sin código 404 real.

Están vacías o mal estructuradas.

Acción recomendada: Corregir estas páginas asegurando contenido útil, o devolver un verdadero 404 si ya no deben existir.

3XX - Redirecciones
Casi 950 páginas redirigen, lo cual no siempre es una solución adecuada si:

Redirigen todas a una misma URL genérica (por ejemplo, home o una categoría), algo que Google interpreta como Soft 404.

No tienen una relación semántica real con el destino.

Acción recomendada: Asegurarse de que cada redirección 301 apunte a una página relevante y útil para el usuario. De lo contrario, es mejor devolver un 404 real.

![image](https://github.com/user-attachments/assets/1e0800b7-8132-4ef2-9120-4c162c646e72)

Detalle de URLs: https://docs.google.com/spreadsheets/d/1GNhvUleCNINbnF6yCPPyUFTzDPVaR3l1/edit?usp=sharing&ouid=113874886446922366610&rtpof=true&sd=true 


## 4. Acciones recomendadas para Resolver los Errores 404 y Soft 404

### Redirección 301 de Páginas Eliminadas:
- **Redirección de URLs rotas** a las páginas más relevantes de C&A, ya sea productos, categorías o páginas informativas, utilizando redirecciones **301 permanentes**.
- **Actualización del archivo `.htaccess`** para implementar las redirecciones directamente en el servidor y garantizar que los usuarios y Googlebot sean llevados a la URL correcta.

### Revisión y Ajuste de Redirecciones:
- Revisión de las redirecciones existentes en el sitio y corrección de aquellas que provocan un **soft 404**.
- **Redirección de páginas de productos o categorías descontinuadas** a las páginas de inicio de categoría o a páginas similares para no perder tráfico.

### Sitemap y Robots.txt:
- **Eliminación de URLs rotas** del archivo Sitemap de C&A para evitar que Google continúe rastreándolas y tratándolas como páginas válidas.
- **Ajuste del archivo robots.txt** para asegurarnos de que las páginas no indexables, como los soft 404, no sean rastreadas por Googlebot.

---

## 5. Resultados Posteriores y Validación

Después de realizar todas las correcciones necesarias, se debe **validar los cambios**:
- Eliminar la gran mayoría de los **errores 404 directos**.
- Verificar que las redirecciones 301 que se implementen dirijan el tráfico correctamente a las páginas relevantes.
- Las URLs de **soft 404** deben responder adecuadamente con un código de estado **404 real** en lugar de un código 200.

---

## 6. Recomendaciones y Plan de Acción Futuros

### Monitoreo Continuo:
Para mantener la salud SEO del sitio y evitar la aparición de nuevos errores 404 o soft 404:
- Realizar una **auditoría periódica** de errores 404 en Google Search Console y Screaming Frog.

### Optimización de la Arquitectura del Sitio:
Es recomendable revisar de forma periódica la **estructura de enlaces internos** para evitar que páginas obsoletas sean accesibles, lo que podría generar nuevos 404.

### Validación de Contenido Obsoleto:
A medida que C&A realice cambios en el catálogo de productos o en las categorías, se debe proceder con la creación de redirecciones 301 **para todo contenido que sea eliminado o reubicado**.

---

## 7. Impacto Esperado
- **Mejora en la experiencia de usuario** al eliminar páginas rotas y redirigir a los visitantes a páginas relevantes.
- **Mejora en el rastreo e indexación de Google** gracias a la correcta configuración de las redirecciones y la eliminación de URLs rotas del Sitemap.
- Aumento en la **autoridad SEO** del sitio, evitando pérdidas de "link equity" por redirecciones rotas o páginas de error.
- Reducción del **presupuesto de rastreo desperdiciado** al garantizar que las páginas válidas sean las que Googlebot rastrea.

---







# Estructura recomendada para una página 404 real:
## 1. Código de Respuesta 404 Real
Asegúrate de que el servidor esté configurado para devolver un código de estado 404. Esto es fundamental para indicar a los motores de búsqueda (como Google) que la página realmente no existe.

Esto se debe configurar en tu servidor web (por ejemplo, Apache o Nginx) o a través del archivo .htaccess si usas un servidor Apache.

## 2. Mensaje claro de error
La página debe mostrar un mensaje claro y amigable que explique que la página no se encuentra, algo como:

"Lo sentimos, la página que buscas no está disponible."

"Esta página no existe."

Evita mensajes como "Error 404" a secas. Utiliza un tono amigable que no frustre al usuario.

## 3. Opciones de navegación
Enlaces a otras páginas del sitio: Para ayudar al usuario a encontrar lo que está buscando, incluye enlaces a otras páginas importantes de tu sitio, como:

Página de inicio

Categorías populares

Artículos o productos más vistos

Barra de búsqueda: Ofrecer una barra de búsqueda permite que los usuarios intenten encontrar lo que buscan sin tener que abandonar el sitio.

## 4. Diseño coherente con el resto del sitio
La estética de la página de error 404 debe coincidir con el diseño del sitio en general. Esto no solo mejora la experiencia del usuario, sino que también da una sensación de continuidad y profesionalismo.

Evita que la página 404 se vea como un "página vacía", debe ser un mensaje claro dentro del mismo diseño del sitio.

## 5. Redirecciones y enlaces rotos
Si una página ha sido eliminada, y los usuarios todavía intentan acceder a ella, considera redirigirla a una página relacionada o la página de inicio.

Usa redirecciones 301 si es necesario redirigir el tráfico de una página eliminada a una página relevante para evitar la frustración del usuario y la posible pérdida de tráfico.

## 6. Detalles adicionales para los motores de búsqueda
Si una página ya no existe, asegúrate de que el código 404 se mantenga para que los motores de búsqueda sepan que esa URL debe ser retirada de su índice.

No indexar la página de error: Si tu página de error 404 tiene contenido significativo, asegúrate de marcarla con un meta tag noindex para evitar que Google la indexe.

<meta name="robots" content="noindex, nofollow">


## 7. Evitar la indexación de páginas de error
Como se mencionó anteriormente, asegúrate de que Google no indexe las páginas 404, ya que esto podría generar contenido inútil en los resultados de búsqueda.

Puedes hacerlo agregando el siguiente código en el <head> de tu página 404:


<meta name="robots" content="noindex, nofollow">
