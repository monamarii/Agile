# Desktop Pixel Pets — Agile Product Backlog

## Product Vision
A lightweight desktop app that turns real-life task completion into visible progress: users earn coins for finishing tasks, spend coins to claim collectible pixel-art animals, and choose up to 5–6 of their collection to roam their desktop at any time. Built for people (especially neurodivergent users) who benefit from concrete, low-pressure, visual motivation rather than guilt-based to-do lists.

## Target User / Persona
- **Primary:** A student or knowledge worker who struggles to stay motivated with plain to-do lists and responds well to small, immediate visual rewards.
- **Needs:** low setup friction, non-intrusive rewards (doesn't block their actual desktop work), a sense of collection/progress over time.

## Tech Stack Decision
| Criteria | Electron (JS/HTML/CSS) | Python + PyQt/PySide |
|---|---|---|
| Transparent, always-on-top, click-through windows | Native support (`transparent`, `alwaysOnTop`, `setIgnoreMouseEvents`) | Native support (`WA_TranslucentBackground`, frameless `QWidget`) |
| Team familiarity | Best if team already knows JS/web | Best if course/team leans Python |
| Sprite animation | Easy via CSS sprite sheets | Easy via `QMovie`/`QPixmap` frame swapping |
| Packaging for grading demo | `electron-builder` | `PyInstaller` |
| Recommendation | **Default pick** — most forgiving for a first desktop-overlay project | Solid alternative if team is Python-first |

**Decision:** Confirm as a team in Sprint 0 / planning session — do not split the team across two stacks.

## Definition of Done (team-wide, adjust as needed)
- Code reviewed by at least one other team member
- Manually tested on at least one team member's machine
- No console errors during normal use
- Merged to main branch with a passing build

---

## Epics & User Stories

### Epic 1: Task & Coin System
| ID | Story | Points | Acceptance Criteria |
|---|---|---|---|
| T1 | As a user, I can create a task with a name and optional recurrence (daily/one-off) | 3 | Task persists after app restart; recurring tasks reset at midnight |
| T2 | As a user, I can mark a task complete | 2 | Completed tasks are visually distinct; can't double-claim coins from one completion |
| T3 | As a user, I earn coins when I complete a task | 3 | Coin balance updates immediately and persists |
| T4 | As a user, I can see my current coin balance and streak | 2 | Balance/streak visible on main screen at all times |

### Epic 2: Animal Claiming & Collection
| ID | Story | Points | Acceptance Criteria |
|---|---|---|---|
| A1 | As a user, I can view a gallery of claimable animals with their coin cost | 3 | Locked vs. claimed animals are visually distinguished |
| A2 | As a user, I can spend coins to claim a new animal | 3 | Coins deduct correctly; claimed animal added to collection; can't claim without enough coins |
| A3 | As a user, I can see my full collection in a gallery view | 2 | Gallery lists all claimed animals regardless of active/inactive status |

### Epic 3: Desktop Roaming (core technical risk — front-load this)
| ID | Story | Points | Acceptance Criteria |
|---|---|---|---|
| D1 (spike) | Prove one transparent, click-through, always-on-top window can render and move on screen | 5 | One static sprite visibly floats above other apps without blocking clicks |
| D2 | As a user, an active animal wanders the screen with idle/walk animation | 5 | Animal cycles idle → walk → idle, stays within screen bounds |
| D3 | As a user, multiple active animals can roam simultaneously without performance issues | 5 | 5–6 animals on screen at once with no visible lag |

### Epic 4: Active Display Management
| ID | Story | Points | Acceptance Criteria |
|---|---|---|---|
| M1 | As a user, if I have more animals than the display cap (5–6), I can choose which are active | 3 | Toggling "active" in gallery immediately shows/hides that animal on desktop |
| M2 | As a user, I can't activate more than the cap at once | 2 | Attempting to exceed cap shows a clear message or blocks the action |

### Stretch (only if ahead of schedule)
| ID | Story | Points |
|---|---|---|
| S1 | Click/drag interaction with a roaming animal | 3 |
| S2 | Sound effects on claim/interaction | 2 |
| S3 | Rare/seasonal animal drops | 3 |

---

## Sprint Plan (4 sprints)

**Sprint 1 — Foundations**
Goal: Task and coin system fully working, no animals yet.
Stories: T1, T2, T3, T4

**Sprint 2 — De-risk the hard part**
Goal: One animal proven to work as a transparent, roaming desktop overlay.
Stories: D1 (spike), D2, A1 (gallery UI can be built in parallel while D1/D2 are in progress)

**Sprint 3 — Collection loop**
Goal: Full claim → collect → display flow works end to end.
Stories: A2, A3, M1, M2

**Sprint 4 — Scale & polish**
Goal: Multiple animals roaming together, bug-fixing, demo polish.
Stories: D3, stretch goals as capacity allows

---

## Key Risks
- **Screen-overlay behavior may differ across OS/Windows versions** — resolve this in Sprint 2's spike (D1) before committing later sprints.
- **Performance with multiple animated windows** — validate early in D3, don't leave it to the final week.
- **Scope creep on art assets** — cap the initial animal roster (e.g., 6–8 species) so art doesn't become the bottleneck.
