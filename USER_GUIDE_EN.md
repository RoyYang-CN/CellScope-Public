# CellScope Public Edition — User Guide

[Download](https://github.com/RoyYang-CN/CellScope-Public/releases/latest) · [Buy a license](https://www.creem.io/product/prod_1q96Nt7Aj1oyc29rYtZGeo) · [简体中文简介](README_CN.md)

## 1. What CellScope does

CellScope Public Edition is a desktop audit tool for wireless engineering parameters. It reads Excel engineering data, identifies cells, coordinates, PCI, frequency, TAC, RAT and coverage type, then performs spatial, reuse and regional consistency checks.

### Unified import

Recognizes common Chinese and English headers and normalizes coordinates, RAT, coverage type and key fields.

### Rule-based audits

Checks PCI reuse, TAC regional continuity, third-party TAC patterns and same-site same-frequency MOD3 conflicts.

### Traceable outputs

Writes anomalies, neighborhood distributions, decision basis, recommendations and data issues to a structured workbook.

**In one sentence:** CellScope turns manual filtering, neighborhood lookup, parameter comparison, issue logging and report preparation into one repeatable audit workflow.

## 2. Problems solved

### Fewer manual omissions

When thousands of cells must be checked, manual filters and copied formulas can miss spatial neighbors, duplicate rows or same-site conflicts. CellScope scans the valid dataset consistently.

### More than one-field comparison

PCI, TAC and MOD3 are not judged by one number alone. The tool combines coordinates, RAT, frequency, site identity and coverage type.

### Safer recommendations

Recommendations require support, ratio and lead-margin checks. Mixed regional evidence is sent for manual review instead of forcing a change.

### Traceable evidence

The workbook keeps current values, neighbor counts, TAC distributions, decision basis, data issues and recheck results for later review.

## 3. Where efficiency improves

CellScope improves efficiency through workflow automation and standardized evidence, not merely by opening Excel faster.

### Batch checks instead of row-by-row filtering

Import one engineering workbook and run data validation, PCI, TAC and MOD3 checks in a single workflow.

### Spatial statistics instead of manual lookup

Coordinates are used to calculate distances and neighborhoods, reducing map comparison, copy/paste work and manual notes.

### One audit workbook instead of scattered conclusions

Anomalies, recommendations, raw evidence and data-quality findings are brought together for handoff and review.

**Typical uses:** daily parameter audits, pre-change validation, bulk data-quality checks, problem-cell triage and review handoff.

Actual time savings depend on data volume, input quality and the amount of engineering review required. CellScope does not promise a fixed percentage improvement.

## 4. Core audit modules

### PCI check

Checks PCI reuse risk by RAT, frequency, coverage type and spatial distance, and can provide a suggested PCI when the license allows recommendations.

### TAC check

Counts TAC distribution within a regional neighborhood to identify discontinuity, isolated TAC patterns and third-party TAC patterns. The regional count is cross-frequency; same frequency is not required.

### MOD3 check

Checks same-site same-frequency MOD3 conflicts and identifies exact duplicate engineering rows so duplicates do not create false conflicts.

### Data issues

Records invalid coordinates, missing fields, duplicate rows, RAT anomalies and records that cannot safely participate in an audit.

## 5. Workflow

1. **Prepare the workbook** — Make sure the first row is the real header, coordinates are longitude/latitude, and TAC, PCI and frequency fields are not interrupted by merged cells or explanatory text.

2. **Start CellScope** — Select the engineering workbook and review the detected fields and configuration shown by the application.

3. **Run the audit** — The application reads the data, checks PCI, checks TAC, checks MOD3 and generates the report.

4. **Review the workbook** — Start with Data Issues, then review anomaly details, recommended changes and recheck results.

5. **Confirm with engineering evidence** — Use live configuration, map layers, site relationships and maintenance records before applying any change.

**Recommendation:** Keep the original input workbook unchanged and archive it together with the generated audit workbook.

## 6. Input requirements

| Field | Purpose | Requirement |
| --- | --- | --- |
| Cell Name | Report identification and manual lookup | Prefer a complete, unique value. Coordinates may be used as a fallback identifier. |
| Longitude / Latitude | Distance, neighborhood and spatial checks | Use WGS-84 longitude/latitude. Longitude must be within -180 to 180 and latitude within -90 to 90. |
| PCI / Frequency | PCI reuse and MOD3 checks | Values should match the RAT range and the actual network plan. |
| TAC | TAC regional check | Use a consistent numeric or text representation for the same TAC. |
| RAT | LTE / NR grouping | Explicit RAT is recommended. If missing, the application may infer it according to the configuration. |
| ENB/GNB and CELLID | Site identity and duplicate detection | Recommended; these fields improve same-site and duplicate-row decisions. |

**Important:** Incorrect coordinates directly affect distance, neighborhoods and TAC regional decisions. If a map layer does not match the Excel coordinates, correct the source engineering data before rerunning the audit.

## 7. Output workbook

```
your_input_check_result_YYYYMMDD_HHMMSS.xlsx
├─ PCI Check
├─ TAC Check
├─ MOD3 Check
├─ Data Issues
├─ Summary
└─ Config
```

### Anomaly details

Shows current values, neighbor counts, same-value neighbors, neighbor distributions, category and decision basis.

### Recommended changes

Shows suggested PCI, TAC or MOD3 when licensed; otherwise shows the unlock message.

### Recheck

Checks whether conflicts remain after applying recommendations and separates automatic residuals from manual-review items.

### Configuration

Records distance, regional radius, thresholds and license state used for the run.

## 8. TAC regional decision logic

TAC checking does not treat an accidental Delaunay edge as the final business neighborhood. It prioritizes TAC distribution within the configured regional radius.

### Regional evidence first

Within one RAT, cells are counted inside the spatial radius. TAC voting is cross-frequency.

### Protect supported current TACs

If the current TAC has meaningful regional support, another TAC appearing in a geometric neighborhood does not automatically make the cell an outlier.

### Recommend only on clear majority

A candidate must meet the configured ratio and lead-margin requirements. Weak evidence leaves the recommendation empty.

### Manual review for mixed regions

When TACs meet at a boundary or vote counts are close, the report preserves the evidence and asks for manual review.

**Do not read only the suggested value:** review the TAC distribution, map layer and source coordinates before accepting a change.

## 9. Trial and licensing

1. **10-day trial** — The full audit workflow and recommendation results are available during the trial.

2. **After trial expiry** — Data checking, original parameters and anomaly evidence remain available. PCI, TAC and MOD3 recommendations and recommendation-based rechecks require a license.

3. **Buy and activate** — The English purchase button opens the [Creem checkout](https://www.creem.io/product/prod_1q96Nt7Aj1oyc29rYtZGeo). A permanent license for one Windows device costs USD 29.90, tax included. Creem emails your key after payment. Activate online once on that device, then use the licensed features offline.

**License scope:** A Chinese legacy registration key and a Creem license unlock the same features in either display language. Keep license keys and machine codes private.

**Data and engineering boundary:** The input workbook is processed locally; purchase and first activation use external services. Review all suggested changes against live-network evidence before applying them.

## 10. Data quality and anomalies

Records that can reduce confidence in the result are listed separately. Common examples include:

### Coordinate issues

Empty, zero, physically invalid or coordinate-system-mismatched values.

### Duplicate data

Exact duplicate rows are recorded and excluded from duplicate-induced MOD3 conflicts.

### Field issues

Missing required fields, unrecognized RAT values, or PCI/frequency values outside configured ranges.

**Quality first:** If coordinates or cell identity are visibly wrong, correct the input before evaluating PCI, TAC or MOD3 results.

## 11. Frequently asked questions

**Does CellScope modify my original Excel file?**

No. The source workbook is read and a separate audit workbook is generated.

**Does TAC require the same frequency?**

No. TAC regional statistics are cross-frequency, while LTE and NR are checked in separate groups.

**Why is a cell marked for manual review?**

Usually because multiple TACs meet in the region, vote counts are close, or the evidence does not meet the clear-majority rules. The tool keeps the evidence instead of forcing a change.

**Why is there no suggested value?**

The trial may have expired, the full license may not be active, or the candidate may not meet the recommendation thresholds.

**Can the tool replace an engineer’s decision?**

No. It provides batch checking and organized evidence. Final decisions require live network, map, site and maintenance context.

## 12. Usage boundary

**Engineering boundary:** CellScope results are parameter-audit findings and candidate suggestions. They are not final conclusions about coverage, interference, transport, power, construction or network optimization.

Keep the source workbook, configuration and audit result together. For regional boundaries, coordinate anomalies, co-located sites and large parameter changes, review samples before applying a batch change.

CellScope Public Edition · Offline user guide · Results should be reviewed by personnel with wireless-engineering experience.
