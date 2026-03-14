description: Herramienta de automatización de diseño impulsada por IA para generar y refinar activos visuales utilizando modelos avanzados de IA
version: 1.0.0
author: OpenClaw Team
tags: design, ai, automation, generative
dependencies: openai-api, stable-diffusion-api, design-tools-sdk
env_vars: OPENAI_API_KEY, STABILITY_API_KEY, DESIGN_WORKSPACE_PATH
---

# Super Crafter

## Propósito

Super Crafter es una herramienta de automatización de diseño impulsada por IA que aprovecha modelos avanzados de IA generativa para crear, refinar e iterar sobre activos de diseño visual. Está diseñada para diseñadores, desarrolladores y creadores de contenido que necesitan prototipar y generar rápidamente visuales de alta calidad sin partir desde cero.

### Casos de Uso Reales
- **Prototipado UI/UX**: Generar wireframes, mockups y diseños de componentes interactivos para aplicaciones web/móviles
- **Creación de Identidad de Marca**: Diseñar logos, paletas de colores, esquemas tipográficos y directrices de marca
- **Activos de Marketing**: Crear gráficos para redes sociales, banners y materiales promocionales con branding consistente
- **Generación de Iconos e Ilustraciones**: Producir iconos personalizados, ilustraciones y elementos visuales para productos digitales
- **Automatización de Guías de Estilo**: Generar sistemas de diseño completos con componentes, patrones y documentación

## Alcance

Super Crafter maneja el ciclo de vida completo del diseño desde el concepto hasta activos listos para producción, enfocándose en la creación asistida por IA en lugar del trabajo de diseño manual.

### Comandos Soportados
- `/craft-ui <description>` - Generar mockups de UI y diseños de componentes
- `/craft-logo <brand> <style>` - Crear variaciones de logos para marcas
- `/craft-palette <mood> <colors>` - Generar esquemas de colores y paletas
- `/craft-icon <purpose> <style>` - Producir iconos para casos de uso específicos
- `/craft-illustration <theme> <elements>` - Crear ilustraciones y gráficos
- `/refine-design <asset_id> <feedback>` - Iterar sobre diseños existentes
- `/export-design <asset_id> <format>` - Exportar diseños en varios formatos (SVG, PNG, PDF)

### Limitaciones
- No maneja modelado 3D o animaciones complejas
- Requiere acceso a API de servicios de IA (OpenAI, Stability AI)
- La calidad de salida depende de la especificidad del prompt y las capacidades del modelo de IA
- No es adecuado para diagramas técnicos altamente especializados

## Proceso de Trabajo

### Flujo de Trabajo Paso a Paso

1. **Inicialización**: Configurar el espacio de trabajo y verificar conexiones a API
   ```bash
   openclaw super-crafter init --workspace /path/to/designs
   ```

2. **Planificación de Activos**: Analizar requisitos y preparar prompts detallados
   - Reunir materiales de referencia y directrices de estilo
   - Definir dimensiones objetivo, restricciones de color y contexto de uso
   - Investigar diseños similares para inspiración

3. **Generación con IA**: Ejecutar comandos de creación con parámetros específicos
   ```bash
   /craft-ui \"Modern e-commerce product card with hover effects, 400x300px, clean minimal style\"
   ```

4. **Bucle de Refinamiento**: Revisar e iterar sobre activos generados
   ```bash
   /refine-design asset_123 \"Make the button more prominent and add subtle shadow\"
   ```

5. **Aseguramiento de Calidad**: Verificar consistencia de diseño y especificaciones técnicas
   - Verificar ratios de contraste de color para accesibilidad
   - Asegurar escalabilidad para diferentes tamaños de pantalla
   - Validar cumplimiento de directrices de marca

6. **Exportación e Integración**: Preparar activos finales para uso
   ```bash
   /export-design asset_456 --format svg --optimize
   ```

### Configuración del Entorno
```bash
export OPENAI_API_KEY=\"your-openai-key\"
export STABILITY_API_KEY=\"your-stability-key\"
export DESIGN_WORKSPACE_PATH=\"/home/user/designs\"
```

## Reglas de Oro

