# The Finite Structured-State Transformation Principle

**Author:** T. Prather  
**Date:** April 2026  
**Version:** 2.0  
**Status:** Draft for external review  
**Derivation methodology:** Constraint-Guided Reverse Derivation (CGRD)  
**Companion files:** Derivation log (separate file)

---

## Abstract

We derive a constraint structure governing all structured-state change in finite physical systems from three physically well-supported premises: finite capacity (Bekenstein bound), state change costs energy (Landauer's principle), and finite interaction (any physical interaction between degrees of freedom has finite rate and takes finite time). The derivation proceeds entirely downward from these premises to consequences. Nothing is assumed from branch-level results.

The central result is a five-slot feasibility operator:

$$\Phi_{t,\Delta t} := \min(U_t,\; A_{t,\Delta t},\; B_1,\; B_2,\; B_3) > 0$$

where $U$ is the residual (precondition for change), $A$ is the opportunity (accessible portion of the residual over the interval), and $B_1, B_2, B_3$ are three independently necessary execution budgets for throughput, work, and state capacity. Structured-state change is physically achievable over an interval if and only if $\Phi > 0$. The five slots and the min structure are forced by the three premises; no slot count was assumed in advance.

When $\Phi = 0$, exactly three transformation failure modes occur: completion ($U = 0$, nothing remains to change), inaccessibility ($U > 0$, $A = 0$, residual exists but is unreachable this interval), or physical blockage ($U > 0$, $A > 0$, an execution budget is exhausted). Three structural layers produce three modes; no fourth mode exists.

A finite partition has two unconditional structural domains — interior (definitional) and boundary (forced by P3) — producing four unconditional transformation modes: refinement (interior increase), release (interior decrease), transfer (boundary crossing), and partition (boundary reconfiguration). A conditional third domain — relational (dependent on irreducibility of joint structure, established in quantum systems by Bell's theorem) — produces two additional modes: binding (relational increase) and dissolution (relational decrease). Each mode fills the five generic slots with its own physically determined content. No mode's terms substitute into another (swap test). No mode reduces to any combination of others (reduction test). The complete principle was subjected to a 108-test adversarial destruction protocol; all presently identified modes survived all applied tests.

The principle complements existing dynamics: dynamics describes how states evolve; this principle describes when change is physically achievable or must halt. These are complementary, not competing.

---

## 1. Introduction

### 1.1 The problem

Physical theories describe how systems evolve. They do not, in general, provide a single unified statement of when structured-state change in a finite system is physically achievable and when it must halt. The conditions for halting are known in specific domains — thermodynamic equilibrium, channel capacity limits, Bekenstein bounds — but these domain-specific results have not been unified into a single constraint structure that applies across all forms of structured-state change in finite systems.

This paper provides that unification. From three physically well-supported premises, we derive a five-slot feasibility operator, three transformation failure modes, the structural domains in which change can occur, and the transformation modes that exhaust the presently identified possibilities within those domains. The result is presented as a stack of five theorems, each building on the previous.

### 1.2 Relationship to existing physics

The FSSTP does not replace existing physics. It adds a constraint layer that is complementary to dynamics.

Existing physics (dynamics) tells you how states evolve — trajectories, equations of motion, transition rates, evolution operators. This principle (feasibility) tells you when change is physically achievable or must halt — which of five conditions are met, which of three failure modes applies when they are not.

The principle applies across quantum, classical, thermodynamic, biological, and coarse-grained organizational settings because it derives from constraints (P1, P2, P3) that any finitely implemented physical process must satisfy at the level of the chosen coarse-graining. Any physical system with finite capacity, energy cost for state change, and finite interaction rates is subject to the five-slot constraint at that level of description. Organizational and computational examples are intended as coarse-grained physically implemented systems; the theorem applies only insofar as the relevant states, channels, and resource budgets are physically instantiated.

The principle is silent on how a process executes. It states when execution is physically possible. Dynamics provides the trajectories; this principle provides the boundaries within which those trajectories must operate.

### 1.3 Methodology

The FSSTP was derived using Constraint-Guided Reverse Derivation (CGRD), a structured methodology for deriving candidate physical laws from established premises through constraint-guided consequence tracing, compression, destruction testing, and evidence classification. The methodology is presented in a separate companion paper. Claude Opus 4.6 (Anthropic) served as the primary derivation engine; ChatGPT (OpenAI) served as the scientific tone auditor and cross-architectural destructor. The derivation, including all dead ends and intermediate results, is documented in the companion derivation log.

### 1.4 What this paper does not claim

The theorem does not claim that every finite system undergoes structured-state change, that any particular mode is always active, or that the six-mode count is provably exhaustive. It states the conditions under which change is physically achievable and the structural categories into which achievable changes fall, within the presently identified domain decomposition. The exhaustiveness argument is structural and adversarially tested but is not a mathematical impossibility proof. The theorem does not derive the dynamics of any process. It derives feasibility conditions — when change is physically possible — not the mechanisms by which change occurs.

The theorem does not claim that modes operate independently when multiple are active simultaneously. In real systems, modes share physical resource pools — capacity used for refinement is unavailable for transfer, energy spent on release is unavailable for binding. The principal interactions are: refinement and release are complementary (release frees capacity refinement uses), refinement and transfer compete on budgets but cooperate on content (transfer delivers the input refinement encodes), and partition interacts with all modes by reconfiguring the boundaries that determine accessibility. One practically important downstream case is partition-during-transfer: reconfiguring a governance boundary while corrections are in transit can cause those corrections to fail or land in the wrong partition. This can motivate serialized control of boundary changes in downstream applications, but the application-specific implementation belongs to later papers rather than to the theorem itself. Full cross-mode interaction analysis remains a topic for further work.

---

## 2. Premises

Three physical facts. Each physically well supported. Each independent (removing any one produces a different, weaker result).

**P1 — Finite capacity (Bekenstein).** Any finite physical system has finite distinguishable states. The encoding capacity $C_P := \log_2 |\Omega_P|$ of any finite partition $P$ is bounded.

**P2 — State change costs energy (Landauer).** Any irreversible change to a physical system's state dissipates at least $kT \ln 2$ per bit erased.

**P3 — Finite interaction.** Any physical interaction between degrees of freedom has finite rate and takes finite time.

P3 replaces "locality" from earlier formulations. Locality (spatial propagation limits) is a special case of finite interaction in spatial systems. Finite coupling strength is the same premise applied to internal state spaces. The premise is state-space-general: it applies wherever degrees of freedom interact, regardless of whether the interaction is spatial.

No other premises are used unless explicitly flagged as additional.

### 2.1 Premise independence

Each premise is independently necessary:

Without P1 (infinite capacity): the state-capacity budget $B_3$ vanishes from the constraint structure. An infinite-capacity system faces no representational limit.

Without P2 (free state change): the work budget $B_2$ vanishes. State modification has no thermodynamic floor.

Without P3 (instantaneous interaction): the opportunity $A$ and throughput budget $B_1$ both vanish. All residual is immediately accessible at unlimited rate.

Each removal produces a different, weaker constraint operator. No premise is derivable from the others.

### 2.2 Premise robustness

The five-slot structure is robust to premise substitution. Replacing Landauer with the second law of thermodynamics produces the same operator structure but with a less precise work budget (no quantitative floor). Replacing Bekenstein with the holographic principle restricts scope to spatial systems. Replacing finite interaction with relativistic causality restricts to spatially separated interactions. In each case, the operator structure is preserved but scope or precision is reduced. The original premises (Bekenstein, Landauer, finite interaction) are optimally general: they maximize both scope and precision simultaneously.

---

## 3. Theorem 1: The Five-Slot Feasibility Operator

### 3.1 Statement

For any change to structured state in a finite partition $P$ over an interval $[t, t+\Delta t]$:

The change is physically achievable if and only if

$$\Phi_{t,\Delta t} := \min(U_t,\; A_{t,\Delta t},\; B_1,\; B_2,\; B_3) > 0.$$

### 3.2 Derivation

**From P1:** A difference between current state and reference state must exist. If no difference exists, there is nothing to change. This difference is finite and bounded by $C_P$. Call it $U_t$ (the residual).

**From P3:** Not all residual is reachable in a finite interval. Interaction rates are finite, coupling is finite, barriers and propagation delays limit access. Call the reachable portion $A_{t,\Delta t}$ (the opportunity).

**From P3:** The physical pathway through which the change executes has finite throughput. Call this $B_1$ (the throughput budget).

**From P2:** The change costs energy. The thermodynamic floor on irreversible state modification sets a minimum energy expenditure per bit. Call this $B_2$ (the work budget).

**From P1:** The partition has finite state space. Any state modification operates within bounded capacity. Call this $B_3$ (the state capacity budget).

All five are independently necessary. The min structure follows: failure of any one blocks the process regardless of the others.

### 3.3 What is derived and what is not assumed

The five-slot count is derived, not assumed. Five independently necessary conditions emerged from three premises. The min structure is derived: independent necessity produces conjunction, and the minimum of the conjunction determines the achievable increment. No slot count was assumed in advance. No structural pattern from branch-level results was used.

### 3.4 Slot-to-premise tracing

| Slot | Physical meaning | Forced by |
|---|---|---|
| $U_t$ (residual) | Difference between current and reference state | Precondition for change; bounded by P1 |
| $A_{t,\Delta t}$ (opportunity) | Reachable portion of residual over the interval | P3 (finite interaction rates) |
| $B_1$ (throughput) | Finite rate of the physical pathway | P3 (finite interaction rates) |
| $B_2$ (work) | Thermodynamic floor on state modification | P2 (Landauer) |
| $B_3$ (capacity) | Finite state space for modification | P1 (Bekenstein) |

### 3.5 Proof sketch

**Necessity.** If structured-state change occurs over $[t, t+\Delta t]$, then: (1) a difference between current and reference state must have existed ($U > 0$); (2) some of that difference must have been reachable over the interval ($A > 0$); (3) the physical pathway must have had nonzero throughput ($B_1 > 0$); (4) available energy must have been sufficient for at least one bit of state modification ($B_2 > 0$); (5) available state capacity must have been nonzero ($B_3 > 0$). Therefore $\Phi > 0$.

**Sufficiency.** If $\Phi > 0$, then there exists a state modification of size $\varepsilon$ with $0 < \varepsilon \leq \Phi$ that is reachable, transmissible, energetically feasible, and within capacity bounds. The modification is physically achievable by an admissible causal update.

---

## 4. Theorem 2: Three Transformation Failure Modes

### 4.1 Statement

When $\Phi_{t,\Delta t} = 0$, the process halts. Exactly three failure modes exist, corresponding to the three structural layers of the operator.

**Mode A1 — Completion.** $U_t = 0$. No residual remains. The process is complete.

**Mode A2 — Inaccessibility.** $U_t > 0$, $A_{t,\Delta t} = 0$. Residual exists but none is reachable this interval. The process is stuck, not complete.

**Mode B — Physical blockage.** $U_t > 0$, $A_{t,\Delta t} > 0$, but at least one execution budget equals zero: $B_1 = 0$, $B_2 = 0$, or $B_3 = 0$. Opportunity exists but execution is blocked.

### 4.2 Derivation

The five slots partition into three structural layers: residual ($U$), access ($A$), and execution ($B_1, B_2, B_3$). $\Phi = 0$ requires at least one slot to equal zero. Which layer contains the zero determines the failure mode. Three layers produce three modes. This is exhaustive: there is no fourth structural layer because the five slots exhaust the independently necessary conditions forced by the three premises.

### 4.3 Mode A2 versus Mode A1

The distinction between completion (A1) and inaccessibility (A2) is physically significant. In A1, the process has genuinely finished — no further work exists. In A2, work remains but cannot be reached. A system in Mode A2 is not equilibrated; it is trapped. This distinction matters in every domain: a glass (A2) is not a crystal (A1); a kinetically trapped metastable state (A2) is not thermodynamic equilibrium (A1).

---

## 5. Theorem 3: Structural Domains

### 5.1 Statement

A finite partition carrying structured state exists within a system that has the following structural domains.

**Domain 1 — Interior (unconditional).** Exists by definition. A partition carrying structured state has interior degrees of freedom whose configuration is the structured state.

**Domain 2 — Boundary (unconditional).** Exists by P3. Finite interaction requires the partition to interact with its exterior through a finite interface. This interface — the boundary — has its own configuration: the arrangement of mediating degrees of freedom.

**Domain 3 — Relational (conditional).** A system of two or more partitions has a joint state. Whether this joint state constitutes an independent structural domain depends on whether it is reducible to individual partition states. If irreducible, the relational domain is a genuine third domain. If reducible, it is a derived quantity, not an independent domain.

### 5.2 Domain 2 derivation from P3

P3 states that any interaction between degrees of freedom has finite rate and takes finite time. For a partition to interact with its exterior, there must exist mediating degrees of freedom through which the interaction proceeds. These mediating degrees of freedom constitute the boundary. The boundary is not assumed — it is forced by the premise that interaction is finite. An infinite-rate interaction would require no mediating structure; a finite-rate interaction requires a physical channel, and that channel is the boundary.

A constraint boundary is any physical constraint that separates inside from outside. In continuous spatial systems, this is a geometric surface (spatial boundary, Markov blanket). In discrete or internal state spaces, this may be an algebraic constraint (such as color confinement or charge neutrality). The domain decomposition applies wherever constraint-based partitioning exists, regardless of whether the state space is continuous or discrete, spatial or internal.

### 5.3 Domain 3 conditionality

**In quantum systems:** Bell's theorem (1964, experimentally confirmed) proves that the joint state of entangled particles cannot be reduced to local hidden variables in individual particles. Joint structure is irreducible to individual structure. Domain 3 exists as a genuine independent domain. The additional premise is Bell's theorem.

**In classical systems:** Classical correlations can in principle be described by individual states plus coupling structure. However, the coupling geometry constrains achievable correlations independently from individual capacities. Classical irreducibility is structurally motivated but not proven to the standard of Bell. Domain 3 is a candidate in classical systems. Its status remains an open question. The presence of an independent relational domain is established for quantum systems and is not assumed universally; classical reductions reported here are results within the present formalism and test suite.

---

## 6. Theorem 4: Four Unconditional Transformation Modes

### 6.1 Statement

The two unconditional structural domains, each admitting two physically distinct directions or operations, produce exactly four unconditional transformation modes.

### 6.2 Derivation

**Domain 1 (interior):** Structured state measured as deviation from a reference is a non-negative bounded scalar. A non-negative bounded scalar has exactly two directions of change: increase or decrease. Multi-dimensional structure creates parallel instances, not new modes.

Interior increase = **Refinement** (structure grows toward alignment with reference).
Interior decrease = **Release** (structure sheds toward relaxed reference).

**Domain 2 (boundary):** Mediating degrees of freedom can do exactly two things: mediate passage of content (structure crosses the boundary), or change their own configuration (the boundary restructures). A mediating degree of freedom either passes content or changes itself. No third operation exists.

Boundary crossing = **Transfer** (structure moves from one partition to another).
Boundary reconfiguration = **Partition** (boundary changes configuration).

### 6.3 Four modes, each instantiating the five-slot operator

Each mode fills the five generic slots with its own physically determined content:

| Slot | Refinement | Release | Transfer | Partition |
|---|---|---|---|---|
| $U$ (residual) | $G_t$ | $D_t$ | $T_t$ | $Q_t$ |
| $A$ (opportunity) | $S_{t,\Delta t}$ | $R_{t,\Delta t}$ | $K_{t,\Delta t}$ | $A_{t,\Delta t}$ |
| $B_1$ (throughput) | $B_{\mathrm{ch}}$ | $C_{\mathrm{rel}}$ | $C_{\mathrm{cross}}$ | $B_{\mathrm{form}}$ |
| $B_2$ (work) | $B_{\mathrm{work}}$ | $B_{\mathrm{drop}}$ | $B_{\mathrm{trans}}$ | $B_{\mathrm{maint}}$ |
| $B_3$ (capacity) | $B_{\mathrm{cap}}$ | $B_{\mathrm{erase}}$ | $B_{\mathrm{recv}}$ | $B_{\mathrm{coord}}$ |

Each mode has its own physically determined reference object: $E^{\mathrm{acc}}$ (refinement), $\sigma^*$ (release), $Z$ (transfer), $\beta^*$ (partition). No reference object substitutes into another mode.

The mode-specific operators are:

$$\Lambda_{t,\Delta t} = \min(G_t, S_{t,\Delta t}, B_{\mathrm{ch}}, B_{\mathrm{work}}, B_{\mathrm{cap}}) \quad \text{[Refinement]}$$
$$\Omega_{t,\Delta t} = \min(D_t, R_{t,\Delta t}, C_{\mathrm{rel}}, B_{\mathrm{drop}}, B_{\mathrm{erase}}) \quad \text{[Release]}$$
$$\Theta_{t,\Delta t} = \min(T_t, K_{t,\Delta t}, C_{\mathrm{cross}}, B_{\mathrm{trans}}, B_{\mathrm{recv}}) \quad \text{[Transfer]}$$
$$\Psi_{t,\Delta t} = \min(Q_t, A_{t,\Delta t}, B_{\mathrm{form}}, B_{\mathrm{maint}}, B_{\mathrm{coord}}) \quad \text{[Partition]}$$

### 6.4 Cross-mode verification

No mode's terms substitute into another (verified by swap test across all ordered pairs). No mode reduces to any combination of others (verified by standard reduction, three attempts per mode). No mode collapses into another under any parameter limit (verified by limit collapse across all parameters). No mode can be simulated by repeated application of any other single mode (verified by temporal composition across all ordered pairs). These results are documented in the destruction protocol (Section 12).

---

## 7. Theorem 5: Conditional Relational Extension

### 7.1 Statement

In systems where joint structure is irreducible to individual partition structure, a third structural domain produces two additional transformation modes:

**Binding** — relational structure increases (correlation, entanglement, synchronization grows).
**Dissolution** — relational structure decreases (decoherence, desynchronization, decorrelation).

This extension requires an additional premise: the irreducibility of joint structure to individual structure.

### 7.2 The additional premise

**In quantum systems:** Bell's theorem (1964) provides the irreducibility premise. Entanglement cannot be reduced to local hidden variables. The joint state is a genuine physical quantity not derivable from individual states. This is experimentally confirmed.

**In classical systems:** Classical irreducibility is structurally motivated but not established. Classical correlations can in principle be described by individual states plus coupling. Whether the coupling geometry introduces an independent capacity constraint on joint structure — analogous to Bell's irreducibility — is an open question.

### 7.3 The relational modes

Each relational mode fills the five generic slots with joint-state terms:

| Slot | Binding | Dissolution |
|---|---|---|
| $U$ (residual) | $M^{\uparrow}_t$ (achievable mutual structure not yet realized) | $M^{\downarrow}_t$ (releasable mutual structure) |
| $A$ (opportunity) | $J_{t,\Delta t}$ (accessible joint interaction) | $J^{\downarrow}_{t,\Delta t}$ (accessible decoupling pathway) |
| $B_1$ (throughput) | $C_{\mathrm{couple}}$ (coupling throughput) | $C_{\mathrm{decouple}}$ (decoupling throughput) |
| $B_2$ (work) | $B_{\mathrm{bind}}$ (binding work) | $B_{\mathrm{dissolve}}$ (dissolution work) |
| $B_3$ (capacity) | $B_{\mathrm{joint}}$ (joint state capacity) | $B_{\mathrm{release\_joint}}$ (joint state release capacity) |

Reference objects: $M^*_{\max}$ (maximum achievable mutual structure) for binding; $M^*_{\min}$ (minimum achievable mutual structure) for dissolution.

### 7.4 The 6→4 classical transition

In quantum systems, six modes are independently irreducible (Bell prevents reduction of binding/dissolution to iterated individual-state operations).

In classical systems, the temporal composition test found that binding can be reproduced by iterated transfer + refinement, and classical dissolution reduces to the natural decay of correlations when transfer/refinement stop maintaining them. Classical correlations are fully reproducible by individual-state operations.

Within the present formalism and test suite, this produces a clean transition: quantum systems have six irreducible modes; classical systems have four confirmed modes, with two additional modes that are structurally present but reducible to combinations of the four. The classical world is the FSSTP with the relational domain collapsed.

The transition can be expressed as: $N_{\mathrm{eff}} = 4 + 2D$, where $D$ measures the degree of relational residual irreducibility. In quantum systems, $D = 1$; in classical systems, $D = 0$.

### 7.5 Evidence classification

| Claim | Evidence class | Language |
|---|---|---|
| Six modes in quantum systems | Class C (conditional on Bell) | "Given Bell's theorem, six modes follow" |
| Four modes unconditionally | Class B (derived + stress-tested) | "Four modes are forced by P1-P3" |
| Classical irreducibility | Open question | "Classical irreducibility remains open" |
| 6→4 transition | Class C (conditional) | "Derived from premises + decoherence physics" |

---

## 8. The Refinement Mode (Interior Increase)

### 8.1 Definition

Refinement governs the increase of interior structured state toward alignment with a reference. Its distinguishing feature is future-directedness: the residual $G_t$ measures structure relevant to future environmental states, not arbitrary correlation with the past.

**Reference object:** $E^{\mathrm{acc}}$ — the causally accessible environment, determined by causal structure, light cone, and coupling topology. The reference object is physically determined, not chosen.

### 8.2 Slot content

**Residual (U-slot):** $G_t := I(E^{\mathrm{acc}}_{\leq t};\; E^{\mathrm{acc}}_{>t} \mid \Pi_t)$ — unencoded predictive structure: future-relevant environmental structure not yet compressed into the system's minimal predictive state $\Pi_t$. When $G_t = 0$, the system's predictive state is already a sufficient statistic.

**Opportunity (A-slot):** $S_{t,\Delta t} := I(E^{\mathrm{acc}}_{\leq t};\; E^{\mathrm{acc}}_{(t,t+\Delta t]} \mid \Pi_t)$ — locally harvestable predictive signal over the interval.

**Throughput (B₁-slot):** $B_{\mathrm{ch}}(t,\Delta t) := C_{\mathrm{ch}}(t,\Delta t)$ — channel capacity from environment to system over the interval. Forced by P3.

**Work (B₂-slot):** $B_{\mathrm{work}}(t,\Delta t) := W_{\mathrm{avail}}(t,\Delta t) / (kT\ln 2)$ — available dissipative work for writing predictive information, measured in bits. Forced by P2.

**Capacity (B₃-slot):** $B_{\mathrm{cap}}(t,\Delta t) := C_{\Pi,\max} - H(\Pi_t) + B_{\mathrm{realloc}}(t,\Delta t)$ — free predictive-state capacity plus any capacity freed during the interval. Bounded by P1.

### 8.3 The feasibility theorem (refinement mode)

Predictive refinement is physically achievable over $[t, t+\Delta t]$ if and only if

$$\Lambda_{t,\Delta t} := \min(G_t,\; S_{t,\Delta t},\; B_{\mathrm{ch}},\; B_{\mathrm{work}},\; B_{\mathrm{cap}}) > 0.$$

### 8.4 Why predictive content is physically privileged

The residual $G_t$ measures future-relevant structure, not arbitrary correlation. This choice is justified thermodynamically: Still et al. (2012) showed that correlations retained about the environment's past that are not predictive of its future contribute directly to excess dissipation. The claim is restrained: in driven non-equilibrium settings, systems that continue to update under finite work and finite capacity face pressure to compress away non-predictive correlations. This supports treating predictive information as the physically relevant target quantity for efficient refinement.

### 8.5 Mode-specific failure modes

Completion ($G_t = 0$): predictive state is a sufficient statistic. Refinement halts because the work is done. Inaccessibility ($G_t > 0$, $S_{t,\Delta t} = 0$): structure exists but none is harvestable this interval. Physical blockage: channel saturation ($B_{\mathrm{ch}} = 0$), energy exhaustion ($B_{\mathrm{work}} = 0$), or representational saturation ($B_{\mathrm{cap}} = 0$). Representational saturation admits a recovery mechanism through internal compression ($B_{\mathrm{realloc}}$).

---

## 9. The Release Mode (Interior Decrease)

### 9.1 Definition

Release governs the decrease of interior structured state toward a relaxed reference. It is the complement of refinement within the interior domain.

**Reference object:** $\sigma^*$ — the relaxed reference state, determined by conserved quantities and constraints. This is the state toward which the system tends in the absence of external driving.

### 9.2 Slot content

**Residual (U-slot):** $D_t$ — releasable excess: structured state present beyond what the relaxed reference requires. When $D_t = 0$, the system is already at its relaxed reference.

**Opportunity (A-slot):** $R_{t,\Delta t}$ — accessible relaxation pathways over the interval.

**Throughput (B₁-slot):** $C_{\mathrm{rel}}$ — relaxation channel capacity.

**Work (B₂-slot):** $B_{\mathrm{drop}}$ — energy available for the state modification required to shed structure. Release, like any irreversible state change, has a thermodynamic cost.

**Capacity (B₃-slot):** $B_{\mathrm{erase}}$ — erasure capacity: the ability to remove structured state from the system's encoding.

### 9.3 The feasibility theorem (release mode)

Release is physically achievable over $[t, t+\Delta t]$ if and only if

$$\Omega_{t,\Delta t} := \min(D_t,\; R_{t,\Delta t},\; C_{\mathrm{rel}},\; B_{\mathrm{drop}},\; B_{\mathrm{erase}}) > 0.$$

### 9.4 Why release is not the reverse of refinement

Release and refinement share the interior domain and the same three premises, but they differ in reference object ($\sigma^*$ versus $E^{\mathrm{acc}}$), residual content (excess versus gap), and physical meaning (shedding versus accumulating). The swap test confirms this: substituting $G_t$ (predictive gap) into the release structure does not produce a coherent theorem. The two modes are complementary, not inverse.

### 9.5 Mode-specific failure modes

**Mode A1 — Fully relaxed.** $D_t = 0$. The system has reached its relaxed reference state. No excess structure remains to shed.

**Mode A2 — Relaxation-blocked.** $D_t > 0$ but $R_{t,\Delta t} = 0$. Excess structure exists but no relaxation pathway is accessible this interval. The system is stuck above its reference — a metastable excess state.

**Mode B — Resource-limited.** Any of $C_{\mathrm{rel}}$, $B_{\mathrm{drop}}$, or $B_{\mathrm{erase}}$ is zero. Relaxation pathways exist but the system lacks the throughput, energy, or erasure capacity to use them. This is the most common release failure in information ecosystems: storage is cheap but attention to curate stored content is bounded.

---

## 10. The Transfer Mode (Boundary Crossing)

### 10.1 Definition

Transfer governs the movement of structured state across a boundary between two named partitions. It operates in the boundary domain and is content-neutral: any structured state can cross a boundary in either direction.

**Reference object:** $Z$ — the shared coupling domain between source and target partitions, determined by the coupling structure of the partition pair.

### 10.2 Slot content

**Residual (U-slot):** $T_t$ — transferable structure: structured state present in the source partition but absent in the target partition, with respect to the cross-boundary content mapping.

**Opportunity (A-slot):** $K_{t,\Delta t}$ — cross-boundary coupling active over the interval.

**Throughput (B₁-slot):** $C_{\mathrm{cross}}$ — cross-boundary channel capacity.

**Work (B₂-slot):** $B_{\mathrm{trans}}$ — translation work: the energy cost of mapping structure from the source codebook to the target codebook. This cost is determined by the distance between codebooks, not by the information content alone.

**Capacity (B₃-slot):** $B_{\mathrm{recv}}$ — receiving capacity in the target partition.

### 10.3 The feasibility theorem (transfer mode)

Transfer is physically achievable over $[t, t+\Delta t]$ if and only if

$$\Theta_{t,\Delta t} := \min(T_t,\; K_{t,\Delta t},\; C_{\mathrm{cross}},\; B_{\mathrm{trans}},\; B_{\mathrm{recv}}) > 0.$$

### 10.4 Why transfer is not refinement from the environment

Transfer is content-neutral: any structured state can cross a boundary. Refinement is content-selective: only future-predictive structure counts. Transfer's residual measures cross-boundary content difference. Refinement's residual measures unencoded predictive structure. The reference objects are different ($Z$ versus $E^{\mathrm{acc}}$). The budget terms are different ($C_{\mathrm{cross}}$ and $B_{\mathrm{trans}}$ versus $B_{\mathrm{ch}}$ and $B_{\mathrm{work}}$). The swap test confirms non-interchangeability.

### 10.5 Mode-specific failure modes

**Mode A1 — Fully transferred.** $T_t = 0$. All transferable structure has crossed the boundary. Source and target are synchronized with respect to the coupling domain.

**Mode A2 — Coupling-blocked.** $T_t > 0$ but $K_{t,\Delta t} = 0$. Transferable structure exists but the cross-boundary coupling is inactive this interval. The partitions are isolated — no communication pathway is available.

**Mode B — Resource-limited.** Any of $C_{\mathrm{cross}}$, $B_{\mathrm{trans}}$, or $B_{\mathrm{recv}}$ is zero. Coupling exists but the system lacks channel capacity, translation energy, or receiving capacity. The codebook distance component of $B_{\mathrm{trans}}$ makes this mode particularly relevant for cross-domain transfer: the greater the conceptual distance between source and target, the higher the translation cost.

---

## 11. The Partition Mode (Boundary Reconfiguration)

### 11.1 Definition

Partition governs the reconfiguration of boundary structure itself — changes to the mediating degrees of freedom that define the interface between partitions. It is the meta-operational mode: partition changes the scoping objects of all other modes.

**Reference object:** $\beta^*$ — the boundary reference state, determined by conserved quantities and coupling constraints.

### 11.2 Slot content

**Residual (U-slot):** $Q_t$ — reconfigurable boundary structure: the difference between current boundary configuration and the boundary reference.

**Opportunity (A-slot):** $A_{t,\Delta t}$ — accessible reconfiguration pathways over the interval.

**Throughput (B₁-slot):** $B_{\mathrm{form}}$ — boundary formation/dissolution throughput.

**Work (B₂-slot):** $B_{\mathrm{maint}}$ — maintenance energy for the boundary reconfiguration.

**Capacity (B₃-slot):** $B_{\mathrm{coord}}$ — coordination capacity: the cost of updating a single partition's internal state to match the new boundary. This is narrowed to individual coordination; relational coordination is handled by the binding and dissolution modes.

### 11.3 The feasibility theorem (partition mode)

Partition is physically achievable over $[t, t+\Delta t]$ if and only if

$$\Psi_{t,\Delta t} := \min(Q_t,\; A_{t,\Delta t},\; B_{\mathrm{form}},\; B_{\mathrm{maint}},\; B_{\mathrm{coord}}) > 0.$$

### 11.4 Why partition is not transfer of boundary state

Partition changes the boundary configuration itself — the scoping objects that define what is inside and outside. Transfer moves content across an existing boundary without changing the boundary. A boundary reconfiguration can alter what environment is causally accessible to a system ($E^{\mathrm{acc}}$), what relaxation channels are available ($\sigma^*$), and what coupling domains exist ($Z$). Partition enables or constrains all other modes without simulating any of them.

### 11.5 Mode-specific failure modes

**Mode A1 — Boundary-stable.** $Q_t = 0$. The boundary configuration matches its reference state. No reconfiguration is needed or possible.

**Mode A2 — Reconfiguration-blocked.** $Q_t > 0$ but $A_{t,\Delta t} = 0$. The boundary should change but no reconfiguration pathway is accessible this interval. The current partition is frozen despite being suboptimal — a governance deadlock.

**Mode B — Resource-limited.** Any of $B_{\mathrm{form}}$, $B_{\mathrm{maint}}$, or $B_{\mathrm{coord}}$ is zero. Reconfiguration pathways exist but the system lacks the formation throughput, maintenance energy, or coordination capacity to execute them. The coordination component ($B_{\mathrm{coord}}$) is especially relevant for institutional partitions: changing a boundary requires every partition to update its internal state to match, and the coordination cost scales with the number of affected partitions.

---

## 12. The Binding Mode (Relational Increase) [Conditional on P4]

### 12.1 Definition

Binding is the increase of irreducible mutual structure between two or more partitions. "Irreducible" means the joint state cannot be decomposed into independent states of the parts — this is what P4 (Bell-type irreducible correlations) guarantees for quantum systems. In classical systems, all correlations are in principle decomposable, and binding reduces to iterated transfer + refinement.

### 12.2 Slot content

| Slot | Content | Premise |
|---|---|---|
| $U$ (residual) | $M^{\uparrow}_t$ — achievable mutual structure not yet realized | P1 (finite capacity bounds maximum) |
| $A$ (opportunity) | $J_{t,\Delta t}$ — accessible joint interaction this interval | P3 (finite interaction rate) |
| $B_1$ (throughput) | $C_{\mathrm{couple}}$ — coupling throughput | P3 (channel capacity) |
| $B_2$ (work) | $B_{\mathrm{bind}}$ — binding work (energy cost of establishing correlation) | P2 (Landauer) |
| $B_3$ (capacity) | $B_{\mathrm{joint}}$ — joint state capacity | P1 (Bekenstein) |

**Reference object:** $M^*_{\max}$ — maximum achievable mutual structure given the systems' capacities and interaction constraints.

### 12.3 The feasibility theorem (binding mode)

Binding is achievable if and only if: $M^{\uparrow}_t > 0$ (mutual structure gap exists), $J_{t,\Delta t} > 0$ (joint interaction accessible), $C_{\mathrm{couple}} > 0$ (coupling throughput available), $B_{\mathrm{bind}} > 0$ (energy available), and $B_{\mathrm{joint}} > 0$ (joint capacity available). If any slot is zero, binding is blocked.

### 12.4 Why binding is not transfer between partitions

Transfer moves structure FROM one partition TO another across a boundary. Binding creates structure that exists IN NEITHER partition individually — it is irreducibly joint. The swap test confirms: $K_{t,\Delta t}$ (transfer coupling) does not substitute for $J_{t,\Delta t}$ (joint interaction opportunity), because transfer preserves local state identity while binding creates non-local joint state. In classical systems without P4, this distinction collapses — classical "binding" IS iterated transfer, and the mode is not independently load-bearing.

### 12.5 Mode-specific failure modes

**Mode A1 — Maximally entangled.** $M^{\uparrow}_t = 0$ because $M_t = M^*_{\max}$. The systems have achieved maximum mutual structure. No further binding is possible without increasing capacity.

**Mode A2 — Interaction-blocked.** $M^{\uparrow}_t > 0$ but $J_{t,\Delta t} = 0$. Mutual structure could grow but the systems cannot interact this interval. Spatial separation or decoherence prevents coupling.

**Mode B — Resource-limited.** Any of $C_{\mathrm{couple}}$, $B_{\mathrm{bind}}$, or $B_{\mathrm{joint}}$ is zero. Binding is physically possible in principle but blocked by throughput, energy, or capacity constraints.

---

## 13. The Dissolution Mode (Relational Decrease) [Conditional on P4]

### 13.1 Definition

Dissolution is the decrease of irreducible mutual structure between partitions. This is not destruction of the partitions themselves — it is the loss of their joint, non-decomposable correlations. Decoherence is the primary physical mechanism.

### 13.2 Slot content

| Slot | Content | Premise |
|---|---|---|
| $U$ (residual) | $M^{\downarrow}_t$ — releasable mutual structure | P1 (current joint state exceeds reference) |
| $A$ (opportunity) | $J^{\downarrow}_{t,\Delta t}$ — accessible decoupling pathway this interval | P3 (finite interaction rate) |
| $B_1$ (throughput) | $C_{\mathrm{decouple}}$ — decoupling throughput | P3 (channel capacity) |
| $B_2$ (work) | $B_{\mathrm{dissolve}}$ — dissolution work (energy cost of breaking correlation) | P2 (Landauer) |
| $B_3$ (capacity) | $B_{\mathrm{release\_joint}}$ — joint state release capacity | P1 (Bekenstein) |

**Reference object:** $M^*_{\min}$ — minimum achievable mutual structure (typically zero for complete decoherence, nonzero if conservation laws prevent full decorrelation).

### 13.3 The feasibility theorem (dissolution mode)

Dissolution is achievable if and only if: $M^{\downarrow}_t > 0$ (releasable mutual structure exists), $J^{\downarrow}_{t,\Delta t} > 0$ (decoupling pathway accessible), $C_{\mathrm{decouple}} > 0$ (decoupling throughput available), $B_{\mathrm{dissolve}} > 0$ (energy available), and $B_{\mathrm{release\_joint}} > 0$ (release capacity available). If any slot is zero, dissolution is blocked.

### 13.4 Why dissolution is not the reverse of binding

Binding and dissolution share the relational domain and the same three premises, but they differ in reference object ($M^*_{\max}$ versus $M^*_{\min}$), residual content (unrealized versus releasable mutual structure), and physical mechanism (coupling versus decoupling). The swap test confirms: $M^{\uparrow}_t$ (binding residual) does not substitute for $M^{\downarrow}_t$ (dissolution residual), because unrealized joint structure and releasable joint structure are independently measurable quantities that can be simultaneously nonzero. The two modes are complementary, not inverse.

### 13.5 Mode-specific failure modes

**Mode A1 — Fully decohered.** $M^{\downarrow}_t = 0$ because $M_t = M^*_{\min}$. No further dissolution is possible. The systems are maximally independent.

**Mode A2 — Decoupling-blocked.** $M^{\downarrow}_t > 0$ but $J^{\downarrow}_{t,\Delta t} = 0$. Mutual structure could decrease but no decoupling pathway is accessible this interval. Environmental isolation prevents decoherence.

**Mode B — Resource-limited.** Any of $C_{\mathrm{decouple}}$, $B_{\mathrm{dissolve}}$, or $B_{\mathrm{release\_joint}}$ is zero. Dissolution is physically possible in principle but blocked by throughput, energy, or capacity constraints.

---

## 14. Destruction Protocol Results

The complete FSSTP was subjected to a 108-test adversarial destruction protocol with full matrix coverage.

### 14.1 Test matrix

| Test type | Tests run | Result |
|---|---|---|
| Standard reduction (3 per mode) | 18 | All 6 modes survive |
| Limit collapse (10 per mode) | 60 | No mode collapses into another under any limit |
| Temporal composition (all ordered pairs) | 30 | 4 unconditional modes fully irreducible; 2 relational modes irreducible in quantum, reducible in classical |

### 14.2 Key findings

Four unconditional modes are fully irreducible under all applied tests. Binding and dissolution are irreducible in quantum systems (Bell prevents reduction) and reducible in classical systems (iterated transfer + refinement reproduces classical binding). The presence of an independent relational domain is established for quantum systems and is not assumed universally; within the present formalism and test suite, this supports the 6→4 classical transition discussed in Theorem 5.

In the applied temporal-composition tests, partition altered the conditions under which other modes operate without reproducing their processes. This behavior was not observed for the other presently identified modes.

### 14.3 Swap test results

All refinement-specific terms were substituted into other modes' structures, and all other modes' terms were substituted into refinement's structure. All swaps failed cleanly. $G_t$ (predictive gap) does not function as a release residual ($D_t$, releasable excess). $S_{t,\Delta t}$ (predictive signal) does not function as a transfer opportunity ($K_{t,\Delta t}$, coupling). $B_{\mathrm{cap}}$ (predictive-state capacity) does not function as a partition budget ($B_{\mathrm{coord}}$, coordination cost). No term "kind of works" in another mode. This pattern held across all mode pairs.

---

## 15. Exhaustiveness

### 15.1 Domain exhaustiveness

Structured state in a system of partitions lives in exactly three places: inside a partition (interior degrees of freedom), at the boundary (mediating degrees of freedom), or between partitions (joint degrees of freedom, if irreducible). For a system described by partitions with constraint boundaries, there is no fourth spatial relationship. A degree of freedom is inside, at the boundary, or in the joint state.

### 15.2 Direction exhaustiveness

Within each domain, change is measured as deviation from a reference — a non-negative bounded scalar. A non-negative bounded scalar has exactly two directions of change: increase or decrease. No third direction exists.

### 15.3 Operation exhaustiveness at the boundary

Boundary degrees of freedom either mediate passage (transfer) or change their own configuration (partition). A mediating degree of freedom does one or the other. No third operation exists for a set of mediating degrees of freedom.

### 15.4 Combined exhaustiveness

Two or three domains (unconditional or conditional) × two directions/operations per domain = four or six modes. All adversarial attempts to construct additional modes reduce to existing modes or their combinations. No seventh mode has survived reduction testing.

### 15.5 Honest status

The exhaustiveness argument is structural, not a formal proof. It rests on the claim that inside/at/between exhausts the spatial relationships in a partitioned system, and that increase/decrease exhausts the directions for a bounded scalar. Both claims are supported by the inability to construct counterexamples, not by a mathematical impossibility proof. The argument is adversarially tested (108-test destruction protocol produced no counterexample within the present formalism and test suite) but not closed.

---

## 16. Falsifiability

The FSSTP would be falsified by any of the following:

A physical system where structured-state change is achievable despite $\Phi = 0$ (violates the feasibility operator).

A structured-state change that is not interior, boundary, or relational (violates domain exhaustiveness).

A fourth structural domain that is not reducible to the three (violates the three-domain claim).

A transformation failure mode that does not fit A1, A2, or B (violates the three-mode classification).

A demonstration that P1, P2, or P3 is not independent of the others (collapses the budget structure).

A seventh transformation mode that survives reduction testing against all six existing modes.

A physical system where one of the five slots is zero and the process nevertheless continues (violates independent necessity of each slot).

---

## 17. What Is Not Claimed

The FSSTP does not claim six-mode universality. Six modes hold in quantum systems (conditional on Bell). Four modes hold unconditionally. The relational domain's status in classical systems is an open question.

The FSSTP does not derive the dynamics of any process. It derives feasibility conditions — when change is physically possible — not the mechanisms by which change occurs.

The five-slot count could change under extreme conditions where the premises themselves require modification (e.g., near the Planck scale where Bekenstein, Landauer, or finite interaction may need revision). The theorem is as strong as its premises.

The bounded non-closure result — that for a finite system whose environment's predictive structure is not finitely exhaustible by the system's capacity, an exogenous predictive frontier remains at all finite times — is a consequence of the refinement mode's structure. It is not a claim that all remaining structure is useful, reachable, or compressible.

---

## 18. Compressions

**Ultra-compressed:** Finite structure, finite access, finite resources — or the process halts.

**Two-sentence:** Any change to structured state in a finite partition is physically achievable iff a residual exists, is accessible, and three execution budgets are positive. The five-slot constraint is forced by Bekenstein, Landauer, and finite interaction; four modes are forced unconditionally by two structural domains; two additional modes are forced conditionally by a third domain requiring irreducibility of joint structure.

**One-sentence:** Structured-state change in a finite partition requires residual, access, and three execution budgets — each forced by established physics, each independently blockable — taking four unconditional forms across two domains or six conditional on relational irreducibility.

---

## 19. The Complete Family

### 19.1 Six modes across three domains

| Domain | Increase / Forward | Decrease / Reverse | Status |
|---|---|---|---|
| Interior | Refinement | Release | Unconditional |
| Boundary | Transfer | Partition | Unconditional |
| Relational | Binding | Dissolution | Conditional (Bell) |

### 19.2 Six reference objects

| Mode | Reference object | Determined by |
|---|---|---|
| Refinement | $E^{\mathrm{acc}}$ (accessible environment) | Causal structure, coupling |
| Release | $\sigma^*$ (relaxed reference) | Conserved quantities, constraints |
| Transfer | $Z$ (shared coupling domain) | Coupling structure of partition pair |
| Partition | $\beta^*$ (boundary reference) | Conserved quantities, coupling |
| Binding | $M^*_{\max}$ (maximum mutual structure) | Joint system physics |
| Dissolution | $M^*_{\min}$ (minimum mutual structure) | Coupling floor |

Each reference object is physically determined, not observer-chosen. No reference object substitutes into another mode.

---

## References

Bekenstein, J. D. (1973). Black holes and entropy. *Physical Review D*, 7(8), 2333–2346.

Bekenstein, J. D. (1981). Universal upper bound on the entropy-to-energy ratio for bounded systems. *Physical Review D*, 23(2), 287–298. https://doi.org/10.1103/PhysRevD.23.287

Bell, J. S. (1964). On the Einstein Podolsky Rosen paradox. *Physics Physique Fizika*, 1(3), 195–200. https://doi.org/10.1103/PhysicsPhysiqueFizika.1.195

Bérut, A., Arakelyan, A., Petrosyan, A., Ciliberto, S., Dillenschneider, R., & Lutz, E. (2012). Experimental verification of Landauer's principle linking information and thermodynamics. *Nature*, 483(7388), 187–189.

Bousso, R. (2002). The holographic principle. *Reviews of Modern Physics*, 74(3), 825–874. https://doi.org/10.1103/RevModPhys.74.825

Landauer, R. (1961). Irreversibility and heat generation in the computing process. *IBM Journal of Research and Development*, 5(3), 183–191. https://doi.org/10.1147/rd.53.0183

Schlosshauer, M. (2005). Decoherence, the measurement problem, and interpretations of quantum mechanics. *Reviews of Modern Physics*, 76(4), 1267–1305. https://doi.org/10.1103/RevModPhys.76.1267

Shannon, C. E. (1948). A mathematical theory of communication. *The Bell System Technical Journal*, 27, 379–423, 623–656.

Still, S., Sivak, D. A., Bell, A. J., & Crooks, G. E. (2012). Thermodynamics of prediction. *Physical Review Letters*, 109(12), 120604. https://doi.org/10.1103/PhysRevLett.109.120604

Zurek, W. H. (2003). Decoherence, einselection, and the quantum origins of the classical. *Reviews of Modern Physics*, 75(3), 715–775. https://doi.org/10.1103/RevModPhys.75.715
