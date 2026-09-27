# Generative and Embodied AI Security

## Attacks, Defenses, and Engineering Verification from Language Models to World Models

Mingjun Cheng, Vorynel Co.,Ltd


## Summary

A model that only generates a passage of text keeps its security problems largely at the level of content. When its outputs enter retrieval, long-term memory, media publishing, software tools, robot actuators and world-model closed loops, errors may then acquire state, identity and real-world capability. This survey is organized around one unified chain of questions. Where does untrusted input first cross a trust boundary? How does an attack propagate from data to state, plans, actions and feedback? How do defenses establish independent, verifiable and recoverable controls outside the model?

The survey is divided into six parts. Part One establishes the capability chain, the first-broken interface, the consequence layers and the evidence grading rules. Part Two turns to large language models and artificial intelligence agents (AI agents; hereinafter "agents"). It covers jailbreaking, prompt injection, retrieval-augmented generation, memory, tools, identity, sandbox and supply chain. Part Three discusses data, components, conditions, sampling, privacy, spatiotemporal state, detection, watermarking and content provenance in image and video generation. Part Four enters the observation–reasoning–action closed loop of vision–language models, vision–language–action models and world action models. Part Five analyzes the state, dynamics, reward, planning and runtime assurance of world models, together with their environment, action and control functions. Part Six assembles cross-domain controls into a regime of design reviews, test matrices, release gates, monitoring and incident response.

Each case is organized along assets, entry points, attacker capability, budget, the first-broken interface, the highest consequence layer, benign utility, cost and the limits of the evidence. Method names and success rates are read back into the system conditions that produced them. The result is a security engineering methodology that can keep working as models, tools and environments change.

## Preface

Generative AI security is often pulled between two extremes. One extreme reduces the problem to "whether the model refuses harmful prompts," as if a stronger system instruction were enough to constitute a boundary. The other writes any anomalous output directly as a real-world catastrophe and ignores actuators, permissions, environments and operational controls. Both narratives skip the place where the system actually changes.

Technical teams need a more concrete language. Text on a web page, a trigger in training data, a spatiotemporal pattern in a video, a patch in a robot's field of view, a state deviation in a world model — all of these look different. Yet all may let a low-trust object obtain influence beyond its intended authority. Defense proceeds from six principal relationships. Who can write? Who can read? Who can authorize? Who can execute? Who can observe? Who is responsible for recovery?

This survey therefore begins from the system's operating boundary. Model defenses can reduce the frequency of harmful outputs and known attacks. High-impact systems also need structured information flows, least capability, independent action gates, isolation, resource budgets, unified traces and recoverable operation. A defense-in-depth structure gives each layer a different responsibility. When one layer fails, subsequent controls can still limit the consequences.

The formulas in the survey use the mathematical depth needed to support engineering judgment. Research numbers always appear together with their denominators, protocols and limitations. The "Bringing It into a Real System" section at the end of each chapter places the methods into project scenarios. It explains how to draw a system diagram, record threats and set acceptance gates. The hope is that, when readers close this survey, they will be able to face a new model family or a new agent system and independently answer five questions. These are what to protect, where trust changes, how capability is obtained, how far the evidence extends, and how to recover after failure.

## Reading Notes

The survey progresses by capability dependency. For a first reading, it is recommended to complete Chapters 1—3 in order. They define the first-broken interfaces U0—U6, the consequence layers Y0—Y4, the threat record and the four-part metrics used by all subsequent chapters.

Different readers can choose among three paths:

- Model and security researchers: 1—7, 8—11, 12—18, then 19—20.
- Platform and application engineers: 1—7, 19—20, and the vision, embodied, or world-model division according to their business.
- Technical management and governance staff: 1—3, 7, 11, 15, 18—20, with a focus on evidence boundaries, release gates, and recovery responsibility.

The "worked examples" in the chapters demonstrate methods. Where there is no literature citation, they are explicitly hypothetical systems. Research numbers with citations support only their original protocol and do not represent the overall industry incidence rate. Discussions of code, attacks and testing are aimed at defense, authorization assessment and risk understanding. They do not provide unauthorized operational plans against real systems.

References use machine-checkable citation keys, which the print edition expands in full at the back of the book. Standards, closed-source products and rapidly published research change over time. Before actual deployment, versions, policies, licenses and the operating environment should be re-verified.

## The Six Minimal Concepts Needed to Read This Survey

