# daniroj.github.io
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personalizá tu Pantalón</title>
    <style>
        /* Un poco de estilo básico para que se vea prolijo */
        body { font-family: Arial, sans-serif; text-align: center; margin-top: 50px; }
        .paso { display: none; } /* Oculta todos los pasos por defecto */
        .paso.activo { display: block; } /* Solo muestra el paso activo */
        .opcion { margin: 10px; padding: 10px; border: 1px solid #ccc; display: inline-block; cursor: pointer; }
        button { margin-top: 20px; padding: 10px 20px; background-color: #28a745; color: white; border: none; cursor: pointer; font-size: 16px; }
    </style>
</head>
<body>

    <h1>Armá tu pantalón ideal 👖</h1>

    <div id="paso1" class="paso activo">
        <h2>Paso 1: Elegí el modelo</h2>
        <label class="opcion">
            <input type="radio" name="modelo" value="Cargo"> Cargo
        </label>
        <label class="opcion">
            <input type="radio" name="modelo" value="Jogging"> Jogging
        </label>
        <br>
        <button onclick="irAPaso2()">Siguiente</button>
    </div>

    <div id="paso2" class="paso">
        <h2>Paso 2: Elegí tus estampas</h2>
        <label class="opcion">
            <input type="radio" name="estampa" value="Estrellas"> Pack Estrellas
        </label>
        <label class="opcion">
            <input type="radio" name="estampa" value="Fuego"> Pack Fuego
        </label>
        <br>
        <button onclick="mostrarResumen()">Ver mi diseño</button>
    </div>

    <div id="resultado" class="paso">
        <h2>¡Excelente elección! 🔥</h2>
        <p id="texto-resumen"></p>
        <button>Enviar pedido por WhatsApp</button>
    </div>

    <script>
        function irAPaso2() {
            // Revisa si seleccionaron un modelo
            let modeloElegido = document.querySelector('input[name="modelo"]:checked');
            if (modeloElegido) {
                document.getElementById('paso1').classList.remove('activo');
                document.getElementById('paso2').classList.add('activo');
            } else {
                alert("Por favor, elegí un modelo primero.");
            }
        }

        function mostrarResumen() {
            // Revisa si seleccionaron una estampa
            let modeloElegido = document.querySelector('input[name="modelo"]:checked').value;
            let estampaElegida = document.querySelector('input[name="estampa"]:checked');
            
            if (estampaElegida) {
                document.getElementById('paso2').classList.remove('activo');
                document.getElementById('resultado').classList.add('activo');
                
                // Muestra el texto final
                document.getElementById('texto-resumen').innerHTML = 
                    "Elegiste un pantalón <strong>" + modeloElegido + "</strong> con las estampas <strong>" + estampaElegida.value + "</strong>.";
            } else {
                alert("Por favor, elegí tus estampas.");
            }
        }
    </script>

</body>
</html>
