# Tensile Test Report: Carbon and Graphite (ASTM C749-08)

A report template for tensile stress–strain tests on carbon and graphite run to
**ASTM C749-08**. It is a single file, `index.html`, that runs in any modern
browser with no installation or internet connection. You enter the test data in
the page, and it calculates the summaries, draws the charts and prints the
finished report.

## Using it

1. Open `index.html` in Chrome, Edge or Firefox.
2. Click **Load example data** to see a filled-in report, or **New blank report** to start one.
3. Fill in the sections from top to bottom. Entries save automatically in the browser.
4. Use **Save data (.json)** to keep a permanent copy of a report and **Open data…** to reload it.
5. Use **Print / PDF** to produce the issued report (US Letter). It prints with a title block, numbered sections, form-style fields, and a running header and footer showing the report number, revision, status and "Page X of Y". Data-entry instructions, prompts and tools appear only on screen. A blank report prints as a fill-in form.
6. **Export CSV** downloads one row per specimen, with every entered and calculated value.

**Units.** Use the **Units** selector in the toolbar to switch between
**Metric** (mm, N, MPa, mm/mm, °C) and **Standard** (in, lbf, psi, in/in, °F).
Values are always stored in metric and converted for display, so switching back
and forth never changes the data. Typed and pasted values are read in the units
currently selected. The choice is saved with the report, and the billet drawing,
tables, charts, summaries and CSV export all follow it.

## Report sections

| # | Section | Contents |
|---|---------|----------|
| 1 | Test request and material | Customer, PO / work order, material grade, manufacturer; test machine, machine ID, load cell capacity, loading rate, temperature, humidity, test dates, operator |
| 2 | Specimen location in billet | Drawings to scale of the extruded billet, Ø7.750 × 1.000 in thick, and the test specimen. The plan view and section A–A show the 4.750 in specimen lying on a diameter through the billet centre at mid-thickness, perpendicular to the extrusion axis, with 1.500 in of billet at each end. A specimen detail shows the Ø0.500 in ends and Ø0.250 in centre section. |
| 3 | Specimen dimensions | Specimen IDs, two gauge-diameter readings 90° apart, reduced-section length and overall length. The page gives the mean diameter and cross-sectional area. Specimens are added and removed here. |
| 4 | Test results by specimen | The nine values reported by the test software (below), fracture location, include/exclude and notes. A load ÷ area check flags reported stresses that don't match the measured area. |
| 5 | Summary of results | Summary tiles, statistics for every result (n, mean, SD, CV, min, max), a chart for each result by specimen, and a Weibull plot of tensile strength |
| 6 | Remarks and approval | Observations, conclusion and signatures |

### Results entered per specimen (Section 4)

| Result | Unit |
|--------|------|
| Load at Break (Standard) | N |
| Data point at Break (Standard) | index |
| Tensile stress at Break (Standard) | MPa |
| Strain 1 at Break (Standard) | mm/mm |
| Strain gauge length | mm |
| Strain 1 at Tensile Strength | mm/mm |
| Tensile stress at Tensile Strength | MPa |
| Modulus (Young's Tensile stress 0.01% - 0.1%) | MPa |
| Modulus (E-Modulus) | MPa |

Values can be typed in, or pasted in bulk with **Paste a results table from the
test software**. Paste one row per specimen with the columns in the order above,
optionally preceded by a specimen ID column. Rows with IDs are matched by ID.
Header and unit rows are skipped. If strain gauge length is left blank, the
default entered at the top of Section 4 is used.

## Calculations

- **Area** = π·d̄²/4, where d̄ is the mean of the two gauge-diameter readings.
- **Stress check**: load at break ÷ area is compared with the reported tensile stress at
  break, and differences over 2 % are flagged. The page also flags stress at break above
  tensile strength, strain at tensile strength above strain at break, and strain values
  that look like percentages.
- **Included specimens**: with *Include* set to *Auto*, only specimens that fractured within
  the gauge length count in the statistics. *Yes* and *No* override this.
- **Statistics**: sample standard deviation (n − 1); CV = SD ÷ mean.
- **Weibull** (tensile stress at tensile strength): F = (i − 0.5)/n, with least-squares fit of
  ln ln[1/(1−F)] on ln σ, giving the Weibull modulus m and characteristic strength σ₀.

## Example data

**Load example data** fills the report with generated values for ten specimens,
one of which broke in the fillet. The values are illustrative only and are not
measured results.

## Notes

This template organises and reduces test data. It does not reproduce the text of
ASTM C749-08. Check specimen geometry, loading rate, alignment and reporting
requirements against your own copy of the standard.
