# Solución de conflicto — Ejemplo práctico

**Ruta del proyecto (ejemplo):**
`C:\Users\Jesus Mejia\Desktop\LuisaCapa\luisacapa`

**Objetivo:** simular un conflicto en `src/controllers/user.controller.js` y documentar su resolución.

---

## 1 Situación inicial
Partimos de `main` con el archivo `src/controllers/user.controller.js` ya comiteado.

## 2 Comandos para reproducir el conflicto (PowerShell / Windows)

```powershell
cd "C:\Users\Jesus Mejia\Desktop\LuisaCapa\luisacapa"

git switch main


git switch -c feature/user-controller-A

git add src/controllers/user.controller.js
git commit -m "feat(user-controller): versión A"


git switch main

git add src/controllers/user.controller.js
git commit -m "chore: versión en main"


git merge feature/user-controller-A




Al abrir `src/controllers/user.controller.js` verás marcadores como:



##  Resolución manual paso a paso
1. Abrir el archivo en tu editor (VS Code, Notepad++, etc.).
2. Buscar las líneas con `<<<<<<<`, `=======`, `>>>>>>>`.
3. Decidir la versión final (e.g., combinar o elegir una). Ejemplo resultado:
```js
const CONTROLLER_VERSION = 'v1.1-resolved';

```
4. Guardar el archivo.
5. Añadir y commitear los cambios:
```powershell
git add src/controllers/user.controller.js
git commit -m "fix: resolver conflicto en user.controller.js (merge feature/user-controller-A)"
```
6. Verificar el historial:
```powershell
git log --oneline --graph --decorate --all
```

##  Buenas prácticas al resolver conflictos
- Revisar la lógica: asegúrate que la versión resuelta compile y pase pruebas.
- Probar localmente (ejecutar tests si los tienes).
- Añadir comentarios en el commit de resolución explicando por qué se eligió una versión.
- Si el conflicto afecta muchas líneas, considera discutir con quien hizo la otra rama antes de resolver.

---

## Registro de ejemplo (documenta aquí lo que hiciste)
- Fecha: 2025-09-13 20:32:11 UTC
- Archivo en conflicto: `src/controllers/user.controller.js`
- Comandos ejecutados: (ver sección 2)
- Resultado final: commit `fix: resolver conflicto ...`

---

Puedes copiar este archivo a `process/solucion-conflicto.md` en tu repo y luego:
```powershell
git add process/solucion-conflicto.md
git commit -m "docs: documentar resolución de conflicto"
```

