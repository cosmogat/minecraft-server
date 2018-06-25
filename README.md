# minecraft-server
A init daemon for Debian GNU/Linux to manage your minecraft server
## Why a init daemon for minecraft?
Because with this script you can:
* Start and stop minecraft server like other init daemon.
* Get the control of minecraft command line.
* Program scripts for minecraft with bash.
## How to install
First you need an user and a group for minecraft server, you can do this in your command line as root:
```
groupadd minecraft
useradd -g minecraft -d /opt/minecraft -s /bin/false minecraft
adduser USER minecraft
```
where USER is your main user. You can change the directory "/opt/minecrat" but you need to change in the script too. Before to move the script to init daemon folder you maybe want to change some bash variables on this script:
* USUARI <- minecraft user name, in this case is "minecraft"
* RAM <- RAM for the server
* APLIC_RUTA <- Application path
* SERVER_RUTA <- Server path
* REGION_RUTA <- Region path

Now, we assume that you have a working minecraft server in  *$SERVER_RUTA* path with the name "minecraft_server.jar"; a world with its regions in *$REGION_RUTA* path, and the minecraft game in *$APLIC_RUTA* path. If this is true you can install the script with this commands as root in your command line:
```
cp minecraft-server /etc/init.d/minecraft-server
chown root:root /etc/init.d/minecraft-server
chmod 755 /etc/init.d/minecraft-server

```
## How to use
You can use this script as a root user like other daemon scripts in Debian GNU/Linux:
```
/etc/init.d/minecraft-server {start|stop|restart|status}
```
or
```
systemctl {start|stop|restart|status} minecraft-server.service
```
## Autors
* **Cosmo Cat**  [cosmogat](https://github.com/cosmogat)
## License
See the [LICENSE](LICENSE)
