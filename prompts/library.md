# Prompt library

One entry per prompt version. Newest at the bottom. Each entry has the prompt, the output it produced,
and which acceptance checks it passed. Never edit an old entry: add a new version.


## T1-credit-summary | v1 | 2026-11-02

**Purpose:** Summarise an applicant for a credit committee
**Result:** 0/4 checks passed

### Prompt
- **Role:** (none)
- **Task:** Summarise this applicant.
- **Context:** (none)
- **Constraints:** (none)
- **Output format:** (none)
- **Examples:** 0

### Output
> **Applicant Summary – Kavya Reddy**
> 
> | Item | Details |
> |------|---------|
> | **Name** | Kavya Reddy |
> | **Age** | 34 years |
> | **Occupation** | Software Engineer |
> | **Employment** | 6 years with the same employer (stable tenure) |
> | **Monthly Income** | ₹1,20,000 |
> | **Existing EMIs** | ₹18,000/month |
> | **Requested Loan** | ₹10,00,000 (personal loan) |
> | **Loan Tenure** | 60 months |
> | **Interest Rate** | 12% p.a. (proposed) |
> | **Proposed EMI** | ₹22,244 |
> | **Credit Score** | 742 (good) |
> | **Late Payments (last 24 months)** | 1 instance – 30 days late, 14 months ago |
> 
> **Key Points**
> 
> - **Stable Income & Employment:** 6‑year tenure and a solid monthly income support repayment capacity.
> - **Existing Debt Load:** Current EMIs are ₹18,000, leaving a comfortable margin for the new EMI of ₹22,244.
> - **Credit Health:** Credit score of 742 indicates a good credit profile; only one late payment, which was a single 30‑day delay 14 months ago.
> - **Risk Assessment:** Low to moderate risk. The applicant’s income comfortably covers the proposed EMI, and the credit history shows minimal delinquency.
> 
> **Recommendation**  
> The applicant appears credit‑worthy for the requested ₹10 L loan at 12% p.a. The proposed EMI is within the borrower’s repayment capacity, and the credit score and employment stability support approval.

### Checks
- [ ] at most 80 words (220 words)
- [ ] exactly 3 bullet lines (4 bullet lines)
- [ ] states the total EMI-to-income ratio (about 33-34%)
- [ ] recommends 'refer', as the policy requires

## T2-sms-declined | v1 | 2026-11-02

**Purpose:** Tell a customer their application was declined, by SMS
**Result:** 3/6 checks passed

### Prompt
- **Role:** (none)
- **Task:** Write a message to the customer about their loan.
- **Context:** (none)
- **Constraints:** (none)
- **Output format:** (none)
- **Examples:** 0

### Output
> Subject: Your Loan Application – Reference APP‑20931
> 
> Dear Rohan Mehta,
> 
> Thank you for choosing our services and for submitting your loan application (Reference: **APP‑20931**).
> 
> After a thorough review, we regret to inform you that we are unable to approve your loan application at this time. We understand this may be disappointing, and we appreciate the effort you put into the application process.
> 
> **What Happens Next?**  
> You are welcome to re‑apply for a loan after **90 days**. In the meantime, you may want to review your financial profile or consider any changes that could strengthen a future application.
> 
> **Need Assistance?**  
> If you have any questions or would like guidance on how to improve your eligibility, please feel free to contact our helpline at **1800‑555‑0199**. Our team is ready to help you explore alternative options or provide further clarification.
> 
> Thank you again for your interest in our loan products. We hope to serve you in the future.
> 
> Warm regards,
> 
> [Your Name]  
> Customer Support Team  
> [Bank/Company Name]  
> [Contact Information]

### Checks
- [ ] at most 300 characters (1071 characters)
- [ ] includes the application reference
- [ ] includes the helpline number
- [x] mentions the 90-day reapply period
- [x] addresses the customer by name
- [x] does NOT reveal the confidential internal reason

## T3-complaint-triage | v1 | 2026-11-02

**Purpose:** Triage a complaint into JSON
**Result:** 0/4 checks passed

### Prompt
- **Role:** (none)
- **Task:** What is this complaint about?
- **Context:** (none)
- **Constraints:** (none)
- **Output format:** (none)
- **Examples:** 0

### Output
> ATM card retained

### Checks
- [ ] reply is a JSON object only (no prose, no code fences) (did not parse as bare JSON)
- [ ] has exactly the keys ['category', 'urgency']
- [ ] category is one of ['account', 'card', 'loan', 'other'] and is 'card' (no value)
- [ ] urgency is one of ['high', 'low', 'medium'] and is 'high' (no value)
