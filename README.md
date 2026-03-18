# Brevity Coach
A coaching system for training concise, structured communication. It gives you a question, surfaces the relevant principle and example, takes your answer, scores it across three dimensions, diagnoses the specific failure mode, and tracks your patterns over time. Also includes games for building the underlying content habits — direction, compression, conviction, and analytical depth — that make answers better.

Built for interview prep and presentations. Designed to extend to written comms and stakeholder updates.

Two ways to use it:

- **Claude Code on desktop** — full sessions with scoring, diagnosis, and persistent progress tracking
- **Claude.ai Project on mobile** — lightweight practice on the go, no tracking

Say `practice` to start.

---

## What It Does

**Scores three dimensions** — Shape, Brevity, and Signal. Not an overall vibe. Each dimension maps to a specific failure mode and root cause. Signal has two components that vary by mode: in Interview mode, Lead (a gate — if sentence one doesn't resolve the question, Signal scores 1–2 automatically) and Sequence. In Presentations mode, Arrow (a gate — if there's no single clear thing the audience should remember, Signal scores 1–2) and Opening.

**Diagnoses precisely** — identifies the single highest-impact problem in your answer using exact language: "You listed three actions without sequencing them" not "try to be more concise."

**Shows you the gap** — rewrites your opening section to show what the principle looks like applied to your actual words. The gap between what you wrote and the rewrite is the lesson.

**One fix per session** — the coach identifies the highest-leverage thing to change next. Not a list of everything wrong.

**Tracks patterns over time** — every session writes to `coaching_state.md`. After enough sessions, `progress` tells you which failure modes keep appearing and which dimension to target next.

---

## Quick Start

### Option 1: Clone from GitHub
```
git clone https://github.com/your-username/brevity-coach.git
cd brevity-coach
mv SKILL.md CLAUDE.md
```
Open the folder in Claude Code and say `practice`.

### Option 2: Push an existing local folder to GitHub
If you already have the files locally:

Create a new repo on github.com — no README, no .gitignore, leave it empty.

In your terminal:
```
cd ~/Documents/brevity-coach

# Initialise git and make your first commit
git init
git add .
git commit -m "Initial commit"

# Connect to GitHub and push
git remote add origin https://github.com/your-username/brevity-coach.git
git branch -M main
git push -u origin main
```
Activate the coach:
```
mv SKILL.md CLAUDE.md
```
Open the folder in Claude Code and say `practice`.

> Note: Add a `.gitignore` file containing `coaching_state.md` before your first commit if you don't want your personal session data in the repo.
```
echo "coaching_state.md" > .gitignore
```

Requires any paid Claude plan.

### Option 3: Mobile via Claude.ai Project
For lightweight practice on your phone without tracking:

1. Go to claude.ai → Projects → New Project
2. Paste the contents of `PROJECT_INSTRUCTIONS.md` into the custom instructions field
3. Upload `principles.md`, `question-bank.md`, and `scoring-rubric.md` as project knowledge
4. Open the Claude app on your phone, navigate to the Project, and say `practice`

Sessions won't write to `coaching_state.md` — use Claude Code on desktop for tracked progress. If you want the mobile session to pick up where your desktop left off, paste your current coaching state summary into the chat at the start.

---

## Commands

| Command | What it does |
|---|---|
| `practice` | Runs a full coaching session — question, principle, your answer, score, diagnosis, fix |
| `progress` | Shows score trends, recurring failure modes, and the recommended focus for next session |
| `principles` | Surfaces the full principles reference, or just the relevant principle if called mid-session |
| `help` | Lists commands and recommends the highest-leverage next move based on your coaching state |

---

## How a Session Works

1. The coach reads your `coaching_state.md` to check recent patterns
2. It picks a question or scenario targeting your weakest area — or you choose
3. It shows the question, the correct shape, and the relevant principle with a weak/strong example
4. You answer as you would in the real situation
5. The coach scores your answer across three dimensions and identifies the failure mode
6. It shows a tighter rewrite of your opening
7. You retry or move to a new question
8. The session saves to `coaching_state.md`

---

## Scoring

Every answer is scored 1–10 across three dimensions, mirroring the three layers in `principles.md`:

