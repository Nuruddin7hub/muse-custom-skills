# Save Files Safely

## Test the write before you touch the real file

- Test writes with a small throwaway file before you save the real one, and write it with explicit flush and fsync followed by a read back of the file.

- Treat a failed test write as a blocked write environment, and stop all file writes for that run until a fresh test passes.

- Treat a bare write call that reports success as unproven, because buffered data can sit in memory while the real flush fails at shutdown.

- Do the work that needs no file write while writes are blocked, such as auditing scores against files already on disk or drafting a resume brief, and show that work instead of waiting silently.

## Never retry a failed save in place

- Leave the target file untouched after a failed save, and never retry the same save against the same file in the same run.

- Hold the new data where it already lives, such as a dashboard, an artifact, or the source messages, and name that place when you report the failed save.

- Write to a new temporary file in the same folder when writes work again, flush and fsync it, read it back, and only then rename it over the target.

- Check the target file size and record count after any save, and treat a zero byte file or a shrunken file as data loss, not as an empty file to append to.

## Rebuild from the source of truth

- Rebuild a damaged or emptied file from its source of truth before you append anything to it, and use the dashboard, the original alerts, or the ledger that already holds every record.

- Compare the rebuilt record count with the source count, and read back a sample of records before you call the rebuild verified.

- Report the failed save plainly with the file name, the place holding the new data, and the rebuild count, and give no new completion estimate until the next save verifies.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Keep a second copy of a tracked file in a dashboard or artifact, so a rebuild has a source of truth when the file itself is damaged.

- Shorten the gap between saves and verifications when a file has already failed once, so the next failure is caught before more data piles up.
