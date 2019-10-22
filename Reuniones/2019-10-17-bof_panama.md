# Reunión de proyectos (BoF) del WG DNS de LACNOG

Jueves 17 de octubre.
Hotel Hard Rock, ciudad de Panamá, durante LACNOG 2019.
Notas por Hugo Salgado.

## Chairs

 - Hugo Salgado
 - Mauricio Vergara

## Asistentes participantes en micrófono:

 - Ariel Weher
 - Douglas Fischer
 - Luciano Minuchin
 - Lía Solís
 - Alejandro Acosta
 - cerca de 6 personas más en sala
 - 1 participante remoto.

## Material:

 - [slides WG & Evolución del DNS](../Presentaciones/20191009-DNS_WG_BoF-LACNOG2019-mvergara.pdf)


## Minutas:

- Hugo Salgado comienza explicando objetivo del BoF, 
obtener ideas de proyectos que pueda llevar adelante el grupo.

- Hugo muestra [slides](../Presentaciones/20191009-DNS_WG_BoF-LACNOG2019-mvergara.pdf)
de qué es el WG, trabajos realizados en el pasado, trabajo actual.

- Se abre a tópicos para discusión.

- Mauricio Vergara presenta [slides](../Presentaciones/20191009-DNS_WG_BoF-LACNOG2019-mvergara.pdf)
de la evolución del DNS, pasando por DNSSEC hasta DoT/DoH. 
Cómo configurar DoT en Android, DoH en Firefox.

- Se abre a preguntas y discusión abierta.

- Ariel Weher propone un documento de ayuda para añadir soporte DoT y
DoH para resolvers existentes. 
También para tunning de autoritativos y recursivos.
Se pueden coordinar junto al grupo [BCOP de LACNOG](http://www.lacnog.org/wg-bcops/).

- Douglas Fischer presenta la problemática de que resolvers compartan cache entre conectividad v4 y v6. 
Sugiere que se investigue en más detalle. Su solución es separar en dos resolvers distintos.

- Douglas sugiere que los clientes prefieren usar 8.8.8.8, 1.1.1.1, 9.9.9.9 ("Public Resolvers")
porque la calidad de las respuestas de los resolvers de los ISPs es mala. 
No es sólo por privacidad. 
Dice que la latencia es mala estos resolvers externos, del orden de 50ms. 
Dice que 3ms es un objetivo deseable. 
Propone crear un proyecto de VMs instaladas por los ISPs que contengan un DNS ya configurado, 
y que utilicen una IP "bonita", compartida por anycast, 
lo que le daría redundancia cuando se cae porque respondería el siguiente más cerca. 
La VM estaría cifrada para que no pueda entrar nadie, ni siquiera el ISP, 
y al usar DoT o DoH habría privacidad completa del usuario. 
Para seguir hay que definir qué organismo podría apoyar.

- Ariel sugiere que el uso de _Public Resolvers_ es porque es linda y es rápida. 
No hay que recordar IPs complejas del ISP. 
Douglas dice que la experiencia de Brasil es que un gran ISP con buena conexión, 
tenía sus DNS recursivos colapsados. 
Incluso el gobierno tuvo que intervenir para resolverlo. 
Pero a esa altura todos los usuarios ya habían hecho una campaña para usar 8.8.8.8, 
y era mucha mejor calidad. 
Para los ISPs pequeños sigue siendo un problema, no es tan simple tener resolvers de alto rendimiento.

- Luciano Minuchin cuenta que ISPs pequeños en Argentina usan mucho el 8.8.8.8 directo a los usuarios, 
y el 2018 hubo problemas con Google lo que ocasionó que los clientes de esos ISPs quedaran sin servicio. 
El resolver de Google lo entregan vía DHCP. 
Y entregan como backup el 8.8.4.4, que también muere (falla) al morir (dejar de funcionar) Google.

- Luciano indica que un problema común de tener un DNS malo es que éste no entrega revenue.
En el área de operaciones no tienen incentivo en invertir en equipos o software para DNS porque no pueden cobrarlo.

- Se menciona otra mala acción: 
secuestrar el 8.8.8.8 o poner `DNAT` de todo lo que lleve puerto 53 a sus propios resolvers.

- Luciano indica que a diferencia del `BGP`,
que es el mismo siempre independiente de la organización, 
el DNS depende del tamaño de la organización. 
Si es un ISP pequeño es un `BIND` sobre Linux. 
Si es una grande es `F5` y son 100% distintos. 
No tienen el mismo interés. 
Entonces o buscamos cosas que hacer que sean transversales a todos, 
o separamos los esfuerzos por tamaño.

- Hugo comenta que en la propuesta de las VM de Douglas habría que dar alguna interfaz 
de administración al ISP para los filtros que eventualmente le pida su gobierno o legislación. 
Douglas indica que en Brasil el filtrado es por IP así que se hacen _blackholes_, no usan para ello el DNS.
Luciano dice que en Argentina llegan requerimientos de bloqueo por IP o por nombre, 
y en este último caso se resuelve a IP y se usa _blackhole_ igual. 
En Venezuela sí se usa el filtrado vía DNS por nombre,
lo que explica el alto uso de Public Resolver para saltarse estos bloqueos. 
Ante la pregunta si se quiebra DNSSEC, 
no es así porque no reemplazan las respuestas. 
Lía Solís indica que en Bolivia el bloqueo de tráfico efectivamente se hace mediante DNS.

- Hugo resume diciendo que se podría decir que la preocupación en este momento es la intercepción por parte de proveedores. 
Se podría hacer un estudio para demostrar hasta dónde llega y qué tipos de modificaciones existe. 
Se puede documentar mejores prácticas. 
O demostrar los problemas cuando se realizan, documentar por qué es malo.

- Douglas propone avisar de parte del WG a los Public Resolvers si saben que hay secuestro de sus recursos por parte de ISPs de la región. 
Hugo cuenta de un estudio sobre privacidad que detectaba ISPs que
usaban al 8.8.8.8 como forwarder que se podría adaptar.

- Luciano quiere generar estadísticas, 
saber cuántas consultas hay en la región, 
y ayudar a detectar problemas en las redes locales al conocer los números. 
Sugiere [DSC](https://www.dns-oarc.net/tools/dsc) y mejorar su documentación. 
Mauricio dice que hay celo en los operadores por privacidad, 
quizás sólo compartir flujos y números grandes.
