# Every Control Names Its Reader

My task list said a safety control was done. It did not exist on the machine.

In August I audited the AI agent setup I run at home, checking every file meant to change how the system behaves later for what actually read it. Two controls were documented, believed live, and doing nothing.

One was a guard meant to stop destructive commands. The task was ticked done, but the guard had been built on my old Windows machine and never came across when I moved to a Mac. The other was a preferences file the system said it learned from over time. It had never held a single preference, and nothing read it.

Both were on paper. Neither was doing anything, and nothing said so.

Three things I learned:

1. A ticked box records that a task was closed. Ask to see the control fire.

2. Every control names its reader. If nobody can say what consumes the log, the alert or the rule, it is decoration.

3. Re-check after any move. A migration, a reorg or a new tool is when a live control quietly stops being one.

Pick one control in your program this week and ask two things: who reads it, and when did it last fire?

---

*Posted on LinkedIn, November 22, 2026.*

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](../LICENSE).*
