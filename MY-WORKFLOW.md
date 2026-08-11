# My Workflow

Personal notes for working through this course. Not part of the original repo.

## Setup facts

| Thing | Value |
|---|---|
| Repo | `~/AI Engineering From Scratch/ai-engineering-from-scratch` |
| Branch | `my-progress` |
| `origin` | my fork — I push here |
| `upstream` | `rohitg00/ai-engineering-from-scratch` — I pull updates from here |
| Python | 3.12 in `.venv` (repo root) |

## Start of day

```bash
cd "$HOME/AI Engineering From Scratch/ai-engineering-from-scratch"
source .venv/bin/activate          # prompt shows (.venv)
git checkout my-progress
git status
```

Or just run `aischool` (shell function in `~/.zshrc`).

**If `python: command not found` → the venv isn't activated.** macOS has no bare
`python`, only `python3`. Activating the venv is what makes plain `python` work.

## Per lesson

Commit each lesson as I finish it, not once a day:

```bash
git status                                    # always look before adding
git add phases/<phase>/<lesson>/              # add the path, not `.`
git commit -m "Complete lesson 03: GPU setup"
```

Risky experiment inside a lesson:

```bash
git checkout -b experiment/whatever
# ... try it ...
git checkout my-progress                      # abandon
# or: git merge experiment/whatever           # keep
```

## End of day

```bash
git push
```

Bare `push` works — `-u` on the first push set the upstream.

## Weekly — pull new lessons from upstream

Do this **before** starting a lesson, never mid-lesson with uncommitted changes.

```bash
git fetch upstream
git checkout main
git merge upstream/main
git checkout my-progress
git merge main
```

## Rules that matter

- **Never commit model weights** — `.pt`, `.pth`, `.safetensors`, `.ckpt`. Git keeps
  every version forever; GitHub rejects files over 100MB. Commit the code that
  produces the model, not the model.
- **Never commit `.venv`** (278MB) or datasets. Already in `.gitignore`.
- **`git status` before `git add`.** Catches the above before it's permanent.

## Verify the environment

```bash
python phases/00-setup-and-tooling/01-dev-environment/code/verify.py
```

Expect 7/7 core. The two GPU failures are expected on Apple Silicon — CUDA is
NVIDIA-only. When a lesson needs torch: `uv pip install torch torchvision
torchaudio` (no CUDA index URL on a Mac; it uses Metal/MPS).

## Progress

- [x] 00/01 — Dev environment (7/7 verified)
- [ ] 00/02 — Git & collaboration
- [ ] 00/03 — GPU setup and cloud
