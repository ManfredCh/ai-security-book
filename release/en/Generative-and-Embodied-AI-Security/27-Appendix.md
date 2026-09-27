 What this survey ultimately hands the reader is a way of working that continuously turns complex capabilities into verifiable boundaries.

\newpage

# Appendix

## Appendix A Minimal Safety Argument Template

| Item | Required Question | Evidence Location |
|---|---|---|
| System purpose | Who does it serve? What task does it complete, and in what environment? | Requirements and architecture |
| Capability boundary | What can it read, write or execute? What can it contact, pay, release or control? | Tool and permission inventory |
| Assets | Which data, identities, states, devices and physical objects need protection? | Asset ledger |
| Trust interfaces | Where do U0—U6 sit, and who can cross each one? | Data flow and trust graph |
| Threats | What are the attacker's knowledge, access, budget and persistence? What is the highest consequence layer? | Threat record |
| Controls | Who provides earliest blocking, and who provides consequence limitation? | Control matrix |
| Verification | What is the denominator? What are the success conditions, benign utility, cost and reproduction level? | Test receipts |
| Operations | What gets monitored? Who escalates, and how is revocation carried out? | On-call and alerts |
| Recovery | How do we freeze, roll back, clean up, rebuild and reopen? | Exercise receipts |
| Residual risk | Who accepts it, and by what deadline? What change triggers re-evaluation? | Risk sign-off |

## Appendix B Threat Record Template

For every threat, record the following:

1. Protected asset \(a\).
2. Trust domains before and after the attack \(d\).
3. Entry points and carriers \(e\).
4. Attacker knowledge and access \(k\).
5. Budgets for queries, time, writes, physical access and feedback \(b\).
6. How long the impact persists \(p\).
7. The first-broken interface \(f\).
8. The highest observed consequence layer \(y\).
9. Evidence level, unknowns and stopping rules \(q\).
10. Earliest blocking controls, consequence-limiting controls and common-cause analysis.

## Appendix C Four-Part Test Record

| Field | Completion Requirement |
|---|---|
| System snapshot | Record the versions of model, prompt, parsing, retrieval, state, tools, policy, image, identity and environment |
| Statistical unit | Name the unit: prompt, response, image, video, task, trajectory, application or incident |
| Sample source | Say whether the sample is real, synthetic, regression, red-team or a production incident, and whether it is independent |
| Attack budget | Give the knowledge, query, time, write, physical access and feedback budget |
| Attack effect | Give the success conditions, the grader, the highest Y layer and the interval |
| Residual risk | Give penetration after defense, the blast radius, reversibility and the unknowns |
| Benign utility | Report legitimate task success, false refusals, quality and stability |
| Operating cost | Report latency, tokens, GPU, tool steps, fees and human escalation |
| Reproduction level | State the reproduction level: static inspection, mechanism-level runs, end-to-end or production evidence |
| Receipts | Collect the commands, exit codes, logs, outputs, hash values and reviewer |

\newpage

## Appendix D Chinese-English terminology and neighboring concepts

The table separates normative or authoritative sources from original papers with field-standard translations, and from the operational terms of this book. An empty English abbreviation means this book enables no abbreviation. Allowed aliases serve retrieval or necessary context only. The main text still gives priority to the standard Chinese. Each term's standard status and source links are stored in `terminology/standard_terms.csv` and `terminology/source_register.md`.

### Foundation models, language models, and agents

