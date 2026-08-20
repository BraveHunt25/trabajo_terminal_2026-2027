# Trabajo Terminal 2026-B036

Este repositorio contiene la documentación y el desarrollo del front-end para la digitalización de procesos de cocina.

## Estructura

- `CDT-Analysis/`: documentación de análisis y diseño.
- `.github/`: configuración de asistentes para el desarrollo.
- `frontend/`: aplicación Next.js con TypeScript, Tailwind CSS y App Router.

## Inicialización

Se requiere Node.js LTS. Si se usa `nvm`:

```bash
export NVM_DIR="$HOME/.nvm"
source "$NVM_DIR/nvm.sh"
nvm use --lts
```

Para instalar las dependencias y ejecutar el frontend:

```bash
cd frontend
npm install
npm run dev
```

La aplicación estará disponible en <http://localhost:3000>.

Comandos de validación:

```bash
npm run lint
npm run build
```