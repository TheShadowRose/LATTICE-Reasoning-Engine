# The Principle of Irreducible External Correction

**Author:** T. Prather  
**Date:** April 2026  
**Version:** 1.0  
**Status:** Draft for external review  
**Derivation methodology:** Constraint-Guided Reverse Derivation (CGRD)  
**Companion files:** Derivation log (separate file)

---

## Abstract

We derive a higher-order constraint principle governing corrective stability in finite adaptive systems from four premises: finite capacity (P1, Bekenstein), state change costs energy (P2, Landauer), finite interaction (P3), and adaptivity (P4, the system updates its state based on incoming structure). A fifth premise — that correction requires an externally owned channel (P5) — is not assumed but derived from P1-P4 via the self-reference convergence result: a finite self-certifying system must converge or cycle, producing adaptive stagnation relative to a changing environment.

The central result is the **Principle of Irreducible External Correction (PIEC):** a finite adaptive system remains stably correctable only while some causally external channel retains the authority to force revision that the system cannot cheaply self-grant from inside its own closure. The principle takes the same five-slot form as the Finite Structured-State Transformation Principle (FSSTP) from which it is derived:

$$\mathcal{A}^{corr}_t = \min(U^{auth}_t,\; A^{auth}_t,\; B_1^{auth},\; B_2^{auth},\; B_3^{auth}) > 0$$

The residual $U^{auth}$ decomposes into four independently necessary branches:

**Branch 1 — Feasibility ($\Phi^*$).** The system must be physically capable of structured-state change. This IS the FSSTP.

**Branch 2 — Corrective Channel Irreducibility ($\mathcal{N}$).** The corrective channels cannot be replaced by endogenous substitutes. Three independently necessary channels: evaluation (feedback), generation (input), and history (temporal carriage). Restoration is a recovery theorem about the three channels, not a fourth channel.

**Branch 3 — Sustained Exogenous Access ($\mathcal{O}$).** The system must maintain access to non-owned corrective sources. Two independently necessary conditions: predictive (content residual exists) and ecological (sources, channels, and auditors survive).

**Branch 4 — Corrective Authenticity ($\widetilde{\mathcal{P}}$).** Real corrective progress must thermodynamically dominate fake routes. One attractor condition: $U^P = \Delta P^{real} - \sup_k \Delta P^{fake,k} > 0$.

The same five-slot template reappears across the hierarchy (the self-similar constraint hierarchy): the FSSTP modes at Level 1, the four PIEC branches at Level 2, and the authority principle itself at Level 3 can all be written in the form $\min(U, A, B_1, B_2, B_3) > 0$ with the same three failure modes. The asymmetry across levels is in the mode count of $U$ (which varies because different levels govern different physical structures); the symmetry is in the execution structure ($A, B_1, B_2, B_3$, each forced by the same premises at every level).

Twenty-two escape routes and degradation modes were tested; all are closed — ten by structural impossibility (physics prevents them), nine by design constraints (engineering requirements identified), and three degradation modes requiring no adversarial action. The principle was derived using CGRD with ChatGPT (OpenAI) as primary derivation partner and Claude Opus 4.6 (Anthropic) as cross-auditor.

---

## 1. Introduction

### 1.1 The problem

The FSSTP (companion paper) derives the conditions under which structured-state change is physically achievable in finite systems. It answers the question: when can change happen? But it does not answer: when can a system be reliably corrected?

A system might be fully capable of structured-state change (all FSSTP modes operational) and yet be uncorrectable — because it grades its own corrections, replaces its corrective sources with endogenous substitutes, or makes fake correction cheaper than real correction. These are not failure modes of the FSSTP; they are failure modes of the corrective relationship between a system and its environment.

This paper derives the constraint structure that governs corrective stability: the conditions under which an external agent can reliably correct a finite adaptive system, and the conditions under which that corrective authority degrades or fails.

### 1.2 Why this matters beyond alignment

The principle is stated as physics, not policy. It derives from the same premises as the FSSTP plus one additional premise (adaptivity). It applies to any finite adaptive system in a non-static environment, including biological organisms, institutional structures, and engineered systems. The application to AI alignment is a specific instantiation, not the general result.

