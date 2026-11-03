# What One More Change Costs

Every program gets a change request. It sounds small, so someone says yes before figuring out what it does to the schedule or the budget. Weeks later the date has moved, costs are up, and nobody can point to the decision that caused it.

Two common ones. Take a simple program: a system replacement, go-live on day 35, a team of six at $800 a day each. The old system's contract ends on day 50.

**A scope change:** one more data set to migrate. It adds 6 days to a task with 2 days of float. The float absorbs 2 and the task joins the critical path. Go-live moves 4 days, to day 39. The extra work costs $4,800, and keeping the team on 4 more days costs $19,200. That is $24,000, five times the quote. Nobody hid anything. The quote just counted the wrong thing.

**A schedule change:** two testers need 12 more days of testing, on a task with no float. Go-live moves 12 days, to day 47, still three days before the contract end. The testing costs $19,200. Keeping the team on for those 12 days costs $57,600. That is $76,800.

The two are not related, and they could just as easily hit two different programs. But if both land on the same one, go-live moves 16 days, to day 51, one day past the contract end. That one day buys a $40,000 contract extension that neither change would have caused on its own. Add them up: $24,000 plus $76,800 plus $40,000 is $140,800.

So bring options, not a yes or a no. Add two more testers and the testing takes 6 days instead of 12, so go-live lands on day 45, before the contract end. The testing change costs $48,000 instead of $76,800. Or defer one of the changes to the next release and pay only for a workaround until then. Either way, the decision goes to whoever owns the fixed date, with the numbers in front of them.

One habit makes this visible. Give the contract end date for each system being replaced its own milestone in the schedule, some weeks after go-live. That gap is a buffer kept on purpose for running old and new side by side. When a change eats into it, it shows on the schedule, not on an invoice.

An AI tool can run this arithmetic quickly. It cannot know about a date that lives only in someone's head. Put the fixed dates in the plan first, or the fast answer leaves out the largest cost.

What fixed date has caught your program by surprise?

---

*Posted on LinkedIn, November 3, 2026.*

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](../LICENSE).*
