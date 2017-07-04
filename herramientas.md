# ¿Cómo me puedo preparar?

## Revisar su versión de servidor DNS

 * Si es Bind, que sea superior a 9.8 ([más información](https://www.isc.org/downloads/bind/bind-keys/))

 * Microsoft Server desde Windows Server 2012 ([más información](https://technet.microsoft.com/en-us/library/dn593672(v=ws.11).aspx))

 * Unbound desde versión 1.4.0

 * PowerDNS no tiene soporte para rollover automático, *se debe hacer manualmente* ([más información](https://doc.powerdns.com/md/recursor/dnssec/#trust-anchor-management))


## Set de herramientas útiles


 * Probar la capacidad de recibir llaves grandes, [http://keysizetest.verisignlabs.com/] de Verisign Labs.

 * Test de algoritmos, [https://rootcanary.org/test.html] de Root Canary 

 * Revisar si su resolvedor está validando con DNSSEC, [https://dnssec.vs.uni-due.de/]

