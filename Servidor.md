# SERVIDOR

> Estamos utilizando una raspberry pi 4 modelo b, el cual es mini ordenador de escritorio.

Bibliografía empleada:

- https://pedropablomoral.com/raspberrypi/proyectos/servidor-casero/     --> paso: MariaDB (seguridad comando)
- https://internetpasoapaso.com/instalar-servidor-web-en-raspberry-pi/

## ¿QUÉ NECESITAMOS?

- Raspberry Pi 4B
- Micro SD > 16Gb Clase 10
- Disco Externo USB / Adaptador SATA a USB
- Cable de red
- Case para tu Raspberry
- Computador / portatil con Linux / MacOS / Windows (Para el proceso de instalación)
- Teclado (Para el proceso de instalación)
- Adaptador micro HDMI a HDMI (Para el proceso de instalación)



---
# Servidor Web en Raspberry Pi 4 con Flask 
---
## PASOS

- **Actualizar el sistema** ->  sudo apt update && sudo apt upgrade -y
- **Instalar python y pip** ->  sudo apt install python3 python3-pip -y
- **Instalar Flask** -> sudo pip3 install flask
- **Código para crear el servidor**:
```
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def home():
    return render_template("index.html")

@app.route("/about")
def about():
    return render_template("about.html")

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000, debug=True)
```
- **Para ejecutar el servidor flask** -> python3 app.py
Esto va a mostar una dirección (localhost) y el puerto. Para ver su contenido en el navegador pegarlo en el navegador.
- **Para ejecutarlo con otro dispositivo**: Cambiar la direccion por la ip de la Raspeberry (ver ip con: hostname -I) y pegarlo en el navegador.
## Estructura del Proyecto

```plaintext
flask_app/
│── static/          # Archivos estáticos (CSS, JS, imágenes)
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   └── script.js
│   └── images/
│
│── templates/       # Archivos HTML (Jinja2)
│   ├── index.html
│   
│
│── app.py         # Código principal de Flask


```
