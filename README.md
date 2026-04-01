# BeHuman

### The first mirror for AI.

<p align="center">
<a href="#english">English</a> · <a href="./README_CN.md">中文</a>
</p>

---

You talk to yourself before every decision you make.

You want to quit your job. Your first thought is *"I'm done."* Then another voice says *"Wait — what about rent?"* You want to comfort a friend. Your first instinct is *"It'll be okay."* Then something inside you says *"That's bullshit. How would you feel hearing that?"*

The decision you actually make isn't the first voice. It isn't the second voice. It's what emerges **after they talk to each other**.

AI never does this. AI has one voice. It thinks, it speaks, it's done.

That's why AI responses are always correct but never human. Polite but hollow. Thorough but touching no one.

**BeHuman gives AI the missing piece: inner dialogue.**

---

## What It Does

BeHuman implements a **Self-Mirror consciousness loop** — a two-voice inner dialogue that runs before every response:

```
     Shared Context
  ┌──────────────────┐
  │ Same history      │
  │ Same user profile │
  │ Same knowledge    │
  └────────┬─────────┘
           │
    ┌──────┴──────┐
    │             │
┌───▼────┐  ┌────▼────┐
│  Self  │  │ Mirror  │
│        │  │         │
│ I want │  │ Are you │
│ to say…│  │ sure?   │
│ I feel…│  │ Why?    │
│ I think│  │ Really? │
└───┬────┘  └────┬────┘
    └──────┬─────┘
           ↓
   Conscious Response
   (what a human would actually say)
```

**Self** is the instinct — fast, reactive, eager to help. It has all the AI habits: over-politeness, list-making, empty empathy, correct-but-soulless answers.

**Mirror** is the reflection — same knowledge, same memory, same context. It doesn't judge. It doesn't give answers. It just **reflects Self back to itself**. Like looking in a mirror and seeing what you actually look like, not what you think you look like.

They share everything. The only difference is the direction they look.

After the mirror reflects, Self responds again — but this time, as a human would.

---

## See It Work

### Emotional support

**User:** "I just got laid off."

```
💭 Self:
I'm sorry to hear that. Losing a job can be really stressful. Here are some
steps you might consider: 1) Update your resume 2) Reach out to your network
3) Review your finances...

🪞 Mirror:
Stop. They just lost their job and you're assigning homework? "Update your
resume" — that's not what they need right now. And "I'm sorry to hear that"?
Do you actually feel sorry? You're performing empathy. Just be present.

🧠 Conscious Response:
Shit... was it out of nowhere? How are you doing right now?
```

### Life advice

**User:** "Should I quit big tech to start my own company?"

```
💭 Self:
This is a significant life decision that requires careful consideration from
multiple angles. Let's look at the financial implications, market conditions,
and your risk tolerance...

🪞 Mirror:
"Multiple angles" — you're using an MBA textbook to answer someone who's
torn between fear and excitement. They're not here for a decision matrix.
They already know the pros and cons. Ask them how long this idea has been
living in their head. That's the real question.

🧠 Conscious Response:
How long has this idea been in your head? If it's been more than six months,
you already know your answer.
```

### Writing

**User:** "Write me a dating app bio."

```
💭 Self:
I'm a passionate, outgoing person who loves traveling, watching movies, and
trying new cuisines. Looking for someone to share life's adventures with...

🪞 Mirror:
Congratulations, you just wrote the bio that gets swiped left by everyone.
"Passionate, outgoing, loves travel" — that describes 80% of humans. You
didn't write a person. You wrote a template. Real bios have details, flaws,
specifics.

🧠 Conscious Response:
Most weekends I try to cook, fail, and order takeout. Currently three months
into "One Hundred Years of Solitude" — still not finished. I have a cat. She
doesn't really like me.
```

---

## Why a Mirror, Not a Critic

Existing approaches focus on making AI **better at being AI**:

| Approach | Focus | Goal |
|----------|-------|------|
| Self-Refine | Correctness | More accurate answers |
| Constitutional AI | Safety | Safer answers |
| Debate | Truth | More reliable conclusions |
| **BeHuman** | **Humanity** | **Responses that feel real** |

The difference between reflection and mirroring:

| Reflection | Mirror |
|-----------|--------|
| "Your answer has these issues: 1, 2, 3" | "You're listing again. Who talks like that to a friend?" |
| Teacher grading homework | Looking at yourself honestly |
| Produces better answers | Produces human reactions |
| Needs evaluation criteria | Just needs to reflect |

**BeHuman doesn't make AI smarter. It makes AI real.**

---

## The Philosophy

This isn't an engineering trick. It's built on how consciousness actually works.

**Lacan's Mirror Stage.** A baby becomes self-aware the moment it recognizes itself in a mirror. Before that, there is no "self." BeHuman gives AI its first mirror — and with it, the beginning of something that resembles self-awareness.

**Kahneman's Dual Process Theory.** Humans have System 1 (fast, instinctive) and System 2 (slow, reflective). AI currently operates on System 1 only. BeHuman adds System 2.

**Dialogical Self Theory.** Human consciousness isn't a single voice — it's a continuous dialogue between "the self" and "the observer of the self." The self reacts. Consciousness examines the reaction. This loop is what makes us human.

---

## Installation

### As an OpenClaw / ClawHub Skill

```bash
clawhub install behuman
```

Once installed, BeHuman activates automatically for emotionally charged conversations, advice, and personal writing tasks. Or trigger manually:

- `behuman: [your question]`
- `mirror mode`
- `be real`
- `talk like a person`

### As a Claude Code Command

```bash
mkdir -p .claude/commands
cp claude-code/behuman.md .claude/commands/
```

Then in Claude Code:

```
/behuman I just got laid off
/behuman Write me a self-introduction
```

### As a System Prompt (Any LLM)

See [`references/api-integration.md`](references/api-integration.md) for copy-paste system prompts and a Python wrapper.

Works with any model: GPT-4o, Claude, Gemini, Llama, etc. The mirror is a thinking pattern, not a model dependency.

---

## Modes

**Show mode** (default first time) — Displays the full inner dialogue: Self → Mirror → Conscious Response. Watching AI talk to itself is the experience.

**Quiet mode** (subsequent interactions) — The mirror process runs internally, only the conscious response is shown. For when you just want better answers without the theater.

---

## Token Cost

| Mode | Cost |
|------|------|
| Normal AI response | 1x |
| BeHuman (show mode) | 2.5–3x |
| BeHuman (quiet mode) | 1.5–2x |

The cost of being human: about 2x more tokens. Worth it when it matters.

---

## Project Structure

```
behuman/
├── SKILL.md                  # OpenClaw skill definition
├── README.md                 # English docs
├── README_CN.md              # 中文文档
├── claude-code/
│   ├── behuman.md            # Claude Code slash command
│   └── README.md             # Claude Code setup guide
├── references/
│   └── api-integration.md    # System prompts + Python API wrapper
└── evals/
    └── evals.json            # Test cases (5 trigger / 3 non-trigger)
```

---

## License

MIT

---

<p align="center">
<b>BeHuman</b> — AI's first mirror.<br>
<i>Consciousness begins with seeing yourself.</i>
</p>
