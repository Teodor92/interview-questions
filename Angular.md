# Angular

- What is the difference between one-way data flow and two-way data - binding?
> Two way data binding means that UI fields are bound to model data dynamically such that when a UI field changes, the model data changes with it and vice-versa.
> One way data flow means that the model is the single source of truth.
Changes in the UI trigger messages that signal user intent to the model (or “store” in React). Only the model has the access to change the app’s state.
> The effect is that data always flows in a single direction, which makes it easier to understand.
> One way data flows are deterministic, whereas two-way binding can cause side-effects which are harder to follow and understand.

> Angular is a two-may binding framework(although one way data binding is possible with reactive forms) and React is a one-way data binding framework.