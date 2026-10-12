---
description: Crea un git worktree en .worktrees/<nombre-del-worktree>
---

Ejecuta exactamente este comando bash en el directorio de trabajo actual,
sin cambiarte de directorio y sin hacer nada más (no mkdir, no edits, no
commit, no operaciones adicionales):

git worktree add .worktrees/$1

`$1` es el nombre del worktree recibido como argumento.
