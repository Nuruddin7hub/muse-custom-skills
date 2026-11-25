# Supervise a Long Running Loop

## Define the heartbeat before the loop starts

- Write the stall definition into the run brief before the first round, with the check interval, the stall threshold, and the exact output that counts as progress.

- Treat a new ledger entry plus new output files as progress, and treat a chat message or a restart note alone as no progress.

- Keep exactly one pending section in the run log, always the current state, and read the last heading when you check it, so a stale section cannot trigger a resume.

- Keep run state and logs in durable workspace files, never in temporary files, because a machine reset wipes temporary files and kills background work.

- Name the quiet phases in the brief, such as learning or watching, because a loop in such a phase may write no files for 30 minutes or more and file silence alone is not a stall.

## Check the loop yourself on a fixed cadence

- Check the loop yourself at the interval in the brief, and never treat a watchdog job or a monitoring promise as a substitute for that check.

- Read the ledger, the last round entry, and the newest output files at each check, and compare them with the previous check before you decide the loop is moving.

- Treat silence past the stall threshold as a stall, even when no error was reported, and act on it in the same check.

- Restart a stalled loop within one hour of detection, and resume it from the saved state on disk.

## Decide direction changes instead of parking them

- Never write a coordinator brief that parks a direction changing fix as awaiting the user or as the user call, because a parked fix stops the loop while the user may be asleep.

- Decide each direction changing fix yourself when the brief and the critics support it, log the decision under Decisions in the run ledger, and keep working.

- Treat only the ship gate as a real wait, and never start the final render or any other long and costly export before the user approves the stills, while you keep refining and test the render pipeline on a few short frames.

- Check every coordinator brief before you send it for a flag, a question, or a deferred decision that the base skill does not state, and remove it before the coordinator starts.

- Re-read the base skill intake rule before you add any new gate, and add a gate only when the base skill or the user states it in those words.

## Resume without rebuilding or overwriting

- Read the brief, the shot list, and the last two ledger entries before you resume, then start the next round and never rebuild output that already works.

- Check whether the current output already exists complete before you resume, by probing its duration and structure and confirming its size grew as expected, and never judge a long job by its process handle alone.

- Log a skip and exit without resuming when the output is already complete, because a resume after completion can overwrite finished work with a partial file.

- Drop any line that forbids a rerun before you match a resume instruction, so a prohibition cannot be misread as a pending step.

- Kill a duplicate worker by its exact process id, kill its child writer too, and verify exactly one writer remains before you start a replacement.

## Report a stall with exact accounting

- Report the stall with the exact accounting, namely where the hours went, the last completed round, the latest logged scores, and the next round you started.

- Give no new completion estimate in a stall report, because an estimate does not repair a stall.

- Claim a repair only after the next round has produced a new ledger entry and new output files, because a restart message alone is not a repair.

- Send progress and keep working in the same turn, and never end your turn to wait for a reply, because showing work must never read as pausing it.

## Available connectors

- Use muse.connector_search to find other connectors and muse.skill_search to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with Custom Connectors and MCPs, or build a custom connector.

## Alternatives for better results

- Shorten the check interval when a loop has already stalled once, instead of keeping the interval that missed the first stall.

- Split a loop that keeps stalling at the same step into smaller rounds with a ledger entry per round, so a stall is visible at the next check instead of hours later.
