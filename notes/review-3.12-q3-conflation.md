# Adversarial review — branch 3.12, four-integer conflation removal

Reviewer: independent adversarial referee (did not author the changes).
Scope: `git diff main...HEAD` on branch 3.12. At review time HEAD advanced twice during
the session: 7aff57d (main correction, 13 files), 6c92ae2 (B.8 `comp` argument), and
d71cd3f (O18 v2.0 hypothesis restatement, outside the seven rulings; reviewed anyway,
see Finding 9). Compiled artifacts in `out/` were verified current with HEAD
(build 2026-08-14 23:38:33; PDF contains both the `comp; g, u` argument and the new O18
citation title).

## Blocking findings

### 1. Chapter 5 still asserts that the electromagnetic winding w organizes the mass spectrum

`tex/2-dynamics_and_particles/05-projection-gauge/003-topological-constraints.tex:52-54`:

> "The winding number~$w$ labels distinct equivalence classes of admissible projected
> configurations and plays a central role in the organization of the mass spectrum
> (Section~\ref{sec:spectral-mass-hierarchy})."

The revised chapter 11 scope sentence
(`tex/5-predictions_discussion_conclusion/11-spectral-mass-hierarchy/spectral-mass-hierarchy.tex:21-25`)
states the opposite: the torsion sector index r "is distinct from the electromagnetic
fiber winding~$w$ of Section~\ref{sec:topological-constraints}, and no identification of
a torsion sector with a specific particle is made in this chapter." The two sections now
cross-reference each other with contradictory claims. The chapter-5 sentence is a
surviving instance of the retracted w-to-mass-sector conflation and must be rewritten
(e.g. restrict it to the rest-energy cost of maintaining a winding, without claiming a
central role in the chapter-11 hierarchy).

### 2. Chapter 9 summary still asserts the retracted strong-sector mechanism

`tex/4-quantum_mechanics/09-quantum_phenomena_and_entanglement/013-summary-quantum.tex:8-9`:

> "Strong interactions and confinement are reinterpreted through topological stability
> of knotted solitonic configurations."

This is the summary of the same chapter whose strong-sector subsection
(`tex/4-quantum_mechanics/09-quantum_phenomena_and_entanglement/011-standard-model.tex:57-61`)
now states, per ruling 2, that the origin of color charge, confinement, and asymptotic
freedom "is an open problem" and that no topological invariant identifying composite
sectors and no confinement mechanism is currently derived. The summary asserts as
achieved what the body declares open. The sentence must be aligned with the
open-problem statement.

## Minor findings

### 3. Chapter 2 confinement paragraph in tension with the open-problem posture

`tex/1-foundations/02-definition-and-fundamental-properties-of-the-chi-field/011-energy-mass-constants.tex:47-54`:
"Confinement reflects a structural constraint ..." and "Quark confinement thus appears
as a direct consequence of the non-injective character of the projection." The register
is interpretive rather than a derivation claim, and it does not use the retracted
integers, but after ruling 2 the framework officially derives no confinement mechanism.
Recommend a hedged formulation ("could be interpreted as", or an explicit pointer to the
open problem).

### 4. Undefined `comp` argument in the B.8 feasibility condition

`tex/6-appendices/appB/008-perspectives-mass.tex:64` (commit 6c92ae2) writes
`\lambda_{\mathrm{bind}}(\mathrm{comp};\,g,u)` while every other occurrence of
`\lambda_{\mathrm{bind}}` in B.8 (lines 13, 21, 76) and B.9 is bare, and the token
`comp` is never introduced. The reader can infer it from line 16 ("a characteristic
composite-sector scale"), and the parameterization-only-in-the-feasibility-condition
pattern matches the pre-existing `\lambda_e(g,u)`, so the sentence still reads
correctly; but the label should either be introduced ("where comp denotes the composite
bound sector") or dropped. Not blocking.

### 5. Residual legacy names in labels, file names, and one heading (invisible in output)

`eq:muon-ratio-final` (002-noncommutativity-mass.tex:97), `sec:leptonic-synthesis`
(002:73), `sec:baryonic-sector` (004-baryonic-sector.tex:2), `eq:Aw-fredholm` (002:38),
and the file name `004-baryonic-sector.tex` retain pre-revision names. Keeping them is
the correct choice for label stability (point C) and none of them appears in the PDF;
recorded here only so a future rename is done deliberately, with its cascade.

### 6. Strong-sector heading still names the open results

`tex/4-quantum_mechanics/09-quantum_phenomena_and_entanglement/011-standard-model.tex:54`:
the starred heading "Strong Sector: Topological Confinement and Color" reads like a
result while the body states open problems. It is not TOC-visible (starred). Consider
"Strong Sector: Open Problems". Cosmetic.

### 7. Pre-existing lambda_p vs lambda_bind notation split in B.9

`tex/6-appendices/appB/009-spectral-scaling.tex:9` uses $\lambda_p$ in prose while the
figure and the rest of B.8/B.9 use $\lambda_{\mathrm{bind}}$. Pre-existing, untouched by
this diff; noted for completeness.

### 8. Stale untracked build artifacts still carry the retracted material

`tex/Cosmochrony.aux` and `tex/Cosmochrony.bbl` (untracked, mtime May 14) still contain
`BattyeSutcliffe2022` and `eq:massratio_topo`. They are outside `out/` and not part of
the deposit, but a compile run without `-output-directory` would pick them up. Recommend
removing them (deletion requires permission) or adding them to .gitignore hygiene.

### 9. Out-of-scope commit d71cd3f landed on the branch during review

"State the conjugate-pair fibre structure as a hypothesis (O18 v2.0)" touches
`tex/1-foundations/02-definition-and-fundamental-properties-of-the-chi-field/004-relational-projection.tex`
and the Beau2026a22 title in `tex/cosmochrony-bibliography.bib`. It is not covered by
the seven rulings. Content reviewed: it downgrades a proved-necessity claim to a
structurally motivated hypothesis with the fibre identification stated as open — the
right epistemic direction, no withdrawal narration, no interaction with the
four-integer separation. The build was re-run after it (bbl and PDF carry the new O18
title). No defect; recorded because the review gate should know the branch tip moved.

## Verified clean (no finding)

- A. Completeness: zero occurrences in any tracked .tex/.bib of: trefoil, triality,
  Q=3/Q{=}3, w=3 (any sector-identification sense), w_p/w_e winding labels, the 27
  multiplicity factor (3^3, 27 chi_c^2), the 8.3 value of chi-tilde_c,
  BattyeSutcliffe, massratio_topo, or any electron/muon/proton identification of the
  chapter-11 sectors r=1,2,3. Abstract (`tex/abstract.tex`), introduction plan,
  conclusion, and TOC-visible titles clean; the only remaining "parameter-free"
  relation is the boxed m_(2)/m_(1) with no measured-value agreement claimed anywhere;
  the only remaining m_p/m_e statements are the ruled exploratory B.8/B.9 material and
  the ch. 13 list of constants the framework does NOT explain. Remaining generic
  "knot"/"knotted" language (ch. 4, appE.8) carries no trefoil or N_c content. B.9's
  "$Q{=}1$" label on the fundamental mode is the retained soliton degree of the B.2
  table, not the excised Q=3.
- B. No-narration: no "previously / no longer / removed / withdrawn / earlier draft"
  phrasing in any changed file or any added diff line.
- C. Label integrity: the only deleted label is `eq:massratio_topo` (ruled excision);
  nothing references it (the sole former `\ref{sec:baryonic-sector}` lived inside the
  excised E.9 block and left with it). `sec:baryonic-sector` and
  `sec:leptonic-synthesis` still exist; they have no incoming `\ref` sites, so nothing
  dangles.
- D. Internal consistency: chapter 11 uses the abstract index r throughout
  (Omega_r, A(r), H_adm^(r), m_(1), m_(2), m_(3)); the only $w$ in the chapter is the
  legitimate contrast sentence in the chapter intro. `m_{(1)}` is introduced coherently
  in 001-spectral-stability.tex ("reference mass scale ... lowest non-trivial
  admissible eigenmode"). The prose around the boxed relation claims no agreement with
  the measured muon/electron value.
- E. New statements: the SU(3)-open transmittance item, the strong-sector open-problems
  paragraph, the B.2 row ("Spin-1/2; charge from winding n, not Q" — consistent with
  the table's own n index for the U(1) winding), and the B.8 "composite bound sector"
  sentence make no new unproved identifications (three-constituent language fully
  absent).
- F. Bibliography and build: `Manton2022` is a well-formed @book (Manton, N. S.,
  "Skyrmions --- A Theory of Nuclei", World Scientific, London, 2022,
  DOI 10.1142/q0368 — matching the actual World Scientific Europe volume).
  `out/Cosmochrony.bbl` contains Manton2022 (item 72) and no BattyeSutcliffe entry.
  `out/Cosmochrony.log` (23:38 build, current with HEAD): 0 "undefined" matches, no
  `^!` LaTeX errors, no multiply-defined labels; `out/Cosmochrony.blg`: 0 errors, only
  pre-existing brace-balance warnings on old entries (Dirac1930, Weinberg1972,
  Rovelli2004).

## Verdict

FAIL — the deposit gate must not proceed until:

1. `tex/2-dynamics_and_particles/05-projection-gauge/003-topological-constraints.tex:52-54`
   no longer asserts that the electromagnetic winding w plays a central role in the
   organization of the chapter-11 mass spectrum (contradiction with the new scope
   sentence).
2. `tex/4-quantum_mechanics/09-quantum_phenomena_and_entanglement/013-summary-quantum.tex:8-9`
   no longer asserts the strong-sector reinterpretation that the same chapter now
   states as an open problem.

After both one-sentence fixes and a full recompile (pdflatex, bibtex, pdflatex twice,
log grep), the remainder of the revision is deposit-ready; minor findings 3-8 are
recommended but not gating.

# Focused re-review — branch 3.13, fix commit 5953463

Scope of this pass, per the reopened gate: verify only that commit 5953463 (HEAD of
branch 3.13, which also carries d71cd3f reviewed above) resolves blocking findings 1
and 2 and minor finding 6, introduces no new defect, and that the build is current.
The earlier full pass was not redone.

## a) Resolution of the findings

Finding 1 — RESOLVED.
`tex/2-dynamics_and_particles/05-projection-gauge/003-topological-constraints.tex:52-59`
now reads: the winding number w "organizes the quantization of electric charge"; "The
organization of the mass spectrum is carried by a distinct abstract torsion sector
index (Section~\ref{sec:spectral-mass-hierarchy})"; and the rest-energy sentence now
refers to "a non-trivial topological structure" rather than "a non-trivial winding".
The mutual cross-reference is now consistent in both directions: chapter 11's scope
sentence (spectral-mass-hierarchy.tex:21-25) says r is distinct from the w of
Section~\ref{sec:topological-constraints}, and chapter 5 now says the mass spectrum is
carried by that distinct index and cites chapter 11 for it. The retained closing
sentence ("Mass emerges as a spectral and topological consequence of persistent
non-contractible structures within the projection fiber") no longer names w and is
compatible with the torsion-sector mechanism. No residual contradiction.

Finding 2 — RESOLVED.
`tex/4-quantum_mechanics/09-quantum_phenomena_and_entanglement/013-summary-quantum.tex:8-9`
now reads "The origin of strong interactions and confinement within the projection
framework remains an open problem", matching verbatim in substance the strong-sector
subsection body (011-standard-model.tex:57-61). The summary paragraph still flows
(gauge bosons, then strong sector, then mass, then entanglement).

Finding 6 (minor) — RESOLVED.
The starred heading is now "Strong Sector: Color and Confinement as Open Problems"
(011-standard-model.tex:54); label `subsec:qcd-topology` unchanged, heading not
TOC-visible, and it now matches the body.

## b) New sentences: overclaim, narration, terminology

No overclaim: both new statements are status assertions weaker than what they
replaced. No withdrawal narration: "remains an open problem" is current-status
phrasing already used throughout the paper; a sweep of the three files for
narration/withdrawal vocabulary and for the retracted phrase "central role" returned
nothing. No new undefined term: "abstract torsion sector index" is exactly the term
the chapter-11 intro defines at the target of the accompanying cross-reference.
One stylistic remark, not a finding: the sentence "the winding number w ... organizes
the quantization of electric charge" slightly restates the immediately preceding
Proposition (Charge quantisation); harmless redundancy.

## c) Commit scope and the remaining taxonomy mention

`git show 5953463 --stat` confirms exactly the three files above are touched
(10 insertions, 8 deletions), nothing else. The generic taxonomy mention at
`tex/2-dynamics_and_particles/04-particles-as-localized-excitations-of-the-chi-field/002-topological-stability.tex:18`
("vortex, skyrmion, and knotted configurations") remains a pointer to the Appendix B
soliton constructions with no trefoil, color, or multiplicity content — still
non-gating in my judgment.

## d) Build currency and cleanliness

Working tree clean under tex/ and out/. Build timestamps 23:45:39 (log, PDF), equal to
the commit time of 5953463; log header confirms the 23:45 run. Zero "undefined"
matches and zero `^!` error lines in out/Cosmochrony.log. Extracted PDF text contains
all three new formulations ("Color and Confinement as Open Problems", "remains an open
problem", "carried by a distinct abstract", "organizes the quantization of electric")
and zero occurrences of the retracted summary sentence ("reinterpreted through
topological").

## Verdict (3.13 tree)

PASS — deposit gate may proceed to Jérôme. Non-gating minor findings 3, 4, 5, 7, 8 of
the first pass remain open as recommendations.
