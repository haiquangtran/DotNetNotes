# .NET Notes

## ASP.NET (2 Options: MVC or Web Forms)

## MVC
- Framework (lightweight)
- Defined in System.Web.Mvc namespace and supported part of System.Web namespace.

### Model = Business/Application Logic
- Retreive and store model state in DB
- Model Objects are part of the application that implement the logic for the apps data domain. 
- Use validation logic to enforce business rules for the classes.

### View = UI/Presentation Logic
- Components that display the UI (typically from the model)
- Only displays information
- Should never perform business logic or interact with DB directly.

### Controller = Input Logic
- Handles user interaction, works with model, and reflects views to render (Handles requests, retrieves models, specifies view templates etc).
- Acts as a middleman between View and Model.
  - Handles and responds to user input & interaction between View and Model

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
  - State over HTTP
  - provies dozens of events etc
- Uses Page Controller Pattern that adds functionality to individual pages.
- Uses View State or Server-based forms, which can make managing state Information easier.
- Small teams + Rapid app dev
- Tightly integrated (less complex), less code

## Front Controller Pattern
- Centralized request ahndling mechanism
- Solves decentralization problem by channeling all requests through a single controller.
- Controller usually implemented in 2 parts: 
  - A handler (handles requests such as GET, POST etc)
  - A hierarchy of commands (executes the requests)

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
  - Source control
  - Management tools (agile etc)
  - CI
  - Analytics

## .dll file (Extension)
- Dynamic Link Libraries
- Binary files containing executable code that can only be executed/loaded by an application (cannot be directly executed). 
- Like Executables (EXE) but are not directly executable.
- Are Microsoft's implementation of shared libraries. 
- Contains: functions, classes, variables, resources (images, files, icons etc), that an EXE uses or other DLL uses.

## ASP.NET MVC Views and UI Rendering 
- By default, the MVC framework uses custom types (ViewPage, ViewMasterPage, and ViewUserControl) that inherit from the existing ASP.NET page (.aspx), master page (.master), and user control (.ascx) types as views.

### View Pages
- Are an instance of ViewPage class.
- The ViewPage class defines a ViewData property that returns a ViewDataDictionary Object (containing the data the view should display).
- The MVC framework uses URL routing to determine which controller action to invoke, and the controller action then devices which views to render.
- The @ Page directive contains the Inherits attribute, which defines the relationship between the application and the view. (Allows you to perform actions from the application code).
- .aspx files

### Master-Page Views
- Can use master pages to define a consistent layout and structure.
- In a typical site, the master page is bound to a content page in the @ Page directive of the content page. 
- Can also use dynamic master pages (assign master page at run time) when you call the View method of the Controller class. 
- .master files

### Partial Views
- enables you to define a view that will be rendered inside a parent view
- Implemented as ASP.NET user controlers (.ascx).
- When instantiated, it has it's own copy of ViewDataDictionary object that is available to the parent view (Similar to scopes in angular). 
  - Can access the data of the parent view 
  - However, if partial view updates the data, those updates only affect the partial view's ViewData Object. (The parent view's data is not changed).

### Helper classes and Members for rendering views
- MVC framework includes the following helpers:
  - Form helpers for form elements (i.e radio buttons, list boxes, select buttons, password fields etc)
  - URL helpers which let you generate URLs for routing
  - HTML helpers, include functions to manage HTML strings, such as Encode, Decode, AttributeEncode, and RenderPartial

## Class Members in C#
- Are members of a class that represent the data and behaviour of a class
- Are members declaed in the class and all those (excluding constructors and destructors) declared in all classes in its inheritance hierachy. 
- Examples: Constants, Fields, Methods, Properties, Operators etc.

## ?? Operator (C# null-coalescing operator)
- Returns left-hand operand if the operand is not null; otherwise it returns the right hand operand
- You can also chain the operator so that you can do a bunch of null comparisons
- "If whatever is to the left is not null, use that, otherwise use what's to the right"

## Model State
- Property of a controller, and can be accessed from those classes that inherit from Mvc.Controller.
- Purpose: Store value submitted to server, and to store validation errors associated with the values. 
- ModelState represents a collection of name and value pairs that were submitted to the server during a POST
- Contains a collection of error messages for each value submitted. 
- Only has names, values, and errors. Doesn't know anything about any model classes

## AutoMapper
- Mapper between two objects. 
- External component that helps in creating a mapping between source and destination model types (Transfers the properties if they are the same, or you can use the ForMember method).
- Once mapping is created then source model object can be converted to a destination model object.
