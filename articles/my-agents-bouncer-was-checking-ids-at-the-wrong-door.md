# My Agent's Bouncer Was Checking IDs at the Wrong Door

*(Half of my AI agents' guardrails were blind, and nothing told me.)*

I keep seeing a claim that a skill makes an agent likely to follow a policy, and a hook makes violations close to impossible. The first half is right. A skill is advice. A hook is code that runs every time.

The second half is only true for the actions the hook is watching. I run a set of Claude Code agents for my own work, guarded by hooks, so I listed what each hook actually matches. Half of them could not see any action the agent took through its connectors to outside tools. That included my file-write guards. The policy was right. The coverage had a hole in it, and nothing alerted me to it.

I closed the worst of it with a different layer: the connectors that can run code now need my approval before every call. The rest don't. Gate everything and I'd be approving all day, and I'd stop reading the prompts.

Some things I learned to ask of any guardrail:

- **What can it see?** Get the list of actions every guardrail matches, then compare it with the list of tools the agent has. The gaps are in the difference.
- **What turns it off?** Some of my agent's rules only load when a matching file is opened. In a long session the context gets compacted and those rules drop out. The agent now gets told which rules to re-read. That is advice again, not enforcement, so I still check.
- **How often does it fire?** On long approval prompts, my own honest answer was "I just hit OK." A check that fires constantly stops being reviewed.

Before you sign off on an agent rollout, ask the team for one table: each guardrail, what it can see, and what it cannot.

---

*Posted on LinkedIn, October 2, 2026. The table it asks for is section 4 of the [Agentic AI Program](https://github.com/ChefPlex/ai-automations/tree/main/ai-programs/agentic-ai-program) template. Related code: [agent-guardrails](https://github.com/ChefPlex/agent-guardrails).*

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](../LICENSE).*
