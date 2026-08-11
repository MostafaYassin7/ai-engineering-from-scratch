# My Learning Plan — Deep Core

Personal path through this course. Not part of the original repo.

## Profile

| | |
|---|---|
| **Target role** | AI/LLM Application Engineer — building products on top of models |
| **Background** | Mid-level backend developer. HTTP, APIs, secrets, git, cloud, infra. No ML. |
| **Placement quiz** | 1/10 — starting from zero on ML knowledge |
| **Depth choice** | Understand what's inside the box, properly |
| **Time** | 10–15 hrs/week |
| **Timeline** | ~6 months. Not urgent — optimizing for being genuinely good, not fast. |

**Scope:** ~290 hours of the course's 1,050. What's cut is cut because it's a
different job (vision, audio, robotics), not because it's hard. Reasons at the bottom.

**The bet:** foundations first, then application. Slower to the first shipped
thing, but you'll understand every layer under what you build. That understanding
is what separates an engineer who can wire up an API from one who can debug it
when it behaves strangely — and it's what interviews probe for.

---

# Part 1 — Foundations (~55 hrs, months 1–2)

The part the fast plan skipped. This is the differentiator.

**Math runs as a side track, not a wall.** Only the 8 core lessons are front-loaded
(Block 1). The remaining 14 are attached to the block where they're actually used —
about 2 hours a week alongside the main work. Same total hours, but you start
seeing results in week one instead of week three. Look for the 📐 markers.

## Block 0 — Finish Phase 0 (~4 hrs)

- [ ] 04 APIs & Keys — **skim.** `.env`, HTTP, secrets already known. Read only:
      `max_tokens` required, `messages` is stateless (you resend history every call),
      tokens are the billing unit, rate limits cap tokens/min not just requests
- [ ] 05 Jupyter Notebooks — **do**
- [ ] 09 Data Management — **do**
- [ ] 12 Debugging & Profiling — **do**
- [ ] Skip 06, 07, 08, 10, 11 — Python envs, Docker, editor, terminal, Linux

## Block 1 — Core math only (~8 hrs, 8 of 22 lessons)

You didn't know what a dot product was. Everything in this field is built from
about six mathematical ideas — these eight lessons are all six. Nothing else in
Phase 1 blocks you, so nothing else goes here.

- [ ] 01 Linear Algebra Intuition (~45 min)
- [ ] 02 Vectors, Matrices & Operations (~75 min) — *the dot product; the single
      operation every model is made of*
- [ ] 04 Calculus for ML — Derivatives & Gradients (~45 min)
- [ ] 05 Chain Rule & Automatic Differentiation (~75 min) — *this is literally
      backpropagation; Phase 3 will feel obvious after it*
- [ ] 06 Probability & Distributions (~45 min)
- [ ] 07 Bayes' Theorem & Statistical Thinking (~75 min)
- [ ] 08 Optimization — Gradient Descent Family (~75 min) — *the training algorithm*
- [ ] 09 Information Theory — Entropy, KL Divergence (~45 min) — *cross-entropy
      loss shows up in every phase after this*

Two weeks at most, then you're into real ML. The other 14 lessons are attached to
the blocks below, where you'll have a reason to care about them.

## Block 2 — Phase 2: ML Fundamentals (~21 hrs + 4 hrs math, all 18 lessons)

**📐 Math side track (~4 hrs)** — do these alongside, each right before the
lesson that needs it:

- [ ] Phase 1 / 15 Statistics for ML (~45 min) — *before Phase 2 / 09 evaluation*
- [ ] Phase 1 / 14 Norms & Distances (~45 min) — *before Phase 2 / 06 KNN*
- [ ] Phase 1 / 10 Dimensionality Reduction — PCA, t-SNE, UMAP (~75 min) —
      *before Phase 2 / 07 unsupervised learning*
- [ ] Phase 1 / 16 Sampling Methods (~75 min) — *before Phase 2 / 17 imbalanced data*


Classical ML. You are not going to train random forests at work, but this phase
teaches you how to *think about models* — and half the vocabulary of the field
comes from here.

Non-negotiable lessons: **09** (evaluation metrics — you missed the 90/10 accuracy
question), **10** (bias/variance), **17** (imbalanced data). These are the ones
that make you good at judging whether an AI system actually works, which is the
core skill of an AI engineer and the thing most newcomers cannot do.

## Block 3 — Phase 3: Deep Learning Core (~15 hrs + 3 hrs math, all 13 lessons)

**📐 Math side track (~3 hrs)**

- [ ] Phase 1 / 12 Tensor Operations (~75 min) — *before Phase 3 / 11 PyTorch*
- [ ] Phase 1 / 13 Numerical Stability (~45 min) — *explains exploding/vanishing
      gradients and why float precision bites; pairs with Phase 3 / 08*
- [ ] Phase 1 / 18 Convex Optimization (~75 min) — *pairs with Phase 3 / 06 optimizers*

How neural networks actually work.

**🚢 Lesson 10 — "Build Your Own Mini Framework" is a portfolio piece.** A
working autograd engine you wrote yourself. Push it as its own repo with a
README explaining the design. Very few applicants have one.

Lessons 11 (PyTorch) and 13 (Debugging Neural Networks) are the practical payoff.

---

# Part 2 — Language & Models (~61 hrs, months 3–4)

## Block 4 — Phase 5: NLP (~23 hrs + 2.5 hrs math, 22 of 29 lessons)

**📐 Math side track (~2.5 hrs)**

- [ ] Phase 1 / 11 Singular Value Decomposition (~75 min) — *the math under
      latent semantic analysis and embedding compression*
- [ ] Phase 1 / 17 Linear Systems (~75 min)


How computers process language, from the 1990s to now. The historical lessons
matter more than they look — they show you *why* transformers won, which is how
you develop taste about architecture.

Skip: 07 (POS tagging), 11 (machine translation), 15 (topic modeling),
18 (multilingual), 24 (coreference), 25 (entity linking), 29 (dialogue state).
Specialized subfields you can return to.

Most important for what comes later: **01, 19** (tokenization), **03, 22**
(embeddings), **10** (attention — the hinge point of the whole field),
**23** (chunking for RAG), **27, 28** (LLM evaluation).

## Block 5 — Phase 7: Transformers Deep Dive (~14 hrs + 1.25 hrs math, all 16 lessons)

**📐 Math side track (~1.25 hrs)** — the last required one. After this, Phase 1
is done except the optional lessons.

- [ ] Phase 1 / 03 Matrix Transformations & Eigenvalues (~75 min) — *do it before
      Phase 7 / 02 self-attention; attention is a learned transformation and this
      makes that sentence mean something*

The architecture behind every model you will ever use. Do all of it.

**🚢 Lesson 14 — "Build a Transformer from Scratch" is a portfolio piece.**

Lesson **12** (KV cache, Flash Attention) is the one that pays rent daily — it
explains why the first token is slow, why long contexts cost more, and what every
inference-optimization conversation is actually about.

## Block 6 — Phase 10: LLMs from Scratch (~20 hrs, 16 of 24 lessons)

Now affordable, because Blocks 1–5 gave you the prerequisites. The fast plan cut
this phase entirely; here it's one of the most valuable things you'll do.

Do: **01–15** and **20** (DeepSeek-V3 walkthrough).

**🚢 Lesson 04 — "Pre-Training a Mini GPT (124M)" is a portfolio piece,** and
the single most credible thing on this list. You will have trained a language
model. Most people applying for AI engineering jobs have not.

Lessons **11–12** (quantization, inference optimization) are directly applicable
to production work later.

Skip the frontier-research lessons: 16–19, 21, 22, 25, 34 (differential attention,
sparse attention, MTP, DualPipe, Jamba, async inference, gradient checkpointing).
Fascinating, not load-bearing for you.

---

# Part 3 — Building (~72 hrs + shipping, months 4–5)

Where the foundations turn into products. From here on, every block ships something.

## Block 7 — Phase 11: LLM Engineering (~17 hrs, all 15 lessons)

**The spine.** Densest, most job-relevant phase in the course. No trimming.

Prompt engineering, CoT, structured outputs, embeddings, context engineering, RAG,
advanced RAG, LoRA, function calling, evaluation, caching and cost, guardrails,
a production app, MCP, prompt caching.

## Block 8 — 🚢 Portfolio: RAG system (~9 hrs)

Phase 19, lessons 64–69. Six ~90-min tasks that compose into a working system.
Do immediately after Block 7 while it's fresh.

- [ ] 64 Chunking Strategies, Compared
- [ ] 65 Hybrid Retrieval — BM25 + Dense Embeddings
- [ ] 66 Cross-Encoder Reranker
- [ ] 67 Query Rewriting — HyDE, Multi-Query, Decomposition
- [ ] 68 RAG Evaluation — Precision, Recall, MRR, nDCG, Faithfulness
- [ ] 69 End-to-End RAG System

