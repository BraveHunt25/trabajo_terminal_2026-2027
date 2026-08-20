# Registro de cambios

## 2026-08-18 - Inicialización del frontend

### Acciones y comandos ejecutados

1. Se verificaron los prerrequisitos:

	```bash
	node --version && npm --version
	```

	Resultado inicial: Node.js no estaba disponible en el `PATH`.

2. Se cargó `nvm` y se verificó Node.js LTS:

	```bash
	export NVM_DIR="$HOME/.nvm"
	source "$NVM_DIR/nvm.sh"
	nvm install --lts
	nvm use --lts
	node --version
	npm --version
	```

	Resultado: Node.js `v24.19.0` y npm `11.17.0`. `nvm` ya estaba instalado y se reutilizó la instalación existente.

3. Se intentó inicializar Next.js en la raíz:

	```bash
	npx create-next-app@latest . --ts --tailwind --eslint --app --src-dir --use-npm --import-alias "@/*"
	```

	Resultado: la ejecución fue rechazada porque la raíz contiene documentación, configuración de asistentes y `src/` que podían entrar en conflicto.

4. Se inicializó la aplicación en una carpeta dedicada:

	```bash
	npx create-next-app@latest frontend --ts --tailwind --eslint --app --src-dir --use-npm --import-alias "@/*" --yes
	```

	La aplicación se creó en `frontend/` con Next.js, TypeScript, Tailwind CSS, ESLint, App Router, `src/` e importaciones mediante `@/*`.

5. La instalación automática de dependencias fue interrumpida durante la primera ejecución. Se completó desde la carpeta del frontend:

	```bash
	cd frontend
	npm install
	```

	Resultado: 359 paquetes añadidos, 360 auditados y 0 vulnerabilidades encontradas.

6. Se eliminó el `package-lock.json` accidental creado en la raíz. El lockfile válido se conserva en `frontend/package-lock.json`.

### Cambios en la estructura

- Se agregó `frontend/` como aplicación ejecutable independiente.
- Se conservaron `CDT-Analysis/`, `.github/`, `README.md`, `LOGS.md` y el contenido documental existente en la raíz.
- Se actualizó `README.md` con la estructura, los comandos de ejecución y las validaciones del frontend.

### Validaciones

Ejecutadas desde `/home/eyael25/projects/tt2026-b036/frontend`:

```bash
npm run lint
npm run build
```

Resultado: ambas finalizaron correctamente. El build de Next.js `16.3.1` compiló TypeScript y generó las rutas estáticas `/` y `/_not-found`.

### Estado del entorno

- Runtime: Node.js LTS `v24.19.0` gestionado con `nvm`.
- Gestor de paquetes: npm `11.17.0`.
- Dependencias instaladas en `frontend/node_modules/`.
- No se configuraron todavía variables de entorno, backend, PostgreSQL, Socket.io ni autenticación JWT.