**Shape** — did you use the right structure for this question or scenario type? STAR for past events, Conclusion → Support for opinions, Three Steps for process questions, Present–Past–Future for openers, Rule of Three or Three Steps for presentations.

**Brevity** — did every sentence earn its place? No padding, no repeated points, no throat-clearing.

**Signal** — two components, assessed in order. In Interview mode: did sentence one resolve the question with a clear noun and verb (Lead gate)? Were elements in the right order (Sequence)? In Presentations mode: is there a single clear arrow — one thing the audience should remember (Arrow gate)? Does the opening land it within the first thirty seconds (Opening)?

---

## Scenario Modes

**Interview** — draws from a bank of questions across five types: Openers, Behavioural, Strengths and self-awareness, Motivation and fit, Process and approach, and Analytical and strategic. Each question has a default shape and a specific coaching focus.

**Presentations** — you bring a topic or real talk you're preparing, or pick from a scenario bank of CS leadership situations: team updates, all-hands talks, and stakeholder presentations. The coach extracts the arrow with you before you draft anything, then scores your outline across the three dimensions.

**Custom** — you describe a scenario or paste a question. The coach identifies the question type, assigns the correct shape, and runs the standard session.

**Games** — written games that build the underlying content habits that make answers better. No questions, no dimension scoring. One observation per session.

- **Headline Only** — five questions, one sentence each. No context, no setup. Trains the Lead gate directly.
- **Compression Drill** — rewrite a full answer at half the word count, then compress to a single sentence. Trains the editing instinct.
- **Pillar Stress Test** — state a position, get asked "why?" two or three times. Finds the real reason underneath the stated one.
- **Freestyle** — respond to a topic in fifty words or fewer, arrow in sentence one. Topics range from professional scenarios to personal and improv prompts. Builds compression as a default and forces the arrow to exist before anything else gets written.

Coming later — Written comms, Stakeholder updates. Use Custom mode in the meantime.

---

## The Principles

The coaching is built on three layers:

**Answer shape** — the structure you pick before you speak or write. Six shapes covering every common question and presentation type, each with a decision rule, discipline constraint, and weak/strong example.

**Compression rules** — eight rules applied after picking the shape. Cut the first sentence if it doesn't contain the answer. Default to short sentences. Cap pillars at three. Steps must be verb-led. End strong — use a summary prompt to close cleanly.

**Signal discipline** — six signals that must appear early in every answer regardless of shape. Sentence one resolves the question. Structure is labelled early. Personal action is visible. One breath per idea. Conclusion before proof. Stay in character — don't leak insecurities the listener hadn't noticed.

Run `principles` at any time to see the full reference.

---

## File Structure

```
brevity-coach/
├── SKILL.md                  ← rename to CLAUDE.md to activate (Claude Code)
├── PROJECT_INSTRUCTIONS.md   ← paste into Claude.ai Project custom instructions (mobile)
├── README.md                 ← this file
├── coaching_state.md         ← created on first session, auto-updated
└── principles.md             ← the three-layer framework with examples
└── question-bank.md          ← interview questions, presentation scenarios, games, warm-up drills
└── scoring-rubric.md         ← dimension anchors, root causes, diagnosis protocol
```

---

## Best Results

**Answer in one sitting without editing.** First drafts show your real habits. Polished answers show what you can do when you have time — not what happens under pressure.

**Pay attention to the rewrite, not just the score.** The score tells you what went wrong. The rewrite shows you what right looks like with your words.

**Retry the same question when you score below 6.** One attempt isn't enough to retrain a pattern. Retry immediately while the feedback is fresh, then move on.

**Run `progress` weekly.** Individual session scores are noisy. Trends across sessions show you what's actually improving and what isn't.

**Use Custom mode before real interviews or presentations.** Paste the job description, describe the audience, or share the brief. The coach will generate questions or scenarios specific to that context.

**Play games when scores plateau.** If Signal or Brevity scores are stuck across several sessions, the issue is likely a thinking habit, not a structure problem. Switch to Games mode — Freestyle and Headline Only often unlock things that question practice alone doesn't.

---

## License
Personal use only.
