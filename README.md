# ALU Back-End: API

## Description

This project explores the use of Python to interact with REST APIs, as an alternative to Bash scripting for tasks involving data gathering and transformation. It demonstrates how to fetch employee TODO data from a remote API and export it in multiple formats (CSV and JSON).

## Background

Old-school system administrators rely heavily on Bash scripting. However, Bash is not suited for tasks like interacting with APIs or handling structured data formats like JSON and CSV. This project uses Python — the language of choice for modern Site Reliability Engineers (SREs) — to fetch, process, and export data cleanly and efficiently.

## Requirements

- Python 3
- `requests` library

Install dependencies:
```bash
pip3 install requests
```

## Files

| File | Description |
|------|-------------|
| `0-gather_data_from_an_API.py` | Fetches and displays an employee's TODO list progress |
| `1-export_to_CSV.py` | Exports an employee's tasks to a CSV file |
| `2-export_to_JSON.py` | Exports an employee's tasks to a JSON file |
| `3-dictionary_of_list_of_dictionaries.py` | Exports all employees' tasks to a single JSON file |

## Usage

### Task 0 — Display TODO progress
```bash
python3 0-gather_data_from_an_API.py <employee_id>
```
**Example:**
```
Employee Ervin Howell is done with tasks(8/20):
	 distinctio vitae autem nihil ut molestias quo
	 voluptas quo tenetur perspiciatis explicabo natus
	 ...
```

### Task 1 — Export to CSV
```bash
python3 1-export_to_CSV.py <employee_id>
```
Generates `<employee_id>.csv` with format:
```
"USER_ID","USERNAME","TASK_COMPLETED_STATUS","TASK_TITLE"
```

### Task 2 — Export to JSON
```bash
python3 2-export_to_JSON.py <employee_id>
```
Generates `<employee_id>.json` with format:
```json
{"USER_ID": [{"task": "TASK_TITLE", "completed": true, "username": "USERNAME"}]}
```

### Task 3 — Export all employees to JSON
```bash
python3 3-dictionary_of_list_of_dictionaries.py
```
Generates `todo_all_employees.json` with all employees and their tasks.

## API

Data is fetched from the public REST API:
```
https://jsonplaceholder.typicode.com
```

Endpoints used:
- `/users/<id>` — fetch a single employee
- `/users` — fetch all employees
- `/todos?userId=<id>` — fetch todos for a specific employee
- `/todos` — fetch all todos

## Author

Alain — ALU Software Engineering student
