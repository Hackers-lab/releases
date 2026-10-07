# Oracle EBS Technical Master Data / Zone Change Module

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](manifest.json)
[![Platform](https://img.shields.io/badge/platform-Chrome%20Extension%20MV3-brightgreen.svg)](https://developer.chrome.com/docs/extensions/mv3/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

An automation extension for the **Oracle E-Business Suite (EBS) CRM Technical Master Data Edit Page** designed to accelerate bulk **MRU (Meter Reading Unit) transfers, Zone Changes, and Administrative Memo Updates**.

---

## Key Features

- **Automated MRU & Zone Updates**: Batch update consumer Meter Reading Units (MRU), zone assignments, and office memo references in Oracle EBS.
- **Embedded In-Page Overlay**: Modern, clean UI overlay on the Oracle EBS page while safely retaining all underlying EBS DOM structures and form controls.
- **1-Click Excel Template**: Download ready-to-use `.xlsx` format with sample consumer records.
- **Excel & CSV Import**: Upload `.xlsx`, `.xls`, or `.csv` files for preview and processing.
- **Automated Form Progression**: Searches each Consumer ID, populates new MRU assignments, inputs memo numbers, memo dates, executor ERP ID, and approver ERP ID.
- **Live Status & Statistics**: Real-time counters for Total, Success, and Failed records with green/red row indicators.
- **Audit Export**: Download a detailed result spreadsheet documenting processed records, timestamps, and error descriptions.

---

## Excel Template Columns

The extension accepts spreadsheets containing the following fields:

| Column | Description | Example |
| :--- | :--- | :--- |
| `SL NO` | Serial number | `1` |
| `CON_ID` | Consumer ID to update | `300201481` |
| `New_MRU` | Target Meter Reading Unit / Zone code | `J62` |
| `Memo No` | Official memo / sanction order number | `GCCC/413` |
| `Memo Date` | Sanction or effective memo date | `25-Jun-2026` |
| `Executor ERP ID` | ERP ID of executing technician/officer | `90018669` |
| `Approvar ERP ID` | ERP ID of approving authority | `90011420` |

> **Tip**: Click **Download Excel Format** directly inside the extension to generate a pre-configured template.

---

## How to Install (Load Unpacked in Chrome)

1. **Download the Extension**:
   - Download `crm-zone-change-extension-v1.0.0.zip` from the [Releases](https://github.com/Hackers-lab/crm-zone-change-extension/releases) page.
   - Extract the `.zip` archive on your computer.
   *(Alternatively, clone this repository: `git clone https://github.com/Hackers-lab/crm-zone-change-extension.git`)*

2. **Open Extensions Page**:
   - Open Chrome and navigate to `chrome://extensions`.

3. **Turn on Developer Mode**:
   - Toggle **Developer mode** in the upper right corner to **ON**.

4. **Load Unpacked**:
   - Click the **Load unpacked** button in the upper left.
   - Select the directory containing `manifest.json`.

5. **Pin Extension**:
   - Click the puzzle icon in Chrome's top toolbar and pin **Oracle EBS Excel Module**.

---

## Step-by-Step Usage

1. **Navigate to Portal**: Log into Oracle EBS CRM and go to the Technical Master Data Edit page (`/OA_HTML/...`).
2. **Download Template**: Click **Download Excel Format** from the extension toolbar or popup.
3. **Prepare Rows**: Enter your consumer IDs and new MRU codes into the spreadsheet.
4. **Upload Data**: Click **Upload Excel** to import your records.
5. **Execute Automation**: Click **Start**. The extension sequentially opens each consumer record, fills the new MRU and memo details, validates, and submits.
6. **Export Summary**: After the batch run finishes, click **Download Results** to save a detailed summary report.

---

## Permissions & Privacy

- **Strictly Local**: Operates exclusively in the local browser environment. No customer identifiers, ERP IDs, or account data are shared externally.
- **Local Storage**: Maintains run status locally to provide safe pause/resume functionality.

---

## License

This project is licensed under the MIT License.

