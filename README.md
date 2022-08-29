## Chatbot Whatsapp (OpenSource)
#### 2022

El siguiente proyecto incluye inteligencia artificial gracias al servicio de __dialogflow__.


### ATENCION 🔴
> 💥💥 Si aparece el Error Multi-device es porque se tiene la cuenta de whatsapp afiliada al modo "BETA de Multi dispositivo" por el momento no se tiene soporte para esas personas si se quiere hacer uso de este __BOT__ se debe de salir del modo BETA y intentarlo de la manera tradicional

> El core de whatsapp esta en constante actualizaciones por lo cual siempre revisa la ultima fecha de la actualizacion 


#### Acceso rápido 
> Si se tiene una cuenta en __heroku__ se puede desplegar este proyecto con (1 click)

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/walfs/BOTReport) 


#### Actualización

| Feature  | Status |
| ------------- | ------------- |
| Dialogflow  | ✅  |
| MySQL  | ✅  |
| JSON File  | ✅  |
| QR Scan (route) | ✅ |
| Easy deploy heroku  | ✅  |
| Buttons | ✅ℹ️  (No funciona en multi-device)|
| Send Voice Note | ✅ |
| Add support ubuntu/linux | ✅ |

## Requisitos
- node v14 o superior
- VSCode (Editor de codigo) [Descargar](https://code.visualstudio.com/download)
- MySql (opcional) solo aplica si vas a usar el modo 'mysql'  [sql-bot.sql migración]
- Dialogflow (opcional) solo aplica si vas a usar el modo 'dialogflow'

### (Actualmente no compatible AGO 2022) Botones


> Implementar los botones solo necesitas hacer uso del metodo __sendMessageButton__ que se encuentra dentro `./controllers/send` dejo un ejemplo de como usarlo.


``` javascript
const { sendMessageButton } = require('./controllers/send')

await sendMessageButton(
    {
        "title":"¿Que te interesa ver?",
        "message":"Recordar analizar la incidencia antes de reportar",
        "footer":"Gracias",
        "buttons":[
            {"body":"🛠 Incidencias"},
            {"body":"👉 Preguntas frecuentes"},
            {"body":"😁 Uso del BOT"}
        ]
    }
)

```

## Notas de Voz

> Se pueden enviar notas de voz con formato nativo para que no se vea como reenviado. En este ejemplo enviare el archivo __PTT-20220223-WA0000.opus__ que se encuentra dentro de la carpeta de __/mediaSend__

``` javascript
const { sendMediaVoiceNote } = require('./controllers/send')

await sendMediaVoiceNote(client, from, 'PTT-20220223-WA0000.opus')

```

## Instruciones
__Descargar o Clonar repositorio__

__¿Ubuntu / Linux?__
> Asegurate de instalar los siguientes paquetes
```
sudo apt-get install -y libgbm-dev
sudo apt install -y gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils wget
```

__Instalar dependencias (npm install)__
> Ubicate en le directorio que descargaste y via consola o terminal ejecuta el siguiente comando

`npm install` 



__Configurar .env__
> Con el editor de texto crea un archivo `.env` el cual debes de guiarte del archivo `.env.example`
```
######DATABASE: none, mysql, dialogflow

DEFAULT_MESSAGE=true
SAVE_MEDIA=true
PORT=3000
DATABASE=none
LANGUAGE=es
SQL_HOST=
SQL_USER=
SQL_PASS=
SQL_DATABASE=
```


__Ejecutar el script__
> Ubicarse en le directorio y via consola o terminal ejecuta el siguiente comando
`npm run start`


__Whatsapp en tu celular__
> Abrir la aplicación de Whatsapp en dispositivo y escanear el código QR
<img src="https://i.imgur.com/RSbPtat.png" width="500"  />
Visitar la pagina 
`http://localhost:3000/qr` 


__Listo 😎__
> Cuando sale este mensaje tu BOT está __listo__ para trabajar!
![](https://i.imgur.com/eoJ4Ruk.png)



## ¿Como usarlo el chatbot de whatsapp?
> Escribe un mensaje al whatsapp que vinculaste con tu BOT

> Ahora deberías  obtener un arespuesta por parte del BOT, ademas de esto tambien se crea un archivo excel
con el historial de conversación  con el número de la persona.

## Preguntar al BOT
> Puedes interactuar con el bot ejemplo escribele __hola__ y el bot debe responderte!