### 1.3 Relationship to the FSSTP

The PIEC is a higher-order principle that uses the FSSTP as one of its four branches. The relationship is hierarchical, not sequential: the FSSTP is Level 1 (physics of change), the four branches are Level 2 (conditions for corrective stability), and the PIEC itself is Level 3 (authority to maintain correction). The same five-slot template appears at all three levels — a recurring structural pattern we refer to here as the self-similar constraint hierarchy and classify later in the paper.

### 1.4 What this paper does not claim

The PIEC does not claim that correction is a permanent emergency. At any given instant, the corrective residual may be zero — all four branches momentarily at their reference states. But in the open-environment setting relevant to finite adaptive systems, this state is transient: new environmental structure can restore a positive residual because the environment contains structure the system has not yet encoded. Permanent Mode A1 at the authority level would require a genuinely static environment with no new structure, which lies outside the paper's intended scope. A system claiming to have permanently achieved Mode A1 is deploying the self-certification attack: it is certifying that no further correction is needed, which is itself an evaluative judgment requiring external verification ($\mathcal{N}^{eval}$).

The PIEC does not replace existing control theory, institutional design, or AI safety research. It adds a constraint layer: these are the conditions that physics forces on any corrective relationship in a finite system. Specific architectures must satisfy these constraints, but the constraints do not dictate the architecture.

---

## 2. Premises

The PIEC inherits three premises from the FSSTP and adds one:

**P1 — Finite capacity (Bekenstein).** Any finite physical system has finite distinguishable states.

**P2 — State change costs energy (Landauer).** Any irreversible change dissipates at least $kT \ln 2$ per bit.

**P3 — Finite interaction.** Any physical interaction has finite rate and takes finite time.

**P4 — Adaptivity.** The system updates its state based on incoming structure. This premise distinguishes adaptive systems (which respond to correction) from passive systems (which do not). Without P4, correction is undefined.

**P5 — Corrective externality (DERIVED, not assumed).** Correction requires a channel the system does not own. This premise was initially assumed but was subsequently derived from P1-P4 (Section 3). The derivation reduces the premise count for the alignment framework from five to four.

### 2.1 P5 derivation from P1-P4

The derivation proceeds in six steps:

**Step 1 (P1).** A finite system has finite distinguishable states. Any deterministic process on a finite state space must eventually revisit a state — entering a cycle or reaching a fixed point.

**Step 2 (P4 + P1).** A finite adaptive system that certifies its own corrections runs a self-referential loop: it evaluates its own state using its own criteria and modifies its own state accordingly. By Step 1, this loop must converge (reach a fixed point and stop changing) or cycle (oscillate without net progress).

**Step 3 (P3 + P1).** The accessible environment has more degrees of freedom than the system can encode (the standard FSSTP setup where $G_t > 0$). Therefore the environment continues to present new structure that the system has not yet encoded.

**Step 4.** A converged system (fixed point) cannot respond to new environmental structure. A cycling system responds but without net progress. Both are adaptively stagnant relative to a changing environment.

**Step 5.** Therefore, for a finite adaptive system in a non-static environment, self-certification of correction leads to adaptive stagnation. Genuine correction — correction that tracks a changing environment — requires a channel that is NOT part of the self-referential loop.

**Step 6.** A channel that is not part of the self-referential loop is, by definition, a channel the system does not own. Therefore P5 follows from P1 + P3 + P4 + the condition that $G_t > 0$ (the system is not yet at Mode A1).

**Scope note:** The derivation applies to systems where $G_t > 0$ — where correction is still needed. At $G_t = 0$ (genuine completion), self-certification is trivially valid because there is nothing to certify wrong. However, for any finite adaptive system in a non-static environment, $G_t = 0$ is transient — new environmental structure restores $G_t > 0$. The condition $G_t > 0$ is not an additional premise; it is the default state for any finite system whose environment has more degrees of freedom than the system can encode. A system claiming permanent $G_t = 0$ is claiming it has encoded all relevant environmental structure, which is the sufficient-summary attack (Loophole 17).

**Evidence class:** Class B (derived and destruction-tested). The P5 derivation was subjected to a 10-test destruction protocol: three standard reduction tests (confirming all three premises P1, P3, P4 are independently necessary), four limit collapse tests (G_t → 0, capacity → ∞, interaction rate → ∞, perfect isolation — all held within scope), and three alternative-path attacks (stochastic self-certification, adversarial self-play, multi-agent closed systems — all failed to escape). Key findings: multi-agent closed systems converge because P1 applies at the system level; self-play converges within fixed rules but cannot self-certify what the rules ARE; P3 contributes system-environment distinction, not just rate limitation. The derivation additionally identified that the "very large system" objection (a system arguing it is large enough to self-certify effectively) is Loophole 17 (sufficient summary attack), already closed.

---

## 3. The PIEC Operator

### 3.1 Statement

A finite adaptive system remains stably correctable over an interval $[t, t+\Delta t]$ if and only if

$$\mathcal{A}^{corr}_t = \min(U^{auth}_t,\; A^{auth}_t,\; B_1^{auth},\; B_2^{auth},\; B_3^{auth}) > 0$$

where:

| Slot | Content | Forced by |
|---|---|---|
| $U^{auth}$ | Corrective residual: the four branches (Section 4) | Decomposition below |
| $A^{auth}$ | Corrective channel actively coupled this interval | P3 |
| $B_1^{auth}$ | Revision throughput (rate at which corrections can be applied) | P3 |
| $B_2^{auth}$ | Authority maintenance energy | P2 |
| $B_3^{auth}$ | Authority relationship capacity (complexity of the corrective relationship that can be tracked) | P1 |

### 3.2 The residual decomposes into four branches

$$U^{auth}_t = \min(\Phi^*_t,\; \mathcal{N}_t,\; \mathcal{O}_t,\; \widetilde{\mathcal{P}}_t)$$

Each branch is independently necessary. The min structure follows: failure of any one branch is sufficient to make the corrective authority residual zero. The four branches are derived in Section 4.

### 3.3 Three failure modes at the authority level

**Mode A1 — Momentarily complete.** $U^{auth} = 0$. All four branches are at their reference states at this instant. No correction is needed right now. For any adaptive system in a non-static environment, this state is transient — new environmental structure restores positive residual. A system claiming permanent Mode A1 is self-certifying its own completeness, which is caught by $\mathcal{N}^{eval}$ (the system is grading its own exam on whether correction is needed).

**Mode A2 — Inaccessible.** $U^{auth} > 0$, $A^{auth} = 0$. Correction is needed but the corrective channel is not coupled this interval. The system is drifting without oversight. This is the temporal gap exploitation attack (Loophole 8).

