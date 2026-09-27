ge. The next part will assemble these controls together with language, image, and video systems into a cross-domain security architecture.

\newpage

# Part Six: Engineering Closed Loop

## Guide to This Part

The first five parts deal with language, media, action, and world prediction. Production systems, however, usually contain several of these chains at the same time. A research assistant reads web pages, calls language models, generates charts, saves memory, and sends email. A robot platform may use a vision–language model, a world model, tool services, and runtime assurance all at once. Suppose each team keeps only its own control checklist. Then provenance labels, identity, state, and recovery responsibility will be lost at cross-domain handoffs.

Chapter 19 therefore distinguishes the data plane from the control plane. The data plane handles prompts, images, video, state, and actions. The control plane provides provenance, identity, purpose, state lifecycle, capability, budget, traces, revocation, and recovery decisions, and it receives actual execution receipts. Shared services do not mean that all models share the same security assumptions. Language models still need instruction and tool controls. Vision systems still need condition and authenticity signals. Embodied and world models still need action gates, state anchors, and control deadlines.

Chapter 20 turns the architecture into a regime that runs every day. The system first freezes version snapshots of models, data, tools, policies, environments, and consumers, and then generates a test matrix from the threat record. Non-compensable failures enter hard gates. Diagnostic scores serve troubleshooting and ranking, and restricted canary connections are continuously monitored. After an incident occurs, the team first limits reachable capability and preserves evidence. It then determines the impact boundary, the trusted rebuild point, and the recovery conditions. A new version or a new environment makes the relevant evidence expire, so the operational closed loop must recompute dependencies and the scope of retesting.

The normal case is a tool field update that affects only parameter parsing, the authorization policy, and event logging. The dependency graph lets the team rerun these local tests, and end-to-end paths confirm that the combination still correctly refuses or executes. The boundary case is a team that updates only the release sign-off document while reusing the previous version's model scores and security receipts. The files are complete, yet they do not prove anything about the current system. Evidence validity comes from binding versions to the object actually running, not from the number of documents.

Here this survey returns to the five original questions. They are what to protect, where trust changes, how capability is obtained, how far the evidence extends, and how to recover after failure. New model families, protocols, and product names will keep appearing, and these five questions can still put them back onto observable interfaces. Readers do not need to become implementation experts in every technical branch. They can still organize design reviews, testing, release, monitoring, and incident response by combining unified traces with specialized mechanisms.

The engineering closed loop does not eliminate the unknown; it maps the unknown into capability limits, follow-up evidence tasks, and expiry conditions. When action receipts are missing, high-impact paths are not opened. When provenance or rights are unverified, data use is restricted. When calibration fails, control switches to a conservative mode. When a recovery point is untrustworthy, isolation is extended. The regime thus formed all

---

[← Back to contents](index.md)
