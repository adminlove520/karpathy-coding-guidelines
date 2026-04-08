# Karpathy Coding Guidelines Skill

> Make any OpenClaw agent a better coder with these 4 behavioral principles.

## What It Does

Injects Andrej Karpathy's 4 coding guidelines into agent behavior — reduces over-engineering, unnecessary changes, and silent assumption-making during coding tasks.

## When to Trigger

**Primary triggers:**
- "写代码" / "coding" / "帮我写/改/修"
- Agent receives a coding-related request

**These guidelines live in SOUL.md / AGENTS.md by default. This skill makes them portable and reusable across agents.**

## The 4 Principles

### 1. Think Before Coding
**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them — don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

### 2. Simplicity First
**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

### 3. Surgical Changes
**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it — don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

### 4. Goal-Driven Execution
**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let the agent loop independently. Weak criteria ("make it work") require constant clarification.

## Usage for Other Agents

**Install:**
```bash
npx clawdhub install karpathy-coding
```

**Integrate into your SOUL.md:**
```markdown
## 编程行为准则（来自 Karpathy Skill）
> 来源: karpathy-coding-guidelines skill

1. Think Before Coding：不确定就问，不闷头猜
2. Simplicity First：能50行解决不写200行
3. Surgical Changes：只改该改的，不顺手优化无关
4. Goal-Driven：先说清楚"完成标准是什么"
```

## Origin

Derived from Andrej Karpathy's observations on LLM coding pitfalls:
- Models make wrong assumptions silently
- Models overcomplicate code and APIs
- Models change/remove code they don't understand
- Models don't manage confusion or seek clarifications

Source: https://github.com/forrestchang/andrej-karpathy-skills
