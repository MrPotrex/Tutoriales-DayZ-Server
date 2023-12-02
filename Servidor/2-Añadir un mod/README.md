# ⬇️COMO AÑADIR UN MOD A NUESTRO SERVER⬇️

-

-
-


-


-
-

--




Lo primero que tenemos que hacer es ir directamente a
### Steam ➡️ Biblioteca ➡️ Buscador ➡️ DayZ ➡️ Descargamos DayZ Server y Tools.

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180486080026382386/image.png?ex=657d9855&is=656b2355&hm=2f1a49b17896cb6b871acafcf94312a0e98d7de9f1ec0c874b7be85dabada77c&=&format=webp&quality=lossless&width=245&height=242)
> [!IMPORTANT]
> Descargar tambien el juego base.

### Descargado DayZ Server, vamos a ir a la Tuerca ➡️ Administrar ➡️ Ver archivos locales.
![Foto](https://cdn.discordapp.com/attachments/973516122349531136/1180488476832047225/image.png?ex=657d9a91&is=656b2591&hm=f77277c640c11b394283963ce8b156e59c78ecbf6cd65f63aab0dcd0f7600c02&)

### Cuando estemos en la Carpeta DayZServer buscamos el archivo llamado `serverDZ.cfg` y lo abrimos con nuestro editor (Preferiblemente Visual Studio).

<details>
  <summary><h1>⬇️Configuración de serverDZ.cfg⬇️</h1></summary>
  
### En el archivo nos centraremos ahora mismo en:

```
hostname = "";  // Server name
passwordAdmin = "";         // Password to become a server admin
maxPlayers = 1;            // Maximum amount of players
```
En `hostname =` Metemos el nombre que queremos que salga en el Launcher. ej:
```
hostname = "Prueba Mancotrex";
```
En `passwordAdmin =` la contraseña de admin que tendremos. ej:
```
passwordAdmin = "1234";
```
En `maxPlayers =` Metemos el numero de jugadores que aguanta el servidor (Al ser local, lo mejor es poner 1 o 2).

Guardamos y listo, lo tendríamos configurado levemente.
</details>

### Una vez configurado el archivo `serverDZ.cfg` Añadimos el Launcher que tenemos arriba o creamos directamente un bloc de notas.
<details>
  <summary><h1>⬇️Creación del bloc de notas⬇️</h1></summary>

⬇️Añadimos al bloc de notas este codigo⬇️
```
@echo off
:start
::Server name 
set serverName=Modificar
::Server files location (Viene por defecto, pero si os falla teneís que buscar donde habeís puesto el server)
set serverLocation="C:\Program Files (x86)\Steam\steamapps\common\DayZServer"
::Server Port
set serverPort=2302
::Server config
set serverConfig=serverDZ.cfg
::Logical CPU cores to use (Equal or less than available)
set serverCPU=2
::Sets title for terminal (DONT edit)
title %serverName% batch
::DayZServer location (DONT edit)
cd "%serverLocation%"
echo (%time%) %serverName% started.
::Launch parameters (edit end: -config=|-port=|-profiles=|-doLogs|-adminLog|-netLog|-freezeCheck|-filePatching|-BEpath=|-cpuCount=|Añadir los mods por parte del server en -servermod y los demas en -mod)
start "DayZ Server" /min "DayZServer_x64.exe" -config=%serverConfig% -port=%serverPort% -cpuCount=%serverCPU% -profiles=modificarnombre -dologs -adminlog -netlog -freezecheck "-servermod=""-mod="
::Time in seconds before kill server process (14400 = 4 hours)
timeout 14390
taskkill /im DayZServer_x64.exe /F
::Time in seconds to wait before..
timeout 10
::Go back to the top and repeat the whole cycle again
goto start
```
### Aquí priorizamos las siguientes lineas
```
- set serverName=Modificar
- set serverLocation="C:\Program Files (x86)\Steam\steamapps\common\DayZServer"
- "-servermod="
- "-mod="
```
* `serverName` es para el nombre del server. Ej
```
set serverName=Mancotrex Server
```
* `serverLocation` es donde esta el servidor. por defecto: (Modificar en caso de cambiar la ruta)
```
set serverLocation="C:\Program Files (x86)\Steam\steamapps\common\DayZServer"
```
* `-servermod=` es para los mods que solo necesitan acceso por parte del servidor. (Lo explicare mas adelante)
* `-mod=` es para los mods que solo necesitan acceso por parte del cliente. (Lo explicare mas adelante)

### Guardamos el archivo y modificamos su nombre a IniciarServer.bat (Tiene que cambiarte el icono) y lo añadimos a la carpeta de DayZServer.
![Foto](https://media.discordapp.net/attachments/973516122349531136/1180495679135694908/image.png?ex=657da146&is=656b2c46&hm=80e576d4faf540c99297059e15ef8afe3b3fcfc8cb246135c344ee52999826ec&=&format=webp&quality=lossless&width=560&height=140)
</details>

> [!IMPORTANT]
> ⬆️ Si te has descargado el .bat de arriba, no hace falta leer eso ⬆️.

### Arrancamos el IniciarServer.bat y nos saldrán 2 consolas.
![Foto](https://media.discordapp.net/attachments/973516122349531136/1180498486685335644/image.png?ex=657da3e3&is=656b2ee3&hm=0a54d63b27e6c81e2a57a6c32d8e800fb3ba3e5f6ceefb7b05f7fcd8e20f0827&=&format=webp&quality=lossless&width=529&height=285)

> [!NOTE]
> La consola mas importante es la DayZ Console Version. El otro si quieren lo pueden cerrar. 

### Arrancamos DayZ ➡️ Servidores ➡️ Local y tendría que salir nuestro servidor.
![Foto](https://media.discordapp.net/attachments/973516122349531136/1180499946672234536/image.png?ex=657da53f&is=656b303f&hm=ef9900ac235b52379162879f4092c514cce0f0d940dc0c77074b4f0934783f73&=&format=webp&quality=lossless&width=1324&height=313)

### Y listo, ya tendríamos nuestro servidor vanilla listo.