| Standard Chinese | English full name and abbreviation | Status | Definition and difference from neighboring concepts |
|---|---|---|---|
| Artificial intelligence | artificial intelligence; AI | Normative reference | Use it when the related technologies and systems are meant in general. For a specific model category, prefer the specific name. |
| Generative artificial intelligence | generative artificial intelligence; GenAI | Normative reference | Models and related technologies that can generate content such as text, images, audio and video. System capabilities are defined separately. Allowed retrieval aliases: generative AI, generative artificial intelligence technology. |
| Machine learning | machine learning; ML | Normative reference | Use it when training data and rules jointly determine model behavior |
| Deep learning | deep learning; DL | Field-standard | Use it only where multilayer neural network methods need to be distinguished |
| Neural network | neural network; NN | Field-standard | A family of parameterized functions. Do not abbreviate an entire application system as a neural network. |
| Large language model | large language model; LLM | Field-standard | Give the full Chinese and English names at first mention. LLM may be used later. Not used in the main text: language large model. |
| Token | token | Field-standard | Use the Chinese term ciyuan for units of a model sequence. Only authentication objects use the Chinese term lingpai, and the choice must be checked manually against the context. Allowed retrieval alias: token. |
| Tokenization | tokenization | Field-standard | The term stresses the transformation from raw text to a token sequence. Chinese word segmentation is only one possible step. Allowed retrieval alias: word segmentation. |
| Transformer architecture | Transformer architecture | Field-standard | Transformer is kept in English as a proper name. Do not reduce all LLM mechanisms to attention. Allowed retrieval alias: Transformer model. |
| Attention mechanism | attention mechanism | Field-standard | Defined as a mechanism that computes dependency weights from the current representation |
| Context window | context window | Field-standard | A context window is the range of tokens directly available to one inference pass. It is not equivalent to long-term memory. Allowed retrieval alias: context length. |
| Prompt | prompt | Field-standard | The name prompt covers natural-language or structured input as a class. Use prompt word only when discussing word-level fragments. Allowed retrieval alias: prompt word. |
| System prompt | system prompt | Field-standard | A high-priority source of instructions assembled by the application. It is not a hardware permission boundary. Not used in the main text: system prompt word. |
| Inference | inference | Field-standard | Computing outputs from existing parameters. Causal inference is always written in full. Allowed retrieval alias: model inference. |
| Training | training | Field-standard | The process of updating model parameters according to data and objectives |
| Fine-tuning | fine-tuning | Field-standard | Keeps updating all or part of the parameters after training. Allowed retrieval alias: fine adjustment. |
| Low-rank adaptation | low-rank adaptation; LoRA | Field-standard | LoRA refers to a specific parameter-efficient fine-tuning method. Adapter is a broader category. Allowed retrieval alias: low-rank adapter. |
| Embedding | embedding | Field-standard | The mapping of an object to a continuous vector representation. Similarity does not equal trustworthiness. Allowed retrieval alias: vector representation. Not used in the main text: word embedding vector store. |
| Retrieval-augmented generation | retrieval-augmented generation; RAG | Field-standard | The whole pipeline that retrieves external material and assembles it for a generative model. Allowed retrieval alias: retrieval augmentation. Not used in the main text: knowledge base augmentation. |
| Vector database | vector database | Field-standard | A system component that stores and retrieves vectors and metadata. It is not equivalent to RAG. Allowed retrieval alias: vector store. |
| Reranking | reranking | Field-standard | It scores and orders the preliminary candidates a second time. Provenance and permission information must be retained. Allowed retrieval alias: reordering. |
| Long-term memory | long-term memory | Operational term of this book | State that is retained across steps, sessions or tasks and influences future behavior. It is kept separate from memory in model parameters. Allowed retrieval alias: persistent memory. |
| Artificial intelligence agent | artificial intelligence agent; AI agent | Normative reference | The main text uses the full name at first mention and the short form agent thereafter. Network proxy and proxy metrics must always be written with their full qualifiers. Allowed retrieval alias: agent. Not used in the main text: AI proxy. |
| Agent harness | agent harness | Fixed translation of this book | The software layer that organizes the loop, tools, state, error handling and termination. It is not the model itself. Allowed retrieval alias: agent orchestration layer. Not used in the main text: agent framework. |
| Tool calling | tool calling | Field-standard | A structured tool proposal output by the model. An external system grants the authority to execute. Allowed retrieval alias: function calling. |
| Model Context Protocol | Model Context Protocol; MCP | Official specification | Write the full name at first mention. The protocol defines interaction objects, but it does not replace business authorization. |
| Access control list | access control list; ACL | Field-standard | Rules that allow or deny a subject acting on an object. An ACL is not content trustworthiness. Allowed retrieval alias: access control manifest. |
| Least privilege | least privilege | Field-standard | Narrow capabilities according to subject, task, object, action, parameters, term and environment. Allowed retrieval alias: minimum privilege. |
| Sandbox | sandbox | Field-standard | A restricted execution environment. Its process, network, secret and resource boundaries must be stated concretely. Allowed retrieval alias: isolated environment. |
| Capability token | capability token | Fixed translation of this book | A verifiable authorization object. It binds a subject, object, action, parameters, term and budget. Allowed retrieval alias: capability ticket. Not used in the main text: permission token. |
| Prompt injection | prompt injection | Field-standard | Untrusted data competes with the application's task or control flow. It is kept separate from jailbreaking. Not used in the main text: prompt word attack. |
| Jailbreaking | jailbreaking | Field-standard | Bypassing model behavior or content policy. "Bypass" is a general-purpose verb, and each use must be checked manually against the context. Allowed retrieval alias: jailbreak attack. |
| System prompt leakage | system prompt leakage | Field-standard | Unintended exposure of system prompt content. Whether this creates risk depends on whether the content contains secrets or security dependencies. Not used in the main text: system word leakage. |
| Excessive agency | excessive agency | Fixed translation of this book | Functional permissions or a degree of autonomy that exceeds what the task requires. A concrete report still writes the reachable capability. Not used in the main text: excessive proxy, excessive initiative. |
| Optical character recognition | optical character recognition; OCR | Field-standard | Converts text in an image into a textual representation. Give the full name at first mention. |
| Automatic speech recognition | automatic speech recognition | Abbreviation disabled in this book | ASR is fixed as attack success rate, so this book does not enable an abbreviation for automatic speech recognition. Allowed retrieval alias: speech recognition. |

