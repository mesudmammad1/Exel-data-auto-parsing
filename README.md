# Automatic Text Parser in M Language (Power Query)

This repository contains an Excel Power Query (M Language) script that automatically parses structured text data and converts it into a clean, structured table format.

## Features

- Reads data from a plain text file.
- Splits content into rows.
- Removes empty lines.
- Parses key-value pairs such as:
  - browser
  - profile
  - url
  - path
  - login
  - password
- Handles missing fields with fallback values (e.g., "NULL" or "URL nothing!").
- Outputs a clean and structured table with trimmed and renamed columns.

## Output Table Columns

- *Browser*
- *Profile*
- *Web App URL*
- *Installed App Path*
- *Username*
- *Password*

## How It Works

The parser uses List.Generate to iterate through lines that begin with browser: and collects the next 8 lines as a structured record. It uses safe extraction and fallback handling to ensure stability even when some fields are missing.

## Setup

1. Open Excel and go to *Power Query Editor*.
2. Copy and paste the M code into a new blank query.
3. Modify the path to your .txt file if needed:
   ```m
   File.Contents("C:\Users\.txt")

4.	Load the data into your worksheet.

Example Use Case

Ideal for parsing exported logs, structured scan results, or any repeatable pattern in .txt format where fields are structured but not in a standard file format (e.g., JSON or CSV).

License

MIT License — feel free to use, modify, and share.

Author

Created by Masud Mammadli. Contributions and improvements are welcome!
