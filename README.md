# FullStackInterviewMaterial
Full stack interview materials

## Angular key notes
# Angular Concepts Revision



## Module

- **Definition:** A module groups components, services, pipes, and directives.

- **Command:** `ng g module student`

- **Default Arrays in Module:**

  - **Declarations:** Register components, directives, and pipes.

  - **Imports:** Import other modules.

  - **Providers:** Register services.

  - **Bootstrap:** Defines the root component to bootstrap.



## Decorator

- **Definition:** Metadata added to classes, properties, methods, or parameters for additional functionality.

- **Examples:** @Component, @Input, @Output



## Component

- **Definition:** A fundamental unit with a template, TypeScript class, and CSS.

- **Data Binding:** Connects component data with view.

  - **Interpolation:** `{{title}}`

  - **Property Binding:** `[innerHTML] = 'FirstName'`

  - **Attribute Binding:** `[attr.colspan] = 'value'`

  - **Class Binding:** `[class.some-class] = 'condition'`

  - **Style Binding:** `[style.font-weight] = "isBold ? 'bold' : 'normal'"`



## Data Binding Types

- **Interpolation:** Display component properties in HTML ({{property}}).

- **Property Binding:** Bind component properties to HTML attributes ([property] = 'value').

- **Attribute Binding:** Set attributes in HTML ([attr.attribute] = 'value').

- **Class Binding:** Add or remove classes ([class.class-name] = 'condition').

- **Style Binding:** Set styles dynamically ([style.property] = 'value').

- **Two-Way Binding:** Use [(ngModel)] for bidirectional data binding; import FormsModule from @angular/forms.



## Directives

- **Definition:** Modify the behavior, appearance, or layout of DOM elements.

- **Types:**

  - **Structural Directives:** Change DOM structure (*ngFor, *ngIf, *ngSwitch).

  - **Attribute Directives:** Modify behavior (NgStyle, NgClass).



## Pipe

- **Definition:** Transforms raw data into a desired format.

- **Example:** `{{student.ID | uppercase}}`



## Routing

- **Definition:** Mechanism for navigating between pages and displaying components.

- **Example Link:** `<a [routerLink]="['/studentLink']">Student</a>`

- **Route Configuration:** `path: 'studentLink', component: StudentComponent`



## Services

- **Definition:** Code or logic used to perform specific tasks, injected via dependency injection.

- **Command:** `ng g s serviceName`



## Dependency Injection (DI)

- **Definition:** A design pattern where classes receive dependencies from external sources instead of creating them internally.



## Forms

- **Types:**

  - **Template-Driven Forms**

  - **Reactive Forms**


## Other materials:
## .NET Core
https://github.com/StefanTheCode/dotnet_interview_questions

## Angular
https://github.com/sudheerj/angular-interview-questions