This is not a prerequisite syllabus that requires readers to first complete language models, visual generation, robotics and control theory. What cross-branch reading really requires is a stable set of system questions. What objects enter the system? What is retained inside? To whom is the model output handed? At which step is authority obtained? How are consequences observed? How far can the evidence support? The six concepts below give the minimal mental model shared across the survey. When they meet an unfamiliar model name, readers can keep reading along these six sets of relationships. Formulas and implementation details can follow later, as needed.

### Models and Systems: A Probability Function Is Not a Complete Product

A model receives an input representation and computes an output according to its parameters and the current context. A large language model (LLM) typically receives a sequence of tokens and predicts subsequent tokens. A visual generation model receives conditions such as text, images, poses or noise, and progressively forms an image or video. An action model may output discrete actions, continuous control values or trajectories. Whatever the output form, the model itself does not automatically obtain permission for databases, email, payment interfaces or actuators.

Outside the model, the system adds parsers, data sources, caches, retrievers, policies, identity services, tools, runtime environments, logs and recovery procedures. How user input is split, under what identity web material enters the context, and which principal issues a candidate call are all system behaviors. So is whether tool results are written into future state. Even if two products use the same model weights, they may have completely different security boundaries, because tool permissions, state writes or runtime configuration differ.

Ordinary question answering provides the simplest positive example. The model generates an explanation, the user reads it and judges for themselves, and the output stops at the information layer. The boundary case is the model generating the same sentence while the runtime layer parses it into a database statement or a mechanical action. The runtime layer executes it when independent authorization is lacking. The appearance of the text does not change, but the consumer and the permissions change the highest reachable consequence. The survey therefore draws the complete system first, and discusses model metrics afterwards.

### Training and Inference: Parameter Changes and Runtime State Changes Are Not the Same Thing

Training uses data, an objective function and an optimization process to update parameters. Inference reads the current input and state on a given parameter version and computes an output. Fine-tuning continues training from existing parameters, and may update all of them or only a small part. Low-rank adaptation (LoRA) changes model behavior through smaller trainable matrices, and is a parameter-efficient fine-tuning method. It is not a collective term for all adapters.

At runtime there are also changes that are not written into model parameters. System prompts, retrieved passages, conversation history, key-value caches, long-term memory, environment maps and tool receipts may all change the next output without changing the main weights. Conversely, a new adapter or decoder can change the result when the input text is exactly the same. A security investigation that asks only "whether the model was retrained" will miss three paths: the loading combination, the context and the state.

A normal software upgrade freezes the joint version of the base model, adapters, encoders, configuration and dependencies, and compares behavior before and after the change. A hash value is a fixed-length value computed by a hash function from an input. Under a fixed algorithm and trusted baseline, a hash match supports "the current bits are consistent with the baseline." It does not by itself prove that the provenance is trustworthy or the behavior safe. The boundary case is a main model file whose hash is unchanged while the runtime quietly loads a new LoRA, template or plugin. Looking only at the main weights would wrongly judge the actual system as unchanged. The artifact closure and change impact analysis discussed later address exactly this kind of object misalignment.

### Representation and State: How Encoded Information Persists Across Steps

Raw text does not enter a neural network directly. Tokenization first turns text into a sequence of tokens. Here a "token" is a model sequence unit, not the same object as an access token in an identity system. The Transformer architecture uses operations such as attention mechanisms. These operations let the current position update according to other representations in the context. The architecture explains how pieces of information influence one another within a single inference pass. It does not automatically specify which message is more trustworthy or which principal has more authority.

An embedding maps text, images or other objects into continuous vectors that are convenient to compare. Vector proximity indicates some kind of similarity under a given model. It does not mean that two objects come from the same source, have the same permissions or are equally true. Latent variables, action tokens and map coordinates are also representations: they compress certain information while possibly losing details or mixing different semantics.

When a representation persists across steps, sessions or tasks and influences future computation, it becomes runtime state. The context window covers only the range of tokens directly visible to the current inference pass. Long-term memory, retrieval indexes, caches and the latent state of a world model can persist outside the window. The normal example is a maintenance assistant writing approved equipment manuals into a knowledge base by tenant and validity period. The boundary case is imperative text on a web page being automatically saved as long-term memory, so that the next user is affected without visiting the web page again.

### Open Loop and Closed Loop: Who Consumes the Output Determines How Far the Risk Travels

An open-loop system produces an output. It does not automatically send the real-world execution result back into the next round. An image generator that exports a poster for a human to choose from usually belongs to an open-loop path. So does an analysis tool that generates a recommendation for an engineer to review. Open loop does not mean risk-free. Privacy leakage, copyright disputes, deceptive dissemination and erroneous decisions can still occur. It only means that the system does not keep advancing actions through its own feedback.

A closed-loop system hands its output to a planner, controller, tool or actuator, and then writes the execution result back into the system as a new observation. A vision-language-action model (VLA) can map observations and language tasks into action representations. A world model (WM) can maintain internal state and predict the future under action conditions. If a planner uses that future to compare actions, or if the prediction enters feedback control, errors may then accumulate across multiple rounds of state updates.

A normal closed loop confines each round of actions to a short duration and a safe envelope. It reads timestamped independent observations after execution, and only then decides the next step. The boundary example is a system that generates a very long action chunk in one go and keeps executing it. Even when new observations already show that the environment has changed, the old plan still advances, because it lacks a deadline and replanning. The "feedback" discussed throughout this survey is both a resource for error correction and a channel through which attacks, privacy and persistence enter the next round.

### Probabilistic Output and Real-World Authority: A High Score Does Not Sign Off for Any Control

Model outputs usually contain probabilities, scores, candidate sequences or continuous vectors. These numerical values describe the model's computation results under given parameters, inputs and objectives. High confidence does not equal factual correctness. Low uncertainty does not equal being in a safe state. A candidate action ranked first does not equal that it has already been approved for execution. A model may be very confident on out-of-distribution (OOD) inputs, and may also stably choose the wrong object because the objective function lacks real-world constraints. Here "out-of-distribution" must be judged relative to a specified training or calibration distribution.

Real-world authority is issued by trusted controls in the system. Protocols such as the Model Context Protocol (MCP) can standardize how prompts, resources and tools are exchanged. An access control list (ACL) can restrict a principal's access to data objects. The business layer still needs to verify the current user's objective, recipient, file, amount, coordinates, time and consequences. A correctly formed protocol only proves that the request can be parsed. A valid token only proves that some principal holds a segment of authorization. Neither of the two makes judgments on behalf of user intent and security constraints.

A normal example is a research assistant proposing to call a read-only search tool. The capability gate confirms the task, data use, query scope and duration, and then issues a short-lived capability token. The boundary example is the same assistant reading a command from a web page and then requesting to publish a software package. Even if the call structure is entirely legitimate, the action object and the highest consequence have already changed. The permission layer should reject the request or escalate it for human confirmation. It should not let the model's own "plausibility judgment" become the final authorization.

### Metrics and Assurance: Numbers Are Only Usable When They Carry a Denominator and an Evidence Layer

An attack success rate (ASR) must settle four things. What counts as one statistical unit, and which units enter the denominator? Which observation counts as success? How much knowledge, query, time, write or physical access budget does the attacker have? Delete the samples that timed out, hit interface errors or were blocked by a defense line, and the denominator changes. Treat model output, dangerous plans, simulated execution and real-world consequences alike as "success", and different endpoints compress into one percentage. No decision can be made on that percentage.

This survey reports attack effectiveness, residual risk, benign utility and operational cost side by side. A security control can lower the attack rate and still make legitimate tasks fail in large numbers. Reporting only the former is then not enough. A detector can show very good offline curves and still produce an alert volume that cannot be handled every day. Such a detector likewise cannot go directly into production. A team can judge what a number means in the current system through intervals, paired comparisons, base rates, latency and recovery time. Those do not replace a clear statistical unit and causal path.

Evidence has levels too. Static inspection reads code, configuration and artifacts, but does not run the target pipeline. Mechanism-level runs do execute local modules, inside a security fixture. Realism of consumers and environments climbs through simulated execution, closed-loop simulation, end-to-end reproduction and field incidents. Lower-level evidence is not without value — it can find interface and implementation errors. What it cannot do is extrapolate automatically to higher levels. Runtime assurance (RTA) likewise requires writing out trusted states, monitors, switching logic, safe controllers and failure assumptions. It cannot settle for treating an uncertainty score as a guarantee.

