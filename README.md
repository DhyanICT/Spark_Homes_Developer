# SparkScope Repair Estimator

SparkScope is a mobile-first, offline-ready repair cost estimator for Spark Homes acquisition walkthroughs.

## What is included

- `index.html` - the full vanilla HTML/CSS/JavaScript app.
- `manifest.webmanifest`, `sw.js`, and PNG icons - PWA install/offline support.
- `SparkScope-Writeup.pdf` - the required one-page submission writeup.

## Run locally

Open `index.html` directly for basic use, or serve the folder to test PWA install/offline behavior:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080/index.html`.

## Libraries and approach

The app intentionally uses no framework and no CDN dependency. ZIP and XLSX export are implemented in vanilla JavaScript so the app can keep exporting estimates while offline. Data is stored in `localStorage` by project, including rooms, quantities, notes, project-level price overrides, global standard-price overrides, and compressed project photos.

## Feature coverage

- Multiple saved projects.
- 108 default price-list items from the provided CSV.
- 19 official repair groups with a No Action Needed option in every group.
- Configurable room instances: interior/general, kitchen, bathroom, systems, exterior, bedroom, and living/common areas.
- Per-project unit-cost overrides plus global price-book CSV upload/editing.
- Add/delete line items per group.
- Progress by reviewed group.
- Camera photo capture with compressed thumbnails and serial-number parsing attempts via available browser barcode/text detection APIs.
- ZIP export containing an Excel `.xlsx` estimate and all saved photos.
- Creative addition: Deal Analyzer with max-offer, projected-profit, contingency, holding, selling, and repair-per-square-foot calculations.

## AI usage note

AI assistance was used to synthesize the brief into a static implementation plan, produce the initial code, and generate the one-page writeup. The data model, feature decisions, and verification pass were kept tied to the provided contest brief and price list.
