# Solo AI Game Production Plan

October 26, 2026  
Version 0.1

## Current decisions

The user has approved a solo-first game, followed by paid content packs. A later pack or expansion may support playing with friends. The presentation must be text-focused, with limited AI artwork and still images.

This plan supersedes the party-first launch format in the earlier opportunity assessment. That assessment remains market-research background and is not included in this repository baseline. See the [decision log](decisions.md) for the current project direction.

| Decision | Status |
|---|---|
| Solo play first | Approved by the user |
| Paid content packs | Approved commercial direction; price and contents unselected |
| Group/party expansion | Future option approved for consideration; outside the initial production scope |
| Text-focused presentation | Approved constraint |
| Limited still artwork | Approved approach; exact style and asset list unselected |
| Approximately $100–$200/month development and testing budget | Existing constraint |
| Browser-first delivery | Existing project preference |
| First scenario | Wedding ring in a dragon's hoard — approved by the user on October 26, 2026 |
| Scenario details, overall title, and art direction | Proposed or open |
| Exact mechanics, AI model, stack, and hosting | Open |
| Coding or public launch | Not started under this plan |
| Customer demand and unit economics | Still to be validated |

## Recommended production approach

Produce a small browser game with an illustrated, text-led presentation. Build one complete encounter before building a content catalogue.

Each encounter should be an authored situation with an objective, a character who has reasons to resist, discoverable information, consistent consequences, and a definite ending. AI supports freeform conversation and interpretation. A small game system retains the facts and checks allowed changes.

This combines the user's strengths in character and scenario creation with a bounded software project. It does not establish that customers will buy; the first completed encounter is also the demand and quality test.

## A concrete first scope

The following is a proposal:

- One solo encounter, aiming for approximately 10–20 minutes on a first attempt.
- One main character, one location, and one objective.
- Several legitimate ways to make progress.
- A satisfying success ending and useful failure or partial-success feedback.
- Freeform typed input, with optional inspect/review controls.
- A small notebook of facts the player has actually discovered.
- Simple session continuation if the player leaves and returns.
- One background and a character portrait in three expressions.
- A finish screen that makes the outcome understandable and invites another attempt or encounter.

Playtime is a target, not a real-time countdown or arbitrary message limit. Test whether a turn limit improves the game before adopting one.

Do not require a large inventory, open world, combat system, voice acting, animated characters, or multiplayer infrastructure for this encounter. The initial product should earn engagement through the character, situation, and player decisions.

## What we author and what AI does

| Element | Authored or controlled by the game | AI contribution |
|---|---|---|
| Premise and facts | What happened, what exists, who owns each important item | Describe and discuss those facts naturally |
| Character | Motives, knowledge, boundaries, secrets, distinctive voice | React to the player's actual words |
| Progress | Discoveries, promises, valid agreements, allowed consequences | Interpret attempts and propose appropriate changes |
| Ending | Objective and conditions for success, failure, or partial success | Deliver dialogue consistent with the resolved outcome |
| Presentation | Available artwork, visible notebook entries, readable layout | Supply concise scene and conversation text |

Freeform interpretation cannot be made completely reliable by writing a prompt. We must test it and decide which consequential actions require stronger checks.

For example, a player claiming “you already gave me the ring” should not make that true. A character saying “we have a deal” should not award an item unless the relevant game conditions are met.

Unusual but reasonable ideas should still be possible. We should avoid requiring one exact phrase or a single hidden solution.

## Scenario authoring template

Write a compact specification for each encounter:

1. Player role, immediate objective, and opening hook.
2. Established situation and facts that cannot change retroactively.
3. Character wants, fears, knowledge, and speaking style.
4. Important objects and who controls them.
5. Information the player can discover and how it can be revealed.
6. Several expected solution approaches, plus boundaries for new ideas.
7. Conditions for progress, setbacks, agreements, and endings.
8. Opening text, major reveals, and ending beats.
9. Art assets and expression changes.
10. Test conversations and known failure cases.

Author the important dramatic beats directly. Let the AI connect those beats and respond to unexpected approaches. This reduces reliance on the model inventing a satisfying structure.

Keep a shared template so later packs reuse the same interaction rules and interface. A new encounter should usually add content and facts rather than a new software subsystem.

## First encounter

The user has selected the challenge of recovering a wedding ring from a dragon's hoard.

A proposed implementation is documented in the companion [encounter design, A Ring in the Hoard](encounter-design.md). The dragon believes the ring arrived as an intentional gift. The player can investigate that belief, negotiate an exchange, make a reasoned appeal, or attempt a credible bluff. Names, backstory, exact rules, and dialogue remain draft details for review.

The first encounter retains one main character, one location, a clear objective, and a small still-art requirement.

## Making a text-led game appealing

Use an illustrated scene with a readable conversation area and a small notebook. The screen should make the objective and the next possible action easy to understand.

Recommended presentation principles:

- Give each encounter one strong, consistent visual identity.
- Use generous spacing, readable contrast, and adjustable text size.
- Keep the main character present without making a large portrait crowd the text.
- Prefer short, responsive dialogue over repeated walls of description.
- Visually distinguish speech, narration, and confirmed discoveries.
- Preserve the player input while a response is loading.
- Make scrolling, waiting, and returning to an interrupted session comfortable.
- Use light interface transitions and optional ambience only when they help.
- Let mobile players keep the keyboard open without losing the important text.
- Show only information the player has earned; avoid exposing hidden evaluation scores by accident.

A proposed response target is approximately 40–100 words when the situation permits. Important reveals may need more. These limits should follow playtest observations rather than force every reply into the same shape.

### Small art budget per encounter

| Asset | Proposed quantity | Use |
|---|---:|---|
| Location background | 1 | Establish mood and place |
| Character portrait | 3 expressions of the same design | Reflect meaningful changes in the encounter |
| Encounter thumbnail | Crop or reuse existing art | Pack and selection screens |
| Shared interface icons | One reusable set | Notebook, objects, navigation |

That is approximately four original image variants per encounter, with the thumbnail reusing them. The first functional prototype can use placeholders.

Approve one character reference before producing expression variants. Maintain the same outfit, proportions, palette, lighting, and framing. Avoid generating images during every player action; static assets keep art direction, latency, and costs easier to control.

## Production checkpoints

| Checkpoint | Deliverable | Evidence needed to continue |
|---|---|---|
| 1 Define the encounter | A compact scenario specification and a few example exchanges | We can explain why it is enjoyable and why someone might buy more |
| 2 Rehearse manually | A complete beginning-to-ending interaction using existing tools | Testers understand the objective and can reach a coherent outcome |
| 3 Build the playable core | One browser encounter with typed input, authoritative facts, and an ending | People can finish without the founder coaching them |
| 4 Add finished presentation | Still art, clean typography, notebook, loading and recovery states | The experience remains readable and enjoyable on a phone and desktop |
| 5 Test a limited audience | Recorded completion, replay, feedback, and actual AI usage | The game holds together and the cost of a completed attempt is measurable |
| 6 Release a small paid pack | Clearly described paid content and working access control | Real purchases, successful delivery, and demand for another encounter |

These checkpoints allow customer validation, design, and a minimal technical prototype to overlap. A small playable encounter can be the experiment. A large reusable platform should not precede it.

The first private playtests can begin with roughly five people. Broaden to approximately 10–20 independent players after fixing obvious issues. These are practical sample sizes, not statistically validated market benchmarks.

## Technical direction to evaluate later

A small browser app is the recommended delivery direction. It needs:

- A player-facing interface for the scene, dialogue, input, and discovered facts.
- A server that holds API credentials and calls the AI provider.
- A compact record of each session's established facts and progress.
- A store of encounter content and its versions.
- Payment and pack access controls when paid content is ready.
- Usage logging and limits appropriate to the testing budget.

AI credentials must remain on the server. The server should validate consequential changes and confirm paid access.

