# 🛡️ Insurance Claim Validator

A lightweight Python tool to validate insurance claims against policy rules. This project simulates a real-world data validation workflow by applying logic checks such as policy status, claim limits, and date ranges. The output is a clean Excel report flagging any issues for auditing and review.

---

## 📌 Features

- ✅ Validates claim amounts against policy coverage limits  
- 📅 Checks if claims are filed within the active policy period  
- ❌ Flags claims linked to inactive or invalid policies  
- 📊 Exports a comprehensive Excel report with validation results

---

## 🛠️ Technologies Used

- Python 3.x  
- pandas  
- openpyxl (for Excel export)  
- CSV file input/output

---

## 📁 File Structure

insurance-claim-validator/
├── claims.csv
├── policies.csv
├── insurance_claim_validator.py
├── validated_claims_report.xlsx
└── README.md

yaml
Copy

---

## 📂 Sample Data

### policies.csv
| policy_id | policyholder_name | policy_limit | policy_start | policy_end | policy_status |
|-----------|-------------------|---------------|---------------|------------|----------------|
| P001 | Alice Smith | 10000 | 2023-01-01 | 2023-12-31 | Active |
| P002 | Bob Johnson | 15000 | 2023-03-01 | 2023-12-31 | Lapsed |
| P003 | Carla White | 8000 | 2023-05-01 | 2024-04-30 | Active |

### claims.csv
| claim_id | policy_id | claim_amount | claim_date |
|----------|------------|----------------|-------------|
| C101 | P001 | 12000 | 2023-07-15 |
| C102 | P002 | 10000 | 2023-09-10 |
| C103 | P004 | 5000 | 2023-08-20 |

---

## 🚀 How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/YOUR_USERNAME/insurance-claim-validator.git
   cd insurance-claim-validator
Ensure you have the required packages:

bash
Copy
pip install pandas openpyxl
Run the script:

bash
Copy
python insurance_claim_validator.py
Open validated_claims_report.xlsx to view results.

📋 Example Output
Each claim is validated with a result like:

"Valid"

"Claim exceeds policy limit"

"Policy not active"

"Claim date out of policy coverage period"

"Invalid policy ID"

👨‍💼 Author: John Rand
