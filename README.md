# **PHP HEADERS**    *(chrome)*


**HOST**: Es el que especifica el nombre del host (el dominio o la dirección IP) al que se le realiza la solicitud. En nuestro caso es el "localhost",  ya que lo ejecutamos de manera local.  Conocer el Host puede llegar a ser útil en situaciones en las que un servidor puede alojar múltiples sitios web con diferentes nombres de dominio o cuando se utiliza la dirección IP para acceder a un servidor. 

**Connection**: Es el que indica si la conexión con el servidor debe mantenerse abierta después de que la respuesta sea completada. En el caso actual, el "keep-alive" expresa que la conexión se mantendrá abierta para futuras solicitudes. Esto permite que se sigan realizando solicitudes y respuestas desde la misma conexión TCP, lo que mejora el rendimiento y evita la sobrecarga de establecer y cerrar conexiones frecuentemente (reducir latencia y mejora de la eficiencia). Pero es importante saber que la persistencia de la conexión está sujeta a las políticas y configuraciones de un servidor. Por ejemplo, para evitar que alguien comience a enviar peticiones a un servidor y lo sobrecargue se le puede poner un periodo de tiempo o un número determinado de solicitudes. 

**Content-length**: Indica la longitud del contenido del cuerpo de la solicitud en bytes. 

**sec-ch-ua**: Es el encabezado específico de Chrome que indica la versión del navegador y el procesador "Chromium". (Secure Contexts HTTP header user-agent client hints). En el caso de FireFox no se implementa directamente el encabezado "sec-ch-ua". En su lugar,  Firefox utiliza otros encabezados estándar, como el encabezado  "User-Agent", para proporcionar información sobre el agente de usuario y otras características. El encabezado "User-Agent".

**sec-ch-ua-platform**: Muestra el sistema operativo donde se está ejecutando el navegador.

**sec-ch-ua-mobile**: Indica si el navegador se ejecuta en un dispositivo mobile. (si arroja ?0 significa que no hay información clara de si es o no un dispositivo móvil).

**User-Agent**: Da información más detallada del navegador y el sistema operativo del cliente.

**Content-type**: Indica el tipo de contenido que está en el cuerpo de la solicitud. En el caso actual es application/json, pero podría ser un pdf, un png o cualquier otro formato.

**Accept**: indica los tipos de contenido que el cliente acepta en la respuesta del servidor. En el caso donde la respuesta es "/", significa que el cliente acepta cualquier tipo de solicitud.

**Origin**: Indica de donde viene la solicitud, la uri de donde se hace la solicitud. En el caso del hacking es importante ocultar esta información para evitar que se realicen demasiadas peticiones al servidor.

**Sec-Fetch-Site**: Indica el contexto de navegación desde donde se realiza la solicitud. Los posibles valores del encabezado "Sec-Fetch-Site" son los siguientes:

1. "*"same-origin": Este valor indica que la solicitud se realiza desde el mismo origen (dominio, protocolo y puerto) que la página actual. En otras palabras, la solicitud se origina dentro del mismo sitio web.*
2. *"same-site": Este valor indica que la solicitud se realiza desde el mismo sitio, pero no necesariamente desde el mismo origen. Esto ocurre cuando hay una política de mismo sitio (same-site policy) en funcionamiento, que limita las solicitudes a un mismo sitio web, aunque los orígenes sean diferentes.*
3. *"cross-site": Este valor indica que la solicitud se realiza desde un sitio cruzado, es decir, desde un origen diferente al de la página actual. Esto puede ocurrir cuando se realizan solicitudes a recursos de otros dominios.*
4. *"cross-origin": Este valor también indica que la solicitud se realiza desde un origen diferente al de la página actual. Es similar a "cross-site", pero puede tener implicaciones adicionales de seguridad debido a la política de mismo origen (same-origin policy) implementada por los navegadores.*

*Es importante destacar que estos valores son proporcionados por el navegador y pueden variar según las políticas de seguridad y privacidad implementadas. Los navegadores modernos utilizan estos valores para proteger a los usuarios y prevenir ataques de seguridad, como el robo de información o la ejecución de scripts maliciosos en sitios cruzados.* "

**Sec-Fetch-Mode**: Se usa para ver la forma en que la navegación realiza una solicitud. Proporciona información de como el navegador recibió la URL de la solicitud, y de esta forma puede ayudarle al servidor a tomar decisiones basadas en el contexto de navegación. Los posibles valores de este encabezado son: 

"

1. *"navigate": Este valor indica que la solicitud se realiza como parte de una navegación normal del usuario, como hacer clic en un enlace o ingresar una URL en la barra de direcciones. Se utiliza cuando el recurso solicitado es la carga inicial de una página.*
2. *"cors": Este valor indica que la solicitud se realiza como parte de una operación de origen cruzado (Cross-Origin Resource Sharing, CORS). Se utiliza cuando el recurso solicitado es un recurso de origen cruzado, lo que significa que la solicitud se realiza desde un dominio diferente al del sitio actual.*
3. *"no-cors": Este valor indica que la solicitud se realiza sin una política de origen cruzado. Se utiliza cuando el recurso solicitado es de origen cruzado, pero el cliente no necesita acceder a la respuesta. Por ejemplo, cuando se realiza una solicitud de seguimiento o para comprobar la disponibilidad de un recurso.*
4. *"same-origin": Este valor indica que la solicitud se realiza dentro del mismo origen (dominio, protocolo y puerto) que la página actual. Se utiliza cuando la solicitud se realiza dentro del mismo sitio web.*
5. *"websocket": Este valor indica que la solicitud se realiza a través de un WebSocket, que es un protocolo de comunicación bidireccional y full-duplex sobre una única conexión TCP.*"

**Sec-Fetch-Dest**: se usa para ver cual es el destino previsto de la solicitud. Da información sobre como el recurso que es solicitado debe ser solicitado en el lado del servidor. Pueden haber mucho valores en este encabezado: "document", "image", "media", "font", "script", "style", "manifest",  "worker", "sharedworker", "fetch" y otros destinos especiales.

**Referer**: Se utiliza para indicar la URL de la página de origen desde la cual se  originó la solicitud actual. Proporciona información sobre la página que enlazó o hizo referencia a la URL actual. funciona por ejemplo cuando haces clic en un enlace en una página web  para acceder a otra página, el navegador envía el encabezado "Referer"  en la solicitud de la página de destino o si completas un formulario en un sitio web y lo envías, el encabezado  "Referer" incluirá la URL de la página que contenía el formulario.

**Accept-Encoding:** Indica los tipos de codificación de contenido que el cliente acepta en la respuesta del servidor. En este caso, el valor indica que el cliente acepta las codificaciones "gzip", "deflate" y "br" (Brotli).

**Accept-Language: **Indica los idiomas que el cliente prefiere en la respuesta del servidor. En este caso, el valor indica que el cliente prefiere los idiomas "en-US" (inglés de Estados Unidos), "en" (inglés genérico), "es-US" (español de Estados Unidos) y "es" (español genérico), con un nivel de preferencia para cada uno.





