# Fitxa tècnica: Configuració d'una IP fixa a Ubuntu Server

## Objectiu
Configurar una adreça IP fixa en un servidor Ubuntu utilitzant Netplan, per tal que el servidor mantingui sempre la mateixa configuració de xarxa.
## Materials
- Ubuntu Server
- Oracle VirtualBox
- Visual Studio Code
- Connexió de xarxa
- Terminal d'Ubuntu Server
## Procediment
1. Iniciar la màquina virtual amb Ubuntu Server.
2. Consultar el nom de la interfície de xarxa amb la comanda:
```bash
ip a
```
3. Accedir al directori de configuració de Netplan:
```bash
cd /etc/netplan
```
4. Obrir el fitxer de configuració:
```bash
sudo nano /etc/netplan/50-cloud-init.yaml
```
5. Configurar la interfície amb una adreça IP fixa.

![img](/primer_repositori/img/configuracio-netplan.png)

6. Guardar el fitxer amb Ctrl+O, prémer Enter i sortir amb Ctrl+X.

7. Aplicar la nova configuració:
```bash
sudo netplan apply
```
8. Comprovar que l'adreça IP s'ha configurat correctament:
```bash
ip a
```
9. Comprovar la connectivitat de xarxa:
```bash
ping 8.8.8.8
```

## Comprovacions

- [ ] La interfície de xarxa mostra l'adreça IP configurada.
- [ ] La configuració de Netplan no mostra errors.
- [ ] El servidor pot fer ping a la passarel·la.
- [ ] El servidor té connexió amb altres dispositius de la xarxa.