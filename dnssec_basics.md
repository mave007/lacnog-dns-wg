# ¿Qué es KSK y DNSSEC?

DNSSEC es una actualización del protocolo tradicional DNS que añade verificación de integridad y autenticidad a los mensajes clásicos del DNS. Lo hace mediante criptografía asimétrica sobre el contenido de las respuestas, distribuyendo las llaves de las firmas dentro del mismo DNS, aprovechando la delegación de los dominios padres hacia sus hijos.

Por lo tanto un resolvedor de nombres, para poder validar con DNSSEC los mensajes, debe conocer la llave raíz del DNS, desde donde se deriva el resto de llaves de los dominios. Esta llave se denomina "KSK de la raíz". Esta llave viene pre-configurada en los softwares DNS que realizan validación, además de ser publicada por diversos medios para permitir su instalación y chequeo manual.

Para más información de DNSSEC, recomendamos visitar [la sección DNSSEC del programa Deploy360 de la Internet Society](http://www.internetsociety.org/deploy360/dnssec/) (en inglés).

