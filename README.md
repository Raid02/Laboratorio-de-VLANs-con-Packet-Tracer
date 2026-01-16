Laboratorio VLAN Básico – Cisco Packet Tracer

Este laboratorio tiene como objetivo practicar la creación de VLANs, asignación de puertos y segmentación de subredes en switches interconectados, usando Packet Tracer.

🔹 Topología

3 switches interconectados: S1, S2, S3

Cada switch tiene 3 VLANs: 10 (Contabilidad), 20 (Asesoría), 30 (RRHH)

Enlaces entre switches configurados como trunk

Puertos a PCs configurados como modo access

Red 192.168.0.0/24 segmentada en 3 subredes /29:

VLAN	Nombre VLAN	    Subred	        Rango de hosts	            Broadcast
10	    Contabilidad	192.168.0.0/29	192.168.0.1 – 192.168.0.6	192.168.0.7
20	    Asesoría	    192.168.0.8/29	192.168.0.9 – 192.168.0.14	192.168.0.15
30	    RRHH	        192.168.0.16/29	192.168.0.17 – 192.168.0.22	192.168.0.23
🔹 Tabla de puertos / VLAN / PC
Switch	Puerto	VLAN	PC conectado	IP asignada
S1	    Fa0/2	10	        PC1	        192.168.0.1
S1	    Fa0/3	20	        PC2	        192.168.0.9
S1	    Fa0/4	30	        PC3	        192.168.0.17
S2	    Fa0/3	10	        PC4	        192.168.0.2
S2	    Fa0/4	20	        PC5	        192.168.0.10
S2	    Fa0/5	30	        PC6	        192.168.0.18
S3	    Fa0/2	10	        PC7	        192.168.0.3
S3	    Fa0/3	20	        PC8	        192.168.0.11
S3	    Fa0/4	30	        PC9	        192.168.0.19                

Los enlaces entre switches están en trunk para transportar todas las VLANs.

🔹 Comandos de verificación recomendados

Ver VLANs en el switch:

show vlan brief


Ver puertos y modo (access/trunk):

show interfaces status
show interfaces trunk


Ver tabla MAC:

show mac address-table


Ver conectividad entre PCs (solo dentro de la misma VLAN):

ping [IP de otro host en la misma VLAN]

🔹 Notas importantes

Cada VLAN funciona como un segmento de red independiente; por defecto, no se comunican entre VLANs.

La segmentación con /29 limita los hosts por VLAN a 6, lo cual es suficiente para este laboratorio.

Este laboratorio es ideal para practicar configuración de VLANs, modos de puertos (access/trunk) y segmentación de subredes.