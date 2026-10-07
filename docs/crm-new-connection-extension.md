# Oracle EBS New Connection Module

[![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)](manifest.json)
[![Platform](https://img.shields.io/badge/platform-Chrome%20Extension%20MV3-brightgreen.svg)](https://developer.chrome.com/docs/extensions/mv3/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

An automation assistant for **Oracle E-Business Suite (EBS) CRM** that automates the **New Service Connection (NSC)** workflow. Designed for utility operators and customer service representatives to process bulk new connection applications quickly, accurately, and without repetitive manual form-filling.

---

## Key Features

- **Batch Application Processing**: Upload customer and application records via Excel (`.xlsx`, `.xls`, `.csv`, `.txt`) for automated batch creation.
- **Built-in Template Generator**: Download pre-formatted Excel template with sample entries at any time with one click.
- **Configurable Application Defaults**:
  - **Document Type & Document Name**: Aadhar Card, Voter ID Card, Driving Licence, Passport, Ration Card, Panchayat/Municipality Certificate, Rent Bill, Tax Bill, and custom Document Name (e.g., `GOVT ORDER`) for departmental orders.
  - **Project Scheme Workflow**: Support for dedicated scheme connections (`Applicable for Project`: `Y` / `N`) with selectable designations like `EVCS RDSS` and `ICDS`.
  - **Verified By**: Custom verification officer identifier.
  - **District**: Full district catalog support.
  - **Category**: Panchayat or Municipality/Corporation.
  - **Meter Type**: Normal Postpaid Meter, Postpaid Smart Meter.
- **Multi-Page Lifecycle Management**: Robust background service worker and content script coordination that gracefully navigates through complex Oracle multi-step forms (Consumer Search -> Creation -> Address -> Identification -> Confirmation).
- **Live Status & Activity Dashboard**:
  - Real-time **Currently Processing** display showing applicant name, contact details, and progress status.
  - Colored row-by-row status tracking (green for success, red for failures with error reasons).
- **Comprehensive Audit Log**: Download complete result logs with generated Application IDs and status reports.

---

## Excel Template Columns

The extension accepts spreadsheets containing the following fields:

| Column | Description | Example |
| :--- | :--- | :--- |
| `Purpose of Supply` | Tariffs / supply category | `DOMESTIC` / `COMMERCIAL` |
| `Gender` | Applicant gender | `MALE` / `FEMALE` |
| `First Name` | Consumer given name | `RAJESH` |
| `Last Name` | Consumer family name | `MUKHERJEE` |
| `Mobile Number` | 10-digit primary contact number | `9876543210` |
| `Address Line1` | Primary address details | `VILL-RAMPUR, PO-SHYAMPUR` |
| `Address Line2` | Secondary address / locality | `NEAR WATER TANK` |
| `Landmark` | Notable landmark for meter installation | `OPP PRIMARY SCHOOL` |
| `Pincode` | 6-digit postal code | `700001` |
| `AADHAAR Card No` | Identification number | `999988887777` |
| `watt` | Requested connected load in watts | `1000` |

> **Tip**: Click **Download Excel Format** inside the extension popup to get an Excel sheet pre-populated with sample applicant records.

---

## How to Install (Load Unpacked in Chrome)

1. **Download the Extension**:
   - Download the latest `crm-new-connection-extension-v1.1.0.zip` from the [Releases](https://github.com/Hackers-lab/crm-new-connection-extension/releases) page.
   - Extract the `.zip` archive on your system.
   *(Alternatively, clone this repository: `git clone https://github.com/Hackers-lab/crm-new-connection-extension.git`)*

2. **Open Chrome Extensions Manager**:
   - Open Chrome and navigate to `chrome://extensions`.

3. **Enable Developer Mode**:
   - Toggle **Developer mode** in the top-right corner to **ON**.

4. **Load Unpacked**:
   - Click the **Load unpacked** button in the upper left.
   - Select the folder containing `manifest.json`.

5. **Pin Extension**:
   - Click the extension puzzle icon in the Chrome toolbar and pin **Oracle EBS New Connection Module**.

---

## Step-by-Step Usage

1. **Login**: Navigate to your Oracle EBS CRM Consumer Search page (`/OA_HTML/...`).
2. **Download Format**: Open the extension and click **Download Excel Format**.
3. **Fill Records**: Add your applicant data according to the format columns.
4. **Upload Excel**: Click **Upload Excel** to import and preview rows in the table.
5. **Configure Defaults**: Select your **Document Type**, **District**, **Category**, and **Meter Type**.
6. **Start Processing**: Click **Start**. The extension automatically navigates into creation forms, populates details, validates inputs, and proceeds through confirmation.
7. **Export Results**: When processing completes, click **Download Results** to obtain an Excel report of all submitted applications.

---

## Permissions & Privacy

- **Strictly Local**: All processing occurs strictly within the local browser context. No customer personal details (PII), addresses, or identification numbers are sent externally.
- **Chrome Storage**: Used locally to maintain application state across page reloads during multi-step form submissions.

---

## License

This project is licensed under the MIT License.

