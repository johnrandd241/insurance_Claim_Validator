import pandas as pd

# Load sample data
claims = pd.read_csv("claims.csv")
policies = pd.read_csv("policies.csv")

# Merge datasets on policy_id
merged = claims.merge(policies, on="policy_id", how="left")

# Convert dates
merged["claim_date"] = pd.to_datetime(merged["claim_date"])
merged["policy_start"] = pd.to_datetime(merged["policy_start"])
merged["policy_end"] = pd.to_datetime(merged["policy_end"])

# Validation logic
def validate_claims(row):
    errors = []
    if pd.isnull(row["policyholder_name"]):
        errors.append("Invalid policy ID")
    else:
        if row["policy_status"] != "Active":
            errors.append("Policy not active")
        if row["claim_amount"] > row["policy_limit"]:
            errors.append("Claim exceeds policy limit")
        if row["claim_date"] < row["policy_start"] or row["claim_date"] > row["policy_end"]:
            errors.append("Claim date out of policy coverage period")
    return "; ".join(errors) if errors else "Valid"

merged["validation_result"] = merged.apply(validate_claims, axis=1)

# Export to Excel
merged.to_excel("validated_claims_report.xlsx", index=False)

print("Validation completed. Output saved to 'validated_claims_report.xlsx'.")
