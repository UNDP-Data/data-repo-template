# 📦 Data Repository Template
This repository serves as a template for organizing and managing data files across projects. It provides a standardized structure for storing, validating, and sharing datasets effectively.

## ✅ Automated Data Validation
A GitHub Action is included to automatically validate uploaded data files (`.csv`, `.json`, `.xlsx`, `.xls`) whenever a commit or pull request modifies files in the `data/` or `schema/` folders.

__🔁 What Happens on Validation Failure__
If validation fails:
* 🔍 The workflow identifies the modified data files
* ♻️ Reverts only the modified files to their previous state
* 💬 Commits the reversion with an appropriate message
* ❌ Fails the workflow to prevent invalid data from being merged

You can view detailed logs and errors in the `GitHub Actions` tab.

__🔧 Trigger Conditions__
This workflow runs on:
* Push to any branch when: Files in data/ or schema/ folders with supported extensions are changed
* Pull Requests modifying those same files

__🛠️ Validation Script__
The validation logic is handled by `validation/validate.js`.

🔍 How It Works:
[1] Looks for files in `data/` with one of the following extensions: `.csv`, `.xlsx`, `.xls`, `.json`.
[2] For each data file, checks for a corresponding schema file in the schema/ directory:
    * The schema file must have the same base name and a .json extension.
    * If no schema exists, the data file is considered valid by default.
[3] Validates the data against the schema.
[4] Logs success or details of any validation errors.

## Related Repos
* [name of the repo where this data is used](link to repo where this data is used): This is the application or project that uses this dataset. [View the application site]({{link to the project site here}})


## Contact
For questions or suggestions, please open an issue or contact the repository maintainer.