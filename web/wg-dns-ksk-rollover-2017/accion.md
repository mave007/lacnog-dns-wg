# ¿Qué hacer si pasa algo?

La acción es distinta dependiendo del tipo de error.

## Si el resolvedor está validando con DNSSEC y no es capaz de resolver ningún nombre de dominio

Primero verifique que esté relacionado con la validación DNSSEC. Para ello puede enviar una consulta especial con un bit que indica que quiere obviar la validación ("checking disabled"):

% dig @IP_RESOLVER . dnskey +cd

Si se obtienen respuestas con la opción "+cd", pero solo un error SERVFAIL sin la opción, entonces claramente hay un problema con la llave raíz KSK. Consulte la documentación de su servidor DNS para ver cómo actualizar la llave a mano, y reinicie. La llave nueva se puede obtener desde el sitio de IANA (https://www.iana.org/dnssec/files) en diversos formatos. Nuevamente consulte la documentación de su servidor DNS con instrucciones del formato requerido.

## Si hay consultas lentas e incluso "timeouts"

Puede tener un problema con el transporte del paquete UDP con los mensajes DNS. Acá es más complejo, depende de su arquitectura de red; pero en general revise que los firewalls, routers, IDS o cualquier dispositivo entre su servidor DNS y la Internet permita que los paquetes DNS superen los 512 bytes. Un límite de 4.096 bytes es bastante seguro, aunque lo ideal es dejarlo en su límite natural de 64KB.

También recuerde que el protocolo DNS exige el uso de TCP usando el puerto 53, además de UDP. Verifique de nuevo que sus firewalls permitan la comunicación libre con TCP. Puede probarlo ejecutando el siguiente comando desde el mismo servidor DNS:

$ dig @a.root-servers.net . dnskey +tcp

# Ayuda

También recuerde que puede escribir a las listas de correo del [Grupo DNS de LACNOG](https://listas.nic.cl/mailman/listinfo/dns-esp), a la [lista general de LACNOG](https://mail.lacnic.net/mailman/listinfo/lacnog) o contactar en forma directa al [grupo de ingeniería de DNS en ICANN](https://www.dns.icann.org/aboutus/mail/)

