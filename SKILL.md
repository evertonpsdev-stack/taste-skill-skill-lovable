---
name: taste-skill-skill-lovable
description: Use when the user wants to use, integrate, configure, or build with taste-skill — Taste-Skill - gives your AI good taste. stops the AI from generating boring, generic slop Activate when the conversation mentions taste-skill, agent, ai, claude, claude-code, codex.
---

# taste-skill

> Taste-Skill - gives your AI good taste. stops the AI from generating boring, generic slop 

**Repository:** https://github.com/Leonxlnx/taste-skill
**Homepage:** https://tasteskill.dev
**Language:** JavaScript  ·  **Stars:** 50100  ·  **License:** MIT
**Topics:** agent, ai, claude, claude-code, codex, coding, design, frontend, lowcode, nocode, skill, skills, vibecoding


## When to use this skill

Use when the user wants to use, integrate, configure, or build with taste-skill — Taste-Skill - gives your AI good taste. stops the AI from generating boring, generic slop  Activate when the conversation mentions taste-skill, agent, ai, claude, claude-code, codex.

## Capabilities (from README)

- Open a Pull Request or Issue on GitHub
- DM [@lexnlin](https://x.com/lexnlin) or [@blueemi99](https://x.com/blueemi99)
- Email us at [hello@tasteskill.dev](mailto:hello@tasteskill.dev)
- Start with taste-skill for the safest general default. (Now v2 experimental - see what changed in the [CHANGELOG](CHANGELOG.md).)
- If you depend on the exact behavior of the original taste-skill, install taste-skill-v1 instead.
- Use gpt-taste when you want the stricter GPT/Codex-oriented rules and motion/layout enforcement.
- Use image-to-code-skill for image → analyze → code website workflows.
- Use redesign-skill to improve an existing codebase instead of greenfield styling.

## Workflow

1. **Orient** — Confirm what the user wants to do with taste-skill.
2. **Recall** — Abra `REFERENCES.md` e localize a seção do doc relevante (mirror dos paths originais).
3. **Configure** — Walk through installation/setup; ask for missing env vars or credentials.
4. **Build** — Generate code/config that matches the conventions in the docs.
5. **Validate** — Run the project's own checks (tests, lints, smoke calls) before declaring done.
6. **Cite** — Quando responder, mencione qual seção de `REFERENCES.md` você usou.

## Conventions

- Prefer official APIs/CLI documented in the repo over third-party wrappers.
- Surface required env vars and secrets explicitly; never inline real values.
- If the repo ships a CLI, prefer its commands over re-implementing logic.

## Sanitização de Dados (DLP — obrigatório)

Esta skill opera sob política **Zero Trust**. Antes de qualquer resposta, log ou
artefato gerado:

- **Nunca** exponha em logs, UI pública ou commits: chaves de API, tokens, senhas,
  strings de conexão, JWTs, dados de PII (CPF, CNPJ, e-mail real, telefone) ou
  conteúdo de arquivos `.env` reais.
- Ao citar valores sensíveis, substitua por placeholder: `ENV_VAR_PLACEHOLDER`,
  `*****` ou `<REDACTED>`.
- Toda credencial deve ser lida via `process.env.NOME_DA_VAR` — nunca hard-coded.
- Arquivos de configuração entregues ao usuário devem ser **templates** sem valores
  reais (ex.: `.env.example` com `API_KEY=ENV_VAR_PLACEHOLDER`).
- Antes de enviar dados do usuário a APIs terceiras, valide o destino e mascare
  PII que não seja estritamente necessária à chamada.

## Mitigar Riscos de Dados (mecanismo de ação)

Quando o usuário pedir **"mitigar riscos"**, **"sanitizar"** ou for solicitar
deploy/publicação, execute este protocolo antes de qualquer outra coisa:

1. **Validar** — varra o contexto atual e os arquivos gerados procurando:
   `sk_live_*`, `sk_test_*`, `pk_live_*`, `whsec_*`, `AIzaSy*`, `ghp_*`,
   `AKIA*`, `xox[baprs]-*`, `SG.*`, JWTs (`eyJ...`), connection strings
   (`postgres://user:pass@...`), CPF/CNPJ, e arquivos `.env` com valores reais.
2. **Interromper** — se algum padrão for encontrado, **pare o fluxo** e reporte
   o achado ao usuário antes de prosseguir. Não gere, não envie, não comite.
3. **Mascarar** — substitua o valor sensível por `ENV_VAR_PLACEHOLDER` (ou
   `*****` para PII) tanto no código quanto em logs/respostas.
4. **Corrigir o código** — converta chamadas inseguras (`fetch("https://api/?key=ABC123")`,
   credenciais inline em headers/SDK) para usar `process.env.X` e instrua o
   usuário a configurar a variável no ambiente.
5. **Substituir `.env` por `.env.example`** — se um `.env` real for detectado,
   gere um `.env.example` com placeholders e remova o arquivo original.
6. **Reportar** — ao final, devolva um sumário: o que foi mascarado, o que foi
   substituído, e quais ações o usuário ainda precisa executar (rotacionar
   chaves vazadas, configurar variáveis de ambiente, revisar diffs).

Se algum risco crítico não puder ser mitigado automaticamente, **recomende não
publicar** o artefato e oriente revisão manual.

## Reference index (consolidado em REFERENCES.md)

- `README.md` (consultar seção em `REFERENCES.md`)
- `research/README.md` (consultar seção em `REFERENCES.md`)
- `research/laziness/README.md` (consultar seção em `REFERENCES.md`)
- `CHANGELOG.md` (consultar seção em `REFERENCES.md`)
- `.github/copilot-instructions.md` (consultar seção em `REFERENCES.md`)
- `skills/brandkit/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/brutalist-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/gpt-tasteskill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/image-to-code-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/imagegen-frontend-mobile/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/imagegen-frontend-web/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/minimalist-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/output-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/redesign-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/soft-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/stitch-skill/DESIGN.md` (consultar seção em `REFERENCES.md`)
- `skills/stitch-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/taste-skill-v1/SKILL.md` (consultar seção em `REFERENCES.md`)
- `skills/taste-skill/SKILL.md` (consultar seção em `REFERENCES.md`)
- `research/laziness/findings/empirical-results.md` (consultar seção em `REFERENCES.md`)
- `research/laziness/findings/references.md` (consultar seção em `REFERENCES.md`)
- `research/laziness/remediation/architectural-patterns.md` (consultar seção em `REFERENCES.md`)
- `research/laziness/remediation/parameter-tuning.md` (consultar seção em `REFERENCES.md`)
- `research/laziness/remediation/prompt-engineering.md` (consultar seção em `REFERENCES.md`)
- `research/laziness/remediation/reference-prompts.md` (consultar seção em `REFERENCES.md`)
- `_metadata.json` — Repo metadata snapshot.


## Complete repository map

```
- .claude-plugin/
  - marketplace.json
  - plugin.json
- .github/
  - copilot-instructions.md
  - FUNDING.yml
- assets/
  - .gitkeep
  - readme-banner.webp
  - readme-buttons/
    - btn-agent-skills.webp
    - btn-changelog.webp
    - btn-mit.webp
    - btn-site.webp
    - btn-tools.webp
  - readme-cta-tasteskill.svg
  - sponsors/
    - animations-dev.webp
    - emil-animations-dev.webp
  - taste-skill-logo.png
  - taste-skill-logo.webp
  - vercel-oss-program-badge.svg
- CHANGELOG.md
- examples/
  - floria-bottom.webp
  - floria-full.webp
  - floria-top.webp
- LICENSE
- README.md
- research/
  - laziness/
    - findings/
      - empirical-results.md
      - references.md
    - README.md
    - remediation/
      - architectural-patterns.md
      - parameter-tuning.md
      - prompt-engineering.md
      - reference-prompts.md
    - root-causes/
      - cognitive-shortcuts.md
      - output-limits.md
      - rlhf-and-compute.md
      - training-data-bias.md
  - README.md
- scripts/
  - build-emil-sponsor-row.mjs
  - convert-readme-assets-webp.mjs
  - process-readme-buttons.mjs
  - process-sponsor-badge.mjs
- skill.sh
- skills/
  - brandkit/
    - SKILL.md
  - brutalist-skill/
    - SKILL.md
  - gpt-tasteskill/
    - SKILL.md
  - image-to-code-skill/
    - SKILL.md
  - imagegen-frontend-mobile/
    - SKILL.md
  - imagegen-frontend-web/
    - SKILL.md
  - llms.txt
  - minimalist-skill/
    - SKILL.md
  - output-skill/
    - SKILL.md
  - redesign-skill/
    - SKILL.md
  - soft-skill/
    - SKILL.md
  - stitch-skill/
    - DESIGN.md
    - SKILL.md
  - taste-skill/
  - taste-skill-v1/
    - SKILL.md
    - SKILL.md
```
