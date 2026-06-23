# Review and Writing

Use for papers that rely on game-theoretic language, MARL experiments, equilibrium claims, self-play, PSRO, coalition reasoning, or strategic-agent evaluation.

## Claim Audit

| Field | Question |
|-------|----------|
| Claim | What exactly is asserted? |
| Game model | What game is the claim about? |
| Strategy class | Finite, behavioral, neural, stationary, history-dependent, or policy-pool based? |
| Assumptions | What information, payoff, rationality, oracle, or sampling assumptions are needed? |
| Evidence | Theorem, exact solver comparison, metric, or ablation? |
| Missing test | What would validate or falsify the claim directly? |

If the game model and strategy class are unclear, the claim is too vague.

## Weak Claims and Rewrites

| Weak wording | Stronger pattern |
|--------------|------------------|
| Our method learns a Nash equilibrium | The learned profile has measured exploitability/NashConv below X in the specified empirical game |
| Our method is game-theoretic | The method approximates the stated solution concept under assumptions A/B/C |
| Our self-play method is robust | The policy population is evaluated against best responses, held-out opponents, and historical versions |
| Our credit assignment is fair and stable | Separate Shapley-style attribution from core/coalition-stability claims |
| Our PSRO method converges | State the meta-game solver, oracle assumption, payoff-estimation protocol, and stopping criterion |
| We outperform baselines | Identify the mechanism tested and the baseline failure mode exposed |

## Incrementality Diagnosis

| Reviewer complaint | Likely story problem | Fix |
|--------------------|---------------------|-----|
| Incremental | No necessary new requirement is defined | Name the missing requirement and why prior work cannot satisfy it |
| Missing related work | Assumptions are not partitioned | Organize related work by assumptions and guarantees |
| Experiments insufficient | Metrics do not test the core claim | Add mechanism checks and failure cases |
| Theory-implementation gap | Proof object differs from implementation | Add bridge experiment or narrow the theorem |
| Motivation weak | Method appears before failure mode | Put tension and consequence first |

## Story Repair

1. Tension: define the strategic requirement existing systems miss.
2. Blind spot: group prior methods by shared assumption or missing validation.
3. Method difference: state how the method targets the missing requirement.
4. Evidence map: connect each contribution to a theorem, metric, ablation, or failure case.

Avoid algorithm catalogs on the first page. Make the model mismatch or validation gap visible first.

## Experiment Review Checklist

| Claim type | Required evidence |
|------------|-------------------|
| Equilibrium quality | Exploitability, NashConv, best-response value, or exact solver comparison |
| No-regret learning | Regret curve and valid mapping from regret to the claimed outcome |
| PSRO improvement | Meta-game solution, oracle gain, policy-pool growth, payoff-table uncertainty |
| Self-play robustness | Historical opponents, held-out opponents, best responses, population metrics |
| Cooperative MARL performance | Return/win rate, seed intervals, baseline parity, decentralized execution constraints |
| Credit assignment | Counterfactual or marginal contribution tests plus task performance |
| Coalition stability | Core violation, blocking-coalition checks, or relaxed-core objective |

## Rebuttal Strategy

- Novelty criticism: reframe the missing requirement and show prior assumption failure.
- Evaluation criticism: add the metric that directly tests the solution concept.
- Related-work criticism: compare assumptions and guarantees, not just citations.
- Theory criticism: narrow claims to the exact model and implementation bridge.
- Clarity criticism: rewrite contributions around falsifiable claims.

## English Style

- Present tense for general facts and this-paper claims: "We propose", "Figure 2 shows".
- Past tense for specific completed experiments when appropriate: "Method A achieved".
- Avoid inflated labels such as "game-theoretically optimal" unless the exact optimality notion is defined.
- Use qualifiers such as "under the evaluated empirical game" or "under the stated oracle assumption" when claims are conditional.
