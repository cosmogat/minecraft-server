# minecraft-server
A init daemon for Debian GNU/Linux to manage your minecraft server

## How to install
First you need an user and a group for minecraft server, you can do this in your command line as root:
```
groupadd minecraft
useradd -g minecraft -d /opt/minecraft -s /bin/false minecraft
adduser USER minecraft
```
where USER is your main user. You can change the directory "/opt/minecrat" but you need to change in the script too. Before to move the script to init daemon folder you maybe want to change some bash variables on this script:
* USUARI <- minecraft user name, in this case is "minecraft"
* RAM <-RAM for the server
* APLIC_RUTA <- Application path
* SERVER_RUTA <- Server path
* REGION_RUTA <- Region path

Now, we assume that you have a working minecraft server in  $SERVER_RUTA path with the name "minecraft_server.jar"; a world with its regions in $REGION_RUTA path, and the minecraft game in $APLIC_RUTA path. If this is true you can install the script with this commands as root in your command line:
```
cp minecraft-server /etc/init.d/minecraft-server
chown root:root /etc/init.d/minecraft-server
chmod 755 /etc/init.d/minecraft-server

```
## How to use

## Autors
* **Cosmo Cat**  [cosmogat](https://github.com/cosmogat)
## License
See the [LICENSE](LICENSE)
