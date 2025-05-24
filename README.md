# Queries Generator

This script generates SQL queries for [INSERT/DELET/UPDATE] [your_table] in bulk. It reads IDs from a CSV file and creates individual queries for each id.

## Features:

- Reads IDs from a CSV file named for examlpe 'ids.csv'
- Splits IDs into smaller batches of for examlpe 200,000 for efficient processing
- Generates SQL queries for each ID
- Saves generated queries to separate CSV files

## Usage:

1. Ensure you have pandas installed (`pip install pandas`)
2. Place your 'ids.csv' file in the same directory as this script
3. Run the script to generate queries

## Configuration:

- The script processes IDs in batches of 200,000 (configurable)
- Output files are saved as 'bulk_queries_X.csv' where X is the batch number

## How it works:

1. Read user IDs from 'ids.csv'
2. Calculate the number of batches needed
3. Iterate through each batch of IDs
4. Generate SQL queries for each ID
5. Save queries to separate CSV files

## Example Output:

Each output file contains one row per user, with the following structure:
| query |
|-------|
| UPDATE your_table SET `value` = '1', `updated_at` = NOW() WHERE `id` = [USER_ID] AND `key` = 'default'; |

## Note:

- Make sure to review and test the generated queries before executing them on your database
- Adjust the batch size if needed to optimize performance for your specific dataset