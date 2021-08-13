# Code Quality - Practices and Metrics

## 1. What is cyclomatic/McCabe complexity?

Cyclomatic complexity measures the number of times you must execute a block of code with varying parameters in order to execute every path through that block. A higher count is bad because it increases the chances for logical errors escaping your testing strategy.

## 2. What are some examples of anti-patterns?

> [https://sourcemaking.com/antipatterns/software-development-antipatterns](https://sourcemaking.com/antipatterns/software-development-antipatterns)

## 3. Who are the Gang of Four? Why should you care?

[https://en.wikipedia.org/wiki/Design_Patterns](https://en.wikipedia.org/wiki/Design_Patterns)

## 4. You have just been put in charge of a legacy code project with maintainability problems. What kind of things would you look to improve to get the project on a stable footing?

## 5. Explain the concept of convention over configuration, and talk about an example of convention over configuration you have seen in the wild.

## 6. What is an idempotent operation?

> In computing, an idempotent operation is one that has no additional effect if it is called more than once with the same input parameters.

> Bonus: Which HTTP Verbs are idempotent? What is a safe http verb? Which are safe?

## 7. What is the differences between Mocks and Stubs/Fakes and where you might use them?

## 8. What is Continuos Integration? And what about Continuos Deployment? And Continuos Delivery?

## 9. What is meant by a sandbox, why you would use one, and identify examples of sandboxes in the wild?

## 10. What Source Control systems have you worked with?

## 11. Describe a software development life cycle.

## 12. How do you react to people criticizing your code/documents?

## 13. Explain the differences between stateless and stateful systems, and impacts of state on parallelism.

## 14. Discuss the concept of YAGNI and explain something you did recently that adhered to this practice.

## 15. What is Refactoring ? Have you used it and it is important? Name three common refactorings.

## 16. What value do daily builds, automated testing, and peer reviews add to a project? What disadvantages are there?

## 17. When do you know your code is ready for production?

## 18. What is TDD? And what about BDD?

## 19. What is logging and why do we use it?

## 20. How would you decide if a library should be included in the project or not?

There are multiple of criteria for adding an additional library to a project:
- Do we need it? Are just using a single function from a huge library?
- Does the functionality already exist in the language?
- How big is it?
- Is the library supported or is it a dead library?
