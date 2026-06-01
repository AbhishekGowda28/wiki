---
publish: true
created: 2026-05-29T08:48:21.821+05:30
modified: 2026-06-01T00:12:34.291+05:30
---

> [!evergreen]  `= choice(length(this.file.outlinks)= 0, "🌰", choice(length(this.file.outlinks)= 1, "🌱", choice(length(this.file.outlinks) < 5 , "🌿", "🌲")))`

# Different Notes

1. Seed - No connection / linked notes
2. Seedling - Only 1 linked note
3. Planted  - More than 1 and less than 5 linked notes
4. Tree / Evergreen note - More than 5 linked notes

> [!button]- Last month `= this.file.cday.month - 1`
