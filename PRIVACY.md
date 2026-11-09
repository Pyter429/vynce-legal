# Política de Privacidad

**Última actualización:** 09-11-2026

En Vynce, valoramos profundamente tu privacidad y tu derecho a la soberanía de tus datos. Esta política explica con total transparencia cómo funciona la aplicación en tu equipo y cuándo se comunica con la red.

## 1. Procesamiento y Almacenamiento Local
Tu biblioteca de música, rutas de carpetas, listas de exclusión (lista negra de carpetas y canciones ignoradas), listas de reproducción, letras guardadas, estadísticas de reproducción, dispositivos vinculados y preferencias (como tu alias o tema visual) se procesan y almacenan **estrictamente de forma local** en tu dispositivo mediante una base de datos SQLite y almacenamiento local de la aplicación. Vynce **nunca** sube tus archivos de audio ni tu base de datos completa a servidores en la nube.

**Traducción de letras (opcional):** Cuando traduces una letra, la traducción se hace en tu equipo con un modelo de traducción automática. **El texto de la letra no se envía a ningún servidor.** Las traducciones se guardan en la misma base de datos local, junto con el idioma detectado y el nombre del modelo usado.

**Notch y Píldora (opcional):** Mientras esta función está activa, Vynce consulta en tu equipo la posición del puntero del mouse y, de las ventanas abiertas, su posición, tamaño, estado y el nombre de su programa (por ejemplo, `chrome.exe`). Lo usa únicamente para decidir cuándo mostrar u ocultar el notch y para aplicar tus reglas por aplicación. **No lee títulos ni contenido de las ventanas**, estos datos no se envían a ningún servidor y solo se guardan los nombres de los programas que agregues a tus reglas. La función viene desactivada y puedes apagarla en **Configuración > Notch y píldora**.

## 2. Conexiones Externas a Internet
Vynce realiza solicitudes a servicios externos únicamente en los siguientes escenarios:
* **Actualizaciones, Textos Legales y Alias (GitHub):** Al iniciar y periódicamente, Vynce consulta los repositorios oficiales en GitHub para verificar actualizaciones del programa, comprobar la vigencia de estos acuerdos legales y sincronizar el diccionario comunitario de alias de artistas.
* **Metadatos, Letras y Estadísticas Artísticas:** Cuando reproduces música o utilizas las funciones de descarga automática/manual de metadatos, Vynce envía el nombre del artista o título de la canción a APIs públicas como **TheAudioDB, Deezer, Apple iTunes, Wikipedia, LRCLIB y Lyrics.ovh** para obtener carátulas, biografías, créditos de producción, letras y disponibilidad de servidores.
* **Modelo de Traducción (Hugging Face):** Solo si aceptas descargarlo para traducir letras, Vynce descarga el modelo (unos 114 MB por dirección de idioma) desde **Hugging Face**, que recibe tu dirección IP y los datos técnicos habituales de una descarga. No se envía ninguna letra, canción ni dato de tu biblioteca. Después funciona sin internet.
* **Datos de CD de Audio (MusicBrainz):** Solo si activas la opción "Buscar datos de CD en internet" y tienes conexión, al insertar un CD Vynce envía a **MusicBrainz** la huella del disco (un identificador calculado a partir de la duración de sus pistas) para obtener el nombre del álbum, las canciones y la portada (desde **Cover Art Archive**). No se envía audio ni ningún archivo, y la respuesta se conserva solo en memoria mientras Vynce está abierto. La opción viene desactivada.
* **Videos Musicales (YouTube):**Para ofrecer la vista de video oficial, Vynce consulta coincidencias mediante búsqueda en **YouTube** e incrusta el reproductor oficial de YouTube cuando está disponible. Al reproducir un video, la conexión directa se realiza con los servidores de Google/YouTube bajo sus propias políticas de privacidad.
* **Enlaces Externos y Donaciones:** Si decides abrir enlaces a redes sociales de artistas, perfiles de Deezer o plataformas de apoyo voluntario (**Ko-fi, PayPal o Mercado Pago**), dichos sitios abrirán en tu navegador externo bajo sus propias políticas.

## 3. Reportes Voluntarios (Bugs, Sugerencias y Metadatos)
Vynce no recolecta telemetría oculta. Solo se envía información al equipo de desarrollo (a través de canales automatizados en **Discord**) cuando tú decides enviar un formulario manualmente:
* **Reporte de Bugs:** Incluye la descripción y pasos que escribas, las capturas de pantalla que adjuntes voluntariamente y datos técnicos básicos de tu entorno (versión de Vynce, sistema operativo, arquitectura y versiones de Electron/Node.js) para diagnosticar el fallo.
* **Sugerencias:** Incluye únicamente la categoría, el texto de tu sugerencia y la versión de Vynce.
* **Reporte de Biografía de Artista:** Si reportas que la biografía o información de un artista es incorrecta, se envía el nombre del artista, el motivo seleccionado, tu comentario opcional, un fragmento de la biografía mostrada y el conteo numérico de pistas y álbumes de ese artista en tu biblioteca local para priorizar la corrección.

## 4. Descubrimiento y Streaming en Red Local (LAN)
Para permitir la función de **Dispositivos y Control Remoto** entre tus computadoras:
* Vynce genera un identificador único local (UUID), ejecuta un servicio local en el puerto **4000** y utiliza el protocolo **Bonjour (mDNS)** dentro de tu red local (Wi-Fi/Ethernet) para anunciar la presencia del reproductor (nombre del equipo, sistema operativo y tipo de chasis).
* Cuando vinculas dos equipos mediante código PIN, ambos dispositivos pueden sincronizar el estado de reproducción y transmitir el flujo de audio y carátulas directamente entre sí a través de tu red local, sin pasar por servidores externos en Internet.

## 5. Control, Lista Negra y Borrado de Datos
Tienes el control absoluto sobre tu información y tus archivos locales:
* **Caché de Metadatos:** Puedes borrar las carátulas y biografías descargadas en cualquier momento desde **Configuración > Avanzado > Limpiar caché**.
* **Modelos y Traducciones:** Puedes borrar los modelos de traducción en **Configuración > Avanzado > Traducción de letras**; las traducciones guardadas se conservan. **Limpiar datos** borra las traducciones guardadas, pero no los modelos.
* **Eliminar de Vynce (Lista Negra):** Puedes ocultar canciones específicas de tu biblioteca mediante la opción **Eliminar de Vynce**, la cual las envía a una lista negra local para que el escáner las ignore sin borrar el archivo físico de tu disco duro. Puedes consultar y restaurar estas canciones en cualquier momento desde **Configuración > Biblioteca**.
* **Eliminar de PC (Borrado Físico Manual):** Vynce nunca modifica ni elimina tus archivos de música de forma automática. Sin embargo, si eliges manualmente la opción **Eliminar de PC** desde el menú contextual de una pista y confirmas expresamente el aviso de seguridad en pantalla, Vynce procederá a borrar el archivo de audio correspondiente del almacenamiento de tu computadora.
* **Restablecimiento de Fábrica:** Puedes eliminar permanentemente toda la base de datos local, listas de reproducción, dispositivos vinculados, configuraciones y cachés utilizando la opción **Restablecer de fábrica** en **Configuración > Acerca de**, o al desinstalar la aplicación (este proceso no elimina tus archivos de música del disco duro).
