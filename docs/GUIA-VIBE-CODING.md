# Vibe Coding: Orquestación Inteligente

## Qué es

Vibe coding es ingeniería de software donde el flujo de trabajo importa tanto como el código.

No es caos. Es estructura invisible—espacios de trabajo limpios, procesos paralelos sin fricción, supervisión que no sofoca.


## Por qué importa

Cuando trabajas **solo**, puedes ignorar esto.

Cuando quieres que **múltiples agentes trabajen en paralelo**, la arquitectura del flujo es tan importante como el código mismo.

Un agente que escribe bien pero en caos desorganizado = productividad ~0.

Múltiples agentes en flujo claro + supervisión invisible = trabajo real que termina.

## Cómo Oasis lo implementa

### 1. Espacio limpio
Cada tarea obtiene su propio **git worktree**.
- No se interfieren entre sí
- Pueden mergear en paralelo
- Si algo falla, no afecta el resto

### 2. Supervisión invisible
Un watcher bash monitorea el equipo.
- Duerme cuando no hay trabajo
- Se despierta cuando algo termina o falla
- Zero overhead, zero tokens

### 3. Decisiones claras
Cuando necesitas intervención humana (tuya), la pregunta es **cristalina**:
```
PR lista: fix login flaky
Riesgo: bajo | CI: verde

> merge it?
```

No hay ambigüedad. No hay "¿qué estaba pasando?"

### 4. Contexto local
Cada proyecto tiene su `AGENTES.md` (no global).
- Reglas específicas del proyecto
- Histórico de decisiones
- Memory que persiste

## Relación con Research

Vibe coding es a software lo que metodología es a investigación.

En mi doctorado (control térmico de rovers):
- Datos bien organizados = experimentos reproducibles
- Workflow claro = resultados confiables
- Documentación fuerte = otros pueden construir sobre tu trabajo

En Oasis:
- Espacio limpio = agentes paralelos sin colisión
- Supervisión clara = sé qué está pasando
- Documentación = otros pueden contribuir

## Aplicación práctica

### Caso: Email CRM Pipeline
Sin vibe coding:
```
Tú: "Arregla las queries del CRM"
Agente: Comienza, pero necesita contexto
Tú: Copiando de aquí, pegando allá
→ Pierde tiempo, sale mal
```

Con Oasis + vibe coding:
```
Tú: "Arregla las queries del CRM"
Oasis: Clona proyecto, spawn agente en worktree limpio
Agente: Lee AGENTES.md (contexto del proyecto)
Agente: Trabaja sin interferir otros procesos
Minutos después: PR lista
```

## La filosofía

Vibe coding = **respeto por el tiempo**.

Tuyo
Del agente 
Del próximo developer 

---

*Oasis es la materialización de vibe coding.*