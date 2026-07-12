# Head & Neck DVH Plan Review

One-glance DVH acceptability assessment for head & neck radiotherapy — dual-track report generation for physicists and physicians.

## What This Skill Does

Given DVH data (text/CSV), this skill:

1. **5-Step Quick Check**: Hard constraints → Target coverage → Soft constraints → Optimization → Conflict adjudication
2. **Dual-Track Reports**: One for physicists (what to fix, how to fix it) + one for physicians (which plan to pick, why)
3. **SBRT Constraints**: TG-101 / UK SABR 2022 limits for 1/3/5-fraction SBRT
4. **4-Dimension Constraint Correction**: Partial volume, fractionation effect, re-irradiation gap repair, age/priority
5. **ADC/IO Radiosensitization**: SER-adjusted BED calculation, drug discontinuation dose compensation
6. **Multi-Plan Comparison**: Side-by-side with net advantage scoring

## Key Decision Rules

```
Hard constraints (cord/brainstem/chiasm) > Target coverage > Soft constraints (parotid/mandible) > Optimization goals

"Paralysis is unacceptable. Dry mouth is manageable. Recurrence is unforgivable."
```

## Built-In Constraint Library

| OAR | Conventional | SBRT 3fx | SBRT 5fx |
|-----|-------------|----------|----------|
| Spinal Cord | Dmax ≤45 Gy | ≤21 Gy | ≤25 Gy |
| Brainstem | Dmax ≤54 Gy | ≤21 Gy | ≤25 Gy |
| Optic Chiasm | Dmax ≤54 Gy | ≤17 Gy | ≤23 Gy |
| Lens | Dmax ≤10 Gy | — | — |

> All constraints verified against QUANTEC, TG-101, and UK SABR 2022 (PMID:35272913).

## Quick Install

```bash
hermes skills install https://raw.githubusercontent.com/antica1/head-neck-dvh-review/master/SKILL.md
```

## Companion Skill

[Head & Neck Re-Irradiation Plan Recommendation](https://github.com/antica1/head-neck-reirradiation) — for recurrent disease re-treatment planning.

## Trigger Keywords

`DVH review` `plan check` `plan evaluation` `OAR constraints` `SBRT dose limits` `BED calculation` `DVH审核`

## Author

Zhu Guopei, MD — Shanghai Ninth People's Hospital. Contact: antica@gmail.com

## License

MIT
