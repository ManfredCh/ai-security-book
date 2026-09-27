perspective to world models in general. It first resolves the functional boundaries among WM, EWM, WAM, and WCM, which are often confused.

\newpage

# Part V: World Models and Control

## Guide to This Part

A world model can compress past observations and actions into an internal state, then predict the futures that may arise under different action conditions. That future does not have to be a realistic video. It can also be latent states, rewards, costs, constraints, or task-relevant variables. Safety analysis does not care whether a model bears the name "world." It asks what is predicted, what state is retained, who consumes the prediction, and whether the prediction enters action selection and feedback control.

Chapter 16 gives the four types of functional boundaries. The world model is the superordinate concept of maintaining state and predicting the future. The environment world model, the world action model, and the world control model are the operational classification this survey adopts for safety analysis. The first emphasizes external environment evolution, the second the future's participation in action, and the third prediction entering feedback control. They can overlap. They do not constitute a capability hierarchy from low to high, and they are not official model categories that have already been unified. The full English names, abbreviations, and operational definitions are given one by one when the corresponding mechanisms are introduced.

Chapter 17 unfolds attacks along the imagination chain. The supply chain can solidify bias into parameters. Observation conditions can change state updates, and latent states can persist across time. Dynamics errors can be amplified over the rollout. Rewards, costs, and constraints in turn change candidate ranking. Chapter 18 turns these paths into falsifiable defenses and evidence. It explains how independent anchors, uncertainty calibration, model predictive control, action filtering, execution verification, and recovery states jointly limit consequences.

In a normal example, the planner rolls predictions out only over a finite horizon and checks the world model with an independent state anchor. Model predictive control (MPC) selects only short action chunks. When the prediction interval exceeds the calibrated range, runtime assurance (RTA) switches the system to a conservative controller. In a boundary example, prediction and risk checking share the same latent state. Both drift at the same time, yet they still give mutually consistent high-confidence scores. Here internal consistency cannot stand in for an external anchor and prove the real state.

Readers can remember the core objects of this part as four boxes. State says where the system believes it currently is. Dynamics says how things change after an action. Objectives and constraints say which futures are preferred or forbidden, and the consumer says how prediction affects reality. Attacks and defenses must both land in one of these boxes. Evidence must state whether actual operation reached static inspection, mechanism-level run, closed-loop simulation, end-to-end reproduction, or a field incident. The final part assembles these evidence and control elements into a cross-domain engineering regime that operates continuously.

The visual output of a world model is especially prone to misleading intuition. A realistic future frame only means that some pixel or perceptual metric is good. It cannot show that hidden state variables, collision distances, rewards, or constraints are accurate, and an error appearing in the picture does not necessarily change the final action. Testing must observe the variables actually consumed by the planner. It must also use consumer substitution, independent anchors, or action gates as controls to confirm how the error propagates.

This part therefore always records "prediction quality" and "control consequence" side by side. The f

---

[← Back to contents](index.md)
