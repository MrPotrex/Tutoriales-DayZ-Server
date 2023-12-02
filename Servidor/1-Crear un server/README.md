# ⬇️COMO CREAR UN SERVIDOR DE DAYZ⬇️

Lo primero que tenemos que hacer es ir directamente a
### Steam ➡️ Biblioteca ➡️ Buscador ➡️ DayZ ➡️ Descargamos DayZ Server y Tools.

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180486080026382386/image.png?ex=657d9855&is=656b2355&hm=2f1a49b17896cb6b871acafcf94312a0e98d7de9f1ec0c874b7be85dabada77c&=&format=webp&quality=lossless&width=245&height=242)
> [!IMPORTANT]
> Descargar tambien el juego base.

### Descargado DayZ Server, vamos a ir a la Tuerca ➡️ Administrar ➡️ Ver archivos locales.
![Foto](https://cdn.discordapp.com/attachments/973516122349531136/1180488476832047225/image.png?ex=657d9a91&is=656b2591&hm=f77277c640c11b394283963ce8b156e59c78ecbf6cd65f63aab0dcd0f7600c02&)

### Una vez estemos en la carpeta DayZServer Añadimos el Launcher que tenemos arriba o creamos directamente un bloc de notas.
<details>
  <summary><h1>Bloc de notas</h1></summary>

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
* serverName es para el nombre del server. Ej
```
set serverName=Mancotrex Server
```
* serverLocation es donde esta el servidor. por defecto: (Modificar en caso de cambiar la ruta)
```
set serverLocation="C:\Program Files (x86)\Steam\steamapps\common\DayZServer"
```
* -servermod= es para los mods que solo necesitan acceso por parte del servidor. (Lo explicare mas adelante)
* -mod= es para los mods que solo necesitan acceso por parte del cliente. (Lo explicare mas adelante)

### Guardamos el archivo y modificamos su nombre a IniciarServer.bat (Tiene que cambiarte el icono) y lo añadimos a la carpeta de DayZServer.
![Foto](https://media.discordapp.net/attachments/973516122349531136/1180495679135694908/image.png?ex=657da146&is=656b2c46&hm=80e576d4faf540c99297059e15ef8afe3b3fcfc8cb246135c344ee52999826ec&=&format=webp&quality=lossless&width=560&height=140)
</details>