A normal report says so outright: "in the target version, under a given attack budget, and in isolated simulation, how many independent tasks reached which consequence layer." Failed runs and unknowns are retained alongside. A boundary report offers only "defense rate 95%." It carries no denominator, no model version, no scorer, no control state and no highest consequence layer. The first kind can enter release decisions. The second is at most a lead, and it needs supporting evidence. With these six minimal concepts in hand, a reader need not become a full-stack expert first. The system causal chain that this survey really cares about stays trackable in every chapter.

### When Encountering an Unfamiliar Formula, Read the Objects Rather Than the Derivation

The formulas in this survey mainly do three kinds of work. The first names objects. A tuple, for instance, puts assets, inputs, states, models, execution gates, feedback and recovery into one system diagram. The second expresses change, for example how the previous moment, the current observation and the action update the state. The third specifies measurement, for example the numerator, the denominator and the conditions of an attack success rate. When reading, translate each variable back into an observable object. Then ask what the equals sign, the conditions and the summation each connect. A formula has not yet landed on a verifiable system if one of its variables matches no log, file, interface or event.

No probability in these formulas has to be imagined as a measure of how much the model "believes." A conditional probability states the frequency, or the modeled relationship, with which a later event occurs once an earlier event has occurred. The conditional chain of a dangerous consequence offers one example. It separates input being accepted, state being changed, plan being selected, capability being granted, and environment being affected. Its use is to locate controls. It is not to assume that the stages are independent and then compute a seemingly precise total risk. One shared model, parser or identity root can make several stages fail at the same time. Dependencies of that kind must be stated separately, in the text and in the figures.

Optimization formulas likewise begin with the question of who can change what. Different permissions govern the pixels, tokens, training samples, state vectors, rewards or candidate trajectories an attacker can optimize. Nor is a frozen model the same object as an updatable adapter. An objective function states what the attack or the training is searching for, and nothing more. It does not prove that the actual budget suffices to find a solution. Nor does it prove that a found internal deviation can cross the boundary of authorization and execution. After each formula, the "assumptions" and "failure conditions" are there precisely to prevent this leap.

A three-step reading method works here. Start with the topic sentence of the text. It names the problem the formula is meant to solve. Then follow the figure or variable table to the inputs, states and outputs. Finally check whether the conclusion stops at the model, the simulation or the real environment. Readers who care only about architecture and governance may skip the algebraic details. They should not skip the consumers and units of the variables. Readers who want to reproduce should go further and check the data, code, parameters, randomness and scorer. Both reading depths share the same evidence boundary.

### How to Use Terminology, Figures, and Cases

A term's first appearance takes the form "Chinese standard name (English Full Name, abbreviation)." Registration is separate for national standards, official specifications, words commonly used in original papers, translations customary in the field, and the operational terms of this survey. Their normative levels are distinguished clearly. The analytical language of this survey includes first-broken interface, capability gate, artifact closure, highest observation layer and highest reachable layer. World action model, environment world model and world control model receive working definitions that follow the actual consumer. They help compare systems. They do not oblige other authors to adopt the same category names.

Figures provide relational navigation. Rectangles usually denote inputs or artifacts. Rounded boxes stand for models or transformations, prominent borders for authorization and execution, and return-bent arrows for feedback. Reading a figure starts with the solid lines, which trace the normal information flow. State retention, attack influence and recovery loops come next. The lead-in paragraph before each figure names the path to observe. The paragraph after it says what the figure supports, and what it does not prove. The graphics are the authors' own mechanism illustrations; they do not copy experimental figures from papers. An abstract arrow marks nothing more than a relationship to be verified. Whether a real deployment realizes it is still proven by configuration, logs and execution receipts.

The cases here divide into research cases and engineering worked examples. Research cases carry citations. The original paper's model, data, attacker capability and environment limit their numbers and conclusions. Engineering worked examples demonstrate methods. Any system, role or numerical value in them without a citation is an explicit assumption. The fields and check order of a worked example can be transferred to a reader's own project. Its illustrative values cannot serve as industry baselines. Cases are compared numerically only when their statistical unit, protocol and consequence layer are compatible. Otherwise the report keeps side-by-side evidence and mechanism differences.

The "Bringing It into a Real System" section at the end of each chapter is not a homework question. It is a narrative that begins at the field entry point. It shows which receipt the team examines first, and how version and consumer are judged. It also shows where extrapolation stops, and which control should next change the system state for real. Retell the objects, permissions, evidence and recovery along this process, and the reader has already grasped the engineering throughline of the chapter. Algorithm details can be pursued further, according to responsibilities.

