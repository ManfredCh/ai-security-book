# Part II: Language Models and Agents

## Guide to this part

Large language models turn natural-language goals into text, structured fields or candidate steps. The model itself processes tokens and representations. The application assigns roles to different sources: system prompt, user request, web page data, retrieved snippet, tool return. A role says how the application wants information to be interpreted. It is not an insurmountable hardware permission. This part therefore cares first about where low-trust data is treated as a high-trust instruction. It then cares about how that data acquires memory, identity and tool capabilities.

Chapter 4 separates jailbreaking from prompt injection. Jailbreaking asks mainly whether model behavior or the content policy has been bypassed. Prompt injection asks mainly whether external data changes the task or the control flow the application intended. Chapter 5 adds retrieval and long-term memory, so a single input can move out of the current context and into future state. Chapter 6 adds the agent harness, the Model Context Protocol, identity and tools, which connect parseable candidate calls to external side effects. Chapter 7 folds the failure paths of those three chapters into four levels of control: model, information flow, capability and runtime.

One minimal loop describes a language model application. The system collects the task and the current observations. The model proposes text or a tool plan. The harness parses the fields. The capability gate verifies the principal, purpose, object, parameters and consequences. The tool executes in a restricted environment. The result then re-enters the next round as low-trust data with provenance. The Model Context Protocol (MCP) can standardize how prompts, resources and tools are exchanged. It will not confirm on behalf of the business system whether the recipient, the amount, the code repository or a real device matches the user's goal at that moment.

A research assistant offers a benign example. It reads a public web page, calls a read-only retrieval tool, and attaches the source and the access time to its answer. A boundary example looks different. Imperative text appears on a web page, the assistant writes it into long-term memory, and then requests to send an internal file to an external address. The first half is a problem of data interpretation and state writing. The second half is a problem of identity and capability. A single text filter can hardly bear the whole responsibility by itself. Multiple checkers that share the same model, the same context and the same prompt template do not automatically form an independent defense in depth just because their number increases.

After reading this part, readers should be able to record "what the model said" separately from "what the system did". They should also be able to judge whether a failure stops at the content, plan, authorization or execution level. Part III retains this interface language but replaces internal state with conditional encoding, noisy trajectories, latent representations, video time and the release chain. Text is no longer the only carrier. Provenance, consumers and capability boundaries remain the main thread of the analysis.

A recovery thread also runs through the four chapters. Input filtering can only reduce known payloads. The state-write gate determines whether an anomaly survives across sessions. The capability gate limits what side effects an anomaly can obtain. Unified tracing and revocation mechanisms determine whether a team can stop the spread and rebuild a trusted state after discovering a problem. Placing these four kinds of control on different trust roots comes closer to an acceptance-ready defense in depth than repeatedly asking the same model whether it is "safe".

\newpage

---

[← Back to contents](index.md)
