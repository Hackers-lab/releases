# Oracle EBS Meter Replacement Extension

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](manifest.json)
[![Platform](https://img.shields.io/badge/platform-Chrome%20Extension%20MV3-brightgreen.svg)](https://developer.chrome.com/docs/extensions/mv3/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

An automated productivity extension for **Oracle E-Business Suite (EBS) CRM** that streamlines and automates the **Meter Replacement** workflow. It eliminates tedious manual record-by-record data entry by allowing operators to upload an Excel/CSV spreadsheet and automate work order lookups, validation, form population, and submission.

---

## Key Features

- **Batch Excel / CSV Processing**: Upload work orders in bulk (`.xlsx`, `.xls`, `.csv`, `.txt`) and process them automatically.
- **Built-in Template Generator**: Download standard Excel template (`.xlsx`) directly from the extension popup with one click.
- **Customizable Automation Parameters**:
  - **Meter Type**: Single Phase Post Paid Normal, Single Phase Post Paid TOD, Single Phase Pre Paid Normal, Single Phase Pre Paid TOD.
  - **Meter Rating**: `5-30`, `10-60`, `10-100`, `20-100`, `50-100`.
  - **Yellow Card Support**: Toggle `Y` / `N`.
  - **Max Reading Difference**: Set custom reading difference tolerance thresholds.
  - **Low Final Reading (Low F/R)**: Configurable handling for low final meter readings.
- **Live Progress & Tracking**:
  - Displays a real-time **Currently Processing** dashboard (Consumer ID, Date entered, Normal Reading, Meter Status).
  - Visual status table with real-time success (green) and failure (red) markers.
- **Run Controls**: Start, pause, resume, or abort automation at any time.
- **Audit & Results Export**: Export full processing results containing status, timestamps, and error diagnostics for audit and reconciliation.

---

## Excel Template Columns

The extension processes Excel/CSV files with the following columns:

| Column | Description | Example |
| :--- | :--- | :--- |
| `Work Order No` | Work order reference number | `431642` |
| `Consumer Id` | Unique consumer identification number | `342167529` |
| `Old Meter No` | Serial number of the meter being replaced | `196642_1` |
| `F/R` | Final reading on the removed meter | `7090` |
| `Status` | Operational status of old meter | `0` (Normal / OK) |
| `New Meter No` | Serial number of the newly installed meter | `NI0061351` |
| `I/R` | Initial starting reading of new meter | `0` |
| `Date of Repl.` | Replacement date | `08-JUL-2026` |
| `Seal No` | Meter security seal number | `SML2361962` |
| `Meter Phase` | Phase specification | `I` or `III` |

> **Tip**: Click **Download Excel Format** inside the extension popup to generate a pre-formatted template with sample rows.

---

## How to Install (Load Unpacked in Chrome)

1. **Download the Extension**:
   - Download the latest `crm-meter-replacement-extension-v1.0.0.zip` from the [Releases](https://github.com/Hackers-lab/crm-meter-replacement-extension/releases) page.
   - Extract the `.zip` archive to a folder on your computer.
   *(Alternatively, clone this repository: `git clone https://github.com/Hackers-lab/crm-meter-replacement-extension.git`)*

2. **Open Extensions Page in Chrome**:
   - Open Google Chrome and enter `chrome://extensions` in the address bar.

3. **Enable Developer Mode**:
   - In the top-right corner of the Extensions page, toggle **Developer mode** to **ON**.

4. **Load the Extension**:
   - Click the **Load unpacked** button in the top-left corner.
   - Browse to and select the extracted folder (the directory containing `manifest.json`).

5. **Pin to Toolbar**:
   - Click the puzzle icon (Extensions) in Chrome's top toolbar.
   - Find **Oracle EBS Meter Replacement Module** and click the pin icon to keep it accessible.

---

## Step-by-Step Usage

1. **Open CRM**: Log into your Oracle EBS CRM portal and navigate to the Meter Replacement work order page (`/OA_HTML/...`).
2. **Open Extension**: Click the extension icon in your Chrome toolbar. The extension will automatically verify that the target Oracle page is open.
3. **Get Template**: Click **Download Excel Format** to obtain the standardized spreadsheet template.
4. **Prepare Data**: Fill out your meter replacement records in Excel.
5. **Upload Spreadsheet**: Click **Upload Excel** and select your file. A table previewing all records will appear.
6. **Set Parameters**: Verify and set your desired **Meter Type**, **Rating**, **Yellow Card**, **Max Diff**, and **Low F/R** options.
7. **Execute**: Click **Start**. The extension will sequentially navigate each work order, enter values, validate, and submit.
8. **Export Results**: Once the batch finishes, click **Download Results** to save an Excel file with detailed execution logs.

---

## Permissions & Privacy

- **No Remote Telemetry**: Runs completely within your browser sandbox. No consumer data, work order numbers, or login credentials are transmitted to any third-party server.
- **Storage Permission**: Used solely for persisting your active batch progress and configuration locally in Chrome storage so automation can resume seamlessly across page refreshes.

---

## License

This project is licensed under the MIT License.

