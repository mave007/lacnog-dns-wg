# ¿Qué podría pasar?

Antes de que cunda el pánico, es importante hacer notar que se tenía alguna preocupación el año 2010 cuando se firmó por primera vez la raíz, pero los problemas fueron mínimos y se solucionaron rápidamente. Esta vez es distinto porque se estresa un poco más el sistema, pero de igual manera se cree estar bien preparados.

Además ICANN, los administradores de la raíz, poseen un equipo de monitoreo y de respuesta a incidentes que estará evaluando todo el tiempo mientras dure esta rotación. En caso de que exista algo que esté afectando a la comunidad en un grado significativo, ICANN posee los mecanismos para anular el cambio y retrotraer al estado actual. Eso se estará evaluando momento a momento y dependiendo del alcance de los problemas.

De todas formas, estos son algunos de los síntomas esperables en sistemas desactualizados o con bloqueos excesivos:

 * lentitud en resolver ciertos nombres de dominio, en el caso de redes que bloqueen paquetes DNS grandes. Los servidores DNS tienen un tiempo de "timeout" que se agotará en la espera de estos mensajes, y luego reintentarán usando TCP en vez de UDP. La conexión TCP no tiene limitantes de tamaño, por lo que finalmente se podrá resolver el nombre, solo que con una demora muy superior a lo normal.

 * imposibilidad de resolver ningún nombre de dominio, en el caso de resolvers que validen con DNSSEC pero que no actualizaron su llave ancla;


