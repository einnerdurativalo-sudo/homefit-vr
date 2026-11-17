# HomeFit VR para Meta Quest 2

Prototipo en WebXR. No hay que instalar nada en las gafas: se abre con un enlace en el **Meta Quest Browser**.

## Opción A: publicar en un enlace HTTPS (la más simple)
1. Sube esta carpeta completa a un servicio de hosting estático con HTTPS, por ejemplo Netlify Drop (arrastrar la carpeta), GitHub Pages o Cloudflare Pages.
2. En las Quest 2, abre el navegador, escribe la dirección que te dieron y guárdala en marcadores.
3. Pulsa **Entrar en RV**.

## Opción B: probar desde tu computador con cable USB (sin hosting)
1. Activa el modo desarrollador en las Quest 2 y conecta el cable USB. Acepta la depuración USB en las gafas.
2. En la computadora, dentro de esta carpeta: `python3 -m http.server 8000`
3. En otra terminal: `adb reverse tcp:8000 tcp:8000`
4. En el navegador de las Quest 2 abre `http://localhost:8000`. Para WebXR, `localhost` cuenta como conexión segura.

No funciona abrir `http://192.168.x.x:8000` por Wi-Fi: sin HTTPS el navegador no ofrece la RV.

## Cómo se usa dentro de las gafas
- Apunta con el rayo del control (o pellizca con la mano si tienes seguimiento de manos activado) para elegir la clase, confirmar la seguridad y pulsar **Iniciar clase**.
- Durante la clase, el gatillo pausa y reanuda. En la pausa puedes terminar la clase.
- Al terminar, elige el esfuerzo percibido (escala de Borg) y guarda la sesión.
- Antes de empezar, despeja una zona de 2 × 2 m y revisa el límite del Guardian.

## Notas
- El conteo de repeticiones usa la altura de la cabeza (sentadillas) y de los controles (press). Es experimental y debe validarse en el piloto.
- Los datos de sesiones se guardan solo en el navegador de las gafas.
- La carpeta `vendor` contiene A-Frame 1.6.0 (licencia MIT), por lo que la página funciona sin conexión después de la primera carga con HTTPS.
