## Rejunte documentación sobre Api-Rest y HTTP

#### Arquitectura REST:
REST, abreviatura de **Representational State Transfer, o Transferencia de Estado Representacional**
es un estilo de arquitectura para diseñar aplicaciones en red.

#### Verbos http:
| Verbo   | Definicion                                                                                                                                                   |      Ejemplo de uso        |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|
| GET     | El método GET,solicita una representación de un recurso específico. Las peticiones que usan el método GET sólo deben recuperar datos.                        | Consultar datos de un producto http://tusitio.com/producto/12ae324
| HEAD    | El método HEAD pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.                                                     | Como es similar a get pero sin respuesta podemos usarlo para consultar si algun recurso esta habilitado. http://tusitio.com/producto/12ae324/token/rewrwer12312dasdas= solo trabajamos con http codes y nos ahorramos el response completo en caso de que no se apruebe al auth.  |
| POST    | El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor. |
| PUT     | El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.                                           |
| DELETE  | El método DELETE borra un recurso en específico.                                                                                                             |
| OPTIONS | El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.                                                       |
| PATCH   | El método PATCH,es utilizado para aplicar modificaciones parciales a un recurso.                                                                             |
| TRACE   | El método TRACErealiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.                                                |
| CONNECT | El método CONNECT establece un tunel hacia el servidor identificado por el recurso.                                                                          |

Links:
- Documentación mozilla **[Http methods]**

[Http methods]:https://developer.mozilla.org/es/docs/Web/HTTP/Methods