RAG is the most commonly asked-about system in AI engineering interviews.

## Block 9 — Phase 13: Tools & Protocols (~24.5 hrs, all 23 lessons)

How models connect to real systems. Do it fully — it's the most underrated phase
in the course, and 18 of its lessons are MCP depth you won't find elsewhere.

*Your OAuth and API design background makes lessons 15–16 (MCP security) unusually
easy. Most people learning MCP have never implemented auth. Lean on that.*

## Block 10 — 🚢 Portfolio: Agent harness (~15 hrs)

Phase 19, lessons 20–29. Ten tasks composing into a working agent runtime — the
kind of thing Claude Code itself is.

- [ ] 20 Loop Contract · 21 Tool Registry · 22 JSON-RPC over Stdio
- [ ] 23 Function Call Dispatcher · 24 Plan-Execute Control Flow
- [ ] 25 Verification Gates · 26 Sandbox Runner · 27 Eval Harness
- [ ] 28 OTel Observability · 29 End-to-End Coding Agent

Strongest systems-thinking piece in the plan.

## Block 11 — Phase 14: Agent Engineering (~31 hrs, lessons 01–30)

Agent loops, planning, memory, orchestration, failure modes.

Most important: **26** (why agents break), **27** (prompt injection),
**30** (eval-driven development). Anyone can make an agent work once; the job is
knowing why it fails and proving it doesn't.

Skip 31–42 (the agent-workbench series) unless you want that specialization.

## Block 12 — 🚢 Portfolio: Eval harness (~9 hrs)

Phase 19, lessons 70–75. The least glamorous, most differentiating project —
almost nobody entering this field can demonstrate they know how to *measure*
whether an AI system works.

---

# Part 4 — Production & Ship (~34 hrs + flagship, month 6)

## Block 13 — Phase 17: Infrastructure & Production (~24 hrs, 22 of 28 lessons)

Where your backend background compounds. You already understand canaries,
gateways, and P99s — you're learning the AI-specific variants.

Do: 01–04, 06, 08–11, 13–16, 19–28.
Skip: 05, 07, 12, 17, 18 (EAGLE-3 internals, TensorRT on Blackwell, edge
inference, disaggregated prefill, LMCache) — deep serving internals you'd only
need if you owned the inference platform.

## Block 14 — Phase 18: Ethics, Safety & Alignment (~10 hrs, selected)

Not optional if you're shipping products people use.

- [ ] 02 Reward Hacking & Goodhart's Law
- [ ] 12 Red-Teaming — PAIR & Automated Attacks
- [ ] 13 Many-Shot Jailbreaking
- [ ] 15 Indirect Prompt Injection
- [ ] 16 Red-Team Tooling — Garak, Llama Guard, PyRIT
- [ ] 20 Bias & Representational Harm
- [ ] 24 Regulatory Frameworks — EU, US, UK, Korea
- [ ] 25 EchoLeak & CVEs for AI
- [ ] 26 Model, System & Dataset Cards
- [ ] 29 Moderation Systems

## Block 15 — 🚢 Flagship capstone (~30 hrs)

One large project. **Decide which at Block 9**, not now — by then you'll know what
you actually enjoy. Leading candidates from Phase 19:

| # | Project | Why it might fit |
|---|---|---|
| 06 | DevOps Troubleshooting Agent for Kubernetes | Plays directly to your infra background. Differentiated — few people build this. |
| 16 | GitHub Issue-to-PR Autonomous Agent | Most universally impressive. Easy to demo live. |
| 02 | RAG over Codebase | Backend-flavored, extends your Block 8 work. |
| 08 | Production RAG Chatbot (Regulated Vertical) | Compliance angle; strong for enterprise roles. |

Build the course version, then **extend it with your own ideas**. Structure plus
something personal — better than either alone.

---

## Portfolio summary

Six public repos by the end, three of them free from the foundations work:

| From | Artifact |
|---|---|
| Block 3 | Mini deep-learning framework (autograd from scratch) |
| Block 5 | Transformer from scratch |
| Block 6 | Pre-trained mini GPT (124M) |
| Block 8 | End-to-end RAG system |
| Block 10 | Agent harness / runtime |
| Block 12 | Eval harness |
| Block 15 | Flagship capstone |

### How to ship one — do this every time a 🚢 block finishes

**Each portfolio piece gets its own repo.** Not a folder in this fork.

Why: if the link you send is `github.com/MostafaYassin7/ai-engineering-from-scratch`,
an interviewer lands on a fork of someone else's 503-lesson course with your work
buried at `phases/19-capstone-projects/64-.../`, and the commit history is mostly
the author's. It reads as coursework. If the link is
`github.com/MostafaYassin7/rag-search-engine`, they land on a project with its own
README and its own history. Same code, completely different impression.

The steps, ~30 minutes per project:

1. Do the lesson work here in the fork — that's where the instructions live and
   where progress is tracked.
2. `gh repo create <project-name> --public --clone` (or create it on github.com)
3. Copy the finished code across. Restructure it as a real project: `src/`,
   `tests/`, `requirements.txt` — not numbered lesson folders.
4. Write a README that answers: what it does, why it exists, how to run it, what
   you learned building it. **This is the part interviewers actually read.**
5. Notebooks in these repos: **keep the outputs committed** (unlike this repo,
   where nbstripout strips them). GitHub renders plots and tables inline, and a
   notebook showing no results is a weak portfolio piece.
6. Extend it with something of your own — a feature the lesson didn't ask for.
   That's what turns a followed tutorial into your project.
7. Link it from the Portfolio summary table above.

---

## Timeline

| Part | Blocks | Hours |
|---|---|---|
| 1 — Foundations | 0–3 | 55 |
| 2 — Language & Models | 4–6 | 61 |
| 3 — Building | 7–12 | 105.5 |
| 4 — Production & Ship | 13–15 | 64 |
| **Total** | | **~286** |

Phase 1 math is 22.75 of those hours: 8 up front in Block 1, then 10.75 spread
across Blocks 2–5 at roughly 2 hrs/week. Four lessons (19 complex numbers,
20 Fourier, 21 graph theory, 22 stochastic processes — 3.5 hrs) are optional and
sit in the parking lot.

At **12 hrs/week ≈ 24 weeks ≈ 5.5 months.** At 15 → ~4.5 months.

Slack is built in on purpose. Estimates slip, life happens, and a plan with no
slack is a plan you abandon.

---

## Cut, and why

| Phase | Hours | Why |
|---|---|---|
| 4 Computer Vision | 27 | Different job. Revisit if you want multimodal work. |
| 6 Speech & Audio | 18 | Different job. |
| 8 Generative AI | 14 | Image/video generation. Read lesson 01 for taxonomy if curious. |
| 9 Reinforcement Learning | 13 | Only needed to train models with RLHF. Phase 10/07 covers what you need. |
| 12 Multimodal AI | 65 | Real specialization. Strong candidate for "what's next" after this plan. |
| 15, 16 Autonomous / Swarms | 48 | Come after single agents are second nature. |
| 19 big capstones (except one) | ~500 | One finished flagship beats three abandoned ones. |

Nothing here is cut for being too hard. It's cut for being a different career.

---

## Rules

1. **Commit per lesson, push daily.** See `MY-WORKFLOW.md`.
2. **Ship each 🚢 block publicly before starting the next block.** Unshipped work
   doesn't count.
3. **The foundations are the point.** Block 1 is the only stretch with no visible
   payoff, and it's capped at two weeks by design. Push through it — skipping the
   foundations is exactly what makes most self-taught AI engineers replaceable.
4. **Don't let the 📐 side track slip.** Two hours a week is easy to skip and the
   debt compounds silently — you won't notice until Phase 7 stops making sense.
   Do each math lesson *before* the lesson it's attached to, not after.
4. **Re-evaluate at Block 9.** By then you'll have trained a model and built a
   RAG system. If it turns out you prefer making things fast and reliable over
   building features, expand Block 13 into all of Phase 17 and trim Block 11 —
   that's the MLOps path, and it's a shorter hop from your background.
5. **Don't add phases back mid-plan.** If something looks interesting, note it at
   the bottom of this file and decide at a re-evaluation point.

## Parking lot

Things to consider after this plan:

- Phase 1 / 19–22 — complex numbers, Fourier transform, graph theory, stochastic
  processes (3.5h). Optional for this path. Fourier matters if you ever touch
  audio; graph theory if you go toward knowledge graphs or GNNs.
- Phase 12 Multimodal (65h) — document AI and vision-native RAG are growing fast
- Phase 16 Multi-Agent (28h) — if agents become your specialty
- Phase 14 lessons 31–42 — the agent workbench series
