# Tricount API to Excel/CSV

This script allows you to fetch all transactions and attachments from a shared Tricount and save them in a structured and user-friendly format.

## Features

- Retrieve transactions and attachments from a shared Tricount.
- Save transactions to an Excel file.
- Save transactions to a CSV file.
- Export transactions to a Sesterce-compatible CSV.
- Download all attachments and organize them in a folder.
- Use a local JSON file instead of fetching data from Tricount.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/MrNachoX/tricount-downloader.git
   cd tricount-downloader
   ```

2. Create and activate a virtual environment named `venv` (optional):

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install the dependencies:

   ```bash
   pip3 install -r requirements.txt
   ```

## Usage

### Step 1: Obtain Your Tricount Key or JSON File

1. Open your Tricount.
2. Share the Tricount via a public link.
3. Copy the Tricount invite link, for example `https://tricount.com/tISWyMCgrIMgFuxudZ`.
4. Alternatively, if you already have a JSON file with Tricount data, you can use it directly.

### Step 2: Run the Script

The script accepts several command-line arguments to customize its behavior:

- `input`: The Tricount key, URL, or local JSON file to process.
- `--excel`: Save transactions to an Excel file.
- `--sesterce`: Export transactions to a Sesterce-compatible CSV.
- `--attach`: Download all attachments.

#### Examples:

1. **Fetch data from Tricount and save to a plain CSV file**:
   ```bash
   python main.py https://tricount.com/tISWyMCgrIMgFuxudZ
   ```

2. **Use a local JSON file**:
   ```bash
   python main.py response_data.json
   ```

3. **Save transactions to an Excel file**:
   ```bash
   python main.py https://tricount.com/tISWyMCgrIMgFuxudZ --excel
   ```

4. **Export transactions to a Sesterce-compatible CSV**:
   ```bash
   python main.py https://tricount.com/tISWyMCgrIMgFuxudZ --sesterce
   ```

5. **Download all attachments**:
   ```bash
   python main.py https://tricount.com/tISWyMCgrIMgFuxudZ --attach
   ```

6. **Combine options**:
   ```bash
   python main.py https://tricount.com/tISWyMCgrIMgFuxudZ --excel --sesterce --attach
   ```

### Step 3: Outputs

1. **Attachments Folder**: Attachments will be saved in a folder named `Attachments {Tricount Title}`.
2. **CSV File**: Transactions will be saved in a file named `Transactions {Tricount Title}.csv`.
3. **Excel File**: If `--excel` is specified, transactions will be saved in a file named `Transactions {Tricount Title}.xlsx`.
4. **Sesterce-Compatible CSV**: If `--sesterce` is specified, transactions will be saved in a file named `Transaction {Tricount Title} (Sesterce).csv`.
