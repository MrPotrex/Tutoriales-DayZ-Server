# ⬇️COMO AÑADIR UN MOD A NUESTRO SERVER⬇️

> [!WARNING]
> ¡Antes de hacer este tutorial, recuerda que tienes que hacer [este](https://github.com/MrPotrex/Tutoriales-DayZ-Server/tree/main/Servidor/1-Crear%20un%20server).

### Nos vamos a dirigir al [Workshop](https://steamcommunity.com/app/221100/workshop/) de DayZ y vamos a buscar un mod. (Yo voy a instalar el [VppAdmin](https://steamcommunity.com/sharedfiles/filedetails/?id=1828439124&searchtext=vppadmin))

* Una vez hayamos encontrado el mod que queremos, tenemos que tener en cuenta 2 cosas. 
### Tenemos que suscribirnos al mod y ver que no necesite dependencias. (En mi caso mi dependencia es el [@CF](https://steamcommunity.com/workshop/filedetails/?id=1559212036))

![foto](https://media.discordapp.net/attachments/973516122349531136/1180545796270206987/image.png?ex=657dcff3&is=656b5af3&hm=dd0b209e938e7f490903c98603c5ae3cf55a6f109c5a7af29361a09526950499&=&format=webp&quality=lossless&width=866&height=123)

## Ahora vamos a los archivos del juego base.

### DayZ ➡️ Tuerca ➡️ Administrar ➡️ Ver archivos locales.
![Foto](https://cdn.discordapp.com/attachments/973516122349531136/1180488476832047225/image.png?ex=657d9a91&is=656b2591&hm=f77277c640c11b394283963ce8b156e59c78ecbf6cd65f63aab0dcd0f7600c02&)

> [!TIP]
> Activa la opción de ver las carpetas ocultas 👁️.

### En la barra, al lado del buscador le damos a  Steamapps ➡️ common ➡️ DayZ ➡️!Workshop.

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180544473156034620/image.png?ex=657dceb7&is=656b59b7&hm=2cd1589675c7e053d9503dc2de35c762d01c59de356f28ff0f697d5a3b8f70fa&=&format=webp&quality=lossless&width=1009&height=80)

### Buscamos las carpetas del mod en `!Workshop`. (En mi caso son `@CF` & `@VPPAdminTools`) Cuando la hayamos encontrado hacemos `Cntrol + C` en la carpeta y vamos a la carpeta del server `DayZServer`, allí hacemos `Cntrol + V` y pegamos la carpeta del mod (@CF) en la carpeta raiz del server.

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180548810758438952/image.png?ex=657dd2c2&is=656b5dc2&hm=6cb5af70bac2c94a4f9fc56f47d80b02391f8fb90f0d5900f46b711c96ad94e2&=&format=webp&quality=lossless&width=562&height=256)

> [!TIP]
> Si le das clic derecho a la carpeta y le das donde dice `Abrir en una nueva pestaña` te será mas facil mover las keys.

### Entramos en la carpeta del mod y nos encontraremos estas carpetas

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180549473005490307/image.png?ex=657dd35f&is=656b5e5f&hm=a3235f58a1f612098192e214f39660389ef21291dd577926299be04c7587d29a&=&format=webp&quality=lossless&width=557&height=107)

### Vamos a entrar en la carpeta `Keys` y vamos a copiar el archivo `nombre.bikey`. Despues vamos a la carpeta raiz del server `DayZServer` y buscamos la carpeta `keys`. pegamos el archivo y nos tendría que quedar así

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180550269038235749/image.png?ex=657dd41d&is=656b5f1d&hm=556545d7ce0690285abe8795e9dd7925d0abc0984cf17af9063fc9146057f9ab&=&format=webp&quality=lossless&width=560&height=235)

> [!NOTE]
> La configuración de `@VPPAdminTools` esta en otro tutorial (PROXIMAMENTE).

### Ahora vamos a ir a `IniciarServer.bat`, Clic derecho y le damos a `Editar`. Cuando nos abra el editor, vamos a buscar la linea de `"-mod="`. Una vez la encontremos tenemos que añadir el nombre de la carpeta del mod. EJ:
```
"-mod=@CF"
```
> [!TIP]
> En el caso de tener una dependencia o querer añadir mas mods debería ser: `"-mod=@CF;@VPPAdminTools"`. Es muy importante respetar los ";" y los Framework añadirlos siempre de los primeros para que carguen antes y no haya ningun problema.

### Guardamos y abrimos el server desde el launcher `IniciarServer.bat`
Si hemos hecho todo paso a paso nuestro servidor iniciará. Si no inicia o no nos deja entrar, leed bien las cosas, puede ser que necesite alguna dependencia o el mod sea privado.

## Abrimos el juego y nos vamos a la opción de Servidores ➡️ Local y debería aparecer así

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180556060784853072/image.png?ex=657dd982&is=656b6482&hm=ab43e578be16485fc34501fd3a60a6c25506e127a697c10dd8add007ccb0285e&=&format=webp&quality=lossless&width=867&height=323)

> [!NOTE]
> Si los mods que añadas no te salen en verde es porque te has saltado algun paso o es del lado del servidor. (Este tutorial es para los mods que van al cliente. Los de server irán en otro tutorial o se añadirá proximamente)

## Entramos a nuestro servidor y verificamos que el mod funcione perfectamente 😄. 

### En caso de querer eliminar el mod, es solamente borrar la carpeta, la key de la carpeta `keys` y eliminarlo del `IniciarServer.bat`.

### En caso de actualización, debes ir al juego, darle a la opción de mods, buscar el que se ha actualizado y darle a reparar antes de ir a la carpeta del mod. Así te ahorras el dolor de cabeza por si no funciona. 

![Foto](https://media.discordapp.net/attachments/973516122349531136/1180558395368022026/image.png?ex=657ddbaf&is=656b66af&hm=c0e873fc68595b7e6833d3aca717b399da90f947dae3c46c7ff249965edfee7d&=&format=webp&quality=lossless&width=825&height=365)

### Hacemos el mismo proceso con la carpeta, la copiamos desde `!Workshop` y la pegamos en la carpeta raiz del server y ya estaría "actualizado".

> [!NOTE]
> Si te sigue fallando puede ser que hayan tenido un problema con la actualización y lo esten arreglando o no hayas hecho bien todo el proceso.

# Y listo, a disfrutar 😄. 