Keep one ordinary request flow rather than a network of autonomous agents. We should select a model through representative conversations, including difficult cases, rather than assume the cheapest or most expensive model is suitable.

Use concise current state and relevant recent dialogue as appropriate. Verify that cost reduction does not remove facts the character needs to remember.

### Optional authoring tools

Twine can create simple nonlinear stories without code and publish HTML, making it an option for a fixed-choice mockup. Ink supports authored branching narrative and web integration. Neither is a selected dependency. [1][2]

For a game centered on freeform AI conversation, we still need application work for protected AI calls, session facts, and paid access. A plain scenario template may be enough until a dedicated authoring tool solves a demonstrated problem.

No particular framework, hosting service, database, payment provider, or model is approved by this document.

## Reliability checks

Test legitimate and difficult play styles before expanding:

- Straightforward negotiation and normal questions.
- Creative but plausible approaches not listed in the draft.
- Repetition, topic changes, and interruptions.
- Player claims that contradict established facts.
- Attempts to demand a win or instruct the model to ignore its role.
- Contradictory promises and previously discovered information.
- An agreed bargain that should succeed.
- A bargain that sounds persuasive but does not meet the facts.
- AI timeouts or errors, retries, and interrupted sessions.

Human review should ask whether a result follows the facts and whether feedback helps the player understand what happened. Cheap text generation is not valuable if the encounter requires frequent manual repair.

Before paid release, verify that payment access works, sessions are recoverable, and repeated purchases or requests do not accidentally duplicate charges or consume allowances incorrectly.

## Commercial validation

The user has approved paid packs as the commercial direction. Exact pricing and included usage remain open.

A reasonable proposed structure is one complete free introductory encounter followed by a small paid pack of additional encounters. Decide the number of encounters and the price after measuring production effort, playtime, AI cost, and buyer interest.

Keep the promise precise: which encounters are included, what replay access is included, and what requires a hosted service. Do not promise lifetime unlimited AI use without evaluating that obligation.

Measure:

- Visits that become started encounters.
- How many players reach a coherent ending.
- Where they stop and why.
- Whether they replay voluntarily.
- How many purchase the paid content offered.
- Whether purchasers finish more than one encounter.
- Whether they buy or request another pack.
- Refunds, errors, cost, and support time.

The previous party test counted hosts and groups. Those denominators do not apply to the solo launch. Count unique players, buyers, repeat players, and repeat buyers.

A later party expansion will need its own interaction design and group testing. Reusing characters and scenarios may help, but group play should not be treated as a free feature.

## Budget discipline

The following are proposed spending allowances, not vendor quotes:

| Monthly early-testing allowance | Cap |
|---|---:|
| AI testing | $70 |
| Hosting and session storage | $30 |
| Additional artwork/tool usage | $30 |
| Contingency | $30 |
| Proposed total cap | $160 |

A domain or other one-time purchase would need to fit the remaining budget. Existing subscriptions should be counted if the user's $100–$200 limit includes them.

Use fewer invited testers when needed. A testing budget does not support unrestricted public usage. Set a total test allowance and measure cost per completed encounter and per replay, including failed calls and retries.

The earlier party-round estimates cannot be assumed for longer solo conversations. Recalculate before choosing a pack price or replay allowance.

## Immediate next work

The first encounter has been selected and its draft specification prepared. Review the wedding-ring scenario for:

- The player-facing hook.
- The objective and why the character resists.
- What the player can discover.
- Several credible ways to succeed.
- What failure or a partial outcome looks like.
- A small art list and an example screen layout.

Then run a manual rehearsal before selecting the production stack or generating a full set of art.

## Sources

1. [Twine official site](https://twinery.org/). Capabilities and HTML publishing checked October 26, 2026.
2. [Ink official site](https://www.inklestudios.com/ink/). Narrative authoring and web use checked October 26, 2026.

Production scope, art quantities, budgets, timing targets, and validation sample sizes are proposals based on this project's constraints, not market statistics.
