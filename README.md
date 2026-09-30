# Ledgerly

A browser-based accounting education prototype. Learners record journal entries for a small business, watch an animated Balance Beam tilt as debits and credits change, and see T-accounts update live.

Built with Claude in plain HTML, CSS, and JavaScript. It has no build step, no dependencies, and no backend.

**Live demo:** https://ledgerlyprototype.vercel.app/

![Ledgerly journal workspace] https://github.com/jarodgabrielcarrillo/Ledgerly-Protoype/blob/e561345b07e90028efaa2b7ccbf5df3f7f0becaa/Preview.png

## What it does

- **Journal workspace** (`workspace.html`): the Balance Beam tilts toward the heavier side and the Post button unlocks only when debits equal credits and the accounts are named. Posted lines update live T-accounts.
- **Scripted scenario**: Driftwood Coffee Co., Day 3. Record a bean delivery bought on credit, then a partial payment to the supplier.
- **The Desk** (`dashboard.html`): case file, closing streak, and a five-step accounting cycle dial (journalize, post, trial balance, adjusting entries, close the period).
- **The Library** (`library.html`): 16 accounts with their normal balances.
- **Scenario generator** (`generator.html`): deals a business from a hardcoded pool.
- **Day 2 review and progress** (`review.html`, `progress.html`): a marked review and a skills balance sheet.
- **Design**: a documented "Modern Ledger" design system (`DESIGN-SYSTEM.md`) with light and dark themes and reduced-motion support.

## Run it

```bash
python -m http.server 3000
```

Open http://localhost:3000. Double-clicking `index.html` also works.

## Roadmap

The generator and the Day 3 scenario use scripted data. To add live AI scenarios, replace `deal()` in `generator.html` with a call to an endpoint that returns `{name, sub, industry, days, accts, blurb, transactions[]}`. The `TXNS` array in `workspace.html` already matches that shape.
