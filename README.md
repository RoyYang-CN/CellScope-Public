# CellScope Public Edition

[简体中文](README_CN.md) · [Download the latest Windows release](https://github.com/RoyYang-CN/CellScope-Public/releases/latest)

CellScope audits LTE and 5G engineering-parameter spreadsheets. It checks PCI reuse conflicts, TAC regional consistency, and same-site MOD3 conflicts, then produces an Excel report with findings, evidence, and candidate corrections. Engineers must review the source data and proposed changes before applying them to a live network.

## Why engineers use it

Checking thousands of cells by hand means repeated filtering, distance lookups, parameter comparisons, and report assembly. CellScope runs those checks together and keeps the evidence behind each finding in one workbook. It highlights data-quality issues and leaves uncertain regional decisions for manual review instead of forcing a suggested value.

Typical uses include routine parameter audits, pre-change checks, bulk data-quality review, and handing findings to another engineer. Actual time saved depends on the dataset and the review required.

See the [detailed English user guide](USER_GUIDE_EN.md) for input fields, report sheets, TAC decision logic, and workflow examples.

## What it does

- Imports common Chinese or English Excel parameter headers. Blank input templates are in [`templates/`](templates/).
- Checks PCI, TAC, and MOD3 issues in one workflow and flags source-data problems that can make a recommendation unreliable.
- Writes a separate audit workbook; it does not overwrite your input file.
- Offers Chinese and English interfaces. English is the initial display language.

## Download and trial

1. Download `CellScopePublic.exe` from the [latest Release](https://github.com/RoyYang-CN/CellScope-Public/releases/latest). Windows 10/11, 64-bit.
2. Run the app and import your own Excel file, or start with one of the blank templates in this repository.
3. The 10-day trial includes checks and recommendations. After the trial, checks and evidence remain available; recommendations require a license.
4. Verify the file hash against `SHA256SUMS.txt` in the Release. This build is currently unsigned, so Windows may show an unknown-publisher warning.

## Purchase and activation

A permanent, single-device license is **USD 29.90, tax included**. [Buy through Creem](https://www.creem.io/product/prod_1q96Nt7Aj1oyc29rYtZGeo) or use **Buy License** inside the English app. Creem emails the license key after payment. Enter it in **Unlock Full Version** while online; the same Windows device can then use the licensed features offline. Keep the key private. Chinese legacy registrations and Creem licenses unlock the same feature set.

The Excel workbook is processed locally. Purchase and first activation use external services. Do not upload real network data or customer identifiers to public issues, posts, or screenshots.

## Support and boundaries

Contact: [hnzzlulu@gmail.com](mailto:hnzzlulu@gmail.com). Include the app version and a sanitized description of the issue; do not publish license keys or real site data.

Results are engineering audit findings and candidate suggestions. Check coordinates, site identity, local planning constraints, and live-network context before changing production parameters.

This repository distributes the packaged app, blank templates, and documentation. The application source code is proprietary and is not included here.
