# Glossary (ubiquitous language)

One meaning per word, used the same way in code, tests, docs and talks.
If a word means two things in two modules, write it twice with the module name.

| Term | Module | Meaning (one line) | Example | Not the same as |
|---|---|---|---|---|
| Product | Catalog | What the vendor sells, as the customer sees it. Has a name, description and category. It is not sold directly; its variants are. | "Cotton T-shirt" | Variant |
| Variant | Catalog | One concrete option of a product (color + size). This is what goes into a cart and what has stock. | "Cotton T-shirt, Black, L" | Product |
| SKU | Catalog | The unique code of one variant, chosen by the vendor. | `TSH-BLK-L` | Product Id |
| Warehouse | Inventory | | | |
| Branch | Inventory | | | |
| StockItem | Inventory | | | |
| Reservation | Inventory | | | |
| Cart | Ordering | | | |
| Order | Ordering | | | |
| SubOrder | Ordering | | | |
| Payment | Payments | | | |
| Webhook | Payments | | | |
| Settlement | Settlement | | | |
