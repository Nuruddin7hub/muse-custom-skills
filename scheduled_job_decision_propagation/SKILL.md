# Propagate a Decision to Scheduled Jobs

## Treat a stop decision as a job change

- Treat words such as stop, retire, suspend, pause, never again, and a channel verdict as a change to scheduled work, not only as a change to the next chat reply.

- Act in the same turn as the decision, before you start the next task, so a job scheduled for the next morning cannot run the old routine overnight.

- Name the exact method or channel that ended, such as scored audits, Lazada prospecting, or a named outreach route, and use that name when you search job files.

## Inventory every job and document that carries the old routine

- List scheduled jobs with `cron.list` and read each job definition file that could touch the stopped method or channel.

- Search the related runbook, goal notes, and state files for the stopped wording, such as a score, an audit PDF, or a named channel, and list every file that still contains it.

- Keep a job that is unrelated to the decision, such as an evening digest or a validation gate, and name it as unchanged in your report.

## Update the definition, not only the switch

- Pause a job with `cron.update` when its work stops for now, and rewrite its definition when its work changes, so the old steps cannot return when the job is enabled again.

- Remove the retired steps from the definition, including scoring, building an audit file, attaching that file, and drafting in the retired style.

- Replace a retired step with the approved replacement only when the user approved one, and leave the step out when no replacement exists.

- Re-list the jobs with `cron.list` and re-read each changed definition file to confirm the pause or the new wording before you report success.

## Report what changed and what stays live

- Report each job by name with one of paused, updated, or unchanged, and give the reason for each choice in plain words.

- Name any job or file you could not open, and say what still needs a check before the next scheduled run.

- Tell the user the next run time of any job you left live, so a stale job cannot run unnoticed.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- When the user only pauses work for a day, set a short pause and name the date it resumes, instead of rewriting the whole job definition.

- When several jobs share one runbook, update the runbook first and then check each job against the new wording, so the jobs and the runbook cannot drift apart again.
