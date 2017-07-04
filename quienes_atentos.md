# Rollover de KSK 2017: ¿Quiénes deben estar atentos?

Hay dos lugares clave que se verán afectados por esta rotación:

 * cualquiera que utilice DNSSEC para validación DNS, ya que la llave raíz es el "ancla de confianza" que origina toda la cadena de confianza para los nombres de dominio, y
 * redes que limiten el tamaño de sus paquetes UDP

De acuerdo a esto, los actores que deben tener cuidado son:

 * Proveedores de servicio DNS recursivo (resolvers), en especial los que están validando con DNSSEC

    + ISPs, hostings, empresas, organizaciones.

 * Proveedores de acceso a Internet (ISP)

    + bloqueo paquetes UDP (firewalls, IDS, etc)

