## Rejunte documentación sobre Api-Rest y HTTP

#### Arquitectura REST:
REST, abreviatura de **Representational State Transfer, o Transferencia de Estado Representacional**
es un estilo de arquitectura para diseñar aplicaciones en red.

#### Verbos http:
| Verbo   | Definicion                                                                                                                                                   |      Ejemplo de uso        |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|
| GET     | El método GET,solicita una representación de un recurso específico. Las peticiones que usan el método GET sólo deben recuperar datos.                        | Consultar datos de un producto http://tusitio.com/producto/12ae324
| HEAD    | El método HEAD pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.                                                     | Como es similar a get pero sin respuesta podemos usarlo para consultar si algun recurso esta habilitado. http://tusitio.com/producto/12ae324/token/rewrwer12312dasdas= solo trabajamos con http codes y nos ahorramos el response completo en caso de que no se apruebe al auth.  |
| POST    | El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor. | Lo usamos cuando queremos **crear** una nueva entidad, por ejemplo post y guardar un nuevo producto. |
| PUT     | El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.                                           | Put es similar a post, el request tiene un body pero se usa cuando queremos **crear o actualizar**.|
| DELETE  | El método DELETE borra un recurso en específico.                                                                                                             | Se usa para borrar una entidad http://tusitio.com/delete/product/12abced |
| OPTIONS | El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.                                                       | Es un preflight request, se usa en api rest para saber si un dominio es accesible y cumple CORS. |
| PATCH   | El método PATCH,es utilizado para aplicar modificaciones parciales a un recurso.                                                                             | Es como **PUT** se usa solo para hacer modificaciones de un recurso. |
| TRACE   | El método TRACE realiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.                                                |
| CONNECT | El método CONNECT establece un tunel hacia el servidor identificado por el recurso.                                                                          |

#### Http codigos de estado:

Más comunmente usados.

#### Respuestas Satisfactorias: 

| Codigo   | Definicion                   |
|---------|------------------------------|
| 200 OK | La solicitud ha tenido éxito.  |
| 202 Accepted | La solicitud se ha recibido, pero aún no se ha actuado. Es una petición "Sin compromiso", lo que significa que no hay manera en HTTP que permita enviar una respuesta asíncrona que indique el resultado del procesamiento de la solicitud. |
| 201 Created| La solicitud ha tenido éxito y se ha creado un nuevo recurso como resultado de ello. Ésta es típicamente la respuesta enviada después de una petición PUT. |


#### ERRORES Cliente: 

| Codigo   | Definicion                   |
|---------|------------------------------|
| 400 Bad Request | This response means that server could not understand the request due to invalid syntax. |
| 401 Unauthorized | Authentication is needed to get requested response. This is similar to 403, but in this case, authentication is possible |
| 403 Forbidden | Client does not have access rights to the content so server is rejecting to give proper response. |
| 404 Not Found | Server can not find requested resource. This response code probably is most famous one due to its frequency to occur in web. |


#### ERRORES Servidor: 

| Codigo   | Definicion                   |
|---------|------------------------------|
| 500 Internal Server Error | The server has encountered a situation it doesn't know how to handle. |
| 501 Not Implemented | The request method is not supported by the server and cannot be handled. The only methods that servers are required to support (and therefore that must not return this code) are GET and HEAD. |
| 502 Bad Gateway | This error response means that the server, while working as a gateway to get a response needed to handle the request, got an invalid response. | 
| 503 Service Unavailable | The server is not ready to handle the request. Common causes are a server that is down for maintenance or that is overloaded. |

Links referencia:
- Documentación mozilla **[Http methods]**
- Documentación mozilla **[Http status codes]**

[Http methods]:https://developer.mozilla.org/es/docs/Web/HTTP/Methods
[Http status codes]:https://restpatterns.mindtouch.us/HTTP_Status_Codes
