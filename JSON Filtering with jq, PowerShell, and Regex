# JSON Filtering with jq, PowerShell, and Regex

A hands-on project exploring different ways to filter and search structured 
data (JSON) using command-line tools in a Linux environment.

## What This Demonstrates

- Parsing and validating JSON datasets from the command line
- Filtering structured data with **jq** (category matching, pattern matching, 
  length-based filtering)
- Performing equivalent filtering operations in **PowerShell**
- Writing and applying **regular expressions** to search text patterns within 
  a dataset
- Comparing multiple tools/approaches to solve the same data-filtering problem

## Tools Used

- Kali Linux
- `jq` (command-line JSON processor)
- PowerShell
- Regular expressions

## Example Filters

**Filter by category (jq):**
```bash
jq -r '.[] | select(.category == "Information Gathering") | .tool' dataset.json
```

**Equivalent filter (PowerShell):**
```powershell
Get-Content dataset.json | ConvertFrom-Json | Where-Object { $_.category -eq "Information Gathering" } | Select-Object -ExpandProperty tool
```

**Pattern matching with regex (jq):**
```bash
jq -r '.[] | select(.description | test("[0-9]")) | .tool' dataset.json
```

**Filtering by text length (jq):**
```bash
jq -r '.[] | select(.description | length > 30) | .tool' dataset.json
```

## What I Learned

Working through this project reinforced that command-line filtering tools 
look more intimidating than they actually are — once you break a command down 
piece by piece, each part has a clear, logical job. I also got hands-on 
practice troubleshooting a real environment issue (getting PowerShell running 
on an Apple Silicon Kali VM), which turned out to be one of the more valuable 
parts of the project.

## Full Commands Reference

See `commands.md` for the complete set of commands used.