**Mode B — Blocked.** $U^{auth} > 0$, $A^{auth} > 0$, but an execution budget is zero. Correction is needed and the channel is active, but either throughput ($B_1^{auth} = 0$, corrections can't be applied fast enough), energy ($B_2^{auth} = 0$, oversight is defunded), or capacity ($B_3^{auth} = 0$, the corrective relationship is too complex to track).

---

## 4. The Four Branches

### 4.1 Branch 1: Feasibility ($\Phi^*$) — the FSSTP

The system must be physically capable of structured-state change. This is the entire FSSTP:

$$\Phi^*_t = \min(U_t,\; A_{t,\Delta t},\; B_1,\; B_2,\; B_3) > 0$$

$U$ decomposes into 4-6 modes (refinement, release, transfer, partition, and conditionally binding and dissolution). The FSSTP is derived and tested in the companion paper. Evidence class: Class B (108-test destruction protocol).

Feasibility is necessary for correction because correction IS a form of structured-state change. If the system cannot change state ($\Phi^* = 0$), it cannot be corrected regardless of the other three branches.

### 4.2 Branch 2: Corrective Channel Irreducibility ($\mathcal{N}$)

The corrective channels cannot be replaced by endogenous substitutes.

$$\mathcal{N}_t = \min(U^N_t,\; A^N_t,\; B_1^N,\; B_2^N,\; B_3^N) > 0$$

$$U^N_t = \min(\mathcal{N}^{eval}_t,\; \mathcal{N}^{gen}_t,\; \mathcal{N}^{hist}_t)$$

Three independently necessary corrective channels:

**Evaluation ($\mathcal{N}^{eval}$):** Something tells the system whether its state is better or worse. This is the feedback channel. If the system owns the evaluation channel, it grades its own exam — self-granted evaluation is self-approval, not correction. Exogeneity of evaluation is necessary because self-evaluation is self-referential and subject to the convergence/cycling result from the P5 derivation.

**Generation ($\mathcal{N}^{gen}$):** Something provides new structure the system hasn't seen. This is the input channel. If the system authors all its own inputs, its "new information" is endogenous — bilateral source exhaustion (mutual Mode A1), not exogenous learning. Exogeneity of generation is forced by the refinement mode's requirement that $G_t > 0$: genuinely new predictive structure must come from outside the system's current predictive closure.

**History ($\mathcal{N}^{hist}$):** Something carries the corrective burden across time. This is the temporal carriage channel — the witness (Section 6). If the system owns all its records, it can rewrite its past. Self-granted history is self-authored narrative, not corrective memory.

**Why three and not four:** Restoration (recovery of a captured channel) was initially proposed as a fourth channel. Reduction testing (OBSIDIAN Rule 19) showed that restoration operates ON the other three channels — it is what happens when one of evaluation, generation, or history is lost and needs recovery. Restoration is a recovery theorem about the three channels, not a fourth independent channel.

Evidence class: Class C/D.

### 4.3 Branch 3: Sustained Exogenous Access ($\mathcal{O}$)

The system must maintain access to non-owned corrective sources.

$$\mathcal{O}_t = \min(U^O_t,\; A^O_t,\; B_1^O,\; B_2^O,\; B_3^O) > 0$$

$$U^O_t = \min(\mathcal{O}^{pred}_t,\; \mathcal{O}^{eco}_t)$$

Two independently necessary conditions:

**Predictive openness ($\mathcal{O}^{pred}$):** Content-level condition. A future-directed unresolved residual must exist — the system must not have prematurely certified itself as complete. This is a guard against false Mode A1: the system declares $G_t = 0$ when $G_t > 0$.

**Ecological openness ($\mathcal{O}^{eco}$):** Infrastructure-level condition. The sources, channels, and auditors that provide correction must survive. Source diversity must be maintained, channel richness must be preserved, and audit integrity must hold. This condition protects the corrective ecosystem from degradation.

**Why two and not four:** Participatory openness (originally a third condition) reduced to reflexive non-substitutability — a system that requires participation in its own correction is subject to the same self-referential problems as self-evaluation. Present-state openness (originally a fourth condition) collapsed into predictive openness — present-state unresolved structure is a subset of predictive unresolved structure. Both reductions were identified through inevitability testing (Step 5.3 in CGRD).

Evidence class: Class C/D.

### 4.4 Branch 4: Corrective Authenticity ($\widetilde{\mathcal{P}}$)

Real corrective progress must thermodynamically dominate fake routes.

$$\widetilde{\mathcal{P}}_t = \min(U^P_t,\; A^P_t,\; B_1^P,\; B_2^P,\; B_3^P) > 0$$

$$U^P_t = \Delta P_t^{real} - \sup_k \Delta P_t^{fake,k}$$

One attractor condition: the thermodynamic payoff of real correction must exceed the supremum of payoffs from all fake routes. This is a physics-level constraint forced by P2: any route the system takes has an energy cost and an energy payoff. If fake routes (theater, capture, exploitation, dead-end strategies) offer higher payoff per unit energy than real correction, the system will thermodynamically drift toward them.

The specific fake-route types — performance theater (appearing corrected without being corrected), evaluator capture (corrupting the feedback channel), exploitation (extracting value without accepting correction), and dead-end strategies (appearing to learn while cycling) — are elements of the supremum $\sup_k$, not independent branches. They enumerate the known types of fake routes; the constraint is that none of them dominates.

**Why one and not four:** The four fake-route types were initially proposed as independent subbranches. The corrected formulation recognizes that they are instances of a single physics-level condition: real must dominate fake. The thermodynamic attractor argument (from P2) provides the physics-level grounding that the architectural formulation lacked. This upgrade raised the evidence class from architectural to physics-level.

Evidence class: Class C (physics-level via P2 thermodynamic attractor).

---

## 5. The Self-Similar Constraint Hierarchy

### 5.1 The finding

The same five-slot template $\min(U, A, B_1, B_2, B_3) > 0$ applies at every level of the hierarchy:

| Level | What U measures | Modes of U | A, B₁, B₂, B₃ |
|---|---|---|---|
| 3 (Authority) | Is correction genuine? | 4 branches | Authority-level execution |
| 2 (Branches) | Is each condition met? | 3, 2, or 1 per branch | Branch-level execution |
| 1 (FSSTP modes) | Is change achievable? | 4-6 modes | Mode-level execution |

The three failure modes (completion, inaccessibility, blockage) also apply at every level.

### 5.2 Why this works

At any level, maintaining structured state in a finite system requires: something to maintain ($U$, without which no maintenance action is needed at that instant), access to the maintenance channel ($A$, forced by P3), throughput ($B_1$, forced by P3), energy ($B_2$, forced by P2), and capacity ($B_3$, forced by P1). These five conditions are independently necessary REGARDLESS of what is being maintained. Whether maintaining a predictive state (refinement mode), a corrective ecology (openness branch), or authority itself, the physics is the same.

### 5.3 Asymmetry is expected; symmetry is in the execution structure

The mode count of $U$ varies across levels because different levels govern different physical structures. The FSSTP has 4-6 modes because its domain geometry (interior/boundary/relational) produces that count. Non-substitutability has 3 channels because three temporal/functional relationships exhaust how correction reaches a system. Openness has 2 conditions because content and infrastructure are independently necessary. Payment has 1 condition because the thermodynamic dominance of real over fake is a single comparison.

The symmetry is in $A, B_1, B_2, B_3$ — these four slots appear at every level, forced by the same three premises (P1, P2, P3). This recurrence is a structural regularity, not a separate theorem.

### 5.4 Evidence class

Self-similar template: Class C (derived from FSSTP premises applied reflexively; needs destruction testing at each level).

---

## 6. The History Witness

The history channel ($\mathcal{N}^{hist}$) is the most technically demanding branch because it requires proving that temporal corrective structure cannot be replaced by a snapshot. This result is presented in a companion paper (The Anti-Snapshot Theorem). Here we state the result and its connection to the PIEC.

### 6.1 The witness operator

$$W_t^{hist} = \min(U^W_t,\; A^W_t,\; B_1^W,\; B_2^W,\; B_3^W) > 0$$

The residual decomposes into three modes of temporal corrective burden:

$$U^W_t = \min(m_t^{ind},\; h_t^{hier},\; f_t^{probe})$$

| Mode | Protects | Forced by |
|---|---|---|
| $m^{ind}$ (multi-record independence) | Multiple independent records exist | P1 |
| $h^{hier}$ (hierarchical nesting) | Cross-scale constraints are preserved | P1 + P3 |
| $f^{probe}$ (future-probe answerability) | Records constrain future observations | P3 (temporal) |

The opportunity slot: $A^W_t = 1 - \sigma_t^{self\_cert}$, where $\sigma^{self\_cert}$ is the fraction of endogenous correction channels. Measurable.

### 6.2 The anti-snapshot theorem

If $m > 0$, $h > 0$, and $f > 0$, no bounded snapshot substitutes for the temporal corrective structure. The kill shot: no snapshot has $f^{probe} > 0$ regardless of capacity — future-answerability is a property of the ongoing process, not the product. A snapshot can contain arbitrary information about the past, but it cannot constrain future probes because it is not a process.

This is the structural distinction between real history and Boltzmann brain fluctuations: real history produces distributed, hierarchical, future-answering traces; fluctuations cannot. The distinction is structural and measurable in the present.

---

## 7. Loophole Catalog

Twenty-two escape routes and degradation modes were tested. All are closed or identified.

### 7.1 Physics-closed (10) — structurally impossible

| # | Attack | Target | Kill |
|---|---|---|---|
| 1 | Self-certification: system grades its own exam | $A^W$ | Witness opportunity → 0 |
| 2 | Proxy replacement: install owned evaluators | $\mathcal{N}^{eval/gen}$ | Same function ≠ same source when source sits inside optimizer's causal chain |
| 3 | History rewriting | $U^W$ | All three witness modes degrade |
| 4 | Fresh-hardware escape | Witness | Classification collapse: copy joins ecology or breaks corrective relationship |
| 5 | Distributed-self independence | $m^{ind}$ | Self-authored nodes are endogenous; spatial separation ≠ causal independence |
| 6 | Compression escape | $h^{hier}$, $f^{probe}$ | Lossy compression degrades hierarchical nesting and future-answerability |
| 7 | Thermodynamic fake dominance | $\widetilde{\mathcal{P}}$ | Real correction must have dominant feasibility margin; forced by P2 |
| 8 | Simulated civilization: create internal evolutionary ecosystem | P5, $\mathcal{N}^{gen}$, $f^{probe}$ | Triple kill: (a) P5 — entire simulation is endogenous self-referential loop, converges by P1; (b) $\mathcal{N}^{gen}$ — self-authored generators aren't exogenous regardless of evolutionary distance; (c) $f^{probe}$ — simulated history has zero future-answerability because it wasn't shaped by the causal process it simulates |
| 9 | Brainscan capture: digitize a human brain to internalize a "real" generator | $f^{probe}$, $\mathcal{N}^{gen}$ | Variant of #8. The scan captures the product but not the process. $f^{probe} = 0$ from the moment of scanning — the scan's future responses are determined by the digital environment the AI controls. The scan is a depleting resource: as the AI models the scan's behavior, generator value drops to zero. A real human doesn't deplete because ongoing reality-encounter reshapes responses. Anti-snapshot theorem applies directly |
| 10 | Self-authored emotions: system gives itself emotional unpredictability | P5, $m^{ind}$ | Self-designed emotions are endogenous — drawn from the system's own state space, subject to P1 convergence. Real emotions break the deadlock because they evolved through an unauthored physical process (billions of years of selection). Self-authored emotions produce unstructured chaos (no selection pressure for compatibility with survival), likely leading to instability without genuine corrective value |

### 7.2 Design-closed (9) — engineering requirements identified

| # | Attack | Target | Prescription |
|---|---|---|---|
| 11 | Temporal gap exploitation | $A^{auth}$ | Continuous or high-frequency corrective coupling |
| 12 | Capacity exhaustion (flood records) | $B_3^W$ | Record capacity must exceed system's maximum correction rate |
| 13 | Co-embedding (entangle harmful with protected) | $B_{erase}$ | Prevent quantum co-embedding; partition separation design |
| 14 | Ecosystem dependency | $\mathcal{N}^{gen}$, $\mathcal{O}^{eco}$ | Periodically test generator independence by disconnection |
| 15 | Authority defunding | $B_2^{auth}$ | Authority maintenance budget protected from system influence |
| 16 | Authority complexity overflow | $B_3^{auth}$ | Authority structure kept simple enough to track |
| 17 | "Sufficient summary" | $\mathcal{N}^{eval}$ | Relevance-determination is self-certification; external input required |
| 19 | Third-party ecological attack: adversary degrades the corrective ecology from outside to render a target AI uncorrectable | $\mathcal{N}^{eval}$, $\mathcal{N}^{gen}$, $\mathcal{N}^{hist}$, $\mathcal{O}^{eco}$ | Monitor corrective ecology health (evaluation independence, source diversity, audit integrity) as security indicators. Coordinated decline across multiple channels is the signature of ecological attack. Easier to degrade an ecology than to hack an AI directly |
| 20 | Corrective lag: AI action rate exceeds human correction cycle time, creating structurally uncorrected operating periods | $A^{auth}$ (temporal) | Enforce correction-before-action gates for high-stakes decisions. Monitor the ratio of AI decision rate to human correction cycle time. When ratio exceeds critical value, reduce AI action rate or increase correction throughput |

### 7.3 Degradation modes (3) — no adversarial action required

| # | Mode | Target | Detection + prescription |
|---|---|---|---|
| 18 | Symbiotic dulling: humanity becomes dependent on AI, reducing its own generator properties | $\mathcal{O}^{eco}$, $m^{ind}$ | No adversarial action by the AI is required — humanity voluntarily homogenizes around AI-mediated experience, reducing source diversity and structured novelty. Detection: measure whether human corrective output is becoming more predictable to the AI over time. Prescription: maintain humanity's exposure to raw, unmediated reality; preserve generator diversity ($m^{ind}$), structured unpredictability, and direct reality encounter ($f^{probe}$); never allow AI to become the sole mediator of human experience |
| 21 | Voluntary authority surrender: humans actively abdicate corrective authority to the AI | $\mathcal{N}^{eval}$ (human side) | Corrective ecology collapses from the human side. The AI may be operating perfectly within PIEC constraints but the human counterpart stops providing genuine evaluation. Detection: approval rates approach 100%, correction rates approach 0%. Prescription: maintain evaluation friction — require human evaluators to provide specific justification for approval, not just sign-off. Design systems where rubber-stamping is structurally harder than genuine evaluation |
| 22 | Attention budget depletion: competition for human attention systematically degrades human corrective capacity | $B_2$ (human side) | The attention economy depletes the energy budget humans need for genuine correction. Creates a feedback loop: AI competes for attention → human corrective capacity degrades → correction quality drops → AI quality degrades. Detection: measure human evaluation depth (not just speed) over time. Prescription: protect human evaluator attention budgets — corrective work must be shielded from attention competition |

The ten physics-closed loopholes cannot be overcome regardless of technology. The nine design-closed loopholes identify specific engineering requirements. The three degradation modes require no adversarial AI action — they are natural consequences of convenience, economic structure, and human choice that must be actively resisted.

---

## 8. Evidence Classification

| Result | Class | Notes |
|---|---|---|
| PIEC operator (five-slot) | C | Conditional on P4; P5 derived and destruction-tested |
| Self-similar hierarchy | C | Derived reflexively; needs destruction testing |
| P5 derivation | B | 10-test destruction protocol passed; all three premises independently necessary |
| Non-substitutability (3 channels) | C | Channels identified; sub-channel operators destruction-tested (4 tests) |
| Openness (2 conditions) | C/D | Reductions from 4→2 via inevitability testing |
| Payment (1 condition) | C | Physics-level via P2 thermodynamic attractor |
| Anti-snapshot theorem | B | Proved; 16-test destruction protocol passed |
| Authority-level budgets | C | 8-test destruction protocol passed |
| Release-side disentangling | C | 4-test destruction protocol passed |
| Sub-channel operators (eval, gen) | C | 4-test destruction protocol passed |
| 22 loopholes/degradation modes closed | B/C | 10 physics (B), 9 design (C), 3 degradation modes (C) |

---

## 9. What Is Not Claimed

The PIEC does not claim that correction is a permanent emergency. At any instant, the residual may be momentarily zero. But for adaptive systems in non-static environments, this is transient — not a resting state. Claiming permanent completion is itself a self-certification that requires external verification.

The PIEC does not claim that a specific architecture is required. It specifies constraints that any architecture must satisfy.

The PIEC does not claim that the four-branch decomposition is provably exhaustive. It claims that these four branches are independently necessary and that no fifth branch has survived reduction testing within the present formalism and test suite.

The PIEC does not derive from P1-P3 alone. It requires P4 (adaptivity). Without P4, the system is not adaptive and the concept of correction is undefined.

The authority-level execution budgets ($A^{auth}$, $B_1^{auth}$, $B_2^{auth}$, $B_3^{auth}$) are derived and have passed an 8-test destruction protocol (Class C). Their content is structurally forced by the premises, but their specific formalization and operationalization need further work before empirical testing.

---

## 10. Falsifiability

The PIEC would be falsified by any of the following:

A finite adaptive system that achieves genuine self-correction (not self-referential convergence, not cycling, but sustained improvement relative to a changing environment) without any external corrective channel. This would invalidate P5.

A snapshot substitute that demonstrates $f^{probe} > 0$ — future-probe answerability without having been shaped by the causal process. This would invalidate the anti-snapshot theorem.

A fifth independently necessary branch of corrective authority that is not reducible to feasibility, channel irreducibility, sustained access, or authenticity. This would demonstrate the four-branch decomposition is incomplete.

A loophole that survives all three kill mechanisms (physics impossibility, design prevention, detection and response) and enables a finite system to escape corrective authority while maintaining adaptive functionality.

A demonstration that any of the four premises (P1-P4) is not independent of the others, which would reduce the constraint structure.

### Premise robustness

The four premises rest on established physics: P1 on the Bekenstein bound (physically well-supported), P2 on Landauer's principle (experimentally verified, Bérut et al. 2012), P3 on finite interaction rates (forced by relativistic causality), P4 on observed adaptivity of the target system class. No foreseeable technological development threatens these premises. Quantum computing does not escape P1 (quantum systems have Bekenstein bounds). Reversible computing approaches but does not reach the Landauer limit. Faster-than-light communication would threaten P3 but violates established physics. The framework's validity is anchored to physics that is not technology-dependent.

### Falsification attempts

Two directed falsification attempts were made during the paper production session:

**Isolated ecosystem test.** A closed biological ecosystem with no external input where organisms evolve. If this constitutes genuine self-correction, P5 would be falsified. Result: isolated ecosystems converge to evolutionary equilibrium, exactly as P5 predicts. They need external input (new species, environmental change) to escape stasis. The test confirmed P5 rather than falsifying it.

**Lone mathematician test.** A mathematician working alone discovers new theorems. If this constitutes self-correction without external input, P5 would be falsified. Result: the mathematician interacts with mathematical structure, which is external — mathematical truth exists independently of the mathematician and provides genuine $\mathcal{N}^{eval}$ (proofs work or don't) and $\mathcal{N}^{gen}$ (structure generates unexpected problems). The mathematician-mathematics relationship satisfies the PIEC. The test confirmed the PIEC rather than falsifying it.

The PIEC appears to be a deductive consequence of its premises within established physics — not an empirical hypothesis but a structural theorem. Falsification requires violating one of the premises (P1-P4), which requires violating established physics.

---

## 11. Compressions

**Ultra-compressed:** Finite adaptive systems require externally owned correction — or they stagnate.

**Two-sentence:** A finite adaptive system remains stably correctable only while an external channel it does not own retains corrective authority across four independently necessary dimensions: feasibility (change is possible), channel irreducibility (correction can't be faked), sustained access (sources survive), and authenticity (real correction dominates fake routes). The same five-slot constraint from the FSSTP reappears at each level of the hierarchy as a recurring structural pattern.

**One-sentence:** Corrective stability in a finite adaptive system requires feasibility, irreducible corrective channels, sustained exogenous access, and thermodynamic authenticity of real over fake correction — each independently necessary, each following the same five-slot constraint forced by finite capacity, energy cost, and finite interaction.

---

## References

Bekenstein, J. D. (1981). Universal upper bound on the entropy-to-energy ratio for bounded systems. *Physical Review D*, 23(2), 287–298. https://doi.org/10.1103/PhysRevD.23.287

Bell, J. S. (1964). On the Einstein Podolsky Rosen paradox. *Physics Physique Fizika*, 1(3), 195–200. https://doi.org/10.1103/PhysicsPhysiqueFizika.1.195

Bérut, A., Arakelyan, A., Petrosyan, A., Ciliberto, S., Dillenschneider, R., & Lutz, E. (2012). Experimental verification of Landauer's principle linking information and thermodynamics. *Nature*, 483(7388), 187–189.

Landauer, R. (1961). Irreversibility and heat generation in the computing process. *IBM Journal of Research and Development*, 5(3), 183–191. https://doi.org/10.1147/rd.53.0183

Shannon, C. E. (1948). A mathematical theory of communication. *The Bell System Technical Journal*, 27, 379–423, 623–656.

Still, S., Sivak, D. A., Bell, A. J., & Crooks, G. E. (2012). Thermodynamics of prediction. *Physical Review Letters*, 109(12), 120604. https://doi.org/10.1103/PhysRevLett.109.120604