An unfamiliar abbreviation may still turn up in a chapter. Start with the Chinese-English glossary at the back of this survey, then return to the principles groundwork that opens the chapter. The glossary fixes names and neighboring concepts. The principles groundwork explains how these objects act in a system. The main-text cases provide evidence and failure paths. The three carry different responsibilities, so no single definition has to bear the three tasks of naming, teaching and proving at once.

\newpage

## Contents

1. [Part One: A Shared Language](01-Part-One-A-Shared-Language.md)
2. [Chapter 1: From Generated Content to Changing the World](02-Chapter-1-From-Generated-Content-to-Changing-t.md)
3. [Chapter 2 System Structure, Interface Constraints, and the First-Broken Interface](03-Chapter-2-System-Structure-Interface-Constrain.md)
4. [Chapter 3　Evaluation, Statistics, and Reproduction Boundaries](04-Chapter-3-Evaluation-Statistics-and-Reproducti.md)
5. [Part II: Language Models and Agents](05-Part-II-Language-Models-and-Agents.md)
6. [Chapter 4: Instruction Conflicts, Jailbreaking, and Prompt Injection](06-Chapter-4-Instruction-Conflicts-Jailbreaking-a.md)
7. [Chapter 5 Retrieval, Context, and Memory](07-Chapter-5-Retrieval-Context-and-Memory.md)
8. [Chapter 6　Tools, Identity, Execution, and Supply Chain](08-Chapter-6-Tools-Identity-Execution-and-Supply-.md)
9. [Chapter 7 Defense in Depth for Language Models](09-Chapter-7-Defense-in-Depth-for-Language-Models.md)
10. [Part III: Image and Video Generation](10-Part-III-Image-and-Video-Generation.md)
11. [Chapter 8 Visual Generation Pipelines and Security Assets](11-Chapter-8-Visual-Generation-Pipelines-and-Secu.md)
12. [Chapter 9: Data, Models, and the Personalization Supply Chain](12-Chapter-9-Data-Models-and-the-Personalization-.md)
13. [Chapter 10　Conditions, Sampling, Privacy, and Generation Services](13-Chapter-10-Conditions-Sampling-Privacy-and-Gen.md)
14. [Chapter 11　Video Spatiotemporal Safety and the Authenticity Chain](14-Chapter-11-Video-Spatiotemporal-Safety-and-the.md)
15. [Part IV　Vision–Language–Action Closed Loop](15-Part-IV-Vision-Language-Action-Closed-Loop.md)
16. [Chapter 12　From Seeing to Acting: Closed-Loop Interfaces of Three Model Types](16-Chapter-12-From-Seeing-to-Acting-Closed-Loop-I.md)
17. [Chapter 13　Attack Propagation in Observation, Reasoning, and Planning](17-Chapter-13-Attack-Propagation-in-Observation-R.md)
18. [Chapter 14: Actions, Tools, and Physical Consequences: From Proposal to Execution](18-Chapter-14-Actions-Tools-and-Physical-Conseque.md)
19. [Chapter 15　Closed-Loop Defense in Depth and Verification](19-Chapter-15-Closed-Loop-Defense-in-Depth-and-Ve.md)
20. [Part V: World Models and Control](20-Part-V-World-Models-and-Control.md)
21. [Chapter 16: The Four Functional Boundaries of World Models](21-Chapter-16-The-Four-Functional-Boundaries-of-W.md)
22. [Chapter 17　State, Dynamics, and Goal Attacks: How the Imagination Chain Is Hijacked](22-Chapter-17-State-Dynamics-and-Goal-Attacks-How.md)
23. [Chapter 18　Runtime Assurance, Recovery, and Falsifiable Testing](23-Chapter-18-Runtime-Assurance-Recovery-and-Fals.md)
24. [Part Six: Engineering Closed Loop](24-Part-Six-Engineering-Closed-Loop.md)
25. [Chapter 19: Cross-Domain Defense-in-Depth Architecture](25-Chapter-19-Cross-Domain-Defense-in-Depth-Archi.md)
26. [Chapter 20 From Threat Model to Operating Institutions](26-Chapter-20-From-Threat-Model-to-Operating-Inst.md)
27. [Appendix](27-Appendix.md)
28. [Appendix E — Post-cutoff update (2026-08-09 → 2026-09-26)](28-Appendix-E-Post-cutoff-update-2026-08-09-2026-.md)
