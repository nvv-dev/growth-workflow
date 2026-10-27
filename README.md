# growth-workflow

Skills de marketing y lanzamiento para agentes: contexto del producto, perfil de voz, copy de landings con prueba para cada afirmación, revisión de posts, fichas de tiendas de apps, checklist de lanzamiento y revisión de páginas legales. Funcionan como plugin de Claude Code y también como carpetas sueltas que puedes leer, copiar o adaptar a cualquier agente compatible con el formato [Agent Skills](https://agentskills.io) (`SKILL.md`).

*English version below.*

## Objetivo

Que el trabajo de marketing hecho con agentes salga de hechos y no de suposiciones: los datos del negocio viven en dos archivos que todas las skills leen (`.agents/product-context.md` y `.agents/voice.md`), ninguna inventa cifras, testimonios ni logos de clientes, y ninguna publica, envía ni gasta dinero por su cuenta.

## Skills

| Skill | Para qué sirve | Se activa |
|---|---|---|
| [product-context](skills/product-context/SKILL.md) | Crea y mantiene `.agents/product-context.md`: producto, cliente ideal, posicionamiento, objeciones, pruebas y aprendizajes, con versión y registro de cambios | Sola, al empezar trabajo de marketing o con datos nuevos del producto |
| [voice-profile](skills/voice-profile/SKILL.md) | Entrevista y 3 a 5 textos reales para armar `about-me.md` y `voice.md`; pregunta antes de empezar | Solo a mano |
| [landing-copy](skills/landing-copy/SKILL.md) | Copy por página desde el mapa de palabras clave y el contexto: titular, subtítulo, beneficios, objeciones y CTA, con variantes | Sola, al escribir una página |
| [post-review](skills/post-review/SKILL.md) | Puntaje de un borrador (gancho, una idea, prueba, voz, formato de la red, CTA) con correcciones; nunca publica | Sola, al revisar un post |
| [app-store-listing](skills/app-store-listing/SKILL.md) | Ficha de Play Store y App Store coherente con la sección de seguridad de datos | Sola, al preparar una ficha |
| [launch-checklist](skills/launch-checklist/SKILL.md) | Antes y después de lanzar: medición, páginas legales, ficha, anuncio, canal de comentarios y vuelta atrás | Solo a mano |
| [legal-pages-check](skills/legal-pages-check/SKILL.md) | Privacidad, términos y cookies contra una lista por país (Colombia, Ley 1581, como ejemplo) y contra lo que la app declara; no es asesoría legal | Solo a mano |

"Solo a mano" significa que la skill tiene `disable-model-invocation: true`: no se carga sola y la invocas tú (por ejemplo `/growth-workflow:launch-checklist`). Así no ocupa contexto en cada sesión.

## Instalación

**Como plugin de Claude Code** (recomendado):

```text
/plugin marketplace add nvv-dev/claude-plugins
/plugin install growth-workflow@nvvdev
```

Si quieres los agentes que usan estas skills (copywriter, estratega de contenido, growth y revisión legal), instala también `growth-agents@nvvdev`.

**Como skills sueltas** (otros agentes o para adaptarlas): copia la carpeta de la skill que quieras dentro de la carpeta de skills de tu agente, por ejemplo `.claude/skills/` en tu repo. Cada carpeta es independiente.

## Cómo están escritas

- Las instrucciones están en inglés para que los escáneres de seguridad de skills (como SkillSpector) las analicen por completo. El agente responde en el idioma de quien la usa.
- Genéricas: no se editan con los datos de tu negocio. Esos datos van en `.agents/product-context.md` y `.agents/voice.md`, que las skills leen.
- Cada skill termina con una sección **Known failures** para registrar los errores reales de los agentes.
- Ninguna skill publica, programa, envía, gasta dinero ni cambia precios. `legal-pages-check` no es asesoría legal: entrega preguntas para un abogado.

## Origen

Son skills propias, escritas desde cero a partir de ideas de proyectos de la comunidad. Ver [CREDITS.md](CREDITS.md).

## Contribuir

Abre un issue o PR. Si una skill falló en un caso real, la mejor contribución es una entrada en su sección **Known failures** con el caso y la regla que lo evita. El CI valida el formato de cada `SKILL.md` y lo pasa por SkillSpector.

## Licencia

MIT.

---

## English

Marketing and launch skills for agents: product context, voice profile, landing page copy with proof for every claim, social post review, app store listings, a launch checklist and a legal pages check. They work as a Claude Code plugin and as standalone folders for any agent that supports the [Agent Skills](https://agentskills.io) `SKILL.md` format.

**Install as a Claude Code plugin:**

```text
/plugin marketplace add nvv-dev/claude-plugins
/plugin install growth-workflow@nvvdev
```

**Or copy a single skill folder** into your agent's skills directory (for example `.claude/skills/`).

Business facts live in `.agents/product-context.md` and `.agents/voice.md`, which the skills read, so the skills stay generic. No skill invents numbers, testimonials or client logos, and none publishes, sends, spends money or changes prices. `legal-pages-check` is not legal advice. Skills marked "solo a mano" use `disable-model-invocation: true`. See [CREDITS.md](CREDITS.md). License: MIT.
