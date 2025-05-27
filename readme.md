````markdown
# RingCentral Deleted Messages Extractor

## Overview

This Python project connects to the RingCentral API using JWT authentication to retrieve deleted SMS and text messages from a specified extension. It processes and organizes the messages into structured Excel reports, making it easy to analyze and archive deleted communications.

---

## Features

- Secure authentication using environment variables (.env)  
- Fetches deleted messages within a configurable date range  
- Groups messages into conversations by contact  
- Exports data to Excel files for reporting and easy review  
- Handles API pagination and filters by message availability  
- Uses popular Python libraries: `pandas`, `openpyxl`, `ringcentral` SDK

---

## Requirements

- Python 3.7 or higher  
- RingCentral developer account with API credentials  
- Required Python packages:
  - `ringcentral`
  - `pandas`
  - `openpyxl`
  - `python-dotenv`

Install dependencies with:

```bash
pip install ringcentral pandas openpyxl python-dotenv
````

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

3. Modify the `AGENT_EXTENSION` variable in the script to the desired RingCentral extension ID.

---

## Usage

Run the script to fetch deleted messages and generate reports:

```bash
python your_script_name.py
```

The output Excel files will be saved in the `rpt/` directory:

* `all_messages.xlsx` — All retrieved messages
* `deleted_messages.xlsx` — Only deleted messages
* `conversations.xlsx` — Grouped conversations
* `readable.xlsx` — Human-readable conversation summaries

---

## Notes

* Ensure your `.env` file is included in `.gitignore` to keep your credentials secure.
* The script handles pagination automatically to retrieve all relevant messages.
* Customize the date range in the parameters section as needed.

---

## License

This project is licensed under the MIT License.

---

## Contact

For questions or support, please contact \[[ghanam4474@gmail.com](mailto:your-ghanam4474@gmail.com)].
