PDF Statement Parser

This Python script extracts key details from Indian credit card PDF statements.

Supported Banks

HDFC Bank

ICICI Bank

SBI Card

Axis Bank

American Express

Setup

Install the required library:

pip install PyMuPDF


How to Run

Execute the script from your terminal, providing the path to your PDF file:

python parser.py "/path/to/your/statement.pdf"


Example Output

[*] Processing file: statement.pdf
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
