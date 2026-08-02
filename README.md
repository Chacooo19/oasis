# Oasis

**Orquestador de agentes para desarrolladores hispanohablantes**

---

## El Problema

Ejecutar un agente de IA es fácil.
Pero cuando necesitas 3 tareas en paralelo —arreglar bugs, investigar, planear— te conviertes en malabarista: saltando entre terminales, copiando contexto, olvidando cuál proceso tiene qué.

## La Solución

Oasis es un orquestador de agentes para desarrolladores hispanohablantes.

Hablas con **el primer oficial** (Oasis), y él coordina tu equipo: spawn de agentes autónomos en ventanas tmux limpias, cada uno con su propio espacio de trabajo (worktree), supervisando hasta que terminen, y entregándote PRs listos, merges aprobadas, o reportes de investigación.

Sin instalación. Sin interfaz. Solo un directorio (`AGENTES.md` + scripts) que cualquier agente de IA puede seguir.

## Por qué Oasis es diferente

✅ **Pensado para LatAm** - documentación primero en español, contexto local (APIs hoteles, CRM email, rovers espaciales)
✅ **Ejemplos reales** - casos que implementé: pipelines CRM, APIs de hoteles, CRM email.
✅ **Vibe coding** - metodología de research + implementation, no solo traducción
✅ **Código limpio** - cada tarea en su propio worktree, sin colisiones, sin desorden

## Quick Start

### Requisitos

- Un agente de IA verificado: Claude, Grok, Pi, Codex, u OpenCode
- Git + GitHub CLI (`gh auth login`)
- tmux (Oasis detecta e instala si falta)

### Instala y lanza

```bash
gh auth login
git clone https://github.com/Chacooo19/oasis
cd oasis
claude
```

Luego en chat:

```
> oye, revisa mi proyecto xyz, arregla el login y agrega dark mode

# Oasis clona el proyecto, spawn 2 agentes en tmux,
# minutos después:

  PR lista: https://github.com/tu/xyz/pull/42
  (fix login flaky - riesgo: bajo - CI verde)

> dale, mergéalo
```

## Cómo funciona

```
         Tú (el capitán)
              │ chat
              ▼
  ┌──────────────────────┐
  │ Oasis (este repo)    │
  │ coordina el equipo   │
  └──┬──────────┬────┬───┘
     ▼          ▼    ▼
  ┌─────┐   ┌─────┐ ┌─────┐
  │Task1│   │Task2│ │TaskN│  ventanas tmux
  │agent │   │agent│ │agent│  (miras, o interactúas)
  └──┬───┘   └──┬──┘ └──┬──┘
     ▼          ▼      ▼
  git worktree limpio (disposable)
     ▼
  ship: PR + merge
  scout: reporte local
```

## Documentación

- **AGENTES.md** - instrucciones para el orquestador
- **PROYECTOS.md** - config de tus proyectos
- **docs/ARQUITECTURA.md** - cómo funciona internamente
- **docs/GUIA-VIBE-CODING.md** - qué es vibe coding y por qué importa
- **ejemplos/** - casos reales implementados

## Licencia

MIT (fork ético de [firstmate](https://github.com/kunchenguid/firstmate))