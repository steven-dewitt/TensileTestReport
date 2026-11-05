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
5. Use **Print / PDF** to produce the issued report. The input boxes print as plain text.
6. **Export CSV** downloads one row per specimen, with every entered and calculated value.

All units are fixed: mm, N, MPa, and strain in mm/mm.

## Report sections

| # | Section | What you enter |
|---|---------|----------------|
| 1 | Test request and material | Customer, grade, lot, condition, specimen drawing; test machine, load cell, extensometer, load train, loading rate, temperature, humidity, conditioning, operator |
| 2 | Original sample (source block / billet) | Sample ID, shape (rectangular block or cylinder), forming method, forming axis, datum definition, three readings of each dimension, mass. The page gives mean, range, volume and bulk density. |
| 3 | Specimen removal locations | For each specimen: ID, long axis (X/Y/Z) and the centre coordinates measured from the datum. The page gives the orientation to the forming axis (∥/⊥, with/against grain), the depth below the nearest surface, and a position check (inside the sample, no overlap with other specimens). A **location map** shows the top, front and side views with each specimen drawn to scale and shaded by tensile strength. |
| 4 | Specimen dimensions | Two gauge-diameter readings 90° apart, reduced-section length, overall length. The page gives the mean diameter and cross-sectional area. |
| 5 | Test results by specimen | The nine values reported by the test software (below), fracture location, include/exclude, notes. A load ÷ area check flags reported stresses that don't match the measured area. |
| 6 | Stress–strain records | Optional raw load–strain data per specimen, pasted from the test software. Used to draw curves and to fill any result left blank in Section 5. |
| 7 | Summary of results | Summary tiles, statistics for every result (n, mean, SD, CV, min, max), means by orientation, a chart for each result, stress–strain curves, a Weibull plot, and any result plotted against position in the sample |
| 8 | Remarks, deviations and approval | Deviations, observations, conclusion, signatures |

### Results entered per specimen (Section 5)

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
Header and unit rows are skipped.

## Calculations

- **Area** = π·d̄²/4, where d̄ is the mean of the two gauge-diameter readings.
- **Bulk density** = mass ÷ volume of the original sample, using mean dimensions.
- **Orientation**: a specimen is ∥ when its long axis is the forming axis and ⊥ otherwise.
  For molded and vibration-molded stock, ∥ is labelled *against grain (AG)*. For extruded
  stock, ∥ is labelled *with grain (WG)*.
- **Included specimens**: with *Include* set to *Auto*, only specimens that fractured within
  the gauge length count in the statistics. *Yes* and *No* override this.
- **Statistics**: sample standard deviation (n − 1); CV = SD ÷ mean.
- **Weibull** (tensile stress at tensile strength): F = (i − 0.5)/n, with least-squares fit of
  ln ln[1/(1−F)] on ln σ, giving the Weibull modulus m and characteristic strength σ₀.

When a result is left blank and a load–strain record exists, it is calculated from the record:

| Result | From the record |
|--------|-----------------|
| Tensile strength point | point of maximum load |
| Break point | last point with load ≥ the break threshold (default 10 % of maximum load); its 1-based index is the data point at break |
| Tensile stress | load ÷ area |
| Young's modulus | least-squares slope of stress on strain between 0.01 % and 0.1 % strain (limits adjustable) |
| E-modulus | chord slope between 0.05 % and 0.25 % strain (limits adjustable) |
| Strain gauge length | the default value entered at the top of Section 5 |

Check the default calculation limits against your test method and software settings before you rely on calculated values.

## Example data

**Load example data** fills the report with generated values for a molded graphite
block with ten specimens: six parallel to the pressing axis and four perpendicular,
one of which broke in the fillet. The values are illustrative only and are not
measured results.

## Notes

This template organises and reduces test data. It does not reproduce the text of
ASTM C749-08. Check specimen geometry, loading rate, alignment and reporting
requirements against your own copy of the standard.
