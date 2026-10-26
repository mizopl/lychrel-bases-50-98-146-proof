# Mechanical Template-Closure Proofs of Lychrel Numbers in Bases $b = 50$, $b = 98$, and $b = 146$ via Modular Carry-Wire Seam Surgery

> **🌟 Part of the [`mizopl/we-star` (`We*`)](https://github.com/mizopl/we-star) Autonomous Scientific Discovery Project:**
> This standalone verification repository is one of 39 machine-verified packages produced by [**`mizopl/we-star`** (`We* = human + AI + autonomous 3-skeptic verification loop`)](https://github.com/mizopl/we-star) on a single 16 GB Apple M1 laptop. Visit [**`github.com/mizopl/we-star`**](https://github.com/mizopl/we-star) for the complete architecture, constitution, and master table of results across 29 open problems.

**Authors:** `mizopl` (Independent Researcher), `Claude` (Anthropic), and `Gemini` (Google DeepMind / Antigravity)  
**Zenodo Preprint (DOI):** [`https://zenodo.org/records/23468033`](https://zenodo.org/records/23468033) (`10.5281/zenodo.23468033`)  
**Preprint PDF:** [`Lychrel_Preprint_2026.pdf`](Lychrel_Preprint_2026.pdf) | **LaTeX Source:** [`Lychrel_Preprint_2026.tex`](Lychrel_Preprint_2026.tex)

---

## Abstract

A **Lychrel number** in base $b \ge 2$ is a positive integer whose orbit under the iterative reverse-and-add map $F_b(n) = n + \operatorname{Rev}_b(n)$ never contains a base-$b$ palindrome. Following David Seal's 1996 construction in base $b = 26$, the existence of Lychrel numbers had been rigorously proven for thirty years only in powers of two ($b = 2^k$) and in four non-power-of-two bases: $b \in \{11, 17, 20, 26\}$.

Using the **Computer Lazy Sunday Solver (`CLSS`)** compositional seam-surgery framework on a single consumer office computer (10-core CPU, 16 GB RAM), we prove the existence of Lychrel numbers in **three new non-power-of-two bases**:
- **$b = 50 = 2 \cdot 5^2$** ([`lychrel_base50_certificate.json`](lychrel_base50_certificate.json), Period-4 template family $T_1(m), T_2(m), T_3(m), T_4(m)$ with $|L_0|=|R_0|=36$, $|M_0|=8$, $82$-digit start integer $n_0 = T_1(1)$),
- **$b = 98 = 2 \cdot 7^2$** ([`lychrel_base98_certificate.json`](lychrel_base98_certificate.json), Period-4 template family with $|L_0|=|R_0|=37$, $|M_0|=16$, $92$-digit start integer $n_0 = T_1(1)$),
- **$b = 146 = 2 \cdot 73$** ([`lychrel_base146_certificate.json`](lychrel_base146_certificate.json), Period-4 template family with $|L_0|=|R_0|=80$, $|M_0|=6$, $168$-digit start integer $n_0 = T_1(1)$).

We also provide the baseline reproduction of David Seal's 1996 construction in base $b = 26$ ([`seal_base26_baseline_certificate.json`](seal_base26_baseline_certificate.json)) and a complete mechanical audit of Rostand S. Kuitché's 2023 preprint across bases $3 \le b \le 10$ ([`kuitche_2023_audit.json`](kuitche_2023_audit.json)).

---

## Summary of Proven Non-Power-of-Two Lychrel Bases

| Base $b$ | Prime Factorization | Period $p$ | Outer Length $\ell$ | Inner Core $\|M_0\|, \|M_2\|$ | Start $\|T_1(1)\|$ (base-$b$ digits) | Reference / Status |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| $b = 11$ | $11$ | $2$ | — | — | — | Classical (pre-1996) |
| $b = 17$ | $17$ | $3$ | — | — | — | Classical (pre-1996) |
| $b = 20$ | $2^2 \cdot 5$ | $4$ | — | — | — | Classical (pre-1996) |
| $b = 26$ | $2 \cdot 13$ | $4$ | $12$ | $12, 13$ | $38$ digits | David Seal (1996) |
| **$b = 50$** | **$2 \cdot 5^2$** | **$4$** | **$36$** | **$8, 9$** | **$82$ digits ($140$ dec. digits)** | **This work (Theorem 3)** |
| **$b = 98$** | **$2 \cdot 7^2$** | **$4$** | **$37$** | **$16, 17$** | **$92$ digits ($183$ dec. digits)** | **This work (Theorem 4)** |
| **$b = 146$** | **$2 \cdot 73$** | **$4$** | **$80$** | **$6, 7$** | **$168$ digits ($364$ dec. digits)** | **This work (Theorem 5)** |

---

## One-Command Mechanical Verification

To run the complete symbolic carry-transducer verifier, concrete parameter sweep ($1 \le m \le 500$), and $100,000$-step regular-expression orbit simulation (reaching $50,082$ base-$50$ digits):

```bash
python3 author_checker_lychrel_check.py
```
