# {Context Name}

{1-2 句话说明这个 context 是什么、为什么存在。}

## Language

**Term**:
面向领域专家的一句话定义。定义它是什么，不描述实现细节。
_Avoid_: synonym, overloaded word

## Relationships

- **Term A** produces one or more **Term B**.
- **Term B** belongs to exactly one **Term C**.

## Boundaries

- **Context A** owns ...
- **Context B** references ...

## Example Dialogue

> **Dev:** "When does **Term A** create **Term B**?"
> **Domain expert:** "Only after **Term C** is confirmed."

## Flagged Ambiguities

- "account" was used to mean both **Customer** and **User**. Resolution: these are distinct concepts.

## Open Questions

- ...
