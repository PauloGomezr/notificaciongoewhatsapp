# Solicitar Ubicación del Usuario
Para solicitar la ubicación del usuario y redirigir a WhatsApp, sigue estos pasos:

Crea una página HTML:

html
Copiar código
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Enviar Ubicación a WhatsApp</title>
    <script>
        function obtenerUbicacion() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(enviarUbicacion, mostrarError);
            } else {
                alert("La geolocalización no es soportada por este navegador.");
            }
        }

        function enviarUbicacion(position) {
            const lat = position.coords.latitude;
            const lon = position.coords.longitude;
            const mensaje = `Hola, mi ubicación es: https://www.google.com/maps?q=${lat},${lon}`;
            const numero = "1234567890"; // Cambia esto por tu número de WhatsApp
            window.location.href = `https://wa.me/${numero}?text=${encodeURIComponent(mensaje)}`;
        }

        function mostrarError(error) {
            switch (error.code) {
                case error.PERMISSION_DENIED:
                    alert("El usuario negó el permiso para la geolocalización.");
                    break;
                case error.POSITION_UNAVAILABLE:
                    alert("La ubicación no está disponible.");
                    break;
                case error.TIMEOUT:
                    alert("La solicitud de geolocalización ha expirado.");
                    break;
                case error.UNKNOWN_ERROR:
                    alert("Ocurrió un error desconocido.");
                    break;
            }
        }
    </script>
</head>
<body onload="obtenerUbicacion()">
    <h1>Enviando ubicación a WhatsApp...</h1>
</body>
</html>
Aloja el archivo HTML en GitHub Pages o cualquier otro servicio de alojamiento que soporte HTML y JavaScript.

Incrusta el enlace en tu imagen en Google Sites:

html
Copiar código
<a href="https://tu-usuario.github.io/tu-repositorio/" target="_blank">
    <img src="ruta-a-tu-imagen.jpg" alt="Imagen">
</a>
De esta manera, al hacer clic en la imagen, se obtendrá la ubicación del usuario y se redirigirá a WhatsApp con un mensaje que incluye la ubicación.

Contribuciones
Si deseas contribuir a este proyecto, por favor abre un issue o envía un pull request con tus cambios propuestos. ¡Agradecemos tu colaboración!

Licencia
Este proyecto está bajo la Licencia MIT. Para más detalles, consulta el archivo LICENSE.

css
Copiar código

Este README proporciona una guía completa sobre cómo utilizar el código para añadir un acceso rápido a WhatsApp en una imagen, 
incluyendo instrucciones para modificar el número de teléfono, añadir mensajes predefinidos y solicitar la ubicación del usuario.







