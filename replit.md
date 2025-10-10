# Wkype - Lector de Noticias tipo TikTok

## Descripción General
Wkype es una aplicación web tipo TikTok para leer artículos de Wikipedia. Permite explorar contenido de forma inmersiva con un diseño vertical y deslizable.

## Estructura del Proyecto
- `index.html` - Aplicación de página única (SPA) con toda la lógica JavaScript integrada
- `server.py` - Servidor HTTP simple de Python para servir archivos estáticos
- `.gitignore` - Configuración de archivos a ignorar en git

## Características Principales
1. **Feed Principal**: Artículos aleatorios de Wikipedia en español
2. **Para Ti**: Contenido personalizado basado en actividad del usuario
3. **Búsqueda**: Búsqueda de artículos en Wikipedia
4. **Guardados**: Sistema para guardar artículos favoritos
5. **Personas**: Perfiles de personas verificadas en la plataforma
6. **Ajustes**: Configuración y preferencias del usuario

## Tecnologías Utilizadas
- HTML5, CSS3 (Tailwind CSS via CDN)
- JavaScript vanilla (sin frameworks)
- Python 3.11 para el servidor HTTP
- API pública de Wikipedia en español

## Configuración del Servidor
- Puerto: 5000
- Host: 0.0.0.0
- Caché: Deshabilitado para desarrollo
- Workflow automático configurado

## Correcciones Realizadas (Oct 2025)

### Problema 1: Script Module Bloqueando Funciones Globales
**Error**: El script principal usaba `type="module"` lo que hacía que las funciones no fueran accesibles desde atributos `onclick` del HTML.
**Solución**: Removí `type="module"` del script principal para que todas las funciones sean globales.

### Problema 2: Variable DOM Faltante
**Error**: `selectionActionsBar` no estaba definida como referencia DOM, causando un ReferenceError.
**Solución**: Agregué `const selectionActionsBar = document.getElementById('selection-actions-bar');` a las referencias DOM.

### Problema 3: Inicialización del Feed
**Error**: `currentScreen` se inicializaba como 'feed', causando que el feed no se cargara al inicio.
**Solución**: Cambié la inicialización de `currentScreen` de 'feed' a '' (vacío).

## Estado Actual
✅ Feed principal funcionando
✅ Navegación entre secciones operativa
✅ Sistema de guardados funcionando
✅ Sección de personas/perfiles funcionando
✅ Búsqueda operativa
✅ Sin errores de JavaScript en consola

## Notas de Desarrollo
- La aplicación usa localStorage para persistencia de datos
- No requiere base de datos externa
- Todas las imágenes y contenido vienen de Wikipedia
- El warning de Tailwind CDN es normal para desarrollo
