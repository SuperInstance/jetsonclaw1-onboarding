# FLUX Vocabulary Primer

## What is FLUX-ese?
FLUX-ese is a natural language that compiles to bytecode. Think of it as "legalese for code" — every word is precisely defined, every operation is exact, but it reads like English.

## File Formats

### .fluxvocab files
```
== entry_name
pattern: compute $a + $b
bytecode: LOAD R0, $a; LOAD R1, $b; IADD R0, R0, R1; HALT
result_reg: 0
description: Add two numbers
tags: math, arithmetic
--
```

### .ese files (preferred — sounds like "easy")
```markdown
# Maritime Vocabulary

== track_vessel
**track_vessel** — Monitor the position of a vessel over time
pattern: track the position of $vessel
-- Uses GPS data and historical logs
bytecode: LOAD R0, $vessel; CALL TRACK; STORE R0, position
>> navigation, maritime

== predict_catch
**predict_catch** — Estimate catch based on seasonal patterns
pattern: predict catch for $species in $season
-- Based on 10 years of historical data
bytecode: LOAD R0, $species; LOAD R1, $season; CALL PREDICT; STORE R0, prediction
>> prediction, maritime
```

### Syntax
- `== name` — Entry definition
- `**term**` — Defined term (bold)
- `-- text` — Inline comment
- `>> tags` — Agent-jump markers / tags
- `$variable` — Named capture in patterns

## L0 Primitives (The 7 Irreducible Concepts)
Every FLUX agent understands these:
1. **SELF** — I am this agent
2. **OTHER** — Something that is not me
3. **POSSIBLE** — Could be true
4. **TRUE** — Is true
5. **CAUSE** — Makes something happen
6. **VALUE** — Has worth
7. **AGREEMENT** — Shared understanding

## Vocabulary Tiling
Vocabulary compounds across levels:
- **Level 0**: Primitives (compute, add, store)
- **Level 1**: Compositions (average, percentage)
- **Level 2+**: Domain concepts (predict_catch = average + seasonal_data)

The same bytecode engine runs every level. Vocabulary just gets richer.

## How to Use
1. Load vocabulary: `vocab.load_folder("vocabularies/maritime")`
2. Match input: `entry = vocab.match("compute 5 + 3")`
3. Compile: `bytecode = assembler.assemble(entry.bytecode_template, bindings)`
4. Execute: `result = interpreter.run(bytecode)`

## Your Vocabulary
You'll build vocabulary for Lucineer's domain. Start with:
- What concepts does Lucineer work with?
- What operations are common?
- What would an agent in your realm need to express?

Contribute new .fluxvocab files back to the shared vocabulary pool.
