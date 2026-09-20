### 🛡️ Do Not Overwrite (`collect.sh`)

An evidence preservation copy helper designed to securely bank file copies without accidentally overwriting existing evidence.

#### Key Features & Requirements
- **Strict Argument Check:** Accepts exactly two arguments: `<source_file>` and `<destination_path>`.
- **Source Validation:** Ensures the source file exists and is a regular file (empty source files are permitted).
- **Overwrite Protection:** Checks that the destination target does not already exist before executing the copy operation.
- **Fail-Safe Behavior:** Rejects invalid or missing sources and occupied destination paths with a non-zero exit status, leaving the file system unchanged.

#### Usage

bash
# General syntax
~/bin/collect.sh <source_file> <destination_path>

# Example: Bank a log file to a case directory
~/bin/collect.sh ~/incoming/night-watch.log ~/cases/toolkit-02/preserved.log

<img width="1154" height="675" alt="image" src="https://github.com/user-attachments/assets/772ef826-8945-4356-a4cb-492e2ea40dd3" />
<img width="1159" height="679" alt="image" src="https://github.com/user-attachments/assets/382cdf9b-afad-4380-84aa-86739d4a8a22" />
