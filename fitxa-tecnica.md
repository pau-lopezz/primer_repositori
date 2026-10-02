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

![img](/img/configuracio-netplan.png)

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

## Incidències i solucions

| Incidència | Solució |
|---|---|
| Error de sintaxi al fitxer YAML | Revisar els espais i la indentació del fitxer. |
| No apareix la IP configurada | Executar `sudo netplan apply` i tornar a comprovar amb `ip a`. |
| Apareix `Destination Host Unreachable` | Revisar l'adreça IP, la passarel·la i la configuració de l'adaptador de VirtualBox. |
| Netplan no aplica la configuració | Revisar el fitxer amb `sudo netplan try`. |

## Recursos

- [Documentació de Netplan](https://netplan.readthedocs.io/)
- [Documentació d'Ubuntu Server](https://ubuntu.com/server/docs)
- [Documentació de Markdown de GitHub](https://docs.github.com/en/get-started/writing-on-github)