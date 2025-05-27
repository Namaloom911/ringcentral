```markdown
# RingCentral Deleted Messages Extractor

## Overview

This Python project connects to the RingCentral API using JWT authentication to retrieve deleted SMS and text messages from a specified extension. It offers two scripts: one that processes and organizes messages into structured Excel reports (`app.py`) and another that outputs results to the console (`app_no_excel.py`), making it easy to analyze and archive deleted communications.

---

## Features

- Secure authentication using environment variables (.env)  
- Fetches deleted messages within a configurable date range (default: last 30 days)  
- Groups messages into conversations by contact  
- `app.py`: Exports data to Excel files for reporting and easy review  
- `app_no_excel.py`: Outputs conversation details to the console without Excel dependencies  
- Handles API pagination and filters for deleted SMS/text messages  
- Uses popular Python libraries: `ringcentral`, `pandas`, `openpyxl`, `python-dotenv`

---

## Requirements

- Python 3.7 or higher  
- RingCentral developer account with API credentials  
- Required Python packages:
  - `ringcentral`
  - `python-dotenv`
  - For `app.py` only:
    - `pandas`
    - `openpyxl`

Install dependencies with:

```bash
pip install ringcentral python-dotenv pandas openpyxl
```

---

## Setup

1. Clone the repository:

```bash
git clone https://github.com/Namaloom911/ringcentral
cd ringcentral
```

2. Create a `.env` file in the project root with your RingCentral credentials:

```env
CLIENT_ID=your_client_id
CLIENT_SECRET=your_client_secret
SERVER_URL=https://platform.devtest.ringcentral.com
JWT_TOKEN=your_jwt_token
```

3. Modify the `AGENT_EXTENSION` variable in the desired script (`app.py` or `app_no_excel.py`) to the desired RingCentral extension ID (11-digit extension ID).

---

## Usage

### Option 1: Generate Excel Reports (`app.py`)
Run the script to fetch deleted messages and generate Excel reports:

```bash
python app.py
```

The output Excel files will be saved in the `rpt/` directory:
- `all_messages.xlsx` — All retrieved messages
- `deleted_messages.xlsx` — Only deleted messages
- `conversations.xlsx` — Grouped conversations
- `readable.xlsx` — Human-readable conversation summaries

### Option 2: Console Output (`app_no_excel.py`)
Run the script to fetch deleted messages and display results in the console:

```bash
python app_no_excel.py
```

This script prints conversation details without generating Excel files, ideal for environments without Excel dependencies.

---

## Notes

- Ensure your `.env` file is included in `.gitignore` to keep your credentials secure.
- Both scripts handle pagination automatically to retrieve all relevant messages.
- Customize the date range in the `params` section of the scripts as needed (default: last 30 days).
- `app_no_excel.py` is lightweight and does not require `pandas` or `openpyxl`, making it suitable for minimal setups.

---

## License

This project is licensed under the MIT License.

---

## Contact

For questions or support, please contact [ghanam4474@gmail.com](mailto:ghanam4474@gmail.com).
```