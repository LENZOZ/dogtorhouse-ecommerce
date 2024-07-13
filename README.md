
# Dogtorhouse

Bienvenido al repositorio de Dogtorhouse, una plataforma ecommerce para productos de mascotas. Este es un monorepo que contiene tanto el frontend como el backend del proyecto.

## Estructura del Proyecto

El repositorio está organizado de la siguiente manera:

```
dogtorhouse/
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...otros archivos de configuración del frontend
├── backend/
│   ├── src/
│   ├── tests/
│   ├── package.json
│   └── ...otros archivos de configuración del backend
├── .gitignore
├── README.md
└── ...otros archivos de configuración del proyecto
```

## Uso de Ramas

Utilizamos las siguientes ramas para organizar nuestro flujo de trabajo:

- **main**: Contiene la última versión estable del código.
- **develop**: Rama de integración para ambas partes, frontend y backend. Todas las características y correcciones se integran aquí antes de ser liberadas.
- **dev/nombre-desarrollador**: Cada desarrollador trabaja en su propia rama basada en `develop`.
- **release/x.y**: Utilizadas para la preparación final de una nueva versión.

### Flujo de Trabajo

1. **Crear una rama personal desde `develop`**:
   ```bash
   git checkout develop
   git pull origin develop
   git checkout -b dev/tu-nombre
   git push -u origin dev/tu-nombre
   ```

2. **Trabajar en una característica o corrección**:
   - Crear una rama de características desde la rama personal.
   ```bash
   git checkout dev/tu-nombre
   git pull origin dev/tu-nombre
   # Para frontend:
   git checkout -b feature/frontend/nuevo-carrito
   # Para backend:
   git checkout -b feature/backend/nueva-api
   # Realizar cambios y commits
   git commit -m "feat: [frontend] agregar funcionalidad de carrito de compras"
   git commit -m "feat: [backend] agregar nueva API"
   git push -u origin feature/frontend/nuevo-carrito
   git push -u origin feature/backend/nueva-api
   ```

3. **Realizar un pull request (PR) a `develop`**:
   - Desde la interfaz de GitHub, crear un PR desde `feature/frontend/nuevo-carrito` hacia `develop` y otro desde `feature/backend/nueva-api` hacia `develop`.
   - Revisar y fusionar los cambios en `develop`.

4. **Preparar una nueva versión**:
   ```bash
   git checkout develop
   git pull origin develop
   git checkout -b release/1.0
   git push -u origin release/1.0
   ```

5. **Fusionar la versión en `main`**:
   - Crear un PR desde `release/1.0` hacia `main`.
   - Revisar y fusionar los cambios en `main`.
   - Etiquetar la versión en `main`.
   ```bash
   git tag -a v1.0 -m "Versión 1.0"
   git push origin v1.0
   ```

6. **Hotfixes**:
   - Crear una rama de hotfix desde `main` para corregir errores críticos.
   ```bash
   git checkout main
   git pull origin main
   git checkout -b hotfix/correccion-critica
   # Realizar cambios y commits
   git commit -m "hotfix: corregir error crítico de autenticación"
   git push -u origin hotfix/correccion-critica
   ```

   - Crear un PR desde la rama de hotfix hacia `main` y `develop`.
   - Revisar y fusionar los cambios en ambas ramas.

## Nomenclatura de Commits

Para mantener un historial de commits claro y consistente, utilizamos la siguiente convención de mensajes de commits:

- **Características**: `feat: descripción de la característica`
  - Ejemplo: `feat: agregar funcionalidad de carrito de compras`
- **Corrección de errores**: `fix: descripción del error corregido`
  - Ejemplo: `fix: corregir bug en la página de checkout`
- **Hotfixes**: `hotfix: descripción del error crítico corregido`
  - Ejemplo: `hotfix: corregir error crítico de autenticación`
- **Mejoras de rendimiento**: `perf: descripción de la mejora`
  - Ejemplo: `perf: optimizar carga de imágenes`
- **Cambios de estilo**: `style: descripción del cambio de estilo`
  - Ejemplo: `style: mejorar el diseño del header`
- **Refactorización**: `refactor: descripción del refactor`
  - Ejemplo: `refactor: reorganizar el componente de productos`
- **Documentación**: `docs: descripción del cambio en la documentación`
  - Ejemplo: `docs: actualizar el README con instrucciones de instalación`

## Desarrollo Independiente

Para trabajar de manera independiente en el frontend o backend, utiliza los siguientes comandos:

### Levantar solo el frontend:
```bash
cd frontend
npm install
npm start
```

### Levantar solo el backend:
```bash
cd backend
npm install
npm run dev
```

Para más detalles, consulta los respectivos `README.md` en las carpetas `frontend` y `backend`.

## Equipo de Trabajo
- **Diseño UX/UI**
  - A
- **Frontend**:
  - A
- **Backend**:
  - Lorenzo Esteban Baeza Núñez
- **Aplicaciones Móviles**
  - A

## Contribuciones

¡Gracias por tu interés en contribuir a Dogtorhouse! Para comenzar, por favor lee nuestras [Guías de Contribución](CONTRIBUTING.md) y el [Código de Conducta](CODE_OF_CONDUCT.md).

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.
