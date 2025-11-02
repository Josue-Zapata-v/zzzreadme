# 🚀 Rick & Morty Character Explorer

Una aplicación web moderna y responsiva construida con **React + Vite** para explorar los personajes del universo de **Rick & Morty**. La aplicación consume la **API de Rick and Morty** y demuestra conceptos avanzados de React, enrutamiento, filtrado, paginación, validación de formularios y diseño responsivo.

---

## 📋 Tabla de Contenidos

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Características Principales](#-características-principales)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Instalación y Configuración](#-instalación-y-configuración)
- [Páginas de la Aplicación](#-páginas-de-la-aplicación)
- [Hooks y Servicios](#-hooks-y-servicios)
- [Buenas Prácticas Implementadas](#-buenas-prácticas-implementadas)
- [Equipo del Proyecto](#-equipo-del-proyecto)
- [Despliegue](#-despliegue)
- [Licencia](#-licencia)

---

## 🎯 Descripción del Proyecto

**Objetivo:** Construir una aplicación React de 3 páginas que permita a los usuarios:

1. Descubrir personajes destacados en la página de inicio
2. Explorar el catálogo completo de personajes con filtrado, búsqueda y paginación
3. Contactar al equipo de desarrollo mediante un formulario validado

Este proyecto fue desarrollado como parte de un ejercicio académico para demostrar el dominio de React, manejo de estado, consumo de APIs y diseño de interfaces modernas.

---

## ✨ Características Principales

- 🔍 **Búsqueda en tiempo real** con debounce para optimizar llamadas a la API
- 🎛️ **Filtros múltiples** por estado (vivo/muerto/desconocido) y especies
- 📄 **Paginación avanzada** con selector de elementos por página (10, 20, 50)
- 📱 **Diseño 100% responsivo** adaptado a dispositivos móviles, tablets y escritorio
- ✅ **Validación de formularios** en tiempo real con retroalimentación visual
- ⚡ **Rendimiento optimizado** con lazy loading de imágenes y caché de datos
- ♿ **Accesibilidad** implementada con etiquetas ARIA y navegación por teclado
- 🎨 **UI moderna** con Bootstrap 5.3.8 y animaciones suaves

---

## 🛠 Tecnologías Utilizadas

| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| React | ^18 | Biblioteca principal para la UI |
| Vite | Latest | Herramienta de desarrollo rápida |
| React Router DOM | ^6 | Enrutamiento y navegación |
| Axios | ^1.6 | Cliente HTTP para peticiones API |
| Bootstrap | 5.3.8 | Framework CSS para diseño responsivo |
| Rick and Morty API | v1 | Fuente de datos de personajes |

---

## 🗂 Estructura del Proyecto

```
rick-morty-character-explorer/
│
├── src/
│   ├── components/
│   │   ├── common/
│   │   │   ├── Navbar.jsx           # Barra de navegación
│   │   │   ├── Footer.jsx           # Pie de página
│   │   │   ├── LoadingSpinner.jsx   # Indicador de carga
│   │   │   └── ErrorAlert.jsx       # Componente de errores
│   │   │
│   │   ├── home/
│   │   │   ├── HeroSection.jsx      # Sección hero principal
│   │   │   └── FeaturedCharacters.jsx # Personajes destacados
│   │   │
│   │   ├── list/
│   │   │   ├── FilterBar.jsx        # Barra de filtros
│   │   │   ├── CharacterCard.jsx    # Tarjeta de personaje
│   │   │   └── Pagination.jsx       # Controles de paginación
│   │   │
│   │   └── contact/
│   │       └── ContactForm.jsx      # Formulario de contacto
│   │
│   ├── pages/
│   │   ├── HomePage.jsx             # Página de inicio
│   │   ├── ListPage.jsx             # Página de listado
│   │   ├── ContactPage.jsx          # Página de contacto
│   │   └── NotFoundPage.jsx         # Página 404
│   │
│   ├── services/
│   │   ├── api.js                   # Instancia de Axios
│   │   └── characterService.js      # Servicio de personajes
│   │
│   ├── hooks/
│   │   ├── useCharacters.js         # Hook para listado
│   │   └── useCharacter.js          # Hook para detalle (opcional)
│   │
│   ├── App.jsx                      # Componente principal
│   ├── main.jsx                     # Punto de entrada
│   └── index.css                    # Estilos globales
│
├── public/
├── package.json
├── vite.config.js
└── README.md
```

---

## 🚀 Instalación y Configuración

### Prerrequisitos

- Node.js (versión 16 o superior)
- npm o yarn

### Pasos de Instalación

```bash
# 1. Clonar el repositorio
git clone https://github.com/Cris-div/Proyecto-o3-React.git
cd Proyecto-o3-React

# 2. Instalar dependencias
npm install

# 3. Ejecutar servidor de desarrollo
npm run dev

# 4. Abrir en el navegador
# La aplicación estará disponible en http://localhost:5173
```

### Scripts Disponibles

```bash
npm run dev      # Inicia el servidor de desarrollo
npm run build    # Construye la aplicación para producción
npm run preview  # Previsualiza la versión de producción
npm run lint     # Ejecuta el linter
```

---

## 📱 Páginas de la Aplicación

### 1️⃣ Página de Inicio (`/`)

**Propósito:** Presentar la aplicación y mostrar personajes destacados.

**Componentes:**

- **Sección Hero**
  - Imagen de fondo a pantalla completa
  - Título: "Explora el Multiverso de Rick & Morty"
  - Subtítulo: "Descubre todos los personajes y locaciones de la serie"
  - Botón CTA: "Ver Personajes" → navega a `/list`

- **Sección de Personajes Destacados**
  - Grid de 6-8 tarjetas de personajes
  - Cada tarjeta muestra: imagen, nombre, especie y estado
  - Botón: "Ver Todos los Personajes" → navega a `/list`

**Responsividad:**
- Desktop: 3 tarjetas por fila
- Tablet: 2 tarjetas por fila
- Mobile: 1 tarjeta por fila

---

### 2️⃣ Lista de Personajes (`/list`)

**Propósito:** Mostrar el catálogo completo con filtros y paginación.

**Funcionalidades:**

- **Barra de Filtros**
  - Búsqueda por nombre (con debounce)
  - Filtro por estado: vivo, muerto, desconocido
  - Filtro por especie
  - Botón para limpiar todos los filtros

- **Grid de Personajes**
  - Tarjetas responsivas con imagen, nombre, especie y badge de estado
  - Grid adaptativo: 4 columnas (desktop), 2 (tablet), 1 (mobile)

- **Paginación**
  - Botones Anterior/Siguiente
  - Botones numéricos con elipsis para muchas páginas
  - Selector de elementos por página (10, 20, 50)
  - Indicador: "Página X de Y"

**Notas Técnicas:**
- La API retorna 20 elementos por página por defecto
- El selector de elementos por página maneja esto mediante:
  - 10 elementos: corta los resultados localmente
  - 20 elementos: 1 página de la API
  - 50 elementos: concatena múltiples páginas con caché

---

### 3️⃣ Página de Contacto (`/contact`)

**Propósito:** Formulario de contacto con validación en tiempo real.

**Campos del Formulario:**
- **Nombre**: obligatorio, mínimo 3 caracteres
- **Email**: obligatorio, formato válido
- **Asunto**: obligatorio
- **Mensaje**: obligatorio, mínimo 10 caracteres

**Comportamiento:**
- Validación en tiempo real con mensajes de error debajo de cada campo
- Retroalimentación visual: bordes rojos para errores, verdes para válidos
- Mensaje de éxito al enviar: "✅ Tu mensaje fue enviado exitosamente"
- Limpieza del formulario tras envío exitoso

**Diseño:**
- Formulario centrado con ancho máximo de 600px
- Totalmente responsivo en dispositivos móviles

---

## 🔧 Hooks y Servicios

### Hooks Personalizados

**`useCharacters.js`**
- Maneja el estado de la lista de personajes
- Gestiona filtros, paginación y elementos por página
- Controla estados de carga y error
- Implementa caché para optimizar peticiones

**`useCharacter.js`** (opcional)
- Obtiene detalles de un personaje individual por ID

### Servicios

**`api.js`**
- Instancia configurada de Axios
- baseURL: `https://rickandmortyapi.com/api`
- Interceptores opcionales para manejo de errores

**`characterService.js`**
- `getCharacters({ page, name, status, species, gender })` - Obtiene lista de personajes
- `getCharacterById(id)` - Obtiene un personaje por ID
- `getMultipleCharacters(ids)` - Obtiene múltiples personajes por IDs

---

## 🎨 Diseño y Estilo

### Principios de Diseño

- **Minimalista y moderno**: Diseño limpio con énfasis en el contenido
- **Colores vibrantes**: Paleta inspirada en la serie (verde neón, azul brillante)
- **Animaciones suaves**: Transiciones en hover y efectos de entrada
- **Tipografía clara**: Jerarquía visual bien definida

### Responsividad

- **Mobile First**: Diseñado primero para dispositivos móviles
- **Breakpoints**:
  - Mobile: < 576px
  - Tablet: 576px - 992px
  - Desktop: > 992px

### Accesibilidad

- ✅ Etiquetas ARIA en elementos interactivos
- ✅ Contraste de colores adecuado (WCAG AA)
- ✅ Navegación por teclado completa
- ✅ Atributos `alt` en todas las imágenes
- ✅ Estados de foco visibles

---

## ✅ Buenas Prácticas Implementadas

1. **Arquitectura basada en componentes** con separación de responsabilidades
2. **Hooks y servicios reutilizables** para lógica compartida
3. **Búsqueda con debounce** y caché para reducir llamadas a la API
4. **Diseño responsivo** optimizado para todos los dispositivos
5. **Manejo de errores robusto** con componentes de error y reintentos
6. **Código limpio** con nombres descriptivos y comentarios JSDoc
7. **Lazy loading** de imágenes para mejor rendimiento
8. **Validación de formularios** exhaustiva con feedback visual

---

## 👥 Equipo del Proyecto

| Nombre | Rol | Responsabilidades |
|--------|-----|-------------------|
| **Yair Araujo Gabriel** | Líder Técnico | Estructura base, configuración de rutas y arquitectura |
| **Yamile Ochoa Marin** | Desarrolladora Frontend | Página de inicio, Hero Section y personajes destacados |
| **Christian David Unocc Ramirez** | Desarrollador Frontend | Página de listado, filtros y sistema de paginación |
| **Josue Zapata Villegas** | Desarrollador Fullstack | Página de contacto, servicios, documentación y despliegue |

---

## 🌐 Despliegue

### Configuración para Producción

**Variables de Entorno:**

```env
VITE_API_BASE_URL=https://rickandmortyapi.com/api
```

### Plataformas Recomendadas

- **Vercel** (recomendado para proyectos Vite/React)
- **Netlify**
- **Railway**
- **GitHub Pages**

### Pasos para Desplegar en Vercel

```bash
# 1. Instalar Vercel CLI
npm install -g vercel

# 2. Construir el proyecto
npm run build

# 3. Desplegar
vercel

# 4. Desplegar a producción
vercel --prod
```

### Configuración de Netlify

Crear archivo `netlify.toml` en la raíz:

```toml
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

---

## 📄 Licencia

Este proyecto fue creado con fines educativos. Los datos de personajes son propiedad de la serie Rick & Morty y se obtienen mediante la [Rick and Morty API](https://rickandmortyapi.com).

---

## 🔗 Enlaces Importantes

- **Repositorio:** [https://github.com/Cris-div/Proyecto-o3-React.git](https://github.com/Cris-div/Proyecto-o3-React.git)
- **API Documentación:** [https://rickandmortyapi.com/documentation](https://rickandmortyapi.com/documentation)
- **Demo en Vivo:** [Añadir enlace tras despliegue]

---

## 📞 Contacto

zjosue775@gmail.com

---

<div align="center">
  <p>Hecho con ❤️ por el equipo de desarrollo</p>
  <p>⭐ Si te gustó este proyecto, no olvides darle una estrella en GitHub ⭐</p>
</div>
