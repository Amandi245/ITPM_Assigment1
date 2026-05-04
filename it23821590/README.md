# IT3040 – Assignment 1: Transliteration Accuracy Testing

## Overview

This repository contains the Playwright-based test automation project for **IT3040 – IT Project Management**, Assignment 1, Option 1.

The objective is to evaluate how accurately the [PixelsSuite Chat Translator](https://www.pixelssuite.com/chat-translator) converts chat-style **Singlish** input into **Sinhala** output. The automation script tests 50 negative test cases covering all 24 Singlish input types defined in Appendix 1 of the assignment.

---

## Project Structure

```
IT23821590/
├── IT23821590.py          # Main Playwright automation script
├── IT23821590.xlsx             # Test cases Excel file (input + results)
└── README.md                   # This file
```

---

## Prerequisites

- **Python 3.11 or 3.12** — [Download here](https://www.python.org/downloads/)
- **Google Chrome** (recommended) — or let Playwright install Chromium

---

## Installation

### Step 1: Clone or download the repository

```bash
git clone https://github.com/Amandi245/ITPM_Assigment1.git
cd IT23821590
```

Or download the ZIP and extract to `D:\IT23821590`.

### Step 2: Install dependencies

Open Command Prompt and navigate to the project folder:

```cmd
cd /d D:\IT23821590
```

Then run:

```cmd
pip install -U pip
pip install playwright openpyxl
playwright install
```

> **Note:** If `python` is not recognized, use the full path:
> `C:\Users\<your-username>\AppData\Local\Programs\Python\Python312\python.exe`

---

## Running the Tests

Make sure the Excel file (`IT23821590.xlsx`) is in the `D:\test_automation` folder and is **not open** in Excel.

Run the following command:

```cmd
C:\Users\ccrea\AppData\Local\Programs\Python\Python312\python.exe IT23821590.py --excel "IT23821590.xlsx" --url "https://www.pixelssuite.com/chat-translator" --input-col "Input" --expected-col "Expected output" --wait-ms 10000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open --timeout-ms 30000

### What happens when you run it:

1. A Chrome browser opens automatically
2. The script navigates to the Chat Translator site
3. Each Singlish input is typed into the input box
4. The **Translate** button is clicked
5. The Sinhala output is captured and saved to the Excel file
6. Pass/Fail status is recorded automatically

> ⚠️ **Do not close the browser** while the script is running!

---

## Test Results

After running, open `IT23821590.xlsx` to view:

| Column | Description |
|--------|-------------|
| TC ID | Test case ID (Neg_0001 to Neg_0050) |
| Input length type | S (≤30 chars), M (31–299 chars) |
| Input | Singlish input text |
| Expected output | Correct Sinhala translation |
| Actual output | Output captured from the site |
| Status | PASS / FAIL |
| Singlish input types covered | Input type category |
| Evidence or rationale | Reason for the input type |

---

## Test Summary

- **Total test cases:** 50
- **Singlish input types covered:** All 24 types (minimum 2 per type)
- **Target:** All 50 cases should FAIL (demonstrating system weaknesses)

---

## Target Application

**URL:** [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

**Function tested:** Chat Sinhala transliteration (Singlish → Sinhala)

**Out of scope:** Standard Sinhala transliteration, backend APIs, performance/security testing
