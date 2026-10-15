# Flip 7 · Contador de puntajes

Contador de puntajes para el juego de cartas Flip 7, pensado para usar en el celular durante la partida. Se puede instalar como app (PWA) y funciona sin conexión.

La app es una sola página (`index.html`) con CSS y JS inline, sin librerías ni build. Junto a ella están el manifest, el service worker y los íconos.

## Reglas que aplica

- Se juega por rondas. Gana quien llega a 200 puntos o más al cerrar una ronda (la meta se puede cambiar en la configuración).
- Flip 7 suma un bono de +15 sobre los puntos de la ronda.
- Bust vale 0 esa ronda.
- Si hay empate en el primer lugar sobre la meta, se juega otra ronda.

## Cómo se usa

1. **Vista inicial:** se eligen los jugadores (con sugerencias de quienes jugaron antes) y se ve el historial de ganadores. Desde ahí se pueden registrar partidas anteriores, compartir el historial e importarlo.
2. **Juego:** una tarjeta por jugador con puntos de la ronda, Flip 7 y Bust (cada uno con su efecto). "Borrar datos de esta ronda" limpia lo ingresado en la ronda en curso. Al cerrar la ronda se reordena por puntaje.
3. **Configuración (rueda):** editar jugadores a mitad de juego, compartir e importar ganadores, cambiar la meta, tema claro u oscuro, instalar la app y borrar datos.

## Pasar el historial entre teléfonos

No hay cuentas ni servidor: cada teléfono guarda sus datos en `localStorage` (clave `flip7-contador-v2`). Para sincronizar, en un teléfono se toca **Compartir** y se envía el mensaje; en el otro se toca **Importar**, se pega y se elige **Agregar a mi historial** o **Reemplazar mi historial**. La importación también suma los jugadores a la lista de "Jugaron antes".

El formato es texto simple, así que también se puede escribir a mano:

```
Juego 1: Simon
Juego 4 · 15-10-2026: Exe 205, Wato 150, Ware 90
Jugadores: Wato, Ware, Exe
```

O directamente un ganador por línea.

## Instalar como app

Se publica con GitHub Pages (Settings → Pages → Deploy from a branch → `main` / `(root)`). Luego:

- **iPhone:** abrir en Safari → Compartir → Agregar a inicio.
- **Android:** Chrome ofrece instalarla, o desde la rueda de configuración → "Instalar en este teléfono".

En iPhone la app instalada guarda sus datos aparte de Safari. Para llevar el historial, usa Compartir e Importar.

## Archivos

- `index.html`: la app completa.
- `manifest.webmanifest`, `sw.js`: configuración de la PWA y caché sin conexión. Al publicar cambios, conviene subir la versión de `CACHE` en `sw.js`.
- `icons/`: logo en SVG y PNG (192, 512, maskable y apple-touch-icon).
