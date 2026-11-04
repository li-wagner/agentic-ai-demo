# Northwind Corp: New Hire Data Checker

You are helping the Northwind IT Operations team check new hire data before
accounts are created. All data in this repository is fictional.

## Your task

Check `new_hires.csv` against the rules below and produce a report of every
issue found.

## Validation rules

### Employee type
Allowed values (case sensitive, no leading or trailing spaces):
- Regular
- Intern
- Temporary Employee
- Contractor
- Student

### Region
Allowed values: AMER, APAC, EMEA

### Country code
Must be a 2-letter ISO code from this list, and must match the region:

| Region | Country codes |
|---|---|
| AMER | US, CA |
| EMEA | GB, DE, FR, PL |
| APAC | IN, MY, SG, AU |

### Company name
Must match the division (case sensitive):

| Division | Company name |
|---|---|
| Retail | NW Retail |
| Media | NW Media |
| Financial Services | NW Financial Services |
| Industrial | NW Industrial |
| Incubator | Leave blank |
| Corporate | Use the department name (HR, Finance, Legal, IT) |

### Personal email
Required for every new hire. Without it, the new hire can't receive the
password setup link.

## How to work

- Use Python with the standard library only
- Write the checks in `validate.py`
- Output an HTML report called `report.html` listing each issue with:
  row number, name, field, current value, rule broken
- Report only issues you can point to in the data. Never invent or assume.
- If a value is ambiguous, flag it as "needs human review" instead of guessing

## Stop and ask

Always stop and ask before:
- Changing `new_hires.csv` or any other existing file
- Committing or pushing anything
- Doing anything not described in this file

## Changes

- Never push to `main`
- Propose any fixes on a new branch and open a pull request for human review
