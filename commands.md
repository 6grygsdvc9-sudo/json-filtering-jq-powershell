# Commands Reference

Full set of commands used to filter and search the JSON dataset.

## Verify the dataset

```bash
head dataset.json
jq empty dataset.json
```

## Filter by category

```bash
jq -r '.[] | select(.category == "Information Gathering") | .tool' dataset.json
```

**PowerShell equivalent:**
```powershell
Get-Content dataset.json | ConvertFrom-Json | Where-Object { $_.category -eq "Information Gathering" } | Select-Object -ExpandProperty tool
```

## Pattern matching with regex

Find entries whose description contains at least one digit:

```bash
jq -r '.[] | select(.description | test("[0-9]")) | .tool' dataset.json
```

`[0-9]` matches any single digit, 0 through 9 — not the literal number 9.

## Filter by description length

Find entries with descriptions longer than 30 characters:

```bash
jq -r '.[] | select(.description | length > 30) | .tool' dataset.json
```
