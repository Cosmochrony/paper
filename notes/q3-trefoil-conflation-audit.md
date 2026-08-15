# White-paper corrective audit: the $Q=3$ / $w=3$ / trefoil conflation

Status: loose working note, untracked, never committed. Date: 2026-08-14.
Mandate (Jérôme's decision, 2026-08-14, recorded in `../../front-inertia-spectral-distance-recon.md`
§9): targeted corrective audit of the white paper before any Stage B — (i) inventory the consumers of
the conflation, (ii) remove or redefine $Q=3$, (iii) drop the $27$ factor unless independently
re-derived, (iv) repair the invalid `BattyeSutcliffe2022` reference. No white-paper source is
modified by this note; patches below were proposals and are ruled in §5, before
surgical edits, full compile, independent review, and the separate publication go.

## 1. The defect being corrected

The accepted dictionary (front note §9.2/§9.4, with Jérôme's corrections) separates four integers the
white paper currently conflates: the electromagnetic fiber winding $w_{\mathrm{em}} \in \pi_1(S^1)$
(with the corpus's own formula $q_{\mathrm{eff}} = w e$, `003-topological-constraints.tex:48`), the
constituent/triality multiplicity $N_c = 3$, the knot type $K$ (the trefoil is $T(2,3)$), and an
independent soliton degree $Q_{\mathrm{sol}}$ (Skyrme $B \in \pi_3(S^3)$, nucleon at $B = 1$; or a
Hopf charge $Q_H \in \pi_3(S^2)$, with no established proton identification — knotted minimisers
exist at various charges and the knot type does not determine $Q_H$). Identifying the proton with a
$w = 3$ sector contradicts $q_{\mathrm{eff}} = we$ (it would give charge $3e$); no bridge between
$N_c$, triality, and the $T(2,3)$ index is derived anywhere in the corpus.

## 2. Inventory of consumers (exhaustive grep pass, 2026-08-14)

Greps run over `tex/` for: `trefoil`, `triality`, `Q=3` (all spacings), `w=3`, `w_p`,
`BattyeSutcliffe`, `massratio_topo`, `tilde{\chi}_c`, `8.3`, `q_{\mathrm{eff}}`.
Cross-repo greps (`foundation/`, `sm-charge-masse-paper/`, `program/`, `cosmochrony.github.io/`)
found NO spillover of `trefoil`, `BattyeSutcliffe2022`, or the $27$/$1836$ estimate. `program/tex/`
carries none of these claims. The blast radius is the white paper alone (plus its website page and a
new Zenodo version, per the standard cascade).

### Core sites (inside the mandate)

| # | Site | Content | Defect |
|---|------|---------|--------|
| 1 | `05-projection-gauge/002-gauges-transmittance.tex:34-38` | $SU(3)$ from "triality structure of the minimal self-intersecting stable soliton, identified with the trefoil knot ($w=3$)" | trefoil$\,=w{=}3\,$= triality, all three unproved; contradicts $q_{\mathrm{eff}}=we$ |
| 2 | `6-appendices/appE/009-spin-statistics.tex:21-72` | "Topological mass ratios (heuristic)": proton $= w{=}3$ trefoil sector $\Rightarrow$ factor $w_p^3/w_e^3=27$; $\tilde\chi_c\approx8.3$; $27\tilde\chi_c^2\approx1860$ vs $1836$; `eq:massratio_topo` | assumption 1 is the conflation; the whole estimate is anchored to it |
| 3 | `09-quantum.../011-standard-model.tex:57-62` | color = "three fundamental degrees of freedom of the proton's trefoil topology ($Q=3$)"; confinement from separating a $Q=3$ soliton | same conflation, $Q$ variant |
| 4 | `6-appendices/appB/008-perspectives-mass.tex:4-7,63-65` | proton as "composite bound state within a $Q=3$ sector", citing `BattyeSutcliffe2022, MantonSutcliffe2004`; $\lambda_{\mathrm{bind}}(Q{=}3;g,u)$ | $Q=3$ label undefined; first citation invalid |
| 5 | `6-appendices/appB/009-spectral-scaling.tex:30` | TikZ band label "$\lambda_{\mathrm{bind}}$ band ($Q{=}3$)" | same label |
| 6 | `6-appendices/appB/002-topological-solitons.tex:110-131` | summary table: "Skyrmion, $Q=\pm1$, Charge $\propto Q$" | charge tied to soliton degree — second route to the $3e$ problem; the Skyrme anchor separates charge from degree |
| 7 | `tex/references.bib:327-335` | `BattyeSutcliffe2022`: "Battye, Paul M. and Sutcliffe, Paul M., Skyrmion Solutions and Baryon Structure, Ann. Rev. Nucl. Part. Sci. 72 (2022)" | bibliographically nonexistent: DOI `10.1146/annurev-nucl-111919-092432` returns 404 on Crossref (verified 2026-08-14); title unfindable; Battye's first name is Richard, not Paul |

### Adjacent consumers (same missing dictionary — flagged for ruling, arguably beyond the strict mandate)

| # | Site | Content | Issue |
|---|------|---------|-------|
| 8 | `11-spectral-mass-hierarchy/003-irreducible-torsion.tex:86-88` and `004-baryonic-sector.tex` (whole) | the $w=3$ torsion sector read as "baryonic", $m_{w=3}/m_{w=1}\sim\sqrt{\lambda^{(3)}_{\mathrm{bind}}/\lambda_1}$ | if $w$ is the EM winding of `003-topological-constraints.tex:48`, a $w=3$ sector carries charge $3e$ and cannot be the proton; the irreducibility mathematics itself is index-agnostic and salvageable |
| 9 | same chapter, `002-noncommutativity-mass.tex` | $w=1$ "fundamental lepton", $w=2$ Pisano sector | same tension one step earlier: a $w=2$ sector carries charge $2e$; outside the mandate, recorded for a separate ruling |

Self-contained: `eq:massratio_topo` and $\tilde\chi_c \approx 8.3$ are referenced nowhere outside
E.9; the definition of $\tilde\chi_c$ in `appF/001-fundamental-quantities.tex` is independent and
unaffected.

## 3. Proposed patches (per site; options where a real choice exists)

All patches follow the current-result-only rule: no chronological language, no withdrawal
narration — the retracted content simply is not there.

1. **Transmittance (site 1).** Remove "identified with the trefoil knot ($w=3$)" and the triality
   attribution; retype the $SU(3)$ item as: associated with topological constraints of projected
   configurations, threefold structure **posited** (open), with no knot identification. Option (a):
   keep a weakened "threefold structure [open]" sentence; option (b): reduce the item to the generic
   topological-constraint statement only. **Ruling needed: (a) or (b).**
2. **E.9 (site 2).** Excise the heuristic mass-ratio block entirely: the "Topological mass ratios
   (heuristic)" paragraph, the status paragraph, the two-assumption ansatz, `eq:massratio_topo`, and
   the first-principles outlook sentence that consumes it. The spin-statistics content of E.9
   (fermionic/bosonic $4\pi/2\pi$) stays. Rationale: assumption 1 is retracted and no independent
   re-derivation of $27$ exists; $\tilde\chi_c \approx 8.3$ has no other anchor. Label check:
   `eq:massratio_topo` is cited nowhere else (verified).
3. **Standard Model section (site 3).** Replace the two sentences by a conditional statement:
   color-like threefold structure and confinement are **open problems** for the composite sector;
   no topological mechanism is currently derived. Option (b): delete the "Strong Sector" subsection
   content down to the asymptotic-freedom sentence. **Ruling needed: retype vs delete.**
4. **B.8 (site 4).** Replace "within a $Q=3$ sector" by "within a composite bound sector (three
   constituents; the constituent multiplicity is not a fiber winding and carries no charge
   assignment)"; replace $\lambda_{\mathrm{bind}}(Q{=}3;g,u)$ by
   $\lambda_{\mathrm{bind}}(\mathrm{comp};g,u)$ or simply $\lambda_{\mathrm{bind}}(g,u)$; fix the
   citation (see 7).
5. **B.9 figure (site 5).** Relabel the band "($Q{=}3$)" $\to$ "(composite)".
6. **B.2 table (site 6).** Fix the Skyrmion row's charge column: charge is set by the oriented
   fiber winding (as in the vortical row), not by the soliton index; the $Q=\pm1$ index carries the
   spin-$\tfrac12$/statistics property only.
7. **references.bib (site 7).** Delete `BattyeSutcliffe2022`; add
   `Manton2022`: N.S. Manton, *Skyrmions — A Theory of Nuclei*, World Scientific, London (2022),
   ISBN 978-1-80061-247-1 (existence web-verified 2026-08-14; exact DOI to be taken from the
   publisher page during the edit pass). Update B.8's `\cite` to
   `\cite{Manton2022, MantonSutcliffe2004}`. `MantonSutcliffe2004` verified genuine.
8. **Mass-hierarchy chapter (site 8) — ruling needed.** Option (a): keep the spectral mathematics,
   relabel the sector index as an abstract torsion index explicitly decoupled from the EM winding
   (one scope sentence at the chapter head), and remove "baryonic" identifications; option (b):
   remove `004-baryonic-sector.tex` from the compile and keep `003`'s $w=3$ material as generic
   higher-sector structure. Site 9 ($w=2$/Pisano) is recorded but left for a separate decision.

## 4. Protocol after ruling

Surgical edits on a version branch off `main` (never on `main`); full compile chain
(`pdflatex -> bibtex -> pdflatex x2`) with log filtering for unresolved references AND errors;
exhaustive re-grep of every retracted phrase over the whole tex tree (tables, notes, conclusion)
per the cascade-retraction rule; independent adversarial review of the final artefact; then
Jérôme's explicit go; then Zenodo new version (patch bump), merge-back, website page update
(EN + FR per the translation protocol), deploy, and verification of the live pages. The
`program/` registry needs no content change (verified) beyond its normal cascade decision.

## 5. Arbitration rulings (2026-08-14)

These rulings authorise preparation of the surgical source patch on a version branch, but do not
authorise publication. The patched PDF must still pass independent review and receive a separate
post-review publication go.

1. **Transmittance: choose option (b), strengthened.** Remove the trefoil, $w=3$, and triality
   identifications. Do not retain an unattributed ``threefold structure'' as a weakened factual claim.
   State instead that deriving an $SU(3)$-like strong sector from projected topological constraints is
   open; no knot, winding, or soliton-degree mechanism is presently established.
2. **Standard Model strong-sector block: retype, do not silently delete.** Replace the three claimed
   mechanisms by an explicit open-problem paragraph: the framework has not derived colour $SU(3)$,
   confinement, or asymptotic freedom from a specified topological carrier. This preserves the
   programme's intended destination while removing unsupported results.
3. **Mass-hierarchy chapter: preserve the conditional spectral mathematics under a new abstract
   index.** Rename the torsion-sector label throughout the chapter (for example
   $r\in\mathbb N$, with operators $\Omega_r$) and state explicitly that $r$ is neither the
   electromagnetic winding $w_{\mathrm{em}}$ nor a particle label. Remove ``leptonic'', ``muon'',
   ``baryonic'', ``proton'', and corresponding particle-mass interpretations from the $r=1,2,3$
   material unless a separate bridge is supplied. This ruling includes adjacent site 9: correcting
   $r=3$ while leaving $w=2$ identified with a muon would preserve the same defect one step earlier.
   Conditional irreducibility, commutator, and spectral-invariant statements may remain when their
   hypotheses do not depend on the particle dictionary.
4. **Appendix E.9: excise the entire heuristic mass-ratio block.** The factor $27$, the value
   $\tilde\chi_c\approx8.3$ used there, `eq:massratio_topo`, and their outlook sentence have no
   independent derivation after $w_p/w_e=3$ is removed. The spin/statistics material before and after
   the block remains.
5. **B.8/B.9 wording:** use ``composite bound sector'', not ``three-constituent sector'', because the
   latter would introduce another unproved carrier dictionary. Use
   $\lambda_{\mathrm{bind}}(\mathrm{comp};g,u)$ consistently and relabel the figure ``(composite)''.
6. **B.2:** decouple electric charge from the soliton degree. Preserve a charge entry only as a
   separately specified oriented fiber winding; do not write charge proportional to $Q$.
7. **Bibliography:** replace the invalid `BattyeSutcliffe2022` entry with Nicholas S. Manton,
   *Skyrmions — A Theory of Nuclei*, World Scientific, 2022, ISBN 978-1-80061-247-1,
   DOI `10.1142/q0368`. Retain `MantonSutcliffe2004`. The Faddeev–Skyrme papers are comparative
   audit anchors and need not be inserted into B.8 unless the revised prose actually consumes them.

The correction is conceptually significant and therefore requires a new white-paper version and its
normal website/Zenodo propagation after review and explicit publication approval. No programme-paper
content change is required unless the final patch alters a statement actually present in the programme
registry; this must be rechecked against the final diff rather than assumed from the current audit.

## 6. Execution log (2026-08-14, post-ruling)

Surgical edits applied on branch `3.12` (cut off `main` at `a4cefb2`), commits `7aff57d` (13 files,
86 insertions, 146 deletions) and `6c92ae2` ($\lambda_{\mathrm{bind}}(\mathrm{comp};\,g,u)$ argument
per ruling 5), both pushed to `Cosmochrony/paper`.

Per-site outcome:

1. Transmittance: trefoil/$w=3$/triality removed; $SU(3)$ derivation stated as an open problem.
2. E.9: full excision of the heuristic block (27 factor, $\tilde\chi_c\approx8.3$,
   `eq:massratio_topo`, outlook sentence); spin-statistics content untouched.
3. Standard Model strong sector: sub-block kept, retyped as explicit open problems (color,
   confinement, asymptotic freedom).
4. B.8: ``composite bound sector'' (no constituent count); citation now
   `\cite{Manton2022, MantonSutcliffe2004}`; feasibility numerator
   $\lambda_{\mathrm{bind}}(\mathrm{comp};\,g,u)$.
5. B.9: band label ``(composite)''.
6. B.2: Skyrmion row now ``Spin-$\tfrac12$; charge from winding $n$, not $Q$''.
7. Bibliography: `BattyeSutcliffe2022` deleted; `Manton2022` added (book, World Scientific, 2022,
   DOI `10.1142/q0368` — verified to resolve via doi.org redirect to the publisher's book page).
8. Chapter 11: abstract torsion index $r$ throughout (`\Omega_r`, $\mathcal{A}(r)$,
   $H_{\mathrm{adm}}^{(r)}$); scope sentence added in the chapter head ($r$ distinct from the
   electromagnetic winding $w$ of `sec:topological-constraints`, no particle identification);
   $m_{(1)}$ reference scale in 001; boxed relation now $m_{(2)}/m_{(1)}$; outlook retyped to
   composite sectors; 004 retitled ``The Irreducible Sector and Spectral Hierarchy'' (label
   `sec:baryonic-sector` unchanged) with the proton--electron paragraph removed; $\Omega_r$ in 005.
   Site 9 ($w=2$) covered by the same $r$ relabelling. Labels `sec:leptonic-synthesis` and
   `eq:muon-ratio-final` kept unchanged per the label-stability rule.

Verification: exhaustive re-grep over `tex/` for every retracted term (trefoil, triality, $Q=3$ in
all spacings, $w_p$, `BattyeSutcliffe`, `massratio_topo`, the 27 factor) returns zero hits; the only
chapter-11 matches are the two immutable labels and the intentional scope sentence. Full compile
chain (`compile.sh`: pdflatex, bibtex, pdflatex x2) clean — zero errors, zero undefined citations or
references; `out/Cosmochrony.bbl` contains `Manton2022` and no `BattyeSutcliffe`. The generic
$m_e \ll m_\mu \ll m_\tau$ interpretive sentence in the Standard Model section
(`011-standard-model.tex:76`) does not invoke the torsion sectors and was left as-is (outside the
mandate; flagged for the reviewer).

Independent adversarial review: launched on the final tree (HEAD `6c92ae2`), report expected at
`notes/review-3.12-q3-conflation.md`. Publication remains gated on that review and on Jérôme's
explicit post-review go.

## 7. Review cycle (2026-08-14/15)

First independent adversarial review (report: `notes/review-3.12-q3-conflation.md`): **FAIL**, two
blocking semantic survivals in files the diff had not touched — token greps missed them because they
carry the retracted claim without the retracted tokens:

1. `003-topological-constraints.tex:52-54`: $w$ described as playing ``a central role in the
   organization of the mass spectrum'', cross-referencing chapter 11 — contradicting the new scope
   sentence declaring $r$ distinct from $w$.
2. `013-summary-quantum.tex:8-9`: the quantum-chapter summary still asserted strong interactions and
   confinement ``through topological stability of knotted solitonic configurations''.

Fixes applied (commit `5953463`): $w$ now organizes charge quantization while the mass spectrum is
carried by the distinct abstract torsion sector index; the summary states the origin of strong
interactions and confinement as an open problem; the strong-sector heading renamed ``Color and
Confinement as Open Problems'' (reviewer's minor finding; label unchanged). Recompiled clean.

Reviewer's remaining non-gating notes, deliberately left: the chapter-1 quark passage
(`011-energy-mass-constants.tex`, non-projectability reading of confinement — assertive but a
different, orthogonal mechanism; Jérôme may wish to soften it in a later revision); the generic
knot/vortex taxonomy and metaphor mentions; the `comp` argument token (introduced per ruling 5);
stale untracked May-14 `tex/Cosmochrony.aux`/`tex/Cosmochrony.bbl` (deletion left to Jérôme per the
deletion-permission guardrail).

Branch note: the release branch is now **3.13**, created by Jérôme on top of the audit commits and
carrying his own `d71cd3f` (O18 v2.0 conjugate-pair hypothesis restatement, reviewed sound by the
first pass); the fix commit `5953463` is its HEAD, pushed. A focused re-review of the patched
artefact is running; publication remains gated on its verdict and Jérôme's explicit go.

Focused re-review verdict (appended to `notes/review-3.12-q3-conflation.md`): **PASS** for the 3.13
tree (HEAD `5953463`). Both blocking findings resolved with no residual cross-reference
contradiction; replacements are strictly weaker status assertions with no narration and no new
undefined term; commit scope confirmed (three files); build current and clean, with the PDF text
carrying the new formulations and zero retracted phrasing. Non-gating recommendations left open:
chapter-1 confinement hedging, the `comp` token, legacy label names, the $\lambda_p$/$\lambda_{\mathrm{bind}}$
notation split in B.9, stale untracked May-14 `tex/Cosmochrony.aux`/`.bbl`. The deposit gate now
rests with Jérôme's explicit post-review go.

## 8. Publication (2026-08-15, after Jérôme's explicit post-review go)

Deposited via `tools/zenodo_publish.py` (foreground). The deposit guard first caught a stale
`CITATION.cff` version (3.9.1), fixed in commit `81cf86b` before the deposit.

- Version DOI: `10.5281/zenodo.21940064` (record verified live, `metadata.version = 3.13`).
- Concept DOI: `10.5281/zenodo.17957509` (unchanged).
- PDF archived: `@cosmochrony/pdfs/Cosmochrony_3.13.pdf`.
- DOI cascade: concept DOI already current across all 59 bibliography files.
- Merge: `3.13` merged into `main` (`a082510`), pushed; remote `HEAD` verified on `refs/heads/main`.
- Website: the `/science/` page (all five language versions) carries none of the retracted claims and
  no version string; its only $SU(3)$ mention refers to the O-series conditional colour sector, not
  the retracted trefoil mechanism. No site change was needed; live page verified HTTP 200 with zero
  retracted terms in the served content.

Release closed. Open, non-gating: the five reviewer recommendations of §7, and the process lesson
that token greps do not catch semantic survivals (recorded in session memory).
