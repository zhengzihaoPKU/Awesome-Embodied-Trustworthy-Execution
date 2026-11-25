# 🤝 Contributing

Thanks for helping improve **Awesome Embodied Trustworthy Execution**.

## Add or update a resource

Open an Issue or PR with:

1. **Title, year, venue, and official links** — paper, code, and project page where available.
2. **Classification** — layer, subsection, and technical direction, supported by the survey discussion.
3. **Brief notes** — Problem, Core idea, and Why it matters for the detailed CSV.
4. **Tags** — three short English keywords, such as `VLA | Quantization | Pruning`.

## Classification

Follow the companion survey's four system layers:

- Model Software
- Runtime Systems
- Computing Hardware
- Physical Execution and Feedback

Use the relevant discussion in the survey, together with Fig. 3, and retain the existing technical directions. A study may appear in several categories but counts as one resource. Keep benchmarks and datasets separate from performance or timing studies.

## Entry format and style

```markdown
- **Official Acronym**: Full Paper Title. (Year, Venue) [Paper] [Code] [Project]
```

Use the full title when no official acronym exists. Reuse the current resource badges and sort by year descending, then title alphabetically. Keep descriptions concise, technical, and neutral; detailed notes belong in the CSV. Only include verified official links, and do not label a project-page or placeholder repository as Code.

## Keep files consistent

Update both READMEs and the relevant records in `data/papers_detailed.csv` and `data/paper_links_full.csv`. Preserve the CSV columns, existing IDs, anchors, and cross-category mappings. Each resource has one row in each CSV, even when displayed more than once.

Per-paper images are not required. Use authorized figures only; do not add unpublished manuscript PDFs or internal Overleaf sources.

<details>
<summary>Legacy ID reference</summary>

P01 → P005; P17 → P015; P20 → P019; P27 → P046; P38 → P057; S05 → P064; P37 → P065; P42 → P074; P08 → P092.

P09 → P094; P05 → P095; S01 → P102; P07 → P106; P06 → P108; P25 → P119; P26 → P122; P04 → P125; P44 → P134.

</details>
