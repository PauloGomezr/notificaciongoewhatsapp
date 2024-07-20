# Acceso Rápido a WhatsApp en Imágenes

Este proyecto te permite agregar un acceso rápido a WhatsApp en una imagen utilizando un enlace directo de WhatsApp. Solo necesitas modificar el número de teléfono en el enlace de WhatsApp para adaptarlo a tus necesidades.

## Código HTML

A continuación, se muestra el código HTML que permite cambiar fácilmente el número de teléfono sin hacer muchas ediciones.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Acceso a WhatsApp</title>
    <style>
        .whatsapp-link {
            position: relative;
            display: inline-block;
        }
        .whatsapp-link img {
            max-width: 100%;
            height: auto;
        }
        .whatsapp-button {
            position: absolute;
            bottom: 10px;
            right: 10px;
            background-color: #25D366;
            color: white;
            padding: 10px 15px;
            border-radius: 50%;
            text-align: center;
            font-size: 20px;
            text-decoration: none;
            box-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
    </style>
</head>
<body>
    <div class="whatsapp-link">
        <img src="ruta-a-tu-imagen.jpg" alt="Imagen con acceso a WhatsApp">
        <a href="https://wa.me/1234567890" class="whatsapp-button" target="_blank">
            <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" style="width:40px; height:40px;">
        </a>
    </div>
</body>
</html>
Cómo usar el código
Cambia el número de teléfono: Modifica 1234567890 en el atributo href del enlace de WhatsApp con tu número de teléfono (incluyendo el código de país).
Reemplaza la imagen: Sustituye ruta-a-tu-imagen.jpg con la ruta de tu imagen deseada.
Este código crea un enlace de WhatsApp que se superpone sobre una imagen, permitiendo un acceso rápido y fácil. El número de teléfono puede ser modificado directamente en el atributo href del enlace <a>.

Código Compacto
Para una implementación más compacta:

html
Copiar código
<a href="https://wa.me/1234567890" target="_blank">
    <img src="ruta-a-tu-imagen.jpg" alt="Contacta por WhatsApp" style="position: relative;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" style="position: absolute; bottom: 10px; right: 10px; width: 40px; height: 40px;">
</a>
Instrucciones
Cambia el número de teléfono: Modifica 1234567890 en el atributo href del enlace de WhatsApp con tu número de teléfono (incluyendo el código de país).
Reemplaza la imagen: Sustituye ruta-a-tu-imagen.jpg con la ruta de tu imagen deseada.
Este código coloca un icono de WhatsApp en la esquina inferior derecha de la imagen, creando un enlace directo a WhatsApp. Solo necesitas cambiar el número de teléfono en el atributo href para que funcione con cualquier número.

Añadir un Texto Introductorio al Chat
Si deseas añadir un mensaje predefinido:

html
Copiar código
<a href="https://wa.me/1234567890?text=Hola,%20me%20gustaría%20obtener%20más%20información%20sobre%20sus%20servicios" target="_blank">
    <img src="ruta-a-tu-imagen.jpg" alt="Imagen">
</a>
Modifica el texto después de ?text= con el mensaje que deseas enviar. Asegúrate de usar %20 en lugar de espacios para codificar la URL correctamente.

Solicitar Ubicación del Usuario
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

Este README proporciona una guía completa sobre cómo utilizar el código para añadir un acceso rápido a WhatsApp en una imagen, incluyendo instrucciones para modificar el número de teléfono, añadir mensajes predefinidos y solicitar la ubicación del usuario.







