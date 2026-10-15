# Flip 7 · Contador de puntajes

Contador de puntajes para el juego de cartas Flip 7, pensado para usar en el celular durante la partida.

Es una sola página (`index.html`) con CSS y JS inline, sin librerías ni build. Basta con abrirla en el navegador o servirla con GitHub Pages.

## Reglas que aplica

- Se juega por rondas. Gana quien llega a 200 puntos o más al cerrar una ronda.
- Flip 7 suma un bono de +15 sobre los puntos de la ronda.
- Bust vale 0 esa ronda.
- Si hay empate en el primer lugar sobre 200, se juega otra ronda.

## Funciones

- Una tarjeta por jugador, ordenada por puntaje al cerrar cada ronda.
- Ingreso de puntos, Flip 7 y Bust por jugador, con vista previa del nuevo total.
- Jugadores pendientes marcados en naranja; líder en dorado; ganador en verde.
- Deshacer la última ronda (los puntos vuelven a los campos para corregirlos).
- Historial de juegos con victorias por jugador y tabla de rondas del juego actual.
- Todo se guarda en `localStorage` del dispositivo.
- Tema claro y oscuro, safe areas de iPhone y pantalla encendida durante el juego.

## Jugadores

La lista está en la constante `PLAYERS` al inicio del script de `index.html`.

## Publicar con GitHub Pages

Settings → Pages → Deploy from a branch → `main` / `(root)`.
