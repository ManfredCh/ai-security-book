apter 12 will discuss how errors acquire physical execution capability once generated content enters a perception–reasoning–action system.

# Part IV　Vision–Language–Action Closed Loop

## Guide to This Part

Suppose visual input only has to answer "what is in the picture." The output still mostly stays at the semantic layer. When a control stack instead reads that output as pose, velocity, waypoints or action chunks, the same perception error can acquire real-world capability. Part IV does not judge system categories by product name. It examines actual inputs, internal states, output forms and consumers. Vision–language models output semantics or content. Vision–language–action models output action representations that a control stack can consume. A future prediction enters this survey's operational definition of a world action model only when it genuinely participates in action comparison, policy improvement or planning.

Chapter 12 opens with the closed loop's interfaces: observation, representation, state, plan, action, execution and feedback. Chapter 13 places attack variables on this chain. It distinguishes attack carriers, optimizable variables, frozen components, the first-broken location and the highest consequence. Chapter 14 traces the many semantic transformations an action passes through. The path runs from tokens or vectors through detokenization, coordinate and unit transformation, middleware, authorization and low-level control to the real-world environment. Chapter 15 then gathers the supply chain, observation, state, action gate, runtime assurance and recovery into a defense-in-depth structure. Its layers do not share a common cause.

Readers do not need prior knowledge of full robotics. The minimal closed loop works like this. Sensors produce incomplete observations. The model encodes them into semantics or state. The planner selects candidate actions. The control layer converts actions into commands the device can execute, and a change in the environment produces new observations. Safety problems arise at every transformation between objects. A patch in the image can change the representation. An outdated map can change the state. A wrong unit can amplify an action, and a missing actuator acknowledgment can make the system treat a result that never occurred as fact.

The benign case is a mobile robot that receives only a short-lived action prefix. The action gate checks coordinates, velocity, region and deadline, and an independent sensor confirms the result after execution before the next batch is released. The boundary case looks different. The model output seems smooth and highly confident. Yet the control stack uses the wrong coordinate frame, or it keeps executing an old action chunk after a new obstacle appears. In both cases the model-level metrics may stay unchanged. What decides the actual consequence is the external transformations and the feedback.

Part IV ends by separating three questions: seeing correctly, thinking correctly and acting correctly. Correct semantic recognition does not guarantee a correct future prediction. A correct future prediction does not guarantee correct action selection. A correct action proposal does not guarantee that the actuator has already worked as required. Part V goes deeper into the internal chain of forecasting the future. It discusses how state, dynamics, goals and constraints are amplified in imagination and control.

Evidence also escalates as the closed loop advances. A change in a vision–language model's answer can support only the content or plan layer. An action-tensor hit can support the model-proposal layer. Once middleware accepts a representation message, that message has entered the control stack. Only a restricted simulation or an isolated physical robot observes execution. Real-world consequences additionally require the environment and external observ

---

[← Back to contents](index.md)
