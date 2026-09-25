# AGENTS.md

Asteroids — clon arcade en HTML5 Canvas puro, sin dependencias ni bundler.

## Comandos

- No hay `package.json`, ni build/test/lint/typecheck. No hay nada que ejecutar con npm.
- Para verificar: abre `index.html` en el navegador, o `npx serve .` (http://localhost:3000). Revisa la consola del navegador por errores de JS; no existe otra forma de testear.

## Arquitectura

- Toda la lógica está en `game.js`, cargado por `index.html` vía `<script>`.
- El tamaño de canvas está duplicado: `width="800" height="600"` en `index.html` y las const `W`/`H` en `game.js`. Si cambias uno, cambia el otro.
- Estado global como variables top-level (`ship`, `bullets`, `asteroids`, `particles`, `score`, `lives`, `level`, `state`).
- Máquina de estados: `state` ∈ `'playing' | 'dead' | 'gameover'`, manejada en `update()`.

## Convenciones

- Textos de HUD y comentarios en español.
- `'use strict';` al inicio; secciones separadas con `// ── Título ──`.
- Entidades como clases con métodos `update(dt)` y `draw()`; `wrap`, `dist`, `rand`, `randInt` como utilidades en la parte superior.
- Entrada por teclado: mapas `keys`/`justPressed`; `pressed(code)` consume la pulsación un solo frame.