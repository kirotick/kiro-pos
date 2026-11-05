# Changelog for kiro-pos

All notable changes are recorded here. Versions follow semantic versioning.

## v1.1.0 (2026-11-05)
- UPI payments (G-01, interim): a UPI reference (UTR) is now required before "Payment received", in the UPI tab and in split payments. 6 to 30 letters or numbers.
- Every UPI payment is saved with `verified: false` and `confirmedBy: "cashier"`, and is shown as "UPI (confirmed by cashier, not verified)" on the collect screen, paid screen, bill details and printed receipt (with its reference).
- Close day: new card "UPI to check with your bank" (UPI total, bills with UPI, UPI payments, payments with no reference), also on the printed day report and in the activity log.
- No change to amounts, GST, round-off or invoice numbering. KIRO still cannot verify UPI payments itself; that needs a payment provider (kiro-payments, disabled).

## v1.0.0 (2026-11-05)
- Created from `kirotick/KIRO_POS` (commit `252de09`) with the full history of the files it owns.
- Added README, CONTRIBUTING, SECURITY, CODEOWNERS, pull request template, Dependabot and CI with pinned actions.
