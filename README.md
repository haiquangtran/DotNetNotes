# .NET Notes

## ASP.NET (2 Options: MVC or Web Forms)

## MVC
- Framework (lightweight)
- Defined in System.Web.Mvc namespace and supported part of System.Web namespace.

### Model = Business Logic
- Retreive and store model state in DB
- Model Objects are part of the application that implement the logic for the apps data domain. 
- Use validation logic to enforce business rules for the classes.

### View = UI Logic
- Components that display the UI (typically from the model)
- Only displays information
- Should never perform business logic or interact with DB directly.

### Controller = Input Logic
- Handles user interaction, works with model, and reflects views to render (Handles requests, retrieves models, specifies view templates etc).
- Acts as a middleman between View and Model.
	-- Handles and responds to user input & interaction between View and Model

### Features
- DI, Url-mapping, supports REST, SEO, Mark-up, auth, testability, cahcing etc. (Look it up for more).

### Advantages
- Separation of Concerns (clean, maintainbale, testable)
- Loose Coupling/High Cohesion (separation of input logic, business logic, UI logic).
- Easy to test because of the separation (Decoupled)
- Promotoes Parrallel development (For large teams)
- Uses Front Controller Pattern (supports rich routing infrastructure)
- Doesn't use view state or server-based forms
- Good for Web apps supported by large teams who need high degree of control over app behaviour.

## Web Forms

### Advantages 
- Supports event model
	-- State over HTTP
	-- provies dozens of events etc
- Uses Page Controller Pattern that adds functionality to individual pages.
- Uses View State or Server-based forms, which can make managing state Information easier.
- Small teams + Rapid app dev
- Tightly integrated (less complex), less code

## Front Controller Pattern
- Centralized request ahndling mechanism
- Solves decentralization problem by channeling all requests through a single controller.
- Controller usually implemented in 2 parts: 
	-- A handler (handles requests such as GET, POST etc)
	-- A hierarchy of commands (executes the requests)

## Page Controller Pattern
- Controller determining and invokes the requested actions on the model, and determines the correct view to use. 
- PageController: handles HTTP requests and updates model and decides on the corresponding view. 

## IIS (Internet Information Service)
- flexible, secure, manageable Web server
- scalable, open architecture

## IIS Express
- lightweight, self-contained version of IIS optimized for developers
- To develop and test websites

## Entity Framework
- ORM
- Supports Code First (Create model objects by writing classes, can then have the DB created on the fly).
- Connection String/Web.config file (DB info)

## SQL Server Express LocalDB
- lightweight version of SQL Server Express Database Engine that starts on demand and runs in local mode.
- Work with DB's as .mdf files
- Should not be used in production (not designed to work with IIS)
- LocalDB can be migrated to SQL Server or SQL Azure

## Membership DB
- who can control who can access the application

## Code First
- Writing classes for models first, which get created in a database on the fly
- Adds table to DB to see if schema is in sync with model classes
- Code First migrations call seed method after every migration
- Ensures validation rules are enforced before saved to DB

## Database First
- As the name suggests...

## DRY (Don't Repeat Yourself)
- Specify functionality once = reflected everywhere
- Reduces code, less error prone, increase maintainability.

## CLR (Common Language Runtime)
- Requires overloaded methods to have unique parameter signature (same name, different parameters).

## TFS (Team Foundation Server)
- Contains:
	-- Source control
	-- Management tools (agile etc)
	-- CI
	-- Analytics

## .dll file (Extension)
- Dynamic Link Libraries
- Binary files containing executable code that can only be executed/loaded by an application (cannot be directly executed). 
- Like Executables (EXE) but are not directly executable.
- Are Microsoft's implementation of shared libraries. 
- Contains: functions, classes, variables, resources (images, files, icons etc), that an EXE uses or other DLL uses.
