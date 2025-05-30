
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simulador de Consumo Eléctrico</title>
    <link rel="stylesheet" href="css/style.css">

    <div class="navbar">
    <!-- Enlace para abrir el modal de Soporte -->
<li class="nav-item">
   
    <a class="nav-link" href="soporte.html">Soporte</a>
  </li>
  
  <!-- Enlace para abrir el modal de Recomendaciones -->
  <li class="nav-item">
   
    <a class="nav-link" href="index3.html">Recomendaciones</a>
  </li>
  <div id="recomendacionModal" class="modal">
    <div class="modal-content">
      <span class="close" onclick="cerrarRecomendacion()">&times;</span>
      <p id="mensajeRecomendacion"></p>
    </div>
  </div>
  
  
        </div>
        <div class="navbar-actions">
          <button class="mode-toggle" onclick="toggleMode()">🌙</button>
        </div>
      
    
    <style>

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

form input,
form select,
form button {
  max-width: 400px;
  text-align: center;
}

button {
  margin-left: auto;
  margin-right: auto;
  display: block;
}


        /* Paleta de colores */
:root {
  --primary-color: #6a4cf7; /* color principal */
  --bg-light: #fff;
  --bg-dark: #222;
  --text-light: #fff;
  --text-dark: #333;
}

/* Estilos de la barra de navegación */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  background-color: var(--primary-color);
  color: var(--text-light);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 100;
  transition: background-color 0.3s, color 0.3s;
}

.navbar a {
  margin: 0 15px;
  text-decoration: none;
  color: var(--text-light);
  font-weight: bold;
  transition: color 0.3s;
}

.navbar a:hover {
  color: #f7f7f7;
}

.search-bar {
  padding: 8px 12px;
  border-radius: 20px;
  border: none;
  width: 200px;
  transition: width 0.3s;
}

.search-bar:focus {
  width: 300px;
}

.navbar-actions .mode-toggle {
  background: none;
  border: none;
  color: var(--text-light);
  font-size: 18px;
  cursor: pointer;
  transition: color 0.3s;
}

.navbar-actions .mode-toggle:hover {
  color: #f7f7f7;
}

/* Modo oscuro */
body.dark-mode {
  --primary-color: #333;
  --bg-light: #121212;
  --bg-dark: #212121;
  --text-light: #f7f7f7;
  --text-dark: #bbb;
}

body.dark-mode .navbar {
  background-color: var(--primary-color);
  color: var(--text-light);
}

body.dark-mode .navbar a {
  color: var(--text-light);
}

body.dark-mode .search-bar {
  background-color: #444;
  color: var(--text-light);
}

/* Animación para los elementos */
.navbar a, .search-bar, .navbar-actions button {
  opacity: 0;
  animation: fadeIn 0.5s forwards;
}

.navbar a:nth-child(1) { animation-delay: 0.3s; }
.navbar a:nth-child(2) { animation-delay: 0.4s; }
.navbar a:nth-child(3) { animation-delay: 0.5s; }
.navbar a:nth-child(4) { animation-delay: 0.6s; }
.navbar a:nth-child(5) { animation-delay: 0.7s; }

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

        :root {
            --bg-color: #f4f4fc;
            --primary-color: #4a90e2;
            --secondary-color: #ffffff;
            --highlight-color: #a8dadc;
            --text-color: #333333;
            --accent-color: #ff6f61;
            --font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            margin: 0;
            font-family: var(--font-family);
            color: var(--text-color);
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        .container {
            max-width: 900px;
            margin: auto;
            padding: 20px;
            transition: padding 0.3s ease;
        }

        h1, h2 {
            text-align: center;
            color: var(--primary-color);
            transition: color 0.3s ease;
        }

        .card {
            background-color: var(--secondary-color);
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
            transition: background-color 0.3s ease;
        }

        label, select, input, button {
            display: block;
            width: 100%;
            margin-bottom: 10px;
        }

        label {
            font-weight: bold;
        }

        input[type="number"], select, input[type="text"], input[type="email"] {
            padding: 8px;
            border-radius: 6px;
            border: 1px solid #ccc;
            transition: border 0.3s ease;
        }

        button {
            background-color: var(--primary-color);
            color: white;
            padding: 10px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #357ab7;
        }

        .resultados {
            font-size: 18px;
            padding: 10px;
            background-color: var(--highlight-color);
            border-radius: 8px;
            transition: background-color 0.3s ease;
        }

        .registro {
            background-color: #e9ecef;
            padding: 15px;
            border-radius: 8px;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }

        .footer {
            text-align: center;
            margin-top: 30px;
            font-size: 14px;
            color: #666;
            transition: color 0.3s ease;
        }

        .portada {
            text-align: center;
            padding: 80px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }

        .portada h1 {
            font-size: 48px;
            color: var(--primary-color);
            transition: color 0.3s ease;
        }

        .portada button {
            width: auto;
            padding: 15px 30px;
            font-size: 20px;
            transition: background-color 0.3s ease;
        }

        .dark-mode {
            background-color: #333333;
            color: #f4f4fc;
        }

        .dark-mode .card {
            background-color: #444444;
        }

        .dark-mode .resultados {
            background-color: #555555;
        }

        .dark-mode .registro {
            background-color: #666666;
        }

        .dark-mode button {
            background-color: #555555;
        }

        .dark-mode h1, .dark-mode h2 {
            color: #f4f4fc;
        }

        @media (max-width: 600px) {
            .portada h1 {
                font-size: 32px;
            }

            .portada p {
                font-size: 16px;
            }

            .portada button {
                font-size: 16px;
                padding: 10px 20px;
            }

            h1, h2 {
                font-size: 24px;
            }

            .card, .registro {
                padding: 15px;
            }

            input[type="number"], select, button {
                font-size: 14px;
            }

            .resultados {
                font-size: 16px;
            }

            .footer {
                font-size: 12px;
            }
        }


        @media (max-width: 600px) {
  .navbar {
    flex-direction: column;
    align-items: flex-start;
    padding: 10px 15px;
  }

  .menu-items {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin-top: 10px;
  }

  .menu-items a {
    margin: 8px 0;
  }

  .navbar-actions {
    align-self: flex-end;
    margin-top: 10px;
  }

  form input, form select, form button {
    font-size: 16px;
  }

  .container {
    padding: 10px;
  }

  .card {
    margin-bottom: 15px;
  }

  #formularioDatos {
    width: 100%;
    padding: 0 10px;
  }
}

.modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.5);
}

.modal-content {
    background-color: #000000;
    margin: 15% auto;
    padding: 20px;
    border-radius: 10px;
    width: 80%;
    max-width: 500px;
    text-align: center;
}

.close {
    color: #aaa;
    float: right;
    font-size: 24px;
    font-weight: bold;
    cursor: pointer;
}

.modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.5);
}

.modal-content {
    background-color: #050505;
    margin: 10% auto;
    padding: 20px;
    border-radius: 10px;
    width: 80%;
    max-width: 600px;
    text-align: left;
}

.close {
    color: #aaa;
    float: right;
    font-size: 24px;
    font-weight: bold;
    cursor: pointer;
}



    </style>
<body>
    <div id="portada" class="portada">
        <h1>Bienvenido al Simulador</h1>
        
        <p>Ingresa tus datos para comenzar a calcular el consumo eléctrico de tu electrodoméstico.</p>
        <form id="formularioDatos" onsubmit="guardarDatos(event)">
            <input type="text" id="nombre" placeholder="Tu nombre" required>
            <input type="email" id="correo" placeholder="Tu correo" required>
            <input type="number" id="celular" placeholder="Tu número de celular" required>
            <select id="localidad" required>
                <option value="" disabled selected>Selecciona tu localidad</option>
                <option value="Barrios Unidos">Barrios Unidos</option>
                <option value="Bosa">Bosa</option>
                <option value="Cabeza de Vaca">Cabeza de Vaca</option>
                <option value="Chapinero">Chapinero</option>
                <option value="Ciudad Bolívar">Ciudad Bolívar</option>
                <option value="Engativá">Engativá</option>
                <option value="Fontibón">Fontibón</option>
                <option value="Kennedy">Kennedy</option>
                <option value="La Candelaria">La Candelaria</option>
                <option value="Los Mártires">Los Mártires</option>
                <option value="Puente Aranda">Puente Aranda</option>
                <option value="Rafael Uribe Uribe">Rafael Uribe Uribe</option>
                <option value="San Cristóbal">San Cristóbal</option>
                <option value="Santa Fé">Santa Fé</option>
                <option value="Suba">Suba</option>
                <option value="Teusaquillo">Teusaquillo</option>
                <option value="Tunjuelito">Tunjuelito</option>
                <option value="Usaquén">Usaquén</option>
                <option value="Usme">Usme</option>
                <option value="Sumapaz">Sumapaz</option>
            </select>
            <select id="estrato" required>
                <option value="">Selecciona tu estrato</option>
                <option value="1">Estrato 1</option>
                <option value="2">Estrato 2</option>
                <option value="3">Estrato 3</option>
                <option value="4">Estrato 4</option>
                <option value="5">Estrato 5</option>
                <option value="6">Estrato 6</option>
            </select>
            <button type="submit">Iniciar Simulación</button>

            <button type="button" onclick="toggleModoOscuro()">🌙 Modo Oscuro</button>
        </form>
    </div>

    <div id="simulador" style="display:none;">
        <div class="container">
            <h1>Simulador de Consumo Eléctrico</h1>

            <div class="card">
                <h2>Datos del Usuario</h2>
                <div id="datosUsuario"></div>
            </div>
            

            <div class="card">
                <p>Este simulador te permite calcular el consumo eléctrico de electrodomésticos. Ingresa el dispositivo, las horas de uso y su potencia para conocer el gasto total.</p>
                <button onclick="mostrarPromedios()" style="margin-top: 10px;">Datos de referencias para el Usuario</button>
                

                <label for="electrodomestico">Nombre del electrodoméstico:</label>
                <input type="text" id="electrodomestico" placeholder="Ej. Televisor" required>

                <label for="potencia">Potencia del electrodoméstico (en W):</label>
                <input type="number" id="potencia" min="1" max="2000" placeholder="Ej. 150" required>

                <label for="horas">Horas de uso por día:</label>
                <input type="number" id="horas" min="1" max="24" placeholder="Ej. 4" required>



                <button onclick="calcularConsumo()">Calcular Consumo</button>

                <div id="resultado" class="resultados"></div>
                <div id="costoTotal" class="resultados"></div>
            </div>

            <div class="card">
                <h2>Historial de Consumo</h2>
                <button onclick="mostrarHistorial()">Mostrar Registros</button>
                <button onclick="limpiarRegistros()">Limpiar Datos</button>
                <div id="historial"></div>
            </div> 

            <div class="footer">
                Desarrollado para simulación educativa - Consumo Eléctrico
            </div>
        </div>
    </div>

    <!-- Modal de Recomendación -->
<div id="recomendacionModal" class="modal">
    <div class="modal-content">
      <span class="close" onclick="cerrarRecomendacion()">&times;</span>
      <h2>¡Atención!</h2>
      <p id="mensajeRecomendacion"></p>
    </div>
  </div>
  

    <script>

const limites = {
    "1": 70000,
    "2": 90000,
    "3": 110000,
    "4": 140000,
    "5": 170000,
    "6": 190000
};

      function mostrarSimulador() {
            document.getElementById("portada").style.display = "none";
            document.getElementById("simulador").style.display = "block";
        }

        function guardarDatos(event) {
    event.preventDefault();
    const nombre = document.getElementById("nombre").value.trim();
    const correo = document.getElementById("correo").value.trim();
    let celular = document.getElementById("celular").value.trim();
    const localidad = document.getElementById("localidad").value.trim();
    const estrato = document.getElementById("estrato").value.trim();

    // Validar que el nombre no contenga números
    const nombreRegex = /^[a-zA-Z\s]+$/;
    if (!nombreRegex.test(nombre)) {
        alert("El nombre solo puede contener letras y espacios.");
        return;
    }

    // Eliminar cualquier carácter no numérico del número de celular
    celular = celular.replace(/\D/g, "");  // Esto elimina cualquier carácter no numérico

    // Validar que el número de celular tenga exactamente 10 dígitos
    if (celular.length <= 9) {
        alert("El número de celular debe tener exactamente 10 dígitos.");
        return;
    }

    // Validar que el correo contenga "@" y ".com"
    const correoRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!correoRegex.test(correo)) {
        alert("Por favor, ingresa un correo electrónico válido.");
        return;
    }

    // Validación de que todos los campos estén llenos
    if (!nombre || !correo || !celular || !localidad || !estrato) {
        alert("Por favor, completa todos los campos.");
        return;
    }

    // Guardar los datos en localStorage
    localStorage.setItem("usuario", JSON.stringify({ nombre, correo, celular, localidad, estrato }));
    mostrarSimulador();
    mostrarDatosUsuario();
}




        function mostrarDatosUsuario() {
            const usuario = JSON.parse(localStorage.getItem("usuario"));
            if (usuario) {
                document.getElementById("datosUsuario").innerHTML = `
                    <p><strong>Nombre:</strong> ${usuario.nombre}</p>
                    <p><strong>Correo:</strong> ${usuario.correo}</p>
                    <p><strong>Celular:</strong> ${usuario.celular}</p>
                    <p><strong>Localidad:</strong> ${usuario.localidad}</p>
                    <p><strong>Estrato:</strong> ${usuario.estrato}</p>
                `;
            }
        }

        function toggleModoOscuro() {
            document.body.classList.toggle("dark-mode");
        }
        function calcularConsumo() {
    const potencia = parseFloat(document.getElementById("potencia").value);
    const horas = parseFloat(document.getElementById("horas").value);
    const electrodomestico = document.getElementById("electrodomestico").value;
    const usuario = JSON.parse(localStorage.getItem("usuario"));
    const estrato = usuario.estrato;

    // Validación de horas
    if (horas > 24) {
        alert("Las horas de uso no pueden ser mayores a 24.");
        return;
    }
    if (potencia > 2000) {
        alert("La potencia máxima permitida es de 2000 W.");
        return;
    }

    if (potencia && horas) {
        const consumoDiario = (potencia * horas) / 1000; // kWh por día
        const consumoMensual = consumoDiario * 30;
        const consumoAnual = consumoDiario * 365;

        document.getElementById("resultado").innerHTML = `
            <p><strong>Consumo total del ${electrodomestico}:</strong> ${consumoDiario.toFixed(2)} kWh por día.</p>
            <p><strong>Consumo mensual estimado:</strong> ${consumoMensual.toFixed(2)} kWh</p>
            <p><strong>Consumo anual estimado:</strong> ${consumoAnual.toFixed(2)} kWh</p>
        `;

        registrarConsumo(electrodomestico, consumoDiario);

        const tarifa = obtenerTarifa(estrato);

        const costoDiario = consumoDiario * tarifa;
        const costoMensual = consumoMensual * tarifa;
        const costoAnual = consumoAnual * tarifa;

        const promedioCosto = (costoDiario + (costoMensual / 30) + (costoAnual / 365)) / 3;

        document.getElementById("costoTotal").innerHTML = `
            <p><strong>Costo diario (estrato ${estrato}):</strong> $${costoDiario.toFixed(2)} COP</p>
            <p><strong>Costo mensual estimado:</strong> $${costoMensual.toFixed(2)} COP</p>
            <p><strong>Costo anual estimado:</strong> $${costoAnual.toFixed(2)} COP</p>
            <p><strong>Promedio diario estimado:</strong> $${promedioCosto.toFixed(2)} COP</p>
        `;

    
    }

document.getElementById("costoTotal").innerHTML = `
    <p><strong>Costo diario (estrato ${estrato}):</strong> $${costoDiario.toFixed(2)} COP</p>
    <p><strong>Costo mensual estimado:</strong> $${costoMensual.toFixed(2)} COP</p>
    <p><strong>Costo anual estimado:</strong> $${costoAnual.toFixed(2)} COP</p>
    <p><strong>Promedio diario estimado:</strong> $${promedioCosto.toFixed(2)} COP</p>
`;

if (costoMensual > limites[estrato]) {
    mostrarRecomendacion(estrato, costoMensual);
}

}

function verificarConsumo(estrato, gastoMensual) {
    const promedio = promedioPorEstrato[estrato];
    if (gastoMensual > promedio) {
        mostrarAlertaConsumo();
    }
}

function mostrarAlertaConsumo() {
    const mensaje = "⚠️ Su consumo ha superado el promedio normal para su estrato. Por favor revise nuestras recomendaciones en la sección correspondiente o comuníquese con su compañía de energía.";
    const modal = document.getElementById("recomendacionModal");
    const mensajeElemento = document.getElementById("mensajeRecomendacion");
    mensajeElemento.textContent = mensaje;
    modal.style.display = "block";
}

function cerrarRecomendacion() {
    document.getElementById("recomendacionModal").style.display = "none";
}


function mostrarRecomendacion(estrato, costoMensual) {
    const mensaje = `El consumo mensual ($${costoMensual.toFixed(2)} COP) supera el límite para el estrato ${estrato}. Considera reducir el uso.`;
    document.getElementById("mensajeRecomendacion").innerText = mensaje;
    document.getElementById("recomendacionModal").style.display = "block";


    const limites = {
    "1": 70000,
    "2": 90000,
    "3": 110000,
    "4": 140000,
    "5": 170000,
    "6": 190000
};

// Función para verificar si se superó el promedio
function verificarConsumo(estrato, montoPagado) {
    const limite = limites[estrato];
    
    if (limite === undefined) {
        console.log("Estrato no válido.");
        return;
    }

    if (montoPagado > limite) {
        console.log(`Has superado el promedio de pago para el estrato ${estrato} (${limite} COP).`);
    } else {
        console.log(`Estás dentro del promedio para el estrato ${estrato} (${limite} COP).`);
    }
}

// Ejemplo de uso:
const estratoUsuario = "3";
const montoPagado = 125000;

verificarConsumo(estratoUsuario, montoPagado);


if (costoMensual > limites[estrato]) {
    mostrarRecomendacion(estrato, costoMensual);
}

    document.getElementById("mensajeRecomendacion").innerText = mensaje;
    document.getElementById("recomendacionModal").style.display = "block";

    if (costoMensual > limites[estrato]) {
    console.log("Mostrando recomendación...");
    mostrarRecomendacion(estrato, costoMensual);
}


}

function cerrarRecomendacion() {
    document.getElementById("recomendacionModal").style.display = "none";
}


        function obtenerTarifa(estrato) {
            switch (estrato) {
                case "1":
                    return 400; // Estrato 1
                case "2":
                    return 600; // Estrato 2
                case "3":
                    return 800; // Estrato 3
                case "4":
                    return 1000; // Estrato 4
                case "5":
                    return 1200; // Estrato 5
                case "6":
                    return 1400; // Estrato 6
                default:
                    return 0;
            }
        }

        function registrarConsumo(electrodomestico, consumoDiario) {
    const usuario = JSON.parse(localStorage.getItem("usuario"));
    const estrato = usuario.estrato;

    // Calcular el consumo mensual y anual
    const consumoMensual = consumoDiario * 30;
    const consumoAnual = consumoDiario * 365;

    // Obtener la tarifa dependiendo del estrato
    const tarifa = obtenerTarifa(estrato);

    // Calcular el costo diario, mensual y anual
    const costoDiario = consumoDiario * tarifa;
    const costoMensual = consumoMensual * tarifa;
    const costoAnual = consumoAnual * tarifa;

    // Obtener fecha actual
    const fecha = new Date();
    const mes = fecha.toLocaleString("es-ES", { month: "long" });
    const anio = fecha.getFullYear();

    // Crear el objeto de consumo
    const registro = {
        electrodomestico,
        consumoDiario: consumoDiario.toFixed(2),
        consumoMensual: consumoMensual.toFixed(2),
        consumoAnual: consumoAnual.toFixed(2),
        costoDiario: costoDiario.toFixed(2),
        costoMensual: costoMensual.toFixed(2),
        costoAnual: costoAnual.toFixed(2),
        mes,
        anio
    };

    // Guardar el historial en el localStorage
    let historial = JSON.parse(localStorage.getItem("historial")) || [];
    historial.push(registro);
    localStorage.setItem("historial", JSON.stringify(historial));
}



function mostrarHistorial() {
    const historial = JSON.parse(localStorage.getItem("historial")) || [];
    const historialDiv = document.getElementById("historial");

    if (historial.length === 0) {
        historialDiv.innerHTML = "<p>No hay registros aún.</p>";
        return;
    }

    // Inicializar los totales
    let totalConsumoDiario = 0;
    let totalConsumoMensual = 0;
    let totalConsumoAnual = 0;
    let totalCostoDiario = 0;
    let totalCostoMensual = 0;
    let totalCostoAnual = 0;

    // Recorrer el historial y acumular los totales
    historial.forEach((registro) => {
        totalConsumoDiario += parseFloat(registro.consumoDiario);
        totalConsumoMensual += parseFloat(registro.consumoMensual);
        totalConsumoAnual += parseFloat(registro.consumoAnual);
        totalCostoDiario += parseFloat(registro.costoDiario);
        totalCostoMensual += parseFloat(registro.costoMensual);
        totalCostoAnual += parseFloat(registro.costoAnual);
    });

    // Mostrar los registros individuales
    historialDiv.innerHTML = historial.map((registro, index) => `
        <div class="registro">
            <p><strong>Registro ${index + 1}</strong></p>
            <p>Electrodoméstico: ${registro.electrodomestico}</p>
            <p>Consumo diario: ${registro.consumoDiario} kWh</p>
            <p>Consumo mensual: ${registro.consumoMensual} kWh</p>
            <p>Consumo anual: ${registro.consumoAnual} kWh</p>
            <p><strong>Costo diario estimado:</strong> $${registro.costoDiario} COP</p>
            <p><strong>Costo mensual estimado:</strong> $${registro.costoMensual} COP</p>
            <p><strong>Costo anual estimado:</strong> $${registro.costoAnual} COP</p>
            <p><em>Fecha: ${registro.mes} ${registro.anio}</em></p>
        </div>
    `).join("");

    // Mostrar los totales
    historialDiv.innerHTML += `
        <div class="totales">
            <p><strong>Total Consumo Diario:</strong> ${totalConsumoDiario.toFixed(2)} kWh</p>
            <p><strong>Total Consumo Mensual:</strong> ${totalConsumoMensual.toFixed(2)} kWh</p>
            <p><strong>Total Consumo Anual:</strong> ${totalConsumoAnual.toFixed(2)} kWh</p>
            <p><strong>Total Costo Diario:</strong> $${totalCostoDiario.toFixed(2)} COP</p>
            <p><strong>Total Costo Mensual:</strong> $${totalCostoMensual.toFixed(2)} COP</p>
            <p><strong>Total Costo Anual:</strong> $${totalCostoAnual.toFixed(2)} COP</p>
        </div>
    `;
}

        function limpiarRegistros() {
            localStorage.removeItem("historial");
            document.getElementById("historial").innerHTML = "<p>No hay registros.</p>";
        }
        function toggleMode() {
  document.body.classList.toggle("dark-mode");
}


function mostrarPromedios() {
    document.getElementById("promedioModal").style.display = "block";
}

function cerrarPromedio() {
    document.getElementById("promedioModal").style.display = "none";


    

}
function mostrarPromediosEstrato() {
    document.getElementById("promediosEstrato").style.display = "block";
  }

    </script>
</body>
<!-- Modal de Promedios de Consumo -->
<div id="promedioModal" class="modal">
    <div class="modal-content">
      <span class="close" onclick="cerrarPromedio()">&times;</span>
  
      <!-- Promedios por electrodoméstico -->
      <h2>Promedios de consumo eléctrico</h2>
      <p style="font-style: italic; font-size: 14px; color: #555;">
        Estos son valores promedio. Para mayor precisión, revise la etiqueta de consumo de su dispositivo.
      </p>
      <table style="width:100%; margin-top: 10px; border-collapse: collapse;">
        <thead>
          <tr>
            <th style="border-bottom: 1px solid #ccc; text-align: left;">Electrodoméstico</th>
            <th style="border-bottom: 1px solid #ccc; text-align: left;">Consumo Promedio Diario (kWh)</th>
            <th style="border-bottom: 1px solid #ccc; text-align: left;">Consumo Aproximado (W)</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>Refrigerador</td><td>1.2</td><td>50 W</td></tr>
          <tr><td>Televisor LED (5 horas)</td><td>0.3</td><td>60 W</td></tr>
          <tr><td>Lavadora (1 ciclo)</td><td>0.5</td><td>400 W</td></tr>
          <tr><td>Microondas (30 min)</td><td>0.6</td><td>800 W</td></tr>
          <tr><td>Aire acondicionado (8 horas)</td><td>4.8</td><td>600 W</td></tr>
          <tr><td>Bombillo LED (8 horas)</td><td>0.08</td><td>10 W</td></tr>
          <tr><td>Computador portátil (6 horas)</td><td>0.3</td><td>50 W</td></tr>
          <tr><td>Plancha (1 hora)</td><td>1.0</td><td>1000 W</td></tr>
        </tbody>
      </table>
  
      <!-- Botón para mostrar promedios por estrato -->
      <button onclick="mostrarPromediosEstrato()" style="margin-top: 20px;">Ver promedios por estrato</button>
  
      <!-- Promedios por estrato -->
      <div id="promediosEstrato" style="display: none; margin-top: 15px;">
        <h3>Promedio mensual por estrato</h3>
        <p style="font-weight: bold; line-height: 1.6;">
          Estrato 1 → 70,000 COP<br>
          Estrato 2 → 90,000 COP<br>
          Estrato 3 → 110,000 COP<br>
          Estrato 4 → 140,000 COP<br>
          Estrato 5 → 170,000 COP<br>
          Estrato 6 → 190,000 COP
        </p>
      </div>
    </div>
  </div>
  
  

