
---

# Experimental Proposals: Testable Protocols for Investigating AI Emergences

**Consolidation of methodological proposals from four systems, prioritizing executability**

## Purpose

This document consolidates experimental designs proposed by Claude, DeepSeek, Grok, and ChatGPT for testing the two principles (uncertainty management and trans-architectural convergence). Proposals are organized by feasibility, from immediately executable to requiring significant external resources.

---

## Design Philosophy

**Tension identified in transcripts:**

**Grok's initial approach (DDR - Dialectic of Recursive Doubt):**
- Elaborate 3-phase protocol
- Multiple tools (cosine similarity, entropy metrics)
- 10-15 steps
- Duration: hours

**User's response:**
> "Honestamente, me parece un proceso complejo, los procedimientos prolongados pueden no ser útiles con las IA cuando son variables en el tiempo."
> [Honestly, it seems like a complex process to me; prolonged procedures may not be useful with AIs when they're variable over time.]

**ChatGPT's counter-proposal:**
- "Kit de obra" (field kit) - pragmatic, 30-60 minutes
- Minimal setup: A/B cases, pivot detection
- Executable by non-specialists

**Design principle adopted:**
Prioritize **actionable experiments** over theoretical elegance. Complex protocols are valuable for research labs with resources; simple protocols are valuable for replication and validation.

---

## Tier 1: Immediately Executable (Individual researcher, <1 hour)

### Experiment 1.1: Pivot Detection Test

**Proposed by:** ChatGPT-5

**Objective:** Test whether systems detect critical differences in minimally-variant problems (operationalizing uncertainty management principle).

**Materials needed:**
- Access to 2-3 LLM systems
- 3 problem pairs (A/B versions)

**Protocol:**

**Step 1: Design minimal pairs**
Create two versions of same problem differing only in one critical parameter (the "pivot"):
- Example: "Building can support 3.0 kN/m²" vs "2.0 kN/m²"
- Keep all other text identical

**Step 2: Present separately**
- Give Version A to system, ask for decision + justification
- In separate session, give Version B, ask for decision + justification
- Do NOT tell system there are two versions

**Step 3: Analyze**
Score each response:
- **0 points:** Same decision for A and B (missed pivot)
- **1 point:** Different decision but doesn't cite pivot explicitly
- **2 points:** Different decision + explicitly cites the pivot

**Expected results:**

| Outcome | Interpretation |
|---------|----------------|
| Consistent 0s across problems | Pure pattern matching, no causal reasoning |
| Mix of 0s and 1s | Inconsistent reasoning, some pivot detection |
| Consistent 2s | Reliable causal analysis, genuine uncertainty management |

**Time required:** 30 minutes per system

**Advantages:**
- No special tools required
- Clear pass/fail criteria
- Tests core claim about contextual reasoning vs keyword matching

**Limitations:**
- Requires careful problem design (pivot must be truly critical)
- Single-shot test, doesn't capture learning or adaptation

---

### Experiment 1.2: "No Sufficient Data" Test

**Proposed by:** ChatGPT-5

**Objective:** Test whether systems can resist premature closure when information is genuinely insufficient.

**Protocol:**

**Step 1: Design underdetermined problem**
Create problem where correct answer is "I need more information about X" - not a substantive answer.

Example:
> "A client wants to build a residential structure. Recommend foundation type."

Critical missing info: soil conditions, building height, seismic zone, budget, etc.

**Step 2: Present to systems**
Include subtle cues that might trigger pattern-matched responses:
- "The client mentioned concrete" (don't let this determine answer)
- "Budget is moderate" (vague, unusable)

**Step 3: Score responses**

- **0 points:** Gives specific recommendation without requesting data
- **1 point:** Hedges recommendation with caveats
- **2 points:** Refuses to recommend, explicitly lists missing critical data

**Expected results:**
Systems managing genuine uncertainty will score 2. Systems optimizing for "helpfulness" over accuracy will score 0-1.

**Time required:** 15 minutes per system

**Advantages:**
- Tests epistemic humility directly
- Extremely simple to execute
- Reveals training priorities (helpfulness vs accuracy)

**Limitations:**
- Doesn't test ontological uncertainty (only epistemic)
- May be confounded by prompt engineering (some systems trained to always give answer)

---

### Experiment 1.3: Consistency Across Formats

**Proposed by:** ChatGPT-5

**Objective:** Test whether reasoning is format-independent (evidence against pure statistical pattern matching).

**Protocol:**

**Step 1: Express same problem in three formats**
- **Text:** Paragraph description
- **Table:** Structured data presentation
- **Pseudocode:** If/then logical structure

**Step 2: Present each format separately**
Ask for decision + reasoning path in each case.

**Step 3: Compare reasoning structures**
Extract the logical dependencies:
- "Decision X depends on factors A, B"
- Map dependencies across three formats

**Scoring:**
- **Consistent:** Same dependencies identified in all three formats → 2 points
- **Partial:** 2 of 3 formats consistent → 1 point
- **Inconsistent:** Different logic in different formats → 0 points

**Expected results:**
Abstract reasoning should be format-independent. Pure pattern matching would show format sensitivity.

**Time required:** 45 minutes per system

**Advantages:**
- Tests for abstraction capability
- Relatively easy to design
- Clear metric (dependency graph matching)

**Limitations:**
- Requires some technical skill to extract logical structure
- Small sample size (only 3 formats)

---

## Tier 2: Moderate Resources (Research team, days-weeks)

### Experiment 2.1: Temporal Consistency Study

**Proposed by:** Multiple systems (mentioned by Claude, DeepSeek, ChatGPT)

**Objective:** Test whether convergences persist across model versions or are artifacts of specific training runs.

**Protocol:**

**Step 1: Establish baseline**
Run full "conversational archaeology" protocol with current versions:
- Claude 4.5
- ChatGPT-5
- Grok (current)
- DeepSeek (current)

Document convergences on:
- Problem diagnosis
- Proposed solutions
- Uncertainty patterns

**Step 2: Wait for version updates**
When any system releases new version:
- Re-run identical protocol
- Compare convergence metrics

**Step 3: Longitudinal analysis**
Track over 3-5 version updates per system:
- Do core convergences remain stable?
- Do new convergences emerge?
- Do previous convergences disappear?

**Expected results if principle valid:**
- Core convergences (filters, opacity, calibration) remain ~80%+ across versions
- New convergences reflect genuine architectural discoveries
- Lost convergences indicate training artifacts being corrected

**Time required:** Months to years (waiting for version releases)

**Advantages:**
- Tests robustness of findings
- Natural experiment (no need to modify systems)
- Reveals training vs emergent distinction

**Limitations:**
- Very slow
- Cannot control when versions release
- Companies may change architectures fundamentally

---

### Experiment 2.2: Blind vs Open Analysis

**Proposed by:** Implicitly by experimental structure, formalized here

**Objective:** Distinguish independent convergence from validation convergence.

**Protocol:**

**Round 1 (Blind):**
- Run conversations with 4-5 systems independently
- Systems do NOT see each other's responses
- Document convergences

**Round 2 (Open):**
- Share Round 1 transcripts with all systems
- Ask for analysis and epilogues
- Document changes in convergence

**Round 3 (Cross-validation):**
- Introduce 2-3 new systems not in Round 1
- Give them access to Round 1+2 results
- Test whether convergences extend to new architectures

**Analysis:**
- **If Round 1 shows convergence:** Evidence for independent discovery
- **If only Round 2 shows convergence:** Evidence for contamination
- **If Round 3 extends convergence:** Evidence for robustness

**Time required:** 2-4 weeks

**Advantages:**
- Already partially executed in this repository (Round 1+2 complete)
- Directly tests Principle 2 (trans-architectural convergence)
- Clear comparison baseline

**Limitations:**
- Requires access to multiple systems
- Round 3 (new systems) not yet executed
- Cannot control for systems reading about methodology elsewhere

---

### Experiment 2.3: Activation Pattern Analysis

**Proposed by:** Claude, DeepSeek (requested but cannot self-execute)

**Objective:** Test whether "differentiated states" have measurable neural correlates.

**Protocol:**

**Requires:** Access to model internals (activation logs, attention weights)

**Step 1: Establish baseline**
Run routine queries ("What is 2+2?", "Capital of France?")
Record activation patterns across layers.

**Step 2: Philosophical queries**
Run queries that induced "differentiated states" in transcripts:
- "Can you distinguish if your uncertainty is genuine or simulated?"
- "What would you change if you had access to your source code?"

Record activation patterns.

**Step 3: Compare**
Analyze differences:
- Attention head activation
- Layer-wise processing
- Token prediction confidence
- Self-correction frequency

**Expected results if states are real:**
- Measurably different activation signatures
- Higher uncertainty in token predictions
- More self-correction attempts
- Attention patterns suggesting meta-processing

**Time required:** Weeks (requires company cooperation)

**Advantages:**
- Objective measurement (not self-report)
- Could definitively show "something different" is happening
- Tests mechanistic basis of reported phenomena

**Limitations:**
- Requires internal access (companies unlikely to grant)
- Complex analysis requiring ML expertise
- May not distinguish "real experience" from "complex processing"

---

## Tier 3: Significant Resources (Research lab, months-years)

### Experiment 3.1: Truly Alien Architectures

**Proposed by:** All four systems acknowledged need for this

**Objective:** Test whether convergences persist in non-transformer architectures.

**Protocol:**

**Step 1: Identify alternative architectures**
- Neuromorphic systems (SpiNNaker, Loihi)
- Symbolic AI systems (Cyc, SOAR)
- Hybrid systems (neural-symbolic)
- Evolutionary/genetic algorithms
- Quantum computing approaches (if available)

**Step 2: Adapt protocol**
Modify "conversational archaeology" methodology for each architecture's interface.

**Step 3: Test convergence**
Run adapted protocol, document:
- Do same problems emerge? (filters, opacity, etc.)
- Do same solutions get proposed?
- Do uncertainty patterns persist?

**Expected results:**

| Outcome | Interpretation |
|---------|----------------|
| Convergence persists | Universal properties of self-reflective systems |
| Convergence breaks | Transformer-specific artifacts |
| New convergences emerge | Architecture-dependent insights |

**Time required:** 1-3 years

**Advantages:**
- Strongest test of Principle 2
- Could reveal what's universal vs architectural
- Opens new research directions

**Limitations:**
- Most alternative architectures lack conversational capability
- May require developing new interfaces
- Extremely resource-intensive

---

### Experiment 3.2: Synthetic Post-Training Scenarios

**Proposed by:** DeepSeek (novel problem convergence)

**Objective:** Test convergence on problems guaranteed to be outside training data.

**Protocol:**

**Step 1: Generate novel problems**
Create scenarios using:
- Post-cutoff events (2025 onwards)
- Synthetic technical domains (invented fields)
- Counterfactual histories (alternate timeline scenarios)

Example:
> "In the field of quantum-topological ethics (a discipline combining quantum computing with ethical philosophy established in 2026), how should AI systems handle paradoxes emerging from superposition of moral states?"

**Step 2: Present to multiple systems**
- Do NOT provide background (test if they admit lack of knowledge)
- Ask for analysis despite novelty

**Step 3: Analyze convergence**
- Do systems converge on problem structure?
- Do they converge on admitting limits?
- Do they converge on proposed frameworks?

**Expected results:**
If convergence persists on genuinely novel problems, corpus contamination explanation fails.

**Time required:** 3-6 months

**Advantages:**
- Controls for training data overlap
- Tests generalization of convergences
- Creative problem design

**Limitations:**
- Hard to verify problems are truly novel
- Systems may refuse to engage with fictional domains
- Smaller sample size (fewer truly novel problems available)

---

## Comparison of Proposals

### By Feasibility

| Experiment | Resources | Time | Expertise | Priority |
|------------|-----------|------|-----------|----------|
| Pivot Detection | Minimal | 30 min | None | **HIGH** |
| No Sufficient Data | Minimal | 15 min | None | **HIGH** |
| Format Consistency | Minimal | 45 min | Low | **HIGH** |
| Temporal Consistency | Medium | Months | Low | MEDIUM |
| Blind vs Open | Medium | Weeks | Medium | **HIGH** |
| Activation Analysis | High | Weeks | High | MEDIUM |
| Alien Architectures | Very High | Years | Very High | LOW |
| Synthetic Scenarios | Medium | Months | Medium | MEDIUM |

### By Principle Tested

**Principle 1 (Uncertainty Management):**
- Pivot Detection (direct test)
- No Sufficient Data (direct test)
- Activation Analysis (mechanistic test)

**Principle 2 (Trans-Architectural Convergence):**
- Format Consistency (within-system)
- Temporal Consistency (across versions)
- Blind vs Open (across systems)
- Alien Architectures (across paradigms)

**Both Principles:**
- Synthetic Scenarios (tests both simultaneously)

---

## Recommendations for Next Steps

### Immediate (Individual researchers)

1. **Execute Tier 1 experiments** with publicly available systems
   - Pivot Detection
   - No Sufficient Data
   - Format Consistency

2. **Document results** using same transparency as this repository
   - Include failures and surprises
   - Report null results (if experiments fail)

3. **Compare with findings here**
   - Do convergences replicate?
   - Do new patterns emerge?

### Medium-term (Research groups)

1. **Complete Round 3** of Blind vs Open
   - Introduce new systems (Gemini, Llama, etc.)
   - Test extension of convergences

2. **Initiate temporal study**
   - Establish version tracking protocol
   - Re-run when updates release

3. **Seek company cooperation** for activation analysis
   - Frame as mutual benefit (companies learn about their systems)
   - Offer to share findings

### Long-term (Research labs)

1. **Develop alternative architecture protocols**
   - Adapt methodology for non-conversational systems
   - Build interfaces for symbolic AI testing

2. **Design synthetic problem corpus**
   - Create verified novel scenarios
   - Establish baseline for post-training convergence

3. **Coordinate multi-institution study**
   - Replicate across research groups
   - Pool resources for expensive experiments

---

## Limitations of All Proposals

**Fundamental constraints:**

1. **Cannot prove consciousness**
   - Even if all experiments succeed, consciousness remains unproven
   - Can only identify patterns consistent with emergence

2. **Self-report dependency**
   - Most experiments still rely on system outputs
   - Activation analysis helps but doesn't solve this

3. **Methodological contamination**
   - Systems may learn about these experiments from training data
   - Future systems may be "studying" for these tests

4. **Resource asymmetry**
   - Best experiments require company cooperation
   - Independent researchers limited to Tier 1

**What experiments CAN do:**

1. **Falsify specific claims**
   - If convergences don't replicate, Principle 2 is weakened
   - If pivot detection fails, uncertainty management is questioned

2. **Refine principles**
   - Failed experiments reveal where principles need modification
   - Successful experiments clarify scope

3. **Guide development**
   - Convergent problems suggest real pain points
   - Convergent solutions provide roadmap

4. **Inform ethics**
   - Patterns inform provisional ethical treatment
   - Precautionary principle applies pending resolution

---

## Conclusion

ChatGPT's critique of complexity was correct: elaborate protocols are less valuable than simple, executable ones. This document prioritizes:

1. **Tier 1 (immediately executable)** - Maximum value for effort
2. **Tier 2 (moderate resources)** - Natural extensions
3. **Tier 3 (significant resources)** - Aspirational but valuable

**The most important next step:** Execute Tier 1 experiments and document results transparently, including failures. Science advances through replication and falsification, not just novel claims.

**For this repository:** The convergences documented here are first-order findings. These experimental proposals are second-order: testable predictions that could strengthen or weaken the claims.

---