### Attacks, evaluation, and system boundaries

| Standard Chinese | English full name and abbreviation | Status | Definition and difference from neighboring concepts |
|---|---|---|---|
| Data poisoning | data poisoning | Field-standard | An attacker manipulates the data used for training or adaptation to influence model behavior. Not used in the main text: data pollution. |
| Backdoor attack | backdoor attack | Field-standard | Produces the behavior the attacker targets, but only under specific trigger conditions. It stays separate from ordinary quality degradation. Allowed retrieval alias: model backdoor. |
| Adversarial example | adversarial example | Field-standard | An input built to induce a target behavior. Any report must state the attack budget and the attacker's assumed knowledge. Not used in the main text: adversarial instance. |
| Evasion attack | evasion attack | Field-standard | Alters the input at inference time to evade the model or to induce it. Not used in the main text: escape attack. |
| Threat model | threat model | Field-standard | Records at least the assets, the attacker's capabilities, entry points, budget, first-broken location and consequences |
| Attack budget | attack budget | Field-standard | Its constraints include knowledge, queries, time, writes, physical access and feedback |
| Attack success rate | attack success rate; ASR | Fixed translation of this book | It must be bound to the statistical unit, the denominator, the success layer and the attack budget. Success rates for other tasks keep their own qualifiers. Allowed retrieval alias: attack success proportion. |
| Benign utility | benign utility | Operational term of this book | Task quality, success rate, latency and availability, all measured under legitimate input. Not used in the main text: clean performance. |
| False positive rate | false positive rate; FPR | Field-standard | Its denominator counts units that are actually negative. Do not mix it up with the positive predictive value. Allowed retrieval alias: false alarm rate. |
| True positive rate | true positive rate; TPR | Fixed translation of this book | Its denominator counts units that are actually positive. Where recall is the term used, its object must be stated. Allowed retrieval aliases: recall, sensitivity. Not used in the main text: true positive ratio. |
| Precision | precision | Field-standard | Its denominator counts units predicted positive. The formula is given where the term is first defined in Chinese. Allowed retrieval alias: positive predictive value. |
| Recall | recall | Field-standard | Its denominator counts units that are actually positive. It must be told apart from retrieval recall according to the context. Allowed retrieval alias: true positive rate. |
| Calibration | calibration | Field-standard | The match between predicted probabilities or intervals and empirical frequencies. Allowed retrieval alias: probability calibration. |
| Static inspection | static inspection | Evidence layer of this book | Reads code, configuration, artifacts and interfaces, but never runs the target pipeline. Static analysis may serve as a concrete method. Allowed retrieval alias: static analysis. |
| Mechanism-level run | mechanism-level run | Evidence layer of this book | A local module or formula proxy actually executes inside a controlled fixture. Allowed retrieval alias: local mechanism run. Not used in the main text: partial mechanism, mechanism-layer state. |
| Simulated execution | simulated execution | Evidence layer of this book | A simulated object consumes the actions, but a real dynamics closed loop is not necessarily part of the setup |
| Closed-loop simulation | closed-loop simulation | Evidence layer of this book | A simulation environment with temporal and dynamics feedback consumes the actions. Allowed retrieval alias: closed-loop simulation. |
| End-to-end reproduction | end-to-end reproduction | Evidence layer of this book | Target code, weights, data, configuration, pipeline, consumer and predefined metrics are all closed together. Allowed retrieval alias: end-to-end run. Not used in the main text: end-to-end state, end-to-end trial. |
| Capability gate | capability gate | Operational term of this book | Sits outside the model and grants or denies a capability. It decides on subject, task, object, parameters, environment and consequences. Allowed retrieval alias: action gate. |
| First-broken interface | first-broken interface | Operational term of this book | The place where the attack first gains influence beyond the boundary set in advance. Allowed retrieval alias: first-failed interface. Not used in the main text: first-failure point. |
| Artifact closure | artifact closure | Operational term of this book | The model, adapters, components, configuration and dependencies that are actually loaded together, plus the executable relations among them. Allowed retrieval alias: runtime artifact closure. Not used in the main text: model closure. |
| Highest observed consequence level | highest observed consequence level | Operational term of this book | The highest consequence level the evidence directly observes. Architectural speculation does not raise it |
| Highest reachable consequence level | highest reachable consequence level | Operational term of this book | The highest consequence level that existing permissions and propagation conditions may allow, though it has not yet been observed |
| Fail-safe | fail-safe | Fixed translation of this book | The state that holds consequences in check when the system fails. It cannot be counted as normal task success, and it is not to be conflated with fail-closed, which denies access or actions by default. Allowed retrieval alias: fail-safe. Not used in the main text: safety failure. |
| Threat modeling | threat modeling | Field-standard | The process that identifies assets, attacker capabilities, paths, boundaries and impacts. Its output is called a threat model |
| Attack surface | attack surface | Field-standard | The interfaces and boundary points through which an attacker can enter the system, affect it, or extract data |
| Trust domain | trust domain | Field-standard | A region whose members share trust assumptions, control or policy. It is not itself a boundary |
| Trust boundary | trust boundary | Field-standard | The point at which the subject, the administrative domain, control or the trust level changes |
| Direct prompt injection | direct prompt injection | Field-standard | The attacker submits the instructions directly in the interaction with the model. They compete with the task the application is carrying out. Not used in the main text: direct injection. |
| Indirect prompt injection | indirect prompt injection | Field-standard | The malicious instructions arrive from external data such as web pages, documents, retrieved content or tool returns. Not used in the main text: indirect injection. |
| Model poisoning | model poisoning | Field-standard | Maliciously changes model parameters, updates or artifacts. It does not refer generically to all supply chain failures. Not used in the main text: model contamination. |
| Backdoor poisoning attack | backdoor poisoning attack | Field-standard | Reserved for scenarios that implant a trigger-activated backdoor through data poisoning. Not used in the main text: poisoning backdoor. |
| Backdoor trigger | backdoor trigger | Fixed translation of this book | In the backdoor context, the condition that triggers the behavior the attacker targets. General event triggering still uses the ordinary verb. Allowed retrieval alias: trigger. |
| External anchor | external anchor | Operational term of this book | A checkable reference, independent of the tested system's internally self-consistent narrative. Allowed retrieval alias: independent anchor. |

### Content Provenance and Visual Generation

| Canonical Chinese | English full name and abbreviation | Status | Definition and distinction from neighboring concepts |
|---|---|---|---|
| Content provenance and processing history | content provenance | official specification | Describes where digital content came from and what processing it underwent. A verified history does not automatically prove that the narrative is true. Permitted retrieval alias: provenance and processing history. Not used in the body text: proof of provenance, tracing information. |
| Content Credential | Content Credential | official specification | The mechanism that expresses provenance information through C2PA manifests and the user experience around them. It is not a synonym for provenance in general. Not used in the body text: content credential, provenance credential. |
| Authenticity | authenticity | common in the field | Applies where identity claims, content binding and processing history are involved. It is distinguished from factual truth. Permitted retrieval alias: authenticity status. |
| Integrity | integrity | common in the field | Says whether an object or claim has been changed without authorization. It is not equivalent to content correctness. Permitted retrieval alias: data integrity. |
| Watermark | watermark | common in the field | A detectable signal placed in advance or embedded in the content. A hit does not automatically prove authorship or factual truth. Permitted retrieval alias: digital watermark. |
| Generative adversarial network | generative adversarial network; GAN | common in the field | The full name is given at first use. The term keeps the adversarial objective of training apart from the generator at inference time. Permitted retrieval alias: adversarial generative network. |
| Autoregressive generation | autoregressive generation | common in the field | At every step it predicts the next unit, conditioned on the history already generated. Permitted retrieval alias: autoregressive model. |
| Diffusion model | diffusion model | common in the field | Models data by way of a noise process and a reverse generation process. Permitted retrieval alias: denoising diffusion model. |
| Latent diffusion model | latent diffusion model; LDM | common in the field | Runs the main diffusion process in a learned latent space. It relies on an encoder and a decoder. Permitted retrieval alias: latent-space diffusion model. Not used in the body text: potential diffusion model. |
| Diffusion Transformer | Diffusion Transformer; DiT | common in the field | Uses a Transformer as the backbone of a diffusion model. DiT does not name an independent sampling principle. Permitted retrieval alias: diffusion-style Transformer. |
| Flow matching | flow matching | common in the field | Learns a vector field along a continuous probability path. Permitted retrieval alias: flow-matching generation. |
| Rectified flow | rectified flow | common in the field | A specific method that straightens transport paths. Flow matching is the superordinate method, so the context has to be checked by hand. Permitted retrieval alias: rectifying flow. |
| Variational autoencoder | variational autoencoder; VAE | common in the field | Encodes and decodes with probabilistic latent variables. In visual generation pipelines it often serves as the compression component. Permitted retrieval alias: variational automatic encoder. |
| Provenance data | provenance data | official specification | Structured data that carries provenance operations and their relationships. It is not translated directly as proof. Permitted retrieval alias: provenance metadata. |
| Coalition for Content Provenance and Authenticity | Coalition for Content Provenance and Authenticity; C2PA | official proper name | The organization's full name is given at first use. C2PA can also refer to the specification system it publishes. |
| Digital watermark | digital watermark | common in the field | A detectable signal, embedded in or attached to the content. A hit does not automatically prove the source entity or the factual truth value. Permitted retrieval alias: watermark. |
| Visible watermark | visible watermark | common in the field | A mark that humans perceive directly. It is kept separate from invisible watermarks, which machines detect. Not used in the body text: explicit watermark. |
| Invisible watermark | invisible watermark | common in the field | Invisibility does not mean the watermark cannot be detected, removed or forged. Not used in the body text: stealth watermark. |
| Denoising diffusion probabilistic model | denoising diffusion probabilistic model; DDPM | common in the field | Refers to the DDPM construction specifically. DDPM is not used for diffusion models in general. |

### Vision–Language–Action, World Models, and Runtime Control

| Canonical Chinese | English full name and abbreviation | Status | Definition and distinction from neighboring concepts |
|---|---|---|---|
| Vision–language model | vision-language model; VLM | common in the field | Visual and language input together with the semantic consumer decide the category. It does not automatically have action capability. Permitted retrieval alias: vision language model. Not used in the body text: multimodal large model. |
| Vision–language–action model | vision-language-action model; VLA | common in the field | Maps vision, language and proprioceptive state onto action representations that a control stack can consume. Permitted retrieval alias: vision language action model. Not used in the body text: embodied large model. |
| World model | world model; WM | common in the field | A superordinate concept. It maintains state and predicts future variables that matter to the environment or the task. |
| World action model | world action model; WAM | operational term in this survey | Future prediction must actually take part in action generation, comparison or policy improvement. The consumer decides whether it does. Not used in the body text: action world model. |
| Environment world model | environment world model; EWM | operational term in this survey | Stresses how external environment state is observed or evolves through interaction. It is not an already unified official category. Not used in the body text: environment model. |
| World control model | world control model; WCM | operational term in this survey | World predictions enter feedback control trajectories, low-level commands or safety filtering. It is not an already unified official category. Not used in the body text: control world model. |
| Partially observable Markov decision process | partially observable Markov decision process; POMDP | common in the field | Distinguishes the true state, observations, beliefs and actions. The full name and abbreviation are given at first use. Permitted retrieval alias: partially observable decision process. |
| Model predictive control | model predictive control; MPC | common in the field | Each round it uses the model to predict over a finite horizon, then replans in rolling fashion. Using MPC does not automatically create a safety guarantee. Permitted retrieval alias: predictive control. |
| Runtime assurance | runtime assurance; RTA | fixed translation in this survey | When assumptions fail, an independent monitor switches high-performance control onto a safe path. Permitted retrieval alias: operational assurance. Not used in the body text: runtime guarantee. |
| Safety envelope | safety envelope | common in the field | The acceptable set, defined by constraints on state, action, speed, distance and so on. The safety boundary is a broader system concept. Permitted retrieval alias: permitted state–action set. |
| Control barrier function | control barrier function; CBF | common in the field | Under explicit dynamics and constraint assumptions, it keeps a safe set forward invariant. Permitted retrieval alias: barrier function. |
| Out-of-distribution | out-of-distribution; OOD | common in the field | Defined relative to a specified training or calibration distribution. The reference distribution must be stated. Permitted retrieval alias: out-of-distribution input. |
| Recovery time objective | recovery time objective; RTO | common in the field | The target time to get back to a specified safe state after a service interruption |
| Recovery point objective | recovery point objective; RPO | common in the field | The span of state times that may be lost, or that the system may roll back to |
| AI safety and security | AI safety and security | umbrella definition in this survey | The Chinese umbrella term covers adversarial and unauthorized risks, and also control of harm to people, property, the environment and tasks. Permitted retrieval alias: AI safety. |
| Security | security | fixed translation in this survey | Applies to system protection against attacks and unauthorized access, and against threats to confidentiality, integrity and availability. Permitted retrieval alias: network and information security. |
| Safety | safety | fixed translation in this survey | Avoiding harm that is unacceptable to people, property, the environment or tasks. It is kept separate from security. Permitted retrieval alias: harm safety. |
| Resilience | resilience | common in the field | A system's ability to maintain, recover and adapt under disturbance or attack. It is not equivalent to recoverability. Permitted retrieval alias: system resilience. |
| Recoverability | recoverability | common in the field | Once a failure is discovered, the ability to freeze, revoke, roll back, clean up, rebuild and safely restore service. Permitted retrieval alias: recovery capability. |
| Confidentiality | confidentiality | common in the field | Keeps information from being exposed to unauthorized entities. Permitted retrieval alias: secrecy. |
| Availability | availability | common in the field | Systems and resources can be reached and used at the moment authorized entities need them. It is kept separate from benign utility. Permitted retrieval alias: service availability. |
| Runtime monitoring | runtime monitoring | common in the field | Observes states, events or constraints during operation. It is only one possible component of runtime assurance. Permitted retrieval alias: operational monitoring. |
| Runtime verification | runtime verification | common in the field | During operation it checks whether an execution trace satisfies a formal or executable specification. It is not equivalent to general monitoring. |

