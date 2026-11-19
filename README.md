# UFO Archive — Data Collection Case Study

A case study in converting the [U.S. Department of War UFO archive](https://www.war.gov/UFO/) into structured research data with **Oriol Web Crawler**.

**Status:** this public repository documents the workflow. It currently contains no downloadable JSON snapshot or source-document bundle. Technical walkthrough available on request via [LinkedIn](https://www.linkedin.com/in/osintech/).

## Task and approach

The project collects heterogeneous public archive material and organizes it into a machine-readable snapshot for querying, archival research, enrichment, and downstream processing.

**Pipeline:** public web archive → automated collection → extraction → normalization → structured JSON research data.

Oriol separates collection scenarios from individual sources and supports browser automation and HTTP-based collection. This case demonstrates the path from source acquisition to reusable data rather than only a collection of saved links.

## Research outputs

- Structured records derived from public archive pages.
- Source references retained for verification and follow-up.
- JSON-based output for subsequent queries and analysis.

Project overview and screenshots are preserved in the [OSINTech project history](https://github.com/bormaxi8080/bormaxi8080/blob/main/CHANGELOG.md#jun-2026--us-department-of-war-ufo-archive-snapshot).

![Archive collection example](https://raw.githubusercontent.com/bormaxi8080/bormaxi8080/main/img/uap_1.png)

## Example of a normalized record

The following is an **illustrative schema**, not a record exported from the dataset or a claim about the current export field names:

```json
{
  "source_url": "<original archive page URL>",
  "title": "<source document title>",
  "collected_at": "<UTC collection timestamp>",
  "document_urls": ["<linked public document URL>"],
  "text": "<extracted source text>"
}
```

For a JSON array using this illustrative schema, a simple query could list titles and source URLs:

```bash
jq -r '.[] | [.title, .source_url] | @tsv' snapshot.json
```

Adapt queries to the field names of the actual export. No snapshot date, completeness guarantee, or live synchronization is implied by this documentation; these must be established from a specific export and its collection log.

## Related work

[OSINTech profile and selected projects](https://github.com/bormaxi8080) · [OSINT tools and datasets](https://osintech.substack.com/)
