# .NET Notes

# ASP.NET (2 Options: MVC or Web Forms)

# MVC
- Framework (lightweight)
- Defined in System.Web.Mvc namespace and supported part of System.Web namespace.

## Model = Business Logic
- Retreive and store model state in DB
- Model Objects are part of the application that implement the logic for the apps data domain. 
- Use validation logic to enforce business rules for the classes.

## View = UI Logic
- Components that display the UI (typically from the model)
- Only displays information
- Should never perform business logic or interact with DB directly.

## Controller = Input Logic
- Handles user interaction, works with model, and reflects views to render (Handles requests, retrieves models, specifies view templates etc).
- Acts as a middleman between View and Model.
	-- Handles and responds to user input & interaction between View and Model

## Features
- DI, Url-mapping, supports REST, SEO, Mark-up, auth, testability, cahcing etc. (Look it up for more).

## Advantages
- Separation of Concerns (clean, maintainbale, testable)
- Loose Coupling/High Cohesion (separation of input logic, business logic, UI logic).
- Easy to test because of the separation (Decoupled)
- Promotoes Parrallel development (For large teams)
- Uses Front Controller Pattern (supports rich routing infrastructure)
- Doesn't use view state or server-based forms
- Good for Web apps supported by large teams who need high degree of control over app behaviour.

# Web Forms