# AI Agreeing With AI Is Not a Second Opinion

AI agreeing with AI is not a second opinion. Six AI agents agreed with each other. All six were wrong, in exactly the same way.

If you run AI programs, plan for this one. Check how they got there before you trust it.

I hit it on my own agent stack. Six agents, one model, nearly the same prompt, each reviewing a different slice of 41 open-source repositories. One question was simple: which projects are still maintained?

Every agent used GitHub's "last pushed" date. One repository showed a push on September 19. Its main branch had not changed since August 28.

One check by hand, reading the date of the latest commit, found it.

Six matching answers felt like proof. It was one answer, said six times.

Some questions I now ask any team reporting AI results:

1. How did each agent get its answer? Same model, same prompt and same sources means you have one sample run six times.

2. What did a different method show? A seventh copy of the same agent would most likely have agreed. A person reading the source did not.

3. Are you buying coverage or confirmation? More agents read more material, and that is worth paying for. It does not make their conclusions independent.

4. What did it not check? Ask every AI result to state its scope. An answer that does not say what it skipped will read as complete.

Go ask one of these at your next status review. Worst case, the agents were right. Best case, you find the blind spot before it ships.

---

*Posted on LinkedIn, November 13, 2026. Related code: [agent-guardrails](https://github.com/ChefPlex/agent-guardrails).*

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](../LICENSE).*
