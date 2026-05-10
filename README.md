<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Esencia y Sistemas - Creación de Tiendas Online con IA</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: #0a0a2a; color: #ffffff; line-height: 1.6; }
        header { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 2rem; text-align: center; border-bottom: 4px solid #f093fb; }
        .container { max-width: 1200px; margin: auto; padding: 2rem; }
        .estadisticas { display: flex; gap: 2rem; flex-wrap: wrap; justify-content: center; margin-bottom: 2rem; }
        .tarjeta-estadistica { background: rgba(255,255,255,0.1); border-radius: 20px; padding: 1rem; flex: 1; min-width: 120px; text-align: center; backdrop-filter: blur(10px);}
        .numero { font-size: 2rem; font-weight: bold; color: #f093fb; }
        .servicios, .paquetes { display: flex; gap: 2rem; flex-wrap: wrap; justify-content: center; margin-bottom: 3rem; }
        .card { background: rgba(255,255,255,0.1); border-radius: 20px; padding: 1.5rem; flex: 1; min-width: 280px; max-width: 320px; backdrop-filter: blur(10px); border-top: 4px solid #f093fb; text-align: center; }
        .precio { font-size: 2rem; color: #f093fb; font-weight: bold; margin: 1rem 0; background: rgba(0,0,0,0.3); display: inline-block; padding: 0.3rem 1rem; border-radius: 40px; }
        .btn { display: inline-block; background: #f093fb; color: #0a0a2a; padding: 0.8rem 1rem; border-radius: 50px; text-decoration: none; font-weight: bold; margin-top: 1rem; width: 100%; text-align: center; cursor: pointer; border: none; }
        footer { background: #050515; color: #aaa; text-align: center; padding: 2rem; margin-top: 2rem; }
        @media (max-width: 768px) { .servicios, .paquetes { flex-direction: column; align-items: center; } }
        h2 { text-align: center; margin-bottom: 2rem; color: #f093fb; }
    </style>
</head>
<body>
    <header>
        <h1>🚀 ESENCIA Y SISTEMAS</h1>
        <p>Creación de tiendas online con inteligencia artificial</p>
    </header>
    <div class="container">
        <div class="estadisticas">
            <div class="tarjeta-estadistica"><h3>👁️ Visitas</h3><div class="numero" id="visitas">0</div></div>
            <div class="tarjeta-estadistica"><h3>💬 Consultas</h3><div class="numero" id="consultas">0</div></div>
            <div class="tarjeta-estadistica"><h3>💰 Cotizaciones</h3><div class="numero" id="cotizaciones">0</div></div>
        </div>
        
        <h2>📦 Nuestros Servicios</h2>
        <div class="servicios">
            <div class="card"><h3>Tienda Básica</h3><div class="precio">$2,900 MXN</div><ul><li>✅ Catálogo hasta 20 productos</li><li>✅ Chat básico</li><li>✅ Diseño responsivo</li><li>✅ Entrega en 3 días</li></ul><button class="btn" onclick="registrarCotizacion('Tienda Básica')">📲 Contratar</button></div>
            <div class="card"><h3>Tienda Profesional</h3><div class="precio">$5,900 MXN</div><ul><li>✅ Catálogo hasta 100 productos</li><li>✅ Chat con IA integrada</li><li>✅ Panel administrativo</li><li>✅ Entrega en 5 días</li></ul><button class="btn" onclick="registrarCotizacion('Tienda Profesional')">📲 Contratar</button></div>
            <div class="card"><h3>Tienda Premium</h3><div class="precio">$9,900 MXN</div><ul><li>✅ Productos ilimitados</li><li>✅ IA avanzada para ventas</li><li>✅ Pasarela de pagos</li><li>✅ Entrega en 7 días</li></ul><button class="btn" onclick="registrarCotizacion('Tienda Premium')">📲 Contratar</button></div>
        </div>

        <h2>🎯 Paquetes Especiales</h2>
        <div class="paquetes">
            <div class="card"><h3>Emprendedor Digital</h3><div class="precio">$7,900 MXN</div><ul><li>🎯 Tienda Profesional</li><li>🎯 Hosting 1 año gratis</li><li>🎯 Dominio .com incluido</li><li>🎯 Soporte 30 días</li></ul><button class="btn" onclick="registrarCotizacion('Emprendedor Digital')">📲 Contratar</button></div>
            <div class="card"><h3>Agencia IA</h3><div class="precio">$12,900 MXN</div><ul><li>🏆 Tienda Premium</li><li>🏆 Chatbot IA personalizado</li><li>🏆 SEO básico</li><li>🏆 Capacitación incluida</li></ul><button class="btn" onclick="registrarCotizacion('Agencia IA')">📲 Contratar</button></div>
            <div class="card"><h3>Mantenimiento Mensual</h3><div class="precio">$990 MXN</div><ul><li>🔧 Actualizaciones</li><li>🔧 Respaldo semanal</li><li>🔧 Soporte prioritario</li><li>🔧 24/7 monitoreo</li></ul><button class="btn" onclick="registrarCotizacion('Mantenimiento')">📲 Contratar</button></div>
        </div>
    </div>
    <footer>
        <p>📍 Camino Antiguo a Chamilpa #50, Colonia Tlatepexco, Cuernavaca, Morelos, CP 62210</p>
        <p>📧 contacto@esencia-sistemas.com | 📞 52 777 910 7055</p>
        <p>© 2026 Esencia y Sistemas - Creación de tiendas con IA</p>
    </footer>

    <!-- Tidio Chat (Lyro AI) -->
    <script src="//code.tidio.co/turocovxhshqbvu6tzomxcxuaoiejo4m.js" async></script>

    <script>
        let visitas = localStorage.getItem('visitas_esencia') ? parseInt(localStorage.getItem('visitas_esencia')) : 0;
        let consultas = localStorage.getItem('consultas_esencia') ? parseInt(localStorage.getItem('consultas_esencia')) : 0;
        let cotizaciones = localStorage.getItem('cotizaciones_esencia') ? parseInt(localStorage.getItem('cotizaciones_esencia')) : 0;
        visitas++; localStorage.setItem('visitas_esencia', visitas);
        document.getElementById('visitas').innerText = visitas;
        document.getElementById('consultas').innerText = consultas;
        document.getElementById('cotizaciones').innerText = cotizaciones;
        
        window.registrarCotizacion = function(pack) { cotizaciones++; localStorage.setItem('cotizaciones_esencia', cotizaciones); document.getElementById('cotizaciones').innerText = cotizaciones; window.open(`https://wa.me/527779107055?text=Me%20interesa%20el%20paquete%20de%20${pack}`, '_blank'); };
    </script>
</body>
</html>