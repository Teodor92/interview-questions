# Angular

1. What are the building blocks of Angular?

> - Modules
> - Components
> - Templates
> - Directives
> - Data Binding
> - Services
> - Dependency Injection
> - Routing
> - Pipes

2. What is the difference between one-way data flow and two-way data - binding?
> Two way data binding means that UI fields are bound to model data dynamically such that when a UI field changes, the model data changes with it and vice-versa.
> One way data flow means that the model is the single source of truth.
Changes in the UI trigger messages that signal user intent to the model (or “store” in React). Only the model has the access to change the app’s state.
> The effect is that data always flows in a single direction, which makes it easier to understand.
> One way data flows are deterministic, whereas two-way binding can cause side-effects which are harder to follow and understand.

> Angular is a two-may binding framework(although one way data binding is possible with reactive forms) and React is a one-way data binding framework.

3. What is the differentiate between Components and Directives?

> Components break up the application into smaller parts; whereas, Directives add behavior to an existing DOM element.

4. What is the use of the `@Input` and `@Output` directives?

> When it comes to the communication of Angular Components, which are in Parent-Child Relationship; we use @Input in Child Component when we are passing data from Parent to Child Component and @Output is used in Child Component to receive an event from Child to Parent Component.

5. What are the Angular life-cycle hooks?
> - `ngOnChanges()` - Respond when Angular (re)sets data-bound input properties. The method receives a SimpleChanges object of current and previous property values. Called before `ngOnInit()` and whenever one or more data-bound input properties change.
> - `ngOnInit()` - Initialize the directive/component after Angular first displays the data-bound properties and sets the directive/component's input properties. Called once, after the first `ngOnChanges()`.
> - `ngDoCheck()` - Detect and act upon changes that Angular can't or won't detect on its own. Called during every change detection run, immediately after ngOnChanges() and `ngOnInit()`.
> - `ngAfterContentInit()` - Respond after Angular projects external content into the component's view / the view that a directive is in. Called once after the first `ngDoCheck()`.
> - `ngAfterContentChecked()` - Respond after Angular checks the content projected into the directive/component. Called after the ngAfterContentInit() and every subsequent `ngDoCheck()`.
> - `ngAfterViewInit()` - Respond after Angular initializes the component's views and child views / the view that a directive is in. Called once after the first `ngAfterContentChecked()`.
> - `ngAfterViewChecked()` - Respond after Angular checks the component's views and child views / the view that a directive is in. Called after the ngAfterViewInit and every subsequent `ngAfterContentChecked()`.
> - `ngOnDestroy()` - Cleanup just before Angular destroys the directive/component. Unsubscribe Observables and detach event handlers to avoid memory leaks. Called just before Angular destroys the directive/component.

6. What is ng-content Directive?
> The HTML elements like p (paragraph) or h1 (heading) have some content between the tags. For example, `<p>this is a paragraph</p>` and `<h1>this is a heading</h1>`. Now, similar to this, what if we want to have some custom text or content between the angular tags like  `<app-tax>some tax-related content</app-tax>` This will not work the way it worked for HTML elements.  Now, in such cases, the `<ng-content>` tag directive is used.

7. What is ViewEncapsulation?
> ViewEncapsulation decides whether the styles defined in a component can affect the entire application or not. There are three ways to do this in Angular:
> - `Emulated`: styles from other HTML spread to the component.
> - `Native`: styles from other HTML do not spread to the component.
> - `None`: styles defined in a component are visible to all components.

8. What are the differences between Observables and Promises?
> - Observables are lazy, which means nothing happens until a subscription is made. Whereas Promises are eager; which means as soon as a promise is created, the execution takes place.
> - Observable is a stream in which passing of zero or more events is possible and the callback is called for each event. Whereas, promise handles a single event. 