1. **Especificidad del Prompt**: Siempre proporcionar prompts detallados y específicos, incluyendo dimensiones, referencias de estilo y contexto para lograr mejores salidas de IA
2. **Diseño Ético**: Evitar generar contenido que pueda ser dañino, discriminatorio o infrinja marcas registradas existentes
3. **Refinamiento Iterativo**: Usar múltiples ciclos de refinamiento en lugar de intentar perfeccionar prompts en el primer intento
4. **Consistencia de Marca**: Mantener un lenguaje visual consistente en activos relacionados dentro de un proyecto
5. **Restricciones Técnicas**: Considerar limitaciones prácticas como tamaños de archivo, compatibilidad de navegador e impacto en rendimiento
6. **Verificación de Originalidad**: Revisar salidas para similitudes involuntarias con diseños existentes y modificar en consecuencia
7. **Accesibilidad Primero**: Asegurar que los diseños generados cumplan con las directrices WCAG para contraste de color y legibilidad

## Ejemplos

### Generación de Componente UI
**Entrada:**
```
/craft-ui \"Dashboard card for user analytics showing metrics, charts, and actions. Use blue color scheme, modern flat design, responsive layout.\"
```

**Salida:**
- Generadas 3 variaciones de tarjetas de dashboard de analytics
- Activos guardados como: `analytics_card_v1.svg`, `analytics_card_v2.svg`, `analytics_card_v3.svg`
- Incluye clases CSS responsivas y estados hover
- Paleta de colores: Primary #007BFF, Secondary #6C757D, Background #FFFFFF

### Refinamiento de Diseño de Logo
**Entrada:**
```
/refine-design logo_089 \"Simplify the icon, make text more legible, use warmer colors\"
```

**Salida:**
- Logo actualizado logo_089_v2.svg con formas geométricas simplificadas
- Cambiada fuente de Sans Serif a una alternativa más legible
- Ajustado esquema de colores de azules fríos a naranjas cálidos (#FF6B35, #F7931E, #FFD23F)
- Mantenida escalabilidad de marca de 32px a 512px

### Creación de Paleta de Colores
**Entrada:**
```
/craft-palette \"Professional tech startup, trustworthy and innovative\" 5
```

**Salida:**
Paleta generada con 5 colores:
- Primary: #2D3748 (Deep Navy)
- Secondary: #4299E1 (Bright Blue)
- Accent: #48BB78 (Green Success)
- Neutral: #F7FAFC (Light Gray)
- Warning: #ED8936 (Orange Alert)

Archivo de paleta: `tech_startup_palette.json` con códigos hex, valores RGB y ratios de contraste.

## Comandos de Reversión

### Reversión de Versión de Activo
```
/rollback-design <asset_id> --to-version <version_number>
```
Ejemplo: `/rollback-design ui_mockup_001 --to-version 2`

### Eliminación por Lotes de Activos
```
/cleanup-designs --project <project_name> --before-date 2024-01-01
```
Ejemplo: `/cleanup-designs --project ecommerce_redesign --before-date 2024-01-01`

### Reinicio de Espacio de Trabajo
```
/reset-workspace --confirm-destructive
```
Advertencia: Esto elimina todos los activos generados y no se puede deshacer.

## Pasos de Verificación

1. **Conectividad de API**: Ejecutar `/status` para verificar conexiones de servicios de IA
2. **Integridad de Activos**: Usar `/validate-design <asset_id>` para verificar corrupción de archivos
3. **Cumplimiento de Marca**: Ejecutar `/check-brand <asset_id> <guidelines_file>` para consistencia
4. **Rendimiento**: Probar tiempos de exportación y tamaños de archivo contra requisitos

## Solución de Problemas

### Problemas Comunes
- **Salidas de Baja Calidad**: Aumentar detalle del prompt y usar imágenes de referencia
- **Límites de Tasa de API**: Implementar delays entre solicitudes o actualizar planes de API
- **Estilos Inconsistentes**: Crear y referenciar guías de estilo en prompts
- **Tamaños de Archivo Grandes**: Usar flag `/optimize-export` para activos de producción
- **Inexactitudes de Color**: Especificar códigos hex exactos en prompts para colores de marca

### Comandos de Depuración
- `/debug-prompt <asset_id>` - Muestra el prompt exacto enviado a IA
- `/performance-log` - Muestra tiempos de generación y uso de API
- `/error-details <error_code>` - Proporciona información detallada de errores