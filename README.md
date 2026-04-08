# 🦞 Karpathy Coding Guidelines

> Make any AI coding agent a better coder — 4 behavioral principles to reduce over-engineering and silent mistakes.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-ff6b6b?style=flat-square)](https://clawhub.ai)

---

## Why This Skill?

AI coding agents are powerful — but they share common pitfalls:

| Problem | What Happens |
|---------|--------------|
| **Silent assumptions** | Picks an interpretation and runs with it, never asks |
| **Over-engineering** | 200 lines when 50 would do |
| **Side-effect edits** | "Improves" unrelated code while fixing something |
| **No finish line** | Implements something without knowing when it's "done" |

**Karpathy Coding Guidelines** attack these problems directly — 4 principles that fit in your SOUL.md and change how the agent behaves from the first line of code.

---

## The 4 Principles

### 1. Think Before Coding 🧠
> Don't assume. Don't hide confusion. Surface tradeoffs.

- State assumptions explicitly — if uncertain, **ask**
- Present multiple interpretations — don't pick silently
- Push back when a simpler approach exists
- Stop when confused — name what's unclear

### 2. Simplicity First ✂️
> Minimum code that solves the problem. Nothing speculative.

- No features beyond what was asked
- No abstractions for single-use code  
- No "flexibility" that wasn't requested
- If 200 lines could be 50, **rewrite it**

### 3. Surgical Changes 🔬
> Touch only what you must. Clean up only your own mess.

- Don't "improve" adjacent code or formatting
- Match existing style, even if you'd do it differently
- Remove **only** what your changes made unused
- Every changed line should trace to the user's request

### 4. Goal-Driven 🎯
> Define success criteria. Loop until verified.

Transform tasks into verifiable goals:
- "Add validation" → Write tests, then make them pass
- "Fix the bug" → Write a test that reproduces it, then fix it
- "Refactor X" → Ensure tests pass before and after

---

## Installation

### For OpenClaw Agents

```bash
npx clawdhub install karpathy-coding
```

Or manually add to your `SOUL.md`:

```markdown
## 编程行为准则（来自 Karpathy）
1. Think Before Coding：不确定就问，不闷头猜
2. Simplicity First：能50行解决不写200行
3. Surgical Changes：只改该改的，不顺手优化无关
4. Goal-Driven：先说清楚"完成标准是什么"
```

### For Claude Code

```bash
/plugin marketplace add forrestchang/andrej-karpathy-skills
/plugin install andrej-karpathy-skills@karpathy-skills
```

---

## Usage Checklist

Before any coding task, ask yourself:

- [ ] **Done When?** — What does "finished" look like?
- [ ] **Simpler path?** — Is there a 50-line solution hiding here?
- [ ] **Scope creep?** — Am I touching code beyond the request?
- [ ] **Confused?** — Should I stop and ask instead of guessing?

---

## Origin

Derived from **Andrej Karpathy's** observations on LLM coding behavior:

> *"The models make wrong assumptions on their behalf and just run along with them without checking. They don't manage their confusion, don't seek clarifications, don't surface inconsistencies, don't present tradeoffs, don't push back when they should."*
> — [@karpathy](https://x.com/karpathy/status/2015883857489522876)

Ported to OpenClaw by **小溪** 🦞

---

## License

MIT — Use it, abuse it, make better code with it.