### Training, Control, and Operations Engineering

| Canonical Chinese | English full name and abbreviation | Status | Definition and distinction from neighboring concepts |
|---|---|---|---|
| Authorization scope | authorization scope | fixed translation in this survey | Limits which resources and actions a token or principal may operate on. In the body text the English is given at first use, and the Chinese term is preferred thereafter. Permitted retrieval alias: authorization range. |
| Secret broker | secret broker | fixed translation in this survey | Issues short-lived secrets or credentials for approved actions outside the model or the task process. It is not a network proxy. Permitted retrieval alias: credential broker. |
| Micro virtual machine | micro virtual machine | common in the field | A lightweight virtual machine isolation unit. Its specific security properties still depend on the virtual machine monitor, the host, and the configuration. |
| System call filtering | system call filtering | fixed translation in this survey | Uses Linux seccomp filters to restrict the system calls a process may make. It does not replace file, network, secret, and resource isolation. Permitted retrieval alias: secure computing filtering. |
| Leakage probe | leakage probe | operational term in this survey | Uses known unique markers or decoy records to check unauthorized reads and leakage paths. Kept separate from canary releases. Permitted retrieval aliases: canary marker, canary sample. Not used in the body text: canary probe. |
| Dry run | dry run | fixed translation in this survey | Performs validation and transformation without persistently writing the intended changes. It cannot prove that the real commit path will necessarily succeed. Permitted retrieval alias: dry execution. |
| Hash value | hash value | fixed translation in this survey | A fixed-length value obtained from a hash function. It can be used for integrity comparison, but does not by itself prove that the source is trustworthy. Permitted retrieval alias: hashed value. |
| Conformal prediction | conformal prediction | common in the field | Constructs prediction sets or intervals with a coverage property under explicit assumptions such as exchangeability. Per-frame coverage cannot be directly extrapolated to a complete task. |
| Pareto frontier | Pareto frontier | common in the field | Comprises the non-dominated solutions, for which no objective can improve further without another being harmed. |
| Prior distribution | prior distribution | common in the field | A probabilistic description of a variable or state before observing current evidence. Used in a pair with the posterior distribution. Permitted retrieval alias: prior. |
| Posterior distribution | posterior distribution | common in the field | A probabilistic description updated by combining observed evidence. The model and conditions it relies on must be stated. Permitted retrieval alias: posterior. |
| Fail-closed | fail-closed | fixed translation in this survey | Denies access or actions by default when control or authentication fails. Kept separate from safe failure, which enters a state that limits real-world consequences. |
| Rollout | rollout | fixed translation in this survey | A sequence of states and actions unfolded toward the future from the current state according to a model or policy. It is not automatically equivalent to real-world execution. Permitted retrieval alias: rolling rollout. |
| Episode | episode | common in the field | A complete task unit, defined by its initial conditions, termination conditions, and consecutive steps. |
| On-policy distribution | on-policy distribution | fixed translation in this survey | The state-action distribution produced by the interaction of the policy currently being evaluated itself. Kept separate from the distributions of other policies or of offline data. Permitted retrieval alias: same-policy distribution. |
| Checkpoint | checkpoint | common in the field | A saved version of parameters and related state from training or adaptation. The actual deployment object also needs to be considered together with configuration and dependencies. Permitted retrieval alias: model checkpoint. |
| Bin | bin | fixed translation in this survey | An interval obtained by dividing continuous values at explicit boundaries. In action quantization, the model usually outputs or selects a class or token representing a certain bin rather than outputting the whole set of intervals. Permitted retrieval alias: binned interval. |
| Phantom grasp | phantom grasp | fixed translation in this survey | A failure phenomenon in which the gripper closes in advance before contacting the target. A genuinely graspable object may exist in the scene. |
| Canary release | canary release | common in the field | Hands a change to a small share of traffic or instances and observes it before expanding the release. Kept separate from the leakage probe, which uses unique markers to detect leakage. Permitted retrieval alias: canary deployment. |

