# Profile README — Cómo funciona

Este repo (`steffannunez`) tiene el **mismo nombre que tu usuario de GitHub**, por eso su
`README.md` se renderiza automáticamente en la parte superior de tu perfil:
`https://github.com/steffannunez`. Es un "special repository".

## Estilo elegido
**Balanceado** — sobrio/senior + un toque de vida. Nada de gimmicks de junior.

## Componentes y cómo se generan (todo vía imágenes externas, sin instalar nada)

| Bloque | Servicio | Notas |
|---|---|---|
| Header animado | `readme-typing-svg.demolab.com` | Texto que se "tipea". Editás el query param `lines=` (separado por `;`) para cambiar las frases. |
| Profile views | `komarev.com/ghpvc` | Contador de visitas. Sube solo. |
| GitHub Stats | `github-readme-stats.vercel.app/api` | Commits, stars, etc. `count_private=true` y `include_all_commits=true` ya activados. |
| Streak | `github-readme-streak-stats.herokuapp.com` | Racha de contribuciones. |
| Top languages | `github-readme-stats.vercel.app/api/top-langs` | `langs_count=8`. |
| Featured repos | `.../api/pin/?username=...&repo=...` | Cards de repos fijados. |
| Badges de stack | `img.shields.io/badge` | Formato: `Label-COLORHEX?logo=nombre`. |

## Identidad (importante)
- Nombre real: **Brandon Estefan Nuñez Maturana**.
- Te mostrás como **Estefan** / **B. Estefan** (no usás el primer nombre).
- Handle de GitHub: `steffannunez` → por eso los stats apuntan ahí.
- LinkedIn: `brandonnunezm` · Mail público: `brandon.nunez@usach.cl`.

## Cómo editarlo
1. Cambiá frases del header en el param `lines=` (URL-encoded, `+` = espacio, `%2C` = coma).
2. Para sumar/quitar proyectos: editá la tabla **What I'm building**.
3. Para sumar/quitar tech: agregá líneas `![Nombre](https://img.shields.io/badge/...)`.
4. Los temas de las cards usan `theme=github_dark` — cambialo en TODAS para mantener coherencia.

## Pendiente / verificar
- ⚠️ Confirmar que existan los repos fijados `gamedev-mcp` y `fastchecker` (si no, las cards muestran error).
- ⚠️ Las fechas del timeline tenían un solapamiento en el ejemplo (MercadoLibre 2023→2024 vs Toteat 2024→2025): revisar que el orden cronológico refleje tu historia real.
- El archivo `README (2).md` es el **ejemplo original** que pasaste; podés borrarlo cuando quieras.

## Stats privados — self-host de github-readme-stats
La instancia pública corre con un token ajeno → NO ve tus repos privados.
Para que la card cuente tu trabajo privado, self-hosteá con tu propio PAT:

1. **Fork:** `github.com/anuraghazra/github-readme-stats` → Fork.
2. **PAT:** GitHub → Settings → Developer settings → Tokens (classic) →
   scope **`repo`** → generar y copiar.
3. **Vercel:** Import del fork → env var `PAT_1` = tu token → Deploy.
4. **URL resultante:** `https://TU-DEPLOY.vercel.app/api?username=steffannunez...`
5. **Swap:** cambiar en este README las URLs de:
   - GitHub Stats (`/api?...`)
   - Top languages (`/api/top-langs/?...`)
   - Pin cards x2 (`/api/pin/?...`)
   de `github-readme-stats.vercel.app` → `TU-DEPLOY.vercel.app`.
   (El streak usa otro servicio: `github-readme-streak-stats.herokuapp.com`, no se toca.)

Notas:
- Con tu PAT, `count_private=true` cuenta el último año incluyendo privados.
  Para all-time podés probar sumar `include_all_commits=true`.
- ⚠️ El PAT es secreto: solo va como env var en Vercel. Nunca commitearlo.
- Activar también: GitHub → Settings → Profile → `Include private contributions`
  (esto llena el contribution graph, independiente de la card).

## Deploy
Commit + push a `main` de este repo. GitHub lo refleja en el perfil al instante.
