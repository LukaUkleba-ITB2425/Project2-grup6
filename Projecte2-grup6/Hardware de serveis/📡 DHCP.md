## Actualizar y actualizar el sistema

`sudo apt install isc-dhcp-server -y`

Actualiza la lista de paquetes e instalar



## Configuración del DHCP

`sudo nano /etc/default/isc-dhcp-server`

Configuración recomendada para que todo este operativo 

`ddns-update-style none;`
`default-lease-time 600;`
`max-lease-time 7200;`
`authoritative;`

`#Ámbito Intranet (192.168.6.0/24):`
`subnet 192.168.6.0 netmask 255.255.255.0 {`
`range 192.168.6.100 192.168.6.200;`
`option routers 192.168.6.1;`
`option domain-name-servers 192.168.6.1; option domain-name "midominio.local";`
`option broadcast-address 192.168.6.255;`
`}`

`#Ámbito DMZ  192.168.16.0/24:`
`subnet 192.168.16.0 netmask 255.255.255.0 {`
`range 192.168.16.100 192.168.16.200;`
`option routers 192.168.16.1;`
`option domain-name-servers 192.168.16.1;option domain-name "midominio.local";`
`option broadcast-address 192.168.16.255;`
`}`