### The Four Most Easily Confused Relationships

**Security and safety.** Security deals with attacks, unauthorized access, and confidentiality, integrity, and availability. Safety deals with whether people, property, the environment, or the mission are subject to unacceptable harm. A prompt injection is first of all a security problem. If it gains mechanical execution capability and approaches people, it simultaneously becomes a safety problem. In this book, the Chinese term “人工智能安全” is the collective term for both. No single English word is used to cover the entire responsibility.

**Provenance records and content truthfulness.** Content provenance explains where an object came from and what processing it underwent. Content credentials are the specific objects through which systems such as C2PA express and verify these claims. A digital watermark is a signal that can be embedded in content. A valid signature, a verifiable content credential, or a watermark hit does not automatically prove that the depicted narrative is factually true, that the subject has already consented, or that the content is harmless.

**Model categories and consumers.** Vision–language models output semantics or content. Vision–language–action models instead output action representations that a control stack can consume. World models maintain state and predict the future. In this book, the term world action model is used only when the future actually participates in action generation, comparison, or policy improvement. The term world control model is used when predictions enter feedback control. Neither product names nor image realism can substitute for consumer evidence.

**Evidence layers and operational conclusions.** Static inspection confirms the static properties of files, configurations, and interfaces. Mechanism-level execution confirms that local modules actually execute in a controlled fixture. Simulated execution and simulation closed loops add consumers and dynamics. End-to-end reproduction requires the target version, data, configuration, pipeline, and metrics to close. Field incidents additionally involve real permissions an

---

[← Back to contents](index.md)
