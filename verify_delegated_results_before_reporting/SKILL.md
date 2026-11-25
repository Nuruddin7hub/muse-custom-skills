# Verify Delegated Results Before Reporting

## Treat every delegated number as a claim

- Treat a pass total, a score, a count, or a completion claim in a delegated report as unproven until you have checked the files behind it.

- Find the exact file path behind each number when the report does not name one, and do not repeat the number until you have opened that file.

- Treat a chat message, a summary line, or a restart note as no evidence on its own, because only the artifact on disk shows what actually ran.

## Check the artifact on disk

- Open each named output file with `muse.read` and confirm it exists, it is not zero bytes, and its timestamp falls after the run it describes.

- Read the pass total, the score, or the count inside the file and compare it with the number in the report, and treat any mismatch as unverified.

- Open the run log with `muse.read` and look for a crash, a TypeError, or an error line, and treat a run that crashed partway as unverified even when an earlier line claims a pass total.

- Check that every expected output exists, such as the measure file and the smoke and probe outputs, and treat a missing output as no evidence for that check rather than as a pass.

- Treat a zero byte file as no evidence, and never quote a number from a file you have not opened.

## Report only what you verified

- Report a number only after the file on disk shows it, and name the file you checked alongside the number.

- Say plainly that a claim is unverified when its file is missing, empty, or mismatched, and name the file that is missing or wrong.

- Correct an unverified claim openly in the same turn when you find you already repeated it, and state what the disk actually shows instead of the claimed number.

- Never fill a gap by reusing a number from an earlier run, and never describe a rerun as proof that the earlier run passed.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Ask the delegated agent to write its numbers into the output file itself, so the file and the report cannot drift apart.

- Check the smallest artifact first when time is short, because one empty measure file already settles the claim as unverified.
