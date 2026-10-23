# Habla canaria 🌋

Una skill para redactar, adaptar y revisar textos en **español de Canarias**, con expresiones, peculiaridades gramaticales y guasa cuando encaje.

La idea es que el resultado suene natural: conservar lo que quieres decir, ajustar el registro y usar los canarismos con sentido, sin llenar cada frase de tópicos.

## Índice

- [Descripción y objetivos](#descripción-y-objetivos)
- [Características](#características)
- [Ejemplos](#ejemplos)
- [Requisitos y compatibilidad](#requisitos-y-compatibilidad)
- [Instalación](#instalación)
- [Inicio rápido](#inicio-rápido)
- [Uso y configuración](#uso-y-configuración)
- [Actualización y desinstalación](#actualización-y-desinstalación)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Fuentes y metodología](#fuentes-y-metodología)
- [Limitaciones](#limitaciones)
- [Validación](#validación)
- [Solución de problemas](#solución-de-problemas)
- [Contribuciones](#contribuciones)
- [Hoja de ruta](#hoja-de-ruta)
- [Soporte](#soporte)
- [Autoría y agradecimientos](#autoría-y-agradecimientos)
- [Licencia](#licencia)

## Descripción y objetivos

Habla canaria proporciona instrucciones y referencias para que un asistente adapte textos al español de Canarias respetando el sentido, la situación comunicativa y la diversidad del Archipiélago.

Está pensada para mensajes cotidianos, correos profesionales, diálogos y consultas sobre expresiones. También permite revisar adaptaciones para detectar concordancias incoherentes, localismos mal empleados o una acumulación artificial de muletillas.

## Características

- Adapta mensajes, correos y diálogos a una voz canaria.
- Distingue entre registro formal, natural, coloquial y de guasa.
- Tiene en cuenta el uso de ustedes y su concordancia, además de las variantes locales.
- Explica expresiones e insultos, sus matices y su posible carga ofensiva.
- Conserva hechos, cifras, condiciones y grado de certeza del texto original.
- Mantiene la ortografía convencional, sin exagerar el acento por escrito.

## Ejemplos

Estos ejemplos se han creado para el proyecto; no son citas de hablantes.

| Texto original | Adaptación |
| --- | --- |
| ¿Vosotros venís en autobús? | ¿Ustedes vienen en guagua? |
| Ponme un poquito de queso. | Ponme un fisco de queso. |
| Oye, olvidé lo que iba a decirte. | Chacho, se me fue el baifo con lo que iba a decirte. |
| Os enviamos el informe. Si tenéis dudas, contactad con nosotros. | Les enviamos el informe. Si tienen dudas, contacten con nosotros. |

Hay más ejemplos y casos de revisión en [antes y después](examples/antes-despues.md).

## Requisitos y compatibilidad

- Un asistente que admita skills basadas en un archivo `SKILL.md` y referencias en Markdown.
- Para seguir las instrucciones de instalación de esta página: Claude Code con soporte de skills.
- Git, si eliges instalar mediante clonación. La copia manual no lo necesita.

La skill contiene documentos; no requiere compilar código, instalar dependencias de Python o Node.js ni configurar claves de API propias. El cliente de IA puede tener sus propios requisitos de acceso y autenticación.

No se ha realizado una validación de compatibilidad en todos los clientes ni se establece una versión mínima verificada.

## Instalación

### Para un proyecto

Desde la raíz de tu proyecto:

```bash
git clone https://github.com/joaquinsosamartin/habla-canaria-skill.git .claude/skills/habla-canaria
```

### Para todos tus proyectos

```bash
git clone https://github.com/joaquinsosamartin/habla-canaria-skill.git ~/.claude/skills/habla-canaria
```

También puedes descargar el repositorio y copiar su contenido en una de esas carpetas. El archivo `SKILL.md` debe quedar directamente dentro de `habla-canaria/`, junto a `references/` y `examples/`.

Si usas otro cliente compatible con skills, utiliza la ubicación que indique ese cliente. Esta versión no se ha validado en todos los clientes.

## Inicio rápido

Una vez instalada, abre una sesión de Claude Code en el proyecto correspondiente y escribe:

```text
Usa la skill habla-canaria para adaptar este mensaje con tono natural:
¿Vosotros venís en autobús?
```

Una adaptación esperable es: «¿Ustedes vienen en guagua?».

## Uso y configuración

Pide la adaptación e indica el tono que buscas:

```text
Adapta este mensaje a un canario natural, sin exagerar:
[tu texto]
```

```text
Reescribe este correo en español de Canarias, con registro formal:
[tu correo]
```

```text
Escribe un diálogo con guasa entre amigos. Permite pullas leves.
```

```text
Explica qué significa «tolete», sus distintos sentidos y cuándo puede ofender.
```

Si buscas una voz de una isla, localidad, generación o época concreta, indícalo. Sin esa información, la skill utiliza una base canaria amplia y prudente.

### Modos

| Modo | Uso |
| --- | --- |
| Natural | Predeterminado. Expresiones discretas y pertinentes. |
| Formal | Correos y comunicaciones profesionales, sin muletillas añadidas. |
| Coloquial marcado | Más presencia de expresiones, manteniendo la naturalidad. |
| Guasa o diálogo | Ironía y pullas cuando se soliciten o formen parte del original. |
| Explicación | Significado, contexto, registro y fuentes de una expresión. |

Pedir un tono canario **no activa insultos automáticamente**. Una misma palabra puede funcionar como broma entre conocidos o como ofensa: importan la confianza, el tono y la situación.

### Preferencias en la petición

No hay un archivo de configuración adicional. Puedes indicar estas preferencias en lenguaje natural:

| Preferencia | Ejemplo |
| --- | --- |
| Registro | «Formal», «natural» o «coloquial marcado». |
| Contexto local | «Diálogo ambientado en La Gomera». |
| Destinatario | «Para un cliente» o «entre amigos». |
| Guasa e insultos | «Sin insultos» o «con pullas leves». |
| Formato de salida | «Solo el texto» o «explica los cambios». |

La precisión de una voz local depende de la documentación disponible. Indicar una localidad no garantiza que el repertorio cubra todos sus rasgos.

## Actualización y desinstalación

Si instalaste mediante Git, actualiza la instalación del proyecto con:

```bash
git -C .claude/skills/habla-canaria pull --ff-only
```

Para la instalación personal:

```bash
git -C ~/.claude/skills/habla-canaria pull --ff-only
```

Si modificaste archivos localmente, revisa y guarda tus cambios antes de actualizar. Si instalaste mediante copia manual, descarga la versión nueva y sustituye los archivos después de guardar tus personalizaciones.

Para desinstalar, elimina únicamente la carpeta `habla-canaria` de la ubicación donde la instalaste.

## Estructura del proyecto

```text
habla-canaria-skill/
├── README.md
├── SKILL.md
├── LICENSE
├── references/
│   ├── rasgos.md
│   ├── repertorio.md
│   └── fuentes.md
└── examples/
    └── antes-despues.md
```


- [SKILL.md](SKILL.md): instrucciones, modos y revisión final.
- [Rasgos](references/rasgos.md): gramática, pronunciación y variación.
- [Repertorio](references/repertorio.md): nueve entradas de léxico y expresiones, y seis insultos o reproches.
- [Fuentes](references/fuentes.md): documentación consultada y límites de la selección.
- [Ejemplos](examples/antes-despues.md): reescrituras y casos de revisión manual.

## Fuentes y metodología

La base principal es la [Academia Canaria de la Lengua](https://www.academiacanarialengua.org/), con consultas sobre el español de Canarias y entradas de su Diccionario básico de canarismos. Se consultó también prensa canaria y repertorios divulgativos; cada entrada indica su fuente.

Las definiciones se resumen con redacción propia y los ejemplos son originales. Se da prioridad a fuentes académicas; las entradas apoyadas en prensa se identifican como evidencia secundaria. Las decisiones editoriales se distinguen de los rasgos documentados.

## Limitaciones

Esta primera versión es una selección documentada, no un diccionario exhaustivo ni una norma oficial. Aún no cuenta con validación por hablantes de cada isla. Las intensidades de los modos y las notas sobre carga ofensiva son orientaciones editoriales.

## Validación

El repositorio incluye [casos de revisión manual](examples/antes-despues.md). Para evaluar una modificación, comprueba:

1. Que conserva hechos, cifras, negaciones, condiciones y grado de certeza.
2. Que mantiene la concordancia de tratamientos, verbos y posesivos.
3. Que cada expresión corresponde al significado y al registro previstos.
4. Que no atribuye rasgos locales a todo el Archipiélago sin respaldo.
5. Que los enlaces internos apuntan a archivos existentes.

No hay una batería automatizada de pruebas lingüísticas. Los ejemplos muestran el comportamiento buscado; no garantizan una salida idéntica de todos los modelos.

## Solución de problemas

| Problema | Qué revisar |
| --- | --- |
| El asistente no encuentra la skill | Comprueba que `SKILL.md` está directamente en la carpeta de instalación y que el cliente admite skills. Abre una sesión nueva y menciona su nombre. |
| No encuentra las referencias | Copia también `references/` y `examples/`, conservando su estructura. |
| El resultado contiene demasiadas expresiones | Pide modo natural, sin muletillas añadidas, o registro formal. |
| Aparecen insultos que no querías | Indica «sin insultos» y revisa si el original o las instrucciones de la conversación los solicitaban. |
| Una expresión no encaja con tu isla | Indica la localidad y comunica la corrección con una fuente o contexto de uso. |
| Git no permite actualizar | Revisa los cambios locales antes de volver a ejecutar la actualización; evita sobrescribir tus personalizaciones. |

## Contribuciones

Se agradecen correcciones y propuestas mediante issues o pull requests. Para añadir una expresión, aporta:

1. Significado y contexto de uso.
2. Isla o localidad, si corresponde, y registro o generación cuando se conozcan.
3. Una fuente concreta que respalde la entrada.
4. Un ejemplo original y una nota sobre ambigüedad o carga ofensiva, si procede.

Evita atribuir una palabra a todas las islas sin evidencia o presentar como demostradas las etimologías populares.

## Hoja de ruta

Posibles mejoras, sin fechas comprometidas:

- Ampliar el repertorio con fuentes específicas para cada entrada.
- Mejorar las marcas geográficas, generacionales y de registro.
- Incorporar revisión de hablantes de distintas islas.
- Añadir más ejemplos formales, cotidianos y de diálogo.
- Documentar la compatibilidad comprobada con otros clientes.

## Soporte

Para dudas, errores o propuestas, abre una [incidencia en GitHub](https://github.com/joaquinsosamartin/habla-canaria-skill/issues). Incluye la petición utilizada, la respuesta obtenida y el resultado esperado. Si se trata de una corrección lingüística, añade contexto y fuentes cuando sea posible.

Revisa y anonimiza los ejemplos antes de compartirlos públicamente.

## Autoría y agradecimientos

Proyecto mantenido en el repositorio de [Joaquín Sosa Martín](https://github.com/joaquinsosamartin).


La organización se inspira en [asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill), de danyuchn. Las instrucciones y los ejemplos de este proyecto tienen redacción propia; no aplican el estándar ASD-STE100.

## Licencia

El contenido original del repositorio se distribuye bajo la [licencia MIT](LICENSE). Las fuentes externas enlazadas conservan sus propios derechos.
