# Designing it taught me a few things

<div class="mt-8 text-lg space-y-7">

- **Choosing what is *not* an event.** CI pending triggers nothing; CI red in `needs-testing` triggers nothing.
- **Exactly one way back into `draft`**: an explicit command, never a raw `git push`. A command is a signal — a push is noise.
- **Reviews, defined:** mine excluded, bots ignored unless whitelisted, latest review per reviewer wins, a non-approval beats every approval.
- **Not everything deserves an LLM:** two LLM-powered prompts became plain PHP (`pablo show:prs` reads the poller's cache). The intelligence is in five markdown files; the rest is plumbing.

</div>
