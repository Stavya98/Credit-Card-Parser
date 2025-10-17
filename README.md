PDF Credit Card Statement Parser

A command-line Python script to parse key information from Indian credit card statements in PDF format. It automatically detects the bank from the PDF content and extracts essential details like the cardholder's name, payment due date, total balance, and more.

Key Features

Automatic Bank Detection: Identifies the credit card issuer from the PDF's text.

Data Extraction: Pulls common, important fields from the statement.

Simple & Extensible: Add support for new banks by simply updating the configuration list—no need to change the core logic.

Local Processing: All parsing is done locally on your machine. Your data is never transmitted anywhere.

Command-Line Interface: Easy to integrate into automated workflows and scripts.

Supported Banks

This script is pre-configured to parse statements from the following Indian banks:

HDFC Bank

ICICI Bank

SBI Card

Axis Bank

American Express (India)

Requirements

Python 3.7+

PyMuPDF library

⚙️ Installation

Clone the repository:

git clone [https://github.com/your-username/pdf-parser.git](https://github.com/your-username/pdf-parser.git)
cd pdf-parser


Set up a virtual environment (recommended):

python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`


Install the required library:

pip install PyMuPDF


▶️ Usage

Run the script from your terminal and provide the full path to the PDF statement file as an argument.

Important: Enclose the file path in quotes if it contains spaces.

python parser.py "/path/to/your/credit_card_statement.pdf"


Example Output

When the script successfully parses a file, it will produce output similar to this:

[*] Processing file: hdfc_sample_statement.pdf
[+] Issuer Detected: HDFC Bank

=========================
   Extraction Results
=========================
  Cardholder Name     : YOUR NAME
  Card Last 4 Digits  : 1234
  Payment Due Date    : 25/10/2025
  Total Balance Due   : ₹15,420.50
  Billing Cycle       : Statement Date: 05/10/2025
=========================


If a field cannot be found, it will be marked as Not Found.

🛠️ How to Add a New Bank

The script is designed to be easily extended. To add support for a new bank, follow these steps:

Open parser.py in a text editor.

Find the PARSER_CONFIGS list.

Add a new dictionary to the list for the new bank. Copy an existing one to use as a template.

Update the dictionary fields:

"issuer_name": The full name of the bank for display purposes (e.g., "Kotak Mahindra Bank").

"required_keywords": A list of unique, lowercase strings found in that bank's statements (e.g., ["kotak", "kotak.com"]). The script uses these to identify the bank.

"patterns": A dictionary containing the regular expressions (regex) needed to find each piece of data.

The key is the field name (e.g., 'Cardholder Name').

The value is the regex pattern to find that data.

For custom formatting (like adding a '₹' symbol), provide a tuple: (regex_pattern, lambda m: f"₹{m.group(1)}").

Save the file and test with a sample statement from the new bank.

Disclaimer

This script is intended for personal use. It processes PDF files locally and does not collect or transmit any personal or financial data. The user is solely responsible for how they use this tool and the data it extracts.

License

This project is licensed under the MIT License. See the LICENSE file for details.