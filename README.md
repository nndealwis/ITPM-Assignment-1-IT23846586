# Test Automation - Singlish to Sinhala Translator

Automated test runner for the Pixels Suite Chat Translator. This script uses Playwright to run UI tests, collect actual outputs, and compare them against expected results.

---

## Prerequisites

- **Windows OS** (or adjust commands for Linux/Mac)
- **Python 3.10+** installed (check with `py --version`)
- **Excel file** with test cases (columns: Input, Expected Output, etc.)

---

## Installation

### 1. Install Python Packages

Run these commands from the project directory:

```powershell
# Upgrade pip
py -m pip install -U pip

# Install required packages
py -m pip install playwright openpyxl
```

### 2. Install Playwright Browsers

```powershell
py -m playwright install
```

This downloads Chromium and other browser engines (one-time setup).

---

## Running Tests

### Basic Command

```powershell
py IT23846586.py --excel "IT23846586-Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator"
```

### Full Command with Recommended Options

```powershell
py IT23846586.py --excel "IT23846586-Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1
```



### Run and Save Results to a New File

```powershell
py IT23846586.py --excel "IT23846586-Assignment 1 - Test cases.xlsx" --output "results.xlsx" --wait-ms 5000
```

### Run in Headless Mode (No Browser Visible)

```powershell
py IT23846586.py --excel "IT23846586-Assignment 1 - Test cases.xlsx" --headless
```

### Run with Slower Typing for Visibility

```powershell
py IT23846586.py --excel "IT23846586-Assignment 1 - Test cases.xlsx" --type-delay-ms 150 --slow-mo-ms 500
```

### Run and Keep Browser Open for Inspection

```powershell
py IT23846586.py --excel "IT23846586-Assignment 1 - Test cases.xlsx" --keep-open
```
Then press **CTRL+C** in the terminal to stop and save.

---

## Troubleshooting

### Error: `ModuleNotFoundError: No module named 'playwright'`
→ Run: `py -m pip install playwright openpyxl`

### Error: `Permission denied` when saving
→ Close the Excel file in Excel before running the script.

### Error: `Could not find Chat UI locators`
→ Check that the URL is correct and the website is accessible.

### Browser crashes mid-test
→ Try increasing `--timeout-ms` and `--wait-ms` values.

### Tests run very slowly
→ This is normal with `--type-delay-ms 80`. Reduce to 30 for faster runs.

---

## Output

After completion:
- **Actual output** column is filled with the translator's output
- **Status** column shows:
  - `PASS` — if actual matches expected
  - `FAIL` — if actual doesn't match expected
  - `COLLECTED` — if no expected value was provided
  - `UI Error` — if something went wrong during the test

Results are saved to the `--output` file (or the same `--excel` file if no output specified).



## Support

For issues or questions, check:
- Excel file has proper headers and test data
- Website URL is accessible
- Python and Playwright are properly installed
- Browser/internet connection is stable
