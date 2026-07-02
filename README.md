# College Admissions Predictor

A single-file, client-side web app that estimates undergraduate admission probability at **238 U.S. universities** — every accredited 4-year school in California, Washington, and Oregon, plus the U.S. News Top 200 National Universities.

**Live demo:** https://billbirk.github.io/college-admissions-predictor/

## Features

- **Transparent prediction engine** — a logistic model over each school's residency-adjusted base admit rate, adjusted by GPA, course rigor, test scores, extracurriculars, essays, recommendations, demonstrated interest, application round, and intended-major competitiveness. Every adjustment is shown with its size and reasoning, and every estimate carries a confidence interval rather than false precision.
- **Residency-aware** — in-state vs. out-of-state admit rates and tuition (including UC/CSU system rules and WUE discounts), defaulting to Washington residency.
- **Test-policy aware** — knows which schools are test-required, test-optional, or test-blind for the 2026–27 cycle, and recommends per school whether to submit scores.
- **Direct-to-major estimates** — separate probability shown where the major decision is harder than university admission (e.g., UW Foster freshman-direct).
- **Transcript import** — parses Washington state high school transcript PDFs locally in the browser (pdf.js); other formats fall back to manual entry.
- **Smart recommendations** — classifies schools Dream → Safety and proposes a balanced ~15-school application list.
- **Search, filter, sort, compare, favorites, and export** to CSV, Excel, and PDF.

## Data

School statistics use the most recent published sources available at build time: official fall 2025 University of California admission data (UCOP), university-published admit rates and GPA bands (e.g., UW Office of Admissions), and each school's most recent Common Data Set for the 2025–26 cycle. The college database is a plain JavaScript array, deliberately separated from the prediction engine so data can be refreshed independently.

## Privacy

Everything runs in the browser. Uploaded transcripts are parsed locally and never transmitted or stored; there is no backend, no analytics, and no network calls other than loading the pdf.js/xlsx libraries from a CDN. localStorage holds only favorited/hidden school IDs.

## Hosting

It's one file. Serve `index.html` from any static host (GitHub Pages, Netlify, S3) — no build step, no dependencies to install.

## Disclaimer

Estimates are probabilistic guidance, not guarantees, and are not affiliated with any university. Holistic admissions are inherently uncertain — treat the confidence intervals as the honest part of the answer, and verify current admissions requirements on each school's official pages (linked from every school card).
