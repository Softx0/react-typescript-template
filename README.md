# React TypeScript Template 2025

## Descripción

Template moderno de React con TypeScript completamente configurado con las mejores prácticas de desarrollo. Incluye autenticación, rutas protegidas, sistema de inactividad, y arquitectura escalable siguiendo principios SOLID.

##  Características Principales

###  Tecnologías Core
- **React 18** con TypeScript
- **Vite** como build tool (más rápido que CRA)
- **TailwindCSS** para estilos
- **React Router DOM** para navegación
- **Redux Toolkit** para estado global
- **Context API** para autenticación

###  Autenticación y Seguridad
- Sistema de autenticación con JWT
- Encriptación de tokens con CryptoJS
- Rutas protegidas por roles
- Hook de inactividad configurable
- Logout automático por inactividad

###  Arquitectura Escalable
- Sistema de rutas organizadas por módulos (SOLID)
- Lazy loading de componentes
- Estructura de carpetas escalable
- Servicios API centralizados
- Hooks personalizados reutilizables

###  Herramientas de Desarrollo
- **ESLint** con configuración Airbnb
- **Prettier** para formateo de código
- **Husky** para git hooks
- **Commitlint** para mensajes de commit
- **Lint-staged** para linting automático

###  DevOps y Deploy
- **Docker** con nginx para producción
- **CI/CD** con Azure Pipelines y GitLab
- Scripts de deploy automatizados
- Configuración de variables de entorno

##  Inicio Rápido

### 1. Clonar e Instalar
```bash
git clone <tu-repo>
cd react-typescript-template-2023
npm install
```

### 2. Variables de Entorno
Crea un archivo `.env` basado en las siguientes variables:
```bash
# API Configuration
VITE_API_BASE_URL=http://localhost:3001/api
VITE_API_TIMEOUT=10000

# JWT Configuration
VITE_JWT_SECRET=your-jwt-secret-key
VITE_JWT_EXPIRES_IN=24h

# Feature Flags
VITE_ENABLE_INACTIVITY_TIMER=true
VITE_DEFAULT_INACTIVITY_TIME=300000

# Environment
VITE_ENVIRONMENT=development
```

### 3. Iniciar Desarrollo
```bash
npm run dev
# o
npm start
```

### 4. Build para Producción
```bash
npm run build
```

##  Uso de la Aplicación

### Login
- Usa cualquier email y contraseña para la demo
- Automáticamente se generará un JWT mock
- Redirección automática al dashboard

### Dashboard
- Área protegida que requiere autenticación
- Logout manual o automático por inactividad
- Interfaz moderna con TailwindCSS

##  Estructura del Proyecto

```
src/
├── components/          # Componentes reutilizables
│   ├── routing/        # Componentes de enrutamiento
│   │   ├── ProtectedRoute.tsx
│   │   ├── InactivityWrapper.tsx
│   │   └── RouteRenderer.tsx
├── context/            # Context API providers
│   ├── AuthContext.tsx
│   ├── BaseContext.tsx
│   └── index.ts
├── hooks/              # Custom hooks
│   ├── useAsync.ts
│   ├── useInactivityTimer.ts
│   └── index.ts
├── pages/              # Páginas de la aplicación
│   ├── Login/
│   └── Dashboard/
├── routes/             # Sistema de rutas escalable
│   ├── types/
│   ├── routeConfigs/   # Configuraciones por módulo
│   └── allRoutes.ts    # Consolidador de rutas
├── services/           # Servicios de API
│   ├── api/
│   │   └── axiosConfig.ts
│   └── authService.ts
├── types/              # Definiciones TypeScript
├── utils/              # Utilidades
│   ├── encryption.ts
│   ├── jwt.ts
│   └── apiHelpers.ts
├── config/             # Configuraciones
│   └── env.ts
└── redux/              # Estado global (Redux)
```

##  Scripts Disponibles

### Desarrollo
```bash
npm run dev          # Iniciar servidor de desarrollo
npm run build        # Build para producción
npm run preview      # Preview del build
```

### Calidad de Código
```bash
npm run lint         # Ejecutar ESLint
npm run lint:fix     # Corregir errores automáticamente
npm run format       # Formatear código con Prettier
npm run type-check   # Verificar tipos TypeScript
```

### Testing
```bash
npm run test         # Ejecutar tests
npm run test:coverage # Tests con coverage
```

##  Características Avanzadas

### Sistema de Rutas Escalable
- Configuración modular de rutas
- Lazy loading automático
- Metadata para SEO
- Timeouts de inactividad por ruta

### Gestión de Estado Híbrida
- Redux Toolkit para estado global
- Context API para autenticación
- Hooks personalizados para lógica reutilizable

### Seguridad
- JWT con encriptación AES
- Validación de tokens
- Refresh tokens automático
- Logout por inactividad

### Desarrollo
- Hot reload con Vite
- Type checking en tiempo real
- Git hooks automatizados
- Mensajes de commit estandarizados

##  Docker

### Desarrollo
```bash
docker build -t react-app .
docker run -p 3000:80 react-app
```

### Producción
El template incluye configuración completa de Docker con nginx optimizado para producción.

##  CI/CD

Incluye configuración para:
- **Azure Pipelines** (`azure-pipelines.yml`)
- **GitLab CI** (`.gitlab-ci.yml`)
- **GitHub Actions** (opcional)

##  Clean Architecture

### Arquitectura Implementada

El proyecto sigue los principios de Clean Architecture adaptados para React:

![CleanArchitectureReact](https://user-images.githubusercontent.com/32858351/173492130-2400f1b6-0262-4214-86c8-2733a5219f57.svg)

### Capas

- **Servicios Externos:** Conectan el dominio con APIs externas
  - `services/`: Configuración de Axios y servicios HTTP
  - `api/`: Cliente HTTP centralizado

- **Adaptadores:** Estandarización de datos
  - `adapters/`: Transformación de datos entre capas
  - `utils/`: Utilidades de manejo de APIs

- **Componentes:** Lógica de negocio y presentación
  - `components/`: Componentes reutilizables
  - `hooks/`: Custom hooks
  - `routes/`: Sistema de enrutamiento
  - `pages/`: Páginas de la aplicación

- **Models/State:** Corazón de la aplicación
  - `types/`: Interfaces y modelos TypeScript
  - `context/`: Estado local con Context API
  - `redux/`: Estado global con Redux Toolkit

##  Guías de Uso

### Agregar Nueva Ruta
1. Crear el componente en `src/pages/`
2. Agregar configuración en `src/routes/routeConfigs/`
3. Importar en `src/routes/allRoutes.ts`

### Crear Nuevo Hook
1. Crear archivo en `src/hooks/`
2. Exportar en `src/hooks/index.ts`
3. Usar en componentes

### Agregar Nuevo Servicio
1. Crear archivo en `src/services/`
2. Usar el cliente Axios configurado
3. Manejar errores correctamente

##  Contribuir

1. Fork el proyecto
2. Crear rama feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit con formato (`git commit -m 'feat: agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Crear Pull Request

##  Licencia

Este proyecto está bajo la Licencia MIT.

---

**Hecho con ❤️ para la comunidad de desarrolladores**
