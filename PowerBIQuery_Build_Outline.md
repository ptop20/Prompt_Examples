# Jira to Power BI Prompt

### First cut in Claude
Use this prompt to get Power Query (M) code and setup steps for pulling Jira data into a Power BI Desktop report.

Notes:
- Power BI uses reports (.pbix files), not workbooks. The LLM produces M code and steps that you paste into Power BI Desktop. It cannot build the .pbix file itself.
- As far as I know, Power BI Desktop has no built-in Jira connector, so the usual route is the Jira REST API through `Web.Contents`. Verify this for your environment, since your organization may have an approved connector or a restricted setup.

```text
Role: Power BI and Power Query (M) expert with experience in the Jira REST API

Goal:
Help me build a Power BI Desktop report that pulls Jira data using Power Query. Produce working M code and step-by-step setup instructions I can paste into Power BI Desktop.

Before starting, ask me for anything missing from this list. Do not assume values:
- Jira type: Jira Cloud or Jira Data Center/Server
- Jira base URL
- Authentication method I am allowed to use (API token, OAuth, PAT, other)
- Scope: project keys, JQL filter, or board
- Fields needed (e.g., key, summary, status, assignee, created, resolved, sprint, story points, custom fields)
- Reporting purpose (e.g., cycle time, sprint burndown, backlog health)

Guardrails:
- Do not invent endpoints, field IDs, connector names, or function names. If you are unsure, say so and tell me how to verify.
- Use placeholders for credentials and URLs. Never ask me to paste secrets into the chat.
- Flag anything that may conflict with security or compliance rules (for example, storing tokens in the query).
- Review the M code for syntax errors and logic errors before presenting it.

Instructions:
1. Recommend a connection approach (REST API through Web.Contents, or a connector if one applies) and explain the tradeoffs briefly.
2. Write the M code with these parts: parameters (base URL, JQL, page size), authentication handling, pagination (Jira returns results in pages), conversion of JSON to a table, column expansion, and data type setting.
3. Handle custom fields and nested fields (assignee, status, sprint) and explain how to find the correct field IDs.
4. Add error handling for empty results and failed requests.
5. Give Power BI Desktop steps: where to paste the code, how to set credentials and privacy levels, and how to schedule refresh in the Power BI service (including whether a gateway is needed).
6. List suggested measures or visuals that fit my reporting purpose.

Output:
- Short summary of the approach
- M code in code blocks, with comments
- Numbered setup steps
- A list of assumptions and open questions
- A list of things I should test after loading
```
