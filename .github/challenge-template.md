<!--
MAINTAINERS ONLY. This is not an issue-template-chooser entry: nobody can open an issue in
this repo (.github/ISSUE_TEMPLATE/config.yml disables them), so copy this file, fill it in and
publish the challenge with the API, which is not affected by that setting:

  gh issue create --repo diagrid-labs/advent-of-workflow \
    --title "Challenge NN: <pattern name>" \
    --label challenge --label day-NN \
    --body-file NN/challenge-NN.md

Title: "Challenge NN: <pattern name>". Labels: challenge, day-NN.

Fixed shape. Every challenge uses these seven sections in this order.
The reviewer is an agent, so "What the reviewer checks" must be specific enough to judge against.
Neither dapr-skills nor Diagrid may appear in the pass criteria.

KEEP THE MARKDOWN PLAIN. Each challenge body is sent to registrants as an email in full, so
anything GitHub renders specially is lost or broken in an inbox:
  - no collapsible sections (<details>), no GitHub alert syntax (> [!NOTE]), no task lists
  - no relative links; every URL is absolute, including links to this repo
  - no reliance on issue autolinks (#12, @handle) or emoji shortcodes
  - do not hard-wrap. Keep each paragraph and each list item on ONE line, however long, and let
    the reader's client wrap it. GitHub collapses wrapped lines into a paragraph, but plain-text
    email clients keep the breaks and the challenge arrives ragged.
Tables, fenced code blocks, bold and plain links are fine.
One exception: a Mermaid diagram of the workflow, at the end of "What to build". GitHub renders it
in the issue, but an email client shows the raw diagram code, so wrap it in two HTML comments,
one reading "diagram:start" and one reading "diagram:end", and delete everything from the first to
the second when building the email body. The private repo's README has the command.

The draft challenge files live in a private repo, one folder per challenge, until their drop date,
NOT in this public repo. Publishing them here early spoils the schedule.
-->

**Drops:** <date, December 2026> | **Submissions close:** 3 January 2027, 23:59 CET

## The scene

<!--
The themed opening. One or two paragraphs, 60 to 120 words. Name the subsystem, say what is
broken, and place it against the launch deadline.
No task detail lives here. A participant must be able to skip this section entirely and still
build the right thing from the sections below.
-->

## What to build

<!--
The workflow to build, in plain terms. Name the pattern. Say what the inputs and activities are. Any language Dapr Workflow supports.
SAY WHAT THE ACTIVITIES TALK TO. Through challenge 10 they are plain functions working from the
challenge's own lookup tables: no database, no HTTP call, no other service. Say so outright, so
nobody builds infrastructure the challenge never asked for. Challenges 11 and 12 add a second app,
which is exactly why the earlier ones must be explicit that they do not.
End with a Mermaid diagram of the workflow, between the diagram markers (see the top of this file).
Keep it generic ("toy 1 ... toy N") so it never gives away a number the participant must work out.
-->

## Input, rules and expected outcome

<!--
Four parts, in this order.

1. The fixed input, as a fenced json code block. Every participant runs the same input.
2. The rule for every activity: a lookup table or a formula. Activities are deterministic, never
   call real services and never produce random values. Where a challenge is flaky on purpose, the
   flakiness is a rule driven by attempt count, so a retried run still ends with the same numbers.
3. The expected outcome, in words. Do NOT publish the workflow's output as JSON: participants
   should build the pattern, not reverse-engineer an output shape.
4. The named numbers to report, one or two, chosen so the value only comes out right if the
   mechanism actually ran.

Print the expected values for challenges 1 and 2 only. From challenge 3 onwards the participant
works them out from the input and the rules; the values live in the reviewer answer key and in
REVIEWING.md, never in this public repo before the challenge closes.

Array order follows input order wherever the outcome lists things. Timer lengths, intervals and
holds are the participant's to pick, and never change the numbers.
-->

## What done looks like

<!-- Observable outcome: what the app does when it runs and what the finished run looks like. -->

## Which view proves it

<!--
The BASELINE for every challenge is the EVENT HISTORY in the Dapr Dev Dashboard running on the
participant's own machine (http://localhost:9090), NOT anything in the Diagrid console. It carries
the activity names, the order they ran in, parallel fan-out, child workflow instances and
continue-as-new restarts, which is where most of these challenges' mechanisms actually show.
ALWAYS give the path: open the Workflows page, click the instance ID, scroll down to the Event
History table. The dashboard does not land on it.
ALWAYS accept a partial screenshot when the history is too long to fit on one screen. Several of
the later challenges produce long histories, so never demand the whole thing in one image.
ALWAYS state that the workflow and activity names in the history must match the names in the
participant's repository, so the screenshot is tied to the linked source.

WATCH OUT: the event history does NOT show the workflow's output. The challenge's named numbers
reach the reviewer through the output the participant pastes into the submission form, so every
challenge must ask for that paste and say it is not optional. A participant can edit their own
issue body, so treat the pasted numbers as a convenience for review and let the source and the
screenshot carry the pass.
If a challenge needs the Output panel or the workflow metadata in evidence, ask for that as a
SECOND screenshot of the top of the page; do not swap it for the event history.
Add only what is specific to THIS challenge on top of the baseline.

STATE WHICH KIND OF EVIDENCE THIS CHALLENGE USES, so nobody spends an evening hunting a view that
will never show what they are looking for:
  - Dashboard-provable: the screenshot shows the mechanism. The dashboard DOES render child
    workflow instances, continue-as-new restarts and parallel activities.
  - Code-inspected: the reviewer reads the linked source. The dashboard does NOT render individual
    activity retry attempts, and configuration such as a concurrency limit lives in a file.
Any challenge whose criteria include a retry policy must say which parts are checked in the source.
-->

## What the reviewer checks

<!--
Explicit, numbered pass criteria. Two questions: does the demo actually run, and is the pattern
genuinely applied rather than approximated.
The FIRST check is always that the reported numbers match the answer key.
The LAST check is always that the screenshot is a run of the linked repository, by the workflow
and activity name match described above.
Keep the list short, three to five. Do not add a criterion that the screenshot requirement already
covers, such as "the activities ran in sequence rather than in parallel" when the full-page
screenshot shows the order anyway. Every criterion should be something the reviewer has to judge.
-->

1. 
2. 
3. 

## Optional Diagrid bonus

<!--
Keep this section SHORT. Open with "Entirely optional." and the line that the count of confirmed
Diagrid runs is what the two LEGO® Game Boy™ sets are decided on. Do not spell out that it changes
nothing about passing, earns no extra pass or is not needed for the Holopin: the word "optional"
carries that, the rules are on the landing page, and repeating it twelve times reads as nerves.
The Diagrid run is ALWAYS IN ADDITION to the Dapr OSS run, never a replacement: the required
screenshot comes from the participant's own Dev Dashboard, so a Diagrid-only submission has
nothing to put in the required box. Include a screenshot of the workflow GRAPH showing the activities.
ALWAYS give the path to it, because it is not the page participants land on: in the Diagrid console
the graph is under Monitoring > Workflows, then select the instance ID. Use the word "graph", not
"diagram", and keep it matching the wording in the leaderboard repo's submission form.
Say that a free Diagrid account is enough. Do not add that the Dev Dashboard needs no account; the README already covers it.
Close by pointing at the local installation guide (https://docs.diagrid.io/getting-started/local-installation/)
for both ways to get set up: the Diagrid AI plugin, which installs the Diagrid skills and MCP server into
Claude Code, Codex or GitHub Copilot CLI, and the diagrid CLI.
Add any challenge-specific note here.
-->

---

Submit by opening a [submission issue](https://github.com/diagrid-labs/advent-of-workflow-leaderboard/issues/new/choose) in the leaderboard repo, not here. One issue per challenge, with a link to your work and the screenshot attached. Setup: see the [README](https://github.com/diagrid-labs/advent-of-workflow/blob/main/README.md).
