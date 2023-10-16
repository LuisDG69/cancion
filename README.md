<!DOCTYPE html>
<html>
<head>
    <style>
        html {
            height: 100%;
        }

        body {
            height: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: black; /* cambié la imagen de fondo a un color de fondo negro */
            overflow: hidden;
        }

        @keyframes cresent {
            0% {
                transform: translate(-30px, 30px) scale(0.9);
                box-shadow: none;
            }
            40%, 60% { /* agregué una pausa del 20% en la animación */
                transform: translate(0px, 0px) scale(1.02);
                box-shadow: 0 0 10px #ff5303, 0 0 80px #ff5303;
                background-color: #fc5c00;
            }
            100% {
                transform: translate(30px, -30px) scale(0.9);
                box-shadow: none;
            }
        }

        .moon {
            background-color: black;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            position: relative;
            animation-play-state: paused; /* agregué esta línea para pausar inicialmente la animación */
        }
        .moon::before {
            content: "";
            background-color: #fcf270;
            position: absolute;
            display: block;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            z-index: -1;
            animation-duration: 10s; /* cambié 'animation' a 'animation-duration' */
            animation-name: cresent; /* agregué esta línea */
            animation-timing-function: linear; /* agregué esta línea */
            animation-fill-mode: forwards; /* agregué esta línea */
        }

        @keyframes textFadeIn {
          from { opacity: 0; color:black; }
          to { opacity: 1; color:white; }
        }

        .text {
          position:absolute;
          font-size:20px;
          animation:textFadeIn linear forwards;
          animation-play-state:paused; /* pause the animation initially */
          line-height:1.5; /* add some line spacing */
        }

        #textRight {
          top:50%;
          right:10px;
        }

        #textLeft {
          top:50%;
          left:10px;
        }

        #textBottom {
          bottom:10px;
          left:50%;
          transform:translateX(-50%);
        }
    </style>
</head>
<body>
    <div class="moon"></div> <!-- Agregué este div -->

    <div id="textRight" class="text">La verdad pido disculpas<br>por no hablarte como antes<br>todo el tiempo la verdad es<br>el miedo a que te vuelvas alejar.</div>
    <div id="textLeft" class="text">Quiero que seas feliz<br>tal vez esto es poco para tus intereses<br>no pido tu regreso por que se<br>que eso ya no es posible.</div>
    <div id="textBottom" class="text">Lo único que pido es que sigas siendo feliz<br>alcanzando tus objetivos.</div>

    <script>
      var playButton = document.getElementById('playButton');
      
      setTimeout(function() {
        document.querySelector('.moon').style.animationPlayState = 'running'; /* inicia la animación después de un retraso */
        document.querySelector('#textRight').style.animationPlayState = 'running'; /* inicia la animación del texto derecho después de un retraso */
      }, 5000); // retraso de 5 segundos
      
      setTimeout(function() {
        document.querySelector('#textLeft').style.animationPlayState = 'running'; /* inicia la animación del texto izquierdo después de un retraso */
      }, 10000); // retraso de 10 segundos
      
      setTimeout(function() {
        document.querySelector('#textBottom').style.animationPlayState = 'running'; /* inicia la animación del texto inferior después de un retraso */
      }, 15000); // retraso de 15 segundos
    </script>
</body>
</html>
