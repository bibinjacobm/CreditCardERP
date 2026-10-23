# CreditCardERP
Personal Credit Card Management ERP Desktop Application

# User Guide

## First steps
1. **Cards → ＋ Add Card.** Enter name, issuer, last 4 digits, network, limit, billing day (the day your statement is generated) and expected due days (days from statement to due date).
2. **Bills → ＋ Add Bill** when a statement arrives. Statement and due dates are suggested from the card's billing cycle. Enter the **Total Amount Due** and **Minimum Amount Due exactly as printed** — the app never recalculates them.
3. **Payments → ＋ Add Payment** for each payment. Split payments are unlimited; the amount defaults to the remaining outstanding.

## Status rules (computed live)
| Status | Meaning |
|---|---|
| Pending | Nothing paid yet, due date not passed |
| Minimum Paid | Paid exactly the minimum amount due; balance remains |
| Partially Paid | Any other part payment |
| Paid in Full | Payments equal the total due |
| Overpaid | Payments exceed the total due (excess shown for tracking only) |
| Overdue | Due date passed and less than the minimum was paid |

**Fresh statements:** each new statement is taken as-is. If an earlier statement was overpaid or part-paid, the issuer has already adjusted it in the new statement, so the app does not carry anything forward. Older statements are marked *superseded* and drop out of Outstanding / Due / Overdue totals.

## Dashboard colours
Red = due today or overdue · Orange = due in 1–3 days · Yellow = due in 4–7 days · Green = paid in full.

## Billing Cycle Planner
Shows each active card's next expected statement and days remaining, and reminds you when a recent statement hasn't been entered yet.

## Reports
Card Wise, Issuer Wise, Due Date, Overdue and Payment History. Choose a period (Current FY = 1 Apr–31 Mar, Previous FY, Current Month, Custom, All Time), then export to PDF, Excel or CSV, or Print. Double-click a row to jump to the bill or payment.

## Search
Type in the top bar and press Enter (Ctrl+F). Searches card names, last 4, issuers, notes, references, exact amounts (e.g. `25000`) and dates (e.g. `28-10-2026`).

## Text size
*Settings → Appearance → Text size*: Small, Normal, Large (default), Extra Large, Huge. Or press **Ctrl +** / **Ctrl −**, and **Ctrl 0** to return to Large. The choice is remembered on this computer.

## Backups
Created automatically on exit and once a day, plus before updates, migrations and restores. The latest 30 are kept in the backup folder.

**Choosing the backup folder:** *Backup → Change Folder…* and pick any folder — a second drive, a USB drive, or a cloud-synced folder such as OneDrive, Google Drive or Dropbox for an off-site copy. You can copy existing backups across when switching. *Use Default* returns to `%LOCALAPPDATA%\CreditCardERP\backups`.

Only backup ZIP files go to the chosen folder; the live database always stays on this computer, because cloud sync tools can corrupt a database that is open. If the chosen folder is unavailable (drive unplugged, cloud app signed out), backups go to the default folder and the Backup screen shows a red warning until the folder is back. **Backup → Restore Selected** to roll back. To move to a new PC, copy a backup ZIP across and use *Restore from File…*.

## Security
**Settings → Security** sets an optional 4–8 digit PIN required at start-up. If you forget it, restore a backup made before the PIN was set (PIN data is not included in settings exports but is inside the database).

## Shortcuts
Ctrl+F search · Ctrl+B new bill · Ctrl+P new payment · F5 refresh · Ctrl+Enter save a form · Esc close a form.

## Uninstalling
Uninstall removes the program only. To erase your data too, delete `%LOCALAPPDATA%\CreditCardERP`.
