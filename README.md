# Financial Management Buddy

**A paycheck-first money planner and learning center by Chris Foderingham Sr. and Heather Foderingham**

**Status:** **In Development as of 11/10/2026**

Intended home: **https://finman.chrisfoderingham.com**. This repository will supply the application and deployment configurations needed; which does not consitute that the domain or live banking API configurations have been deployed.

Protect everyday needs and a cash cushion before choosing extra debt payments. Understanding the tradeoffs, recording your decisions, and retaining complete control of your money.

## Run locally for free (Main Goal)

Install Node.js 22 or newer, open this folder, then run:

```inside powershell:
npm start
```

Open **http://127.0.0.1:4186**. No package installation, account, cloud, or bank credentials are needed for the local app. The initial workspace contains explicitly fictional sample data. Open **Settings → Start empty personal workspace** before entering your own records.

``` inside powershell:
npm run build
npm test
```

The build produces `dist/` for AWS Amplify static hosting. Backend dependencies are separate from the free local planner.

## Learning the Included experiences

| Section | What it does |
| --- | --- |
| Overview | Debt totals, paycheck headroom, payoff chart, categorized spending and next steps |
| Paycheck planner | Actual net pay, hourly or salary estimates, custom federal/state/local/payroll withholding, recurring due dates, envelopes, reserves and cash floor |
| Debt payoff | Debt inventory, Snowball, Avalanche, Hybrid and custom priority comparisons, eligibility controls, monthly forecast and CSV export |
| Transactions | Manual entries, CSV import, suggested categories, category corrections, refunds and pending-status handling |
| Accounts | Manual balances and optional authenticated Plaid Link, sync and disconnect |
| Learning center | Twelve practical lessons, analogies, reflection notes and reading progress |
| Activity & alerts | Saved deposit, transfer and payment activity; optional browser notifications while the page remains open |
| Settings | Empty personal mode, fictional demo, JSON backup and restore, cloud sign-in |

## Banking and the user's decision

The optional backend can track **real account activity** after you deploy it and configure eligible Plaid access. Plaid Sandbox supplies mock data. All bank features in this project are read-only: saving a budget, recording a payment or choosing a strategy never sends money. Execute payments and transfers at your bank or creditor after reviewing the plan. Plaid access tokens and credentials stay on the server.

The local workspace uses browser storage, which is not encrypted by this application. Use a trusted device, export private backups, and never enter bank passwords, full account numbers or API secrets into planner fields. Cloud exports contain financial records but no Plaid access tokens.

## Free usage and its limits

The manual/local planner has no subscription or service dependency. Hosting, Cognito, DynamoDB, Lambda, API Gateway, SQS, KMS, Secrets Manager and real Plaid access may incur charges. Free credits, trials and allowances are eligibility- and usage-dependent. In particular, the optional customer-managed KMS key and Secrets Manager secret can cost money at low traffic. This is **not a promise of permanently free real-bank connectivity**.

## Deployment and implementation

- [Amplify and optional backend setup](docs/AWS-DEPLOYMENT.md)
- [Plaid consent, sync, webhooks and disconnect](docs/PLAID-SETUP.md)
- [Calculation rules and limitations](docs/CALCULATIONS.md)
- [Database model and security boundaries](docs/ARCHITECTURE.md)
- [Troubleshooting](docs/TROUBLESHOOTING.md)
- [Verification and staged development](docs/VERIFICATION.md)

Readable code comments explain business rules and why they exist. They describe implementation reasoning and assumptions, rather than imply that the app can determine the right personal financial decision for everyone.

## Source references

- [CFPB: debt reduction approaches](https://www.consumerfinance.gov/archive/blog/how-reduce-your-debt/)
- [CFPB: Your Money, Your Goals toolkit](https://www.consumerfinance.gov/consumer-tools/educator-tools/your-money-your-goals/toolkit/)
- [IRS withholding estimator](https://www.irs.gov/individuals/tax-withholding-estimator)
- [Plaid billing and environment limits](https://plaid.com/docs/account/billing/)
- [Plaid transaction synchronization](https://plaid.com/docs/api/products/transactions/#transactionssync)
- [AWS Amplify pricing](https://aws.amazon.com/amplify/pricing/)

Review current provider terms before enabling paid resources or using the application for personal banking. This first release is a planning implementation with tested domain logic; live deployment and end-to-end bank certification remain separate setup work.
