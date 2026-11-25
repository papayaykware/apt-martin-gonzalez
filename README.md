# Modelo de Análisis de Puestos de Trabajo (A.P.T.)

**Adaptación digital y modernización (v2.0, 2026) del modelo de Mª Teresa Martín González**
Instituto de Pedagogía del Consejo Superior de Investigaciones Científicas (CSIC), Madrid

[![Licencia: CC BY-NC 4.0](https://img.shields.io/badge/Licencia-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/deed.es)

## Descripción

Este repositorio contiene la digitalización y modernización del modelo de Análisis de Puestos de Trabajo (A.P.T.) desarrollado por Mª Teresa Martín González en el Instituto de Pedagogía del CSIC. El modelo original, publicado en 1975, fue pionero en España en la aplicación sistemática del análisis de puestos a la Formación y Orientación Profesionales.

El trabajo de campo original se aplicó a la Familia Profesional Sanitaria (auxiliares de clínica, puericultoras y cuidadores), pero la estructura del modelo es genérica y extrapolable a cualquier ocupación o sector.

**Objetivo.** Convertir un documento histórico en papel en un recurso vivo, editable y aplicable en la orientación profesional, la formación ocupacional y la gestión de recursos humanos.

**Autoría.** Autoría conceptual de la adaptación: Claude (Anthropic). Dirección y adaptación del corpus: Javi Ciborro. Modelo original: Mª Teresa Martín González (CSIC, 1975).

## Estructura del modelo (v2.0)

El A.P.T. se organiza en 4 fases. La Fase III reúne 12 áreas y **131 factores**, agrupados en tres ámbitos clásicos y un bloque añadido en 2026.

```
MODELO A.P.T. v2.0
FASE I    Identificación del puesto de trabajo
FASE II   Descripción del puesto de trabajo
FASE III  Especificación del puesto de trabajo
  ├─ Ámbito: Requerimientos para la ejecución del trabajo
  │    Área 1: Competencia (9)
  │    Área 2: Solución de problemas (6)
  │    Área 3: Responsabilidad (9)
  ├─ Ámbito: Requerimientos de personalidad
  │    Área 4: Conductas-tipo (17)
  │    Área 5: Tensiones de personalidad (6)
  │    Área 6: Actitudes (11)
  │    Área 7: Aptitudes (16)
  │    Área 8: Intereses (10)
  │    Área 9: Motivaciones (9)
  ├─ Ámbito: Requerimientos físicos
  │    Área 10: Capacidades físicas (21)
  │    Área 11: Condiciones de trabajo (9)
  └─ Bloque añadido en 2026
       Área 12: Competencias digitales y teletrabajo (8)
FASE IV   Información profesional
```

## Contenido del repositorio

| Archivo | Formato | Descripción |
|---|---|---|
| `src/doc/Modelo_APT_Martin_Gonzalez_v2.0.xlsx` | Excel | 20 hojas: portada, ficha de puesto, dashboard, fases I-IV, 12 áreas, instrumentos y notas de actualización. **Fuente de verdad.** |
| `src/doc/Modelo_APT_Martin_Gonzalez_v2.0.md` | Markdown | Versión en texto plano generada desde el Excel, para lectura web y control de versiones |
| `src/doc/apt_schema.json` | JSON | Esquema de datos legible por máquina: 131 factores con escala, tipo de escala y dirección de celda en el Excel |
| `src/doc/Estructura.md` | Markdown | Estructura de la versión anterior (123 factores, 11 áreas). Se conserva como referencia histórica |
| `LICENSE.md` | Texto | Licencia Creative Commons Atribución-NoComercial 4.0 Internacional |

### Hojas del Excel

1. Portada
2. Ficha de Puesto
3. Dashboard (medias por área y gráfico)
4. Fase I - Identificación
5. Fase II - Descripción
6. a 17. Fase III, una hoja por área (12 en total, la última nueva en 2026)
18. Fase IV - Información Profesional
19. Instrumentos y Procedimientos
20. Notas de Actualización

## Esquema de datos (`apt_schema.json`)

El esquema se generó desde el Excel y se comprobó contra él: ids consecutivos del 1 al 131 y rangos coincidentes con las fórmulas del Dashboard. Cada factor incluye:

- nombre, descripción, dimensión y opciones de escala;
- tipo de escala: `ordinal`, `nominal` o `descriptivo`;
- hoja, fila y celdas de puntuación y observaciones en el Excel;
- `incluir_en_media` y `revisar_en_piloto` (ver más abajo).

### Advertencia metodológica

La puntuación (1 a 5, o N/A) es un índice descriptivo, sin validación psicométrica. Doce factores tienen categorías sin orden de intensidad (8, 16, 17, 108 a 114, 117 y 130): el esquema los marca como nominales y los excluye de las medias, de modo que `incluir_en_media` suma 119 factores. El Dashboard actual del Excel promedia los 131, así que ambos cálculos difieren. Cinco factores ordinales (10, 12, 14, 19 y 20) están marcados para revisar su ordenación en el piloto.

## Cómo usar este recurso

**Orientación profesional.** Construir perfiles detallados de ocupación con las hojas de la Fase III, aplicar las escalas para valorar la adecuación persona-puesto y adaptar los factores a las ocupaciones del territorio.

**Formación.** Diseñar currículos basados en las competencias detectadas, identificar brechas entre la formación recibida y las exigencias del puesto y desarrollar casos prácticos a partir de las tareas descritas.

**Recursos humanos.** Estandarizar descripciones de puesto, definir requerimientos objetivos para la selección y planificar itinerarios de promoción.

**Investigación.** Replicar el modelo en otros sectores, validar psicométricamente las escalas y contrastarlo con marcos como O*NET, ESCO o el MECU.

## Estado de las actualizaciones

Las Notas de Actualización (hoja 20 del Excel) recogen 15 recomendaciones de modernización. Estado en v2.0 de las de prioridad alta:

| Aspecto | Estado en v2.0 |
|---|---|
| Moneda en pesetas | No aplica: el modelo original no contenía referencias monetarias explícitas |
| Competencias digitales | Implementado: Área 12 (factores 124 a 129) |
| Teletrabajo | Implementado: factores 130 y 131 y campo «Modalidad de trabajo» en la ficha |
| Escalas de medición implícitas | Implementado: puntuación 1-5 con validación de datos en las 12 áreas |
| Cuestionario en papel | Parcial: puntuación y observaciones en Excel; falta versión web de recogida de datos |
| Marco normativo (MECU, SNCFP) | Pendiente: requiere mapeo formal factor a factor |

Siguen pendientes la validación psicométrica (alfa de Cronbach sobre datos reales), la versión web o móvil, las versiones multilingües, la perspectiva de género y el análisis con NLP.

## Referencias originales

- Martín González, Mª Teresa. *Un modelo de Análisis de Puestos de Trabajo aplicable en Formación y Orientación Profesionales.* Instituto de Pedagogía del CSIC, Madrid, 1975.
- García Hoz, Víctor (dir.). *Proyecto de investigación sobre Técnica del Análisis de Puestos de Trabajo en Formación y Orientación Profesionales.*
- Fuentes teóricas del modelo: Piotrowski y Rock (*The Perceptanalytic Executive Scale*); U.S. Department of Labor (*Estimates of Worker Trait Requirements for 4,000 Jobs*); García Yagüe (*Batería Factorial de la Inteligencia*).

## Contribuciones

Es un proyecto abierto. Se aceptan contribuciones como:

- **Issues:** errores, mejoras o nuevas funcionalidades.
- **Pull requests:** adaptaciones a nuevos sectores, traducciones o mejoras de formato.
- **Discussions:** experiencias de aplicación del modelo en contextos reales.

Para contribuir: haz un fork, crea una rama (`git checkout -b feature/nueva-adaptacion`), confirma tus cambios, súbela y abre un pull request. Las contribuciones se entienden publicadas bajo la misma licencia del repositorio.

## Licencia

Esta adaptación se distribuye bajo **Creative Commons Atribución-NoComercial 4.0 Internacional (CC BY-NC 4.0)**. Texto completo en [`LICENSE.md`](LICENSE.md).

Eres libre de:

- **Compartir:** copiar y redistribuir el material en cualquier medio o formato.
- **Adaptar:** remezclar, transformar y construir a partir del material.

Bajo las siguientes condiciones:

- **Atribución:** debes dar crédito adecuado, enlazar la licencia e indicar si se han hecho cambios.
- **No comercial:** no puedes usar el material con fines comerciales.

**Sobre la obra original.** Esta licencia se aplica a las aportaciones de esta adaptación (estructura digital, ampliaciones de 2026, esquema de datos y documentación). No modifica los derechos que pudieran corresponder a los titulares del modelo de 1975, cuya situación se está verificando. Si tienes dudas sobre un uso concreto, consulta con el CSIC.

## Contacto

Consultas sobre el modelo original: Instituto de Pedagogía del CSIC, Madrid. Consultas sobre esta adaptación: abre un issue en este repositorio.

> «La profesión es para el hombre el ámbito que más va a permitir u obstaculizar su realización personal y, a la vez, una de las formas más responsables de su aportación a la comunidad.»
> — Mª Teresa Martín González
