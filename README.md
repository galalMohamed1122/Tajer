# Tajer

> **Status: design phase (week 1).** No code yet. This README grows with the project.

Tajer is a multi-vendor marketplace where vendors also sell in their physical branches through a POS.
Online and in-store sales share **one inventory**, so the last item can never be sold twice.

## The problem in 5 lines

1. Vendors sell online and in their branches, but the stock is the same stock.
2. Two buyers (or a buyer and a cashier) can try to take the last item at the same moment.
3. Payment gateways send webhooks late, twice, or out of order.
4. A customer can reserve stock and never pay, so reserved stock has to come back on time.
5. One order can contain items from several vendors, and each vendor must see only their part.

## Planned modules (modular monolith)

| Module | Responsibility |
|---|---|
| Catalog | Products, variants (color, size), categories, search |
| Inventory | Stock per variant per warehouse or branch, reservations, commit and release. **No oversell.** |
| Ordering | Cart, order as a state machine, split into one sub-order per vendor |
| Payments | A fake gateway (`FakePay`), signed webhooks, Inbox, Idempotency-Key |
| Identity | Customers, vendors, cashiers, admins. A vendor can't see another vendor's orders |

Later: Settlement, POS offline sync, Notifications.

## Roadmap

- [ ] Glossary: [`docs/glossary.md`](docs/glossary.md)
- [ ] ERD: [`docs/erd/`](docs/erd/)
- [ ] ADR-001: why a modular monolith
- [ ] Solution skeleton on .NET 10
- [ ] Inventory domain + concurrency test: 500 buyers, 100 items, exactly 100 orders
- [ ] Payments webhook + idempotency test
- [ ] CI on GitHub Actions

## Tech (planned)

.NET 10, ASP.NET Core, EF Core, SQL Server, xUnit, Testcontainers, Docker Compose, GitHub Actions.

## License

MIT
