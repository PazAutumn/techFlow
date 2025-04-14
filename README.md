# 🚀 Prueba - Implementación de un Pipeline de Integración Continua

Este proyecto corresponde a la evaluación del módulo de Integración Continua (CI), donde se implementa un pipeline funcional usando **Jenkins**, junto con una API de gestión de usuarios utilizando `json-server`. El objetivo es asegurar calidad, retroalimentación inmediata y despliegue automatizado.

---

## 🏢 Contexto

**TechFlow**, una empresa de soluciones digitales, enfrenta dificultades en la automatización del desarrollo de su sistema ERP. Este proyecto simula el entorno real donde se necesita automatizar pruebas y validaciones antes del despliegue a producción.

---

## 📁 Estructura del Proyecto

```
├── app.js                  # API básica de gestión de usuarios
├── db.json                 # Base de datos simulada
├── package.json            # Configuración del proyecto y dependencias
├── tests/
│   └── app.test.js         # Pruebas unitarias preescritas
├── Jenkinsfile             # Definición del pipeline CI
├── README.md               # Documentación del proyecto
└── REPORT.md               # Informe de ejecución y hallazgos
```

---

## ✅ Requerimientos Cumplidos

### 1. Configuración del Repositorio (2 pts)
- Se inicializó un repositorio local con Git.
- Primer commit incluye `db.json` y el código base.
- Repositorio remoto conectado correctamente a GitHub.

### 2. API Funcional (2 pts)
- La API fue verificada y funciona con `json-server`.
- Se ejecuta localmente con:  
  ```bash
  npx json-server --watch db.json --port 3000
  ```

### 3. Pipeline Jenkins (3 pts)
- `Jenkinsfile` configurado para:
  - Clonar el repositorio desde GitHub.
  - Ejecutar `npm install`.
  - Levantar servidor local en puerto `3000`.

### 4. Pruebas Automatizadas (2 pts)
- El pipeline ejecuta `npm test`.
- Falla si alguna prueba no pasa (exit code distinto de 0).

### 5. Reportes y Retroalimentación (1 pt)
- Se genera reporte con los resultados de pruebas.
- Archivo `REPORT.md` incluido con pasos realizados y posibles errores encontrados.

---

## ⚙️ Instalación y Ejecución Local

```bash
git clone https://github.com/PazAutumn/techFlow.git
cd techFlow
npm install
npx json-server --watch db.json --port 3000
```

Para correr las pruebas:

```bash
npm test
```

---

## 🛠 Herramientas Utilizadas

- [Node.js](https://nodejs.org/)
- [json-server](https://www.npmjs.com/package/json-server)
- [Jest](https://jestjs.io/)
- [Jenkins](https://www.jenkins.io/)

---

## 📋 Consideraciones

- Se incluyó validación del servidor dentro del pipeline con un chequeo al puerto 3000.
- Los errores detectados durante la ejecución están detallados en `REPORT.md`.

---

## 👩‍💻 Autor

**Paz Contreras**  
Desarrolladora Backend en formación  
[LinkedIn](https://www.linkedin.com/in/paz-contreras) • [GitHub](https://github.com/PazAutumn)
