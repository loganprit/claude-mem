# Token economics

Use the claude-mem SQLite database at `~/.claude-mem/claude-mem.db`. Inspect the
current schema before querying it; do not assume older columns still exist.

Useful measured values include:

- total and average `discovery_tokens` for the project;
- observation and distinct-session counts;
- the date range and monthly observation counts;
- the observations with the highest recorded discovery-token values;
- estimated read size derived from the stored text fields, clearly labeled as an
  estimate.

Start with queries shaped like these after confirming the schema:

```sql
SELECT COUNT(*), COUNT(DISTINCT memory_session_id),
       SUM(discovery_tokens), AVG(discovery_tokens)
FROM observations
WHERE project = 'PROJECT';

SELECT id, title, discovery_tokens
FROM observations
WHERE project = 'PROJECT'
ORDER BY discovery_tokens DESC
LIMIT 5;

SELECT strftime('%Y-%m', created_at) AS month,
       COUNT(*) AS observations,
       SUM(discovery_tokens) AS discovery_tokens
FROM observations
WHERE project = 'PROJECT'
GROUP BY month
ORDER BY month;
```

Present recorded database values separately from derived values. Do not label
memory “savings” or ROI as measured unless the database records the relevant
counterfactual cost. If a modeled estimate is useful, state its formula and each
assumption, explain that it is not observed savings, and avoid fixed relevance or
per-query savings factors unless the user supplied or approved them.
