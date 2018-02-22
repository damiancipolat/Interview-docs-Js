## Paton de comunicacón por mensajes usando colas.

#### Sistema de mensajeria:
Permite la comunicación entre aplicaciones a través de distintas redes, o dentro de un mismo sistema. 

#### Problematica:
La mensajería es una tecnología que permite que dos aplicaciones se comuniquen demanera confiable, asincrónica y con alto rendimiento. Al utilizar esta tecnología las aplicaciones se comunican a través de canales enviándose paquetes de datos denominados mensajes. 

#### Cola de mensajes:
Un canal funciona como una colección de mensajes que puede ser compartido por múltiples aplicaciones y utilizado concurrentemente.
Las aplicaciones actúan con roles bien definidos en la comunicación: productor yconsumidor.

#### Funcionamiento:
Los mensajes no se transmiten desde el cliente al servidor directamente, sino a travésde colas de mensajes intermedias que almacenan y envían los mensajes. 

Esto tiene una serie de consecuencias:

	- Remitentes y receptores de mensajes están desacoplados, de manera que nonecesitan saber la ubicación de 
	  cada otro (tal vez ni siquiera la identidad).

	- Un remitente sólo pone mensajes en una cola en particular y nonecesariamente sabe quien consume los mensajes. 
	  Por ejemplo, un mensajepodría ser consumido por más de un receptor.

	- Receptores consumen mensajes realizando un monitoreo de colas.