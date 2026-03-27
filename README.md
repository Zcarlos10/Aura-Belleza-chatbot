<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aura Belleza</title>
    <link rel="stylesheet" href="css/inicio2.css">
</head>

<body>

<header>
    <nav class="nav-bar">
        <h1 class="logo">Aura Belleza</h1>
        <ul class="menu">
            <li><a href="inicio2.html">Inicio</a></li>
            <li><a href="Producto.html">Catalogo</a></li>
        </ul>
    </nav>
</header>

<main>
    <section class="hero">
        <div class="hero-text">
            <h2>Resalta tu Belleza con Elegancia</h2>
            <p>Encuentra productos exclusivos que te inspiran a ser tu mejor versión.</p>
            <a href="Producto.html" class="btn-gold">Ver Catalogo</a>
        </div>

        <div class="hero-images">
            <img src="/Pagina/img_pagina_web/cosme1.jpeg">
            <img src="/Pagina/img_pagina_web/cosme2.jpeg">
            <img src="/Pagina/img_pagina_web/cosme3.jpeg">
            <img src="/Pagina/img_pagina_web/cosme4.jpeg">
        </div>
    </section>
    <section class="chat-section">

        <h3>Asistente Virtual</h3>
    
        <div id="chatbot">
    
            <div class="chat-header">
                Chatbot Tienda
            </div>
    
            <div id="mensajes"></div>
    
            <div class="chat-input">
                <input type="text" id="input" placeholder="Escribe..." onkeypress="enter(event)">
                <button onclick="enviar()">Enviar</button>
            </div>
    
        </div>
    
    </section>

    <section class="contacto">
        <h3>Contáctanos</h3>
        <p><strong>Correo:</strong> sjaircrack@gmail.com</p>
        <p><strong>Teléfono:</strong> +51 905 858 500</p>
        <p><strong>Dirección:</strong> Av. Empresaria 123, Lima, Perú</p>
    </section>
</main>

<footer>
    <h3>Síguenos en redes</h3>
    <p>Instagram: aurabelleza</p>
    <p>&copy; 2025 Aura Belleza</p>
</footer>
<script>
function enter(e) {
    if (e.key === "Enter") enviar();
}

function enviar() {
    let input = document.getElementById("input");
    let texto = input.value;

    if (texto.trim() === "") return;

    agregar("Tú: " + texto);

    let respuesta = responder(texto);

    setTimeout(() => {
        agregar("Bot: " + respuesta);
    }, 500);

    input.value = "";
}

function agregar(texto) {
    let chat = document.getElementById("mensajes");
    chat.innerHTML += "<p>" + texto + "</p>";
    chat.scrollTop = chat.scrollHeight;
}

function responder(msg) {
    msg = msg.toLowerCase();

    if (msg.includes("hola")) return "¡Hola! Bienvenido 😊";
    if (msg.includes("productos")) return "Tenemos maquillaje, perfumes y más.";
    if (msg.includes("precio")) return "Precios accesibles y promociones.";
    if (msg.includes("pago")) return "Aceptamos Yape, Plin y tarjetas.";
    if (msg.includes("envio")) return "Envíos a todo el Perú.";
    if (msg.includes("devolucion")) return "Cambios en 7 días.";
    if (msg.includes("gracias")) return "¡Gracias por visitarnos!";

    return "No entendí tu consulta.";
}

window.onload = function() {
    agregar("Bot: ¡Hola! 👋 Soy tu asistente virtual.");
};
</script>
</body>
</html>
