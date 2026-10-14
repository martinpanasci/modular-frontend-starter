# Modular Frontend Starter

Template independiente de frontend con **Next.js App Router, React, TypeScript strict y Tailwind CSS 4**, organizado por features y límites de responsabilidad.

Este repositorio contiene únicamente el frontend; no incluye backend ni requiere el template fullstack. Las integraciones HTTP se configuran para el backend que use cada proyecto.

## Estructura

```text
modular-frontend-starter/
├── .github/          # CI y Dependabot
├── client/           # Aplicación, configuración, tests y dependencias npm
│   ├── .husky/
│   ├── e2e/
│   ├── public/
│   ├── src/
│   ├── test/
│   ├── AGENTS.md
│   ├── README.md
│   └── package.json
└── LICENSE
```

## Inicio rápido

Requiere Node.js >=22.12.0. Desde la raíz del repositorio:

```bash
cd client
npm ci
npm run dev
```

Si necesitás variables locales, copiá `client/.env.example` a `client/.env.local` y ajustá sus valores.

## Calidad y hooks

Todos los comandos npm se ejecutan desde `client/`:

```bash
npm run lint
npm run typecheck
npm test
npm run build
npx playwright install
npm run test:e2e
```

`npm ci` ejecuta `prepare`, que configura Husky desde la raíz Git usando `client/.husky`. El pre-commit entra en `client/` y ejecuta lint-staged con las dependencias locales. Para reinstalar los hooks, ejecutá `npm run prepare` desde `client/`.

GitHub Actions usa `client/` como directorio de trabajo y Dependabot revisa `/client`. `.git` y `.github` permanecen en la raíz; no hay un paquete npm raíz.

Consultá [client/README.md](client/README.md) para arquitectura, configuración y comandos completos, y [client/AGENTS.md](client/AGENTS.md) para las reglas del frontend.
