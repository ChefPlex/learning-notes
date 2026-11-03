# Smart TV Apps as Proxy Nodes: A Supply Chain Problem

Good article on how LG will suspend webOS apps that bundle residential proxy SDKs, code that quietly turns a smart TV into an exit node for someone else's traffic. This is sorely needed at this time: [LG to Ban Residential Proxies from Smart TV Apps](https://krebsonsecurity.com/2026/07/lg-to-ban-residential-proxies-from-smart-tv-apps/) (KrebsOnSecurity).

Security firm Spur found more than 42 percent of apps available for download on LG smart TVs include SDKs that turn one's television into a proxy node indefinitely, with a similar pattern on Samsung. Not obscure apps, either, Pac-Man clones, screensavers, and file utilities shipped with proxy code from providers like Bright Data.

Three takeaways:

**Consent buried in an app isn't transparency.** A one-time consent prompt buried in a TV app is not a substitute for meaningful transparency, ongoing control, and platform oversight.

**The person clicking "accept" often isn't the risk owner.** The risk is amplified when consent comes from individuals within the household who use the device but shouldn't give consent, such as minors.

**This is a supply chain problem before it's a privacy problem.** "Free app" almost always means something else is monetizing the device. Nobody audits SDK behavior at the app store level until someone external does it for them.

Platform enforcement is the only lever that scales, users can't audit this, and review missed a 42 percent prevalence rate until outside researchers flagged it.

---

*Posted on LinkedIn, July 22, 2026.*

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](../LICENSE).*
