# Flip 7 · Contador de puntajes

Contador de puntajes para el juego de cartas Flip 7, pensado para usar en el celular durante la partida.

Es una sola página (`index.html`) con CSS y JS inline, sin librerías ni build. Basta con abrirla en el navegador o servirla con GitHub Pages.

## Reglas que aplica

- Se juega por rondas. Gana quien llega a 200 puntos o más al cerrar una ronda (la meta se puede cambiar en la configuración).
- Flip 7 suma un bono de +15 sobre los puntos de la ronda.
- Bust vale 0 esa ronda.
- Si hay empate en el primer lugar sobre la meta, se juega otra ronda.

## Cómo se usa

1. **Vista inicial:** se eligen los jugadores (con sugerencias de quienes jugaron antes) y se ve el historial de ganadores. Desde ahí también se pueden registrar victorias de partidas anteriores que no se anotaron en el teléfono.
2. **Juego:** una tarjeta por jugador con puntos de la ronda, Flip 7 y Bust. Al cerrar la ronda se reordena por puntaje.
3. **Configuración (rueda):** editar jugadores a mitad de juego, cambiar la meta, tema claro u oscuro, descartar el juego, borrar el historial o borrar todos los datos.

## Datos

Todo se guarda en `localStorage` del teléfono (clave `flip7-contador-v2`); no hay cuentas ni servidor. El historial parte con una victoria de Simon, Mati y Joseto (constante `PRELOADED_WINNERS`). Si había un juego en curso de la versión anterior, se retoma al abrir.

El botón "Compartir" de la vista inicial genera un resumen de ganadores para pegar en el grupo.

## Publicar con GitHub Pages

Settings → Pages → Deploy from a branch → `main` / `(root)`.
