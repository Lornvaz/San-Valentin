<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>San Valentín 💖</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #ffe6f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            overflow: hidden;
        }
        #contenedor {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 30px;
        }
        #pregunta {
            background-color: white;
            padding: 15px;
            border-radius: 15px;
            box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.2);
            display: inline-block;
            text-align: center;
            transition: all 0.5s ease;
            width: auto;
            min-width: 200px;
        }
        button {
            margin: 10px;
            padding: 10px 15px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 18px;
            transition: all 0.3s ease;
        }
        #si {
            background-color: #ff4d79;
            color: white;
        }
        #no {
            background-color: #444;
            color: white;
        }
        #mensaje {
            margin-top: 20px;
            font-size: 22px;
            color: #ff4d79;
            font-weight: bold;
        }
        .corazon {
            position: absolute;
            bottom: -50px;
            font-size: 2em;
            color: red;
            animation: subir 3s linear infinite;
        }
        @keyframes subir {
            0% {
                transform: translateY(0);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div id="contenedor">
        <h1>💌 Una pregunta importante 💌</h1>
        <div style="height: 20px;"></div>
        <div id="pregunta">
            <p style="font-size: 1.5em;">¿Quieres ser mi San Valentín? 💖</p>
            <button id="si" onclick="aceptar()">Sí</button>
            <button id="no" onclick="rechazar()">No</button>
            <p id="mensaje"></p>
        </div>
    </div>
    <script>
        let tamañoNo = 18;
        const mensajesBonitos = [
            "¿Segura? Yo creo que seríamos buen match 💕",
            "Cada día contigo es especial, no me hagas sufrir </3",
            "Eres la persona más linda del mundo, di que sí 💖",
            "Mi corazón late más fuerte por ti ❤️",
            "Te haré muy feliz, solo tienes que aceptar 💌",
            "Imagínate todas las citas bonitas que tendremos 🌹",
            "Ya casi desaparece el botón, mejor di que sí ):",
            "Ya usé todas mis razones, ¿Ahora sí dices que sí? 😅",
            "Acepta y te prometo que será inolvidable 😍"
        ];
        let indiceMensaje = 0;

        function aceptar() {
            let pregunta = document.getElementById("pregunta");
            pregunta.innerHTML = "<h2 style='font-size: 2.5em;'>Te amo, gracias por hacerme una ratita feliz ❤</h2>";
            pregunta.style.padding = "50px";
            pregunta.style.fontSize = "1.2em";
            lanzarCorazones();
        }

        function rechazar() {
            let botonNo = document.getElementById("no");
            let mensaje = document.getElementById("mensaje");

            if (indiceMensaje < mensajesBonitos.length) {
                tamañoNo -= 2;
                botonNo.style.fontSize = tamañoNo + "px";
                botonNo.style.padding = (tamañoNo / 2) + "px " + (tamañoNo) + "px";
                mensaje.innerText = mensajesBonitos[indiceMensaje];
                indiceMensaje++;
            }
        }

        function lanzarCorazones() {
            for (let i = 0; i < 20; i++) {
                let corazon = document.createElement("div");
                corazon.classList.add("corazon");
                corazon.innerHTML = "❤️";
                corazon.style.left = Math.random() * 100 + "vw";
                corazon.style.animationDuration = (Math.random() * 2 + 2) + "s";
                document.body.appendChild(corazon);
                setTimeout(() => {
                    corazon.remove();
                }, 3000);
            }
        }
    </script>
</body>
</html>
