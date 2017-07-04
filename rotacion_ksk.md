# La rotación de la KSK 2017

Durante el año 2017 se realizará un cambio importante en Internet: se hará una rotación de la llave raíz del DNS, cambiando la llave actual -en funcionamiento desde el año 2010- a una nueva.
Este cambio es necesario por seguridad. Una llave criptográfica no debe estar en funcionamiento por mucho tiempo, debido a que aumenta sus posibilidades de quiebre, pérdida, y filtración.
El año 2010 por primera vez se agregó seguridad al DNS, el fundamento del direccionamiento en Internet. Ese cambio fue el inicio de la nueva época de seguridad en los nombres de Internet, y que está dando fruto a nuevas tecnologías contruidas sobre el DNS.
Sin embargo, desde un comienzo se predijo y se diseñó el sistema para que las llaves tuvieran que rotarse cada cierto tiempo. No es posible estimar cuándo dejará de ser segura, pero se definió que un horizonte razonable debería ser de 5 años.
A diferencia de la primera vez, ahora se estresará más el sistema DNS porque:

* la respuesta DNS será más grande aún, y
* es posible que exista software que no se actualice automáticamente.

Este sitio web es una iniciativa del Grupo de Trabajo del DNS de LACNOG, el Grupo de Operadores de Redes de Latinoamérica y el Caribe, y busca entregar información a los operadores de redes, de DNS, y de nombres en dominio en general, para que estén atentos a estos cambios, y tomen las debidas precauciones.

## Cronograma:

* ~27 de Octubre de 2016~: Una nueva KSK fue generada en la instalación Este de administración de llaves de ICANN.
* ~02 de Febrero de 2017~: La nueva KSK fue replicada en la instalación Oeste de administración de llaves de ICANN.
* ~03 de Febrero de 2017~: El anclaje de la zona raíz (Trust Anchors) fue actualizado para incluir la nueva KSK.
* ~27 de Abril de 2017~: Se firmó el primer conjunto de llaves que contienen la nueva KSK.
* 11 de Julio de 2017: Publicación de la nueva KSK en el DNS como parte del DNSKEY RRset que es firmado por la antigua KSK.
* 19 de Septiembre de 2017: Aumento del tamaño las respuesta DNSKEY de los servidores de la zona raíz.
* 11 de Octubre de 2017: La nueva KSK comienza a firmar el conjunto de llaves de la zona raíz (el evento de rotación de la KSK).
* 11 de Enero de 2018: Revocación de la antigua KSK.
* 22 de Marzo de 2018: Último día en que la antigua KSK aparece en la zona raíz.
* Mayo de 2018: Eliminación de la antigua KSK en la instalación Este de administración de llaves de ICANN.
* Agosto de 2018: Eliminación de la antigua KSK en la instalación Oeste de administración de llaves de ICANN.


## Contenido:

* [¿Quiénes deben estar atentos?](quienes_atentos.md)
* [¿Qué es KSK y DNSSEC?](dnssec_basics.md)
* [¿Qué podría pasar?](que_pasara.md)
* [Estar atentos a...](atentos.md)
* [¿Qué hacer si pasa algo?](accion.md)
* [¿Cómo me puedo preparar?](herramientas.md)
* [Más información](mas.md)

