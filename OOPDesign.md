# OOP Design

1. What does “favor object composition over class inheritance” mean?

> It means that code reuse should be achieved by assembling smaller units of functionality into new objects instead of inheriting from classes and creating object taxonomies.
> In other words, use can-do, has-a, or uses-a relationships instead of is-a relationships. Using this approach we:
> - Avoid class hierarchies.
> - Avoid brittle base class problem.
> - Avoid tight coupling.
> - Avoid rigid taxonomy (forced is-a relationships that are eventually > - wrong for new use cases).
> - Avoid the gorilla banana problem (“what you wanted was a banana, what you got was a gorilla holding the banana, and the entire jungle”).
> - Make code more flexible.