# Angular

## 1. What are the building blocks of Angular?

> - Modules
> - Components
> - Templates
> - Directives
> - Data Binding
> - Services
> - Dependency Injection
> - Routing
> - Pipes

## 2. What is the difference between one-way data flow and two-way data - binding?

> Two way data binding means that UI fields are bound to model data dynamically such that when a UI field changes, the model data changes with it and vice-versa.
> One way data flow means that the model is the single source of truth.
Changes in the UI trigger messages that signal user intent to the model (or “store” in React). Only the model has the access to change the app’s state.
> The effect is that data always flows in a single direction, which makes it easier to understand.
> One way data flows are deterministic, whereas two-way binding can cause side-effects which are harder to follow and understand.
> Angular is a two-may binding framework(although one way data binding is possible with reactive forms) and React is a one-way data binding framework.

## 3. What is the differentiate between Components and Directives?

> Components break up the application into smaller parts; whereas, Directives add behavior to an existing DOM element.

## 4. What is the use of the `@Input` and `@Output` directives?

> When it comes to the communication of Angular Components, which are in Parent-Child Relationship; we use @Input in Child Component when we are passing data from Parent to Child Component.
> @Output is used in Child Component to receive an event from Child to Parent Component.

## 5. What are the Angular life-cycle hooks?

> - `ngOnChanges()` - Respond when Angular (re)sets data-bound input properties. The method receives a SimpleChanges object of current and previous property values.
> Called before `ngOnInit()` and whenever one or more data-bound input properties change.
> - `ngOnInit()` - Initialize the directive/component after Angular first displays the data-bound properties and sets the directive/component's input properties. Called once, after the first `ngOnChanges()`.
> - `ngDoCheck()` - Detect and act upon changes that Angular can't or won't detect on its own. Called during every change detection run, immediately after ngOnChanges() and `ngOnInit()`.
> - `ngAfterContentInit()` - Respond after Angular projects external content into the component's view / the view that a directive is in. Called once after the first `ngDoCheck()`.
> - `ngAfterContentChecked()` - Respond after Angular checks the content projected into the directive/component. Called after the ngAfterContentInit() and every subsequent `ngDoCheck()`.
> - `ngAfterViewInit()` - Respond after Angular initializes the component's views and child views / the view that a directive is in. Called once after the first `ngAfterContentChecked()`.
> - `ngAfterViewChecked()` - Respond after Angular checks the component's views and child views / the view that a directive is in. Called after the ngAfterViewInit and every subsequent `ngAfterContentChecked()`.
> - `ngOnDestroy()` - Cleanup just before Angular destroys the directive/component. Unsubscribe Observables and detach event handlers to avoid memory leaks. Called just before Angular destroys the directive/component.

## 6. What is ng-content Directive?

> The HTML elements like p (paragraph) or h1 (heading) have some content between the tags. For example, `<p>this is a paragraph</p>` and `<h1>this is a heading</h1>`.
> Now, similar to this, what if we want to have some custom text or content between the angular tags like  `<app-tax>some tax-related content</app-tax>` This will not work the way it worked for HTML elements.
> Now, in such cases, the `<ng-content>` tag directive is used.

## 7. What is ViewEncapsulation?

> ViewEncapsulation decides whether the styles defined in a component can affect the entire application or not. There are three ways to do this in Angular:
> - `Emulated`: styles from other HTML spread to the component.
> - `Native`: styles from other HTML do not spread to the component.
> - `None`: styles defined in a component are visible to all components.

## 8. What are the differences between Observables and Promises?

> - Observables are lazy, which means nothing happens until a subscription is made. Whereas Promises are eager; which means as soon as a promise is created, the execution takes place.
> - Observable is a stream in which passing of zero or more events is possible and the callback is called for each event. Whereas, promise handles a single event.

## 9. Why do you like Angular?

> - This is a very subjective one and there is no right answer to this :)

## 10. What does this line do?

```typescript
@HostBinding('class.valid') isValid;
```

> Binds a host element property (here, the CSS class valid) to a directive/component property (isValid).

## 11. What is the difference between a smart/container/parent component and dumb/presentational/pure component? What is a good use case example? What are the advantages?

> A Dumb Component is a component that works like a pure function.
(A pure function is a function that for given function arguments, will always produce the same return value.)
A Dumb Component is just like that. It is a component that for received data (inputs), will always look and behave the same, possibly also producing other data (events, via outputs).

> A Smart Component is a component that is more like an impure function.
(An impure function is a function that touches “the outer world”: either by obtaining data from external services or by producing side effects.)
A Smart Component is just like that. It is not only dependant on its’ inputs, but also on some kind of external data (“the outer world”), which is not passed directly via `@Input()`.
It might also produce some side effects that are not emitted through the `@Output()` interface.
For example, a component which gets current user data from a singleton service instantiated elsewhere; from an external API; or from LocalStorage. A component that changes the state of an external service;
issues an API call; or changes the stored data in LocalStorage.

> See [here](https://medium.com/@jtomaszewski/how-to-write-good-composable-and-pure-components-in-angular-2-1756945c0f5b) for more details.

## 12. How do components communicate with each other?

> Types of communication:
> - Parent/child communication using @Input decorator and @Output decorator with EventEmitter.
> - Communication using services and Angular dependency injection system.
> - Communication via store (redux) which also uses Angular DI.

## 12. What is the difference between an observable and a promise?

> A Promise handles a single event when an async operation completes or fails.
Note: There are Promise libraries out there that support cancellation, but ES6 Promise doesn't so far.

> An Observable is like a Stream (in many languages) and allows to pass zero or more events where the callback is called for each event.
Often Observable is preferred over Promise because it provides the features of Promise and more. With Observable it doesn't matter if you want to handle 0, 1, or multiple events.
You can utilize the same API in each case.
>
> - Observable also has the advantage over Promise to be cancelable.
> If the result of an HTTP request to a server or some other expensive async operation isn't needed anymore, the Subscription of an Observable allows to cancel the subscription.
> A Promise will eventually call the success or failed callback even when you don't need the notification or the result it provides anymore.
> - Observable provides operators like map, forEach, reduce, ... similar to an array
> - There are also powerful operators like retry(), or replay(), ... that are often quite handy.

## 13. What is virtual DOM?

> Virtual DOM is about avoiding unnecessary changes to the DOM, which are expensive performance-wise, because changes to the DOM usually cause re-rendering of the page. Virtual DOM also allows to collect several changes to be applied at once, so not every single change causes a re-render, but instead re-rendering only happens once after a set of changes was applied to the DOM.

## 14. What is Shadow DOM?

> Shadow dom is mostly about encapsulation of the implementation.
> A single custom element can implement more-or-less complex logic combined with more-or-less complex DOM. An entire web application of arbitrary complexity can be added to a page by an import and `<my-app></my-app>` but also simpler reusable and composable components can be implemented as custom elements where the internal representation is hidden in the shadow DOM like `<date-picker></date-picker>`.

> Style encapsulation Shadow DOM is also about preventing styles being applied accidentally to elements the designer didn't intend to, for example because the CSS or components library you are using changed a selector that now applies to other elements that use the same CSS class names. Styles added to components are scoped to that component and bleeding out or in of styles is prevented.

## 15. What is Reactive Programming?

> Reactive programming is programming with asynchronous data streams.
