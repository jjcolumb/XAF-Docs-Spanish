[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers#readme)
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/blob/main/README.es.md)
# XAF Considerations for Newcomers

  
XAF is a powerhouse – a software development framework unlike any other. If you are new to XAF and considering it for an upcoming project, be sure to review our product webpage and introductory help materials for a summary of its benefits and productivity features for small and large development teams alike.

[FREE 30-DAY TRIAL](https://go.devexpress.com/devexpressdownload_universaltrial.aspx)
[ROADMAP](https://www.devexpress.com/go/XAF_Roadmap.aspx)

This knowledge base article documents some of XAF's capabilities, and more importantly, describes the experience/knowledge level required to maximize its potential. Like any other advanced development framework, XAF has a learning curve and is best suited for experienced developers who wish to prototype and deliver CRUD-based apps in the most efficient manner possible.

## The Basics

The eXpressApp Framework (XAF) uses a  [hybrid software development flow](https://docs.devexpress.com/eXpressAppFramework/112558/fundamentals/xaf-overview)  - a flow that lies somewhere between a traditional 'all manual' development methodology and a totally 'codeless' approach. Despite all its strengths and advantages, XAF is not the best option for everyone. Those who desire a codeless development framework may discover that at some point in the development process, XAF requires developers to write code.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/4bbab983-7d25-47ce-b30e-c51c421b2616)


This article will define XAF's development flow in clear terms so you do not invest resources into an XAF-based project only to discover (at a later stage) that XAF still requires you to manually code portions of your XAF-powered app. In addition, this article will help clarify the following XAF-related development topics:

-   Tips and prerequisites for XAF developers;
-   XAF versus alternatives;
-   XAF's scope and its limits.

## XAF's Target Audience

XAF was built for software developers who want to maximize productivity. This may sound like a cliché, but once you use eXpressApp Framework (XAF) for a few weeks, you'll discover that this statement is indeed true.

Before I dig deeper, let me stress that XAF is not a tool for non-programmers or beginners. XAF is a general-purpose application framework designed for  **.NET developers**  with experience in line-of-business app development. Based on internal statistics, we know that development teams prefer XAF much more than one-person-shops. So, if you are part of an experienced team, you are likely to benefit most from XAF's capabilities.

These features are favorites among XAF developers:

-   Automatic database and CRUD UI generation for Windows, Web and Mobile platforms including support for over a dozen RDBMS with EF Core and XPO ORM libraries.
-   Rich runtime UI customization for both developers and end-users. Your apps can address changing business requirements without the need for redeployment.
-   Common business essentials like reporting, information security, validation, data visualization and analytics are available out-of-the-box. These modules are fully configurable.
-   .NET business logic and UI configuration code are shared across platforms and databases.
-   With XAF, developers can stay focused on business rules, rather than on low-level coding such as database and UI management.

Here's how Martin Praxmarer of PraKom Software GmbH described XAF's primary benefits:

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/217deb47-b80c-4424-842d-95c5bdb0f84f)


## Martin Praxmarer

### PraKom Software GmbH

XAF has helped us deliver a highly flexible and stable product. XAF allows us to quickly deliver new functionality with a relatively small team. We started with one developer and now have 8 developers working on our XAF-based software.

## Prerequisites

Though XAF's architecture helps developers save significant development time, the framework itself does not police every single aspect of the software development process. You are still required to follow well-established development, testing, deployment and maintenance procedures. Unfortunately, knowledge of Visual Studio, .NET, database management and general programming know-how is not optional. Those who benefit most from XAF have experience in some or all of the following:

-   Ability to use correct C#, VB.NET, SQL, JavaScript, HTML, CSS, XML, JSON syntax.
-   Ability to write classes, members, interfaces, LINQ and SQL queries, handle events.
-   Ability to create Class Libraries and organize project structure and builds, edit configuration files.
-   Ability to use standard Visual Studio features and commands within the code editor, Solution Explorer, Toolbox, etc. (Go To Definition, Find and Replace, add and remove assembly references or NuGet packages, etc.).
-   Ability to resolve compilation and associated errors in Visual Studio using Microsoft documentation or StackOverFlow.
-   Ability to catch and  [debug .NET and JavaScript exceptions](https://docs.devexpress.com/eXpressAppFramework/112572/concepts/debugging-testing-and-error-handling).
-   Ability to monitor, diagnose and mitigate possible  [security](https://github.com/DevExpress/aspnet-security-bestpractices/tree/master/SecurityBestPractices.WebForms)  and  [performance](https://www.devexpress.com/support/center/question/details/t148978/how-to-measure-and-improve-the-application-s-performance)  issues as app complexity,  [database](https://www.devexpress.com/support/center/question/details/t572322/)  size and user load grows.
-   Ability to deploy apps, configure and maintain appropriate development and production environments/associated hardware and software (for instance, web servers, databases, firewall settings).
-   Ability to manage third-party software and service licenses and the like.

  
Of course, those that succeed with XAF are also willing to:

-   Follow best practices for XAF, XPO, Microsoft and DevExpress components.
-   Follow best practices for underlying technologies (.NET, WinForms, ASP.NET WebForms, ASP.NET Core, WCF, SQL Server, IIS, etc).

If you have not built line-of-business apps for desktop and web platforms in the past, or if you are new to .NET and Visual Studio, then it would be best to begin your journey with a different product. XAF cannot replace practical experience. In real-terms, developers who are familiar with object-relational mapping (ORM) libraries (for instance, Hibernate with Java) and the Mode-View-Controller (MVC) UI design pattern (or have developed in-house scaffolding frameworks in the past) reach proficiency with XAF quite quickly (even if they are unfamiliar with.NET itself).

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/2e0b9a00-8311-488f-8213-0b3df7fbf0da)


## Sven Stening

### PSSP GmbH

I believe the real power of XAF is your special way of handling the MVC pattern. Adding a property to a Business Object - no matter if doing it in code or with the Application Model Editor - all possible types of views can show the new values: Detail View, List View, Reports, Statistics, etc. This is really stunning and flabbergasts me every time I see it. You've really done a great job. To be honest I've developed something very similar in the past and used it now for a long time for my projects. But XAF is much more powerful and easier to use. Not to mention your great UI components.

## Product Scope and Real-World Expectations

XAF produces standard .NET WinForms, ASP.NET WebForms or ASP.NET Core Blazor apps. These apps are not different from other types of apps built for these platforms. To use XAF, you have to be familiar with these platforms and related technologies at an intermediate level.

You should think of XAF as an extendable general-purpose framework with a finite set of solutions for a variety of usage scenarios (of course, some usage scenarios have not been considered and have not been implemented). You should not expect that XAF will wrap each DevExpress UI control and its features, or cover every developer need on supported platforms. Unavailable functionality requires you to write code. Though we continually extend XAF based on user feedback and business use requirements, if something is missing from XAF, you may be forced to implement it yourself.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/4f7f3988-947f-4599-b030-a7d8c733bb67)


## Muhamad Nafis

After using XAF for five years, I can't even think of building a complex application without it anymore. It's a very powerful and customizable business app framework built upon the best components on the market. One of the best things is the fantastic support team. Every time I think that something can't be done, they clearly explain how to accomplish what I need. So thanks again to everyone involved. From developers to sales and support, you've made me more productive while making my job easier. There's no better outcome than that!

## Application Migration to XAF

Based on your existing application design and architecture, you should consider at least the following migration aspects.

### Data Store

XAF .NET apps can work directly with a dozen popular database engines. If you have existing databases, you can reuse data in most instances. You may want to make minimal database schema modifications based on XAF-specific features you expect to use within your app (for instance, add columns for optimistic locking). XAF's UI also allows you to display and edit data records that are not connected to database tables:  [Non-Persistent Objects](https://docs.devexpress.com/eXpressAppFramework/116516/concepts/business-model-design/non-persistent-objects).

### ORM Data Model

If you have existing XPO or Entity Framework data model classes, half of the work is already done - you can reuse these data models within XAF as is (or with minor modifications). If you do not have a ready-to-use ORM data model, you can generate it automatically via  [XPO ORM](https://docs.devexpress.com/eXpressAppFramework/113451/task-based-help/business-model-design/express-persistent-objects-xpo/how-to-generate-xpo-business-classes-for-existing-data-tables)  or  [Entity Framework](https://docs.microsoft.com/en-us/ef/core/managing-schemas/scaffolding?tabs=dotnet-core-cli)  wizards (by reverse-engineering database schema).

Data from stored procedures (SP) or external services can be visualized and managed within XAF CRUD forms through the use of Non-Persistent Objects. You can also map your data model to database views – an option often used by those who must support legacy systems.

### Business Logic

XAF relies on ORM methodologies. In most instances, you can manipulate data through object-oriented development paradigms: query and edit ORM objects vs database objects (tables, rows, columns using raw SQL). If you cannot use ORM methodologies, you can still execute stored procedures, call external services or do other things common to regular .NET apps.

Note that non-ORM scenarios should not dominate your application (doing so will prevent you from maximizing XAF's potential). If most of your business logic is handled through legacy SP or RPC, you will ultimately want to rewrite this logic using ORM methodologies.

### UI Construction

XAF automatically generates  [CRUD and auxiliary UI forms](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction)  based on ORM data model structures and associated metadata. For instance, default list and detail  [form editors](https://docs.devexpress.com/eXpressAppFramework/113014/concepts/business-model-design/data-types-supported-by-built-in-editors)  are created based on class property types and attributes). You can customize this UI to address multiple usage scenarios.

If it will take too much time to rewrite an existing UI with XAF, you can reuse your custom user controls and forms within your XAF application. For instance, you can display a standalone non-XAF form from a navigation menu or display a custom (or third-party user control) in an existing XAF form.

For more information, see  [UI customization tips](https://www.devexpress.com/products/net/application_framework/xaf-considerations-for-newcomers.xml#ui-customization-categories)  and  [How to use a custom control that is not integrated by default](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default).

### Reusable Modules

XAF is designed with a modular architecture and includes dozens of XAF components that can be reused in non-XAF apps. For instance, you can reuse XAF's ORM data model, business logic,  [Security System](https://www.devexpress.com/products/net/application_framework/security.xml), localization, audit trail, validation, and other XAF modules in non-XAF forms within your existing app.  [Learn more about Reusable Modules](https://supportcenter.devexpress.com/internal/ticket/details/q94961)

This can be your first step if you are not ready to go "all in" with XAF or just want to explore XAF migration options iteratively (certain ORM data model classes and modules) while retaining the core of your legacy .NET app.

## UI Customization Categories by Skill Level

When you customize XAF's default UI, data access code, or database layer, please consider the following three task categories as they vary by knowledge/experience level.

### Category #1 (Intermediate): Customization of Built-in XAF Features and API

These are usually low code tasks that are completed in a platform-agnostic module declaratively (with attributes) or visually (with designers). Examples:

-   Localize business classes and/or modify View settings in the  [Model Editor](https://docs.devexpress.com/eXpressAppFramework/112582/concepts/application-model/model-editor);
-   Use and configure additional modules via the  [Solution Wizard, Module or Application Designers](https://docs.devexpress.com/eXpressAppFramework/112827/design-time-features/application-designer)  or in code;
-   Use ready-to-use code attributes and other XAF API such as ListView, ViewController, ASPxGridListEditor.

Most XAF users acquire the necessary knowledge to complete these tasks as they navigate our  [Getting Started](https://docs.devexpress.com/eXpressAppFramework/113577/getting-started)  tutorials ([Application Solution Components](https://docs.devexpress.com/eXpressAppFramework/112569/concepts/application-solution-components),  [Business Model Design](https://docs.devexpress.com/eXpressAppFramework/113461/concepts/business-model-design),  [Application Model](https://docs.devexpress.com/eXpressAppFramework/112579/concepts/application-model),  [Data Manipulation and Business Logic](https://docs.devexpress.com/eXpressAppFramework/113708/concepts/data-manipulation-and-business-logic)  among other fundamental XAF-related development concepts). It is critical to explore these topics because no single task can be accomplished without this basic foundation.

### Example

XAF's MainDemo app consists of multiple built-in modules like security, reporting, validation, data audit, etc. XAF developers can either use wizards/designers, drag and drop pre-made XAF components from Visual Studio Toolbox, or manually write a couple of lines of code:

-   C#

```csharp
this.securityStrategyComplex1.Authentication = this.authenticationStandard1;
this.securityStrategyComplex1.RoleType = typeof(PermissionPolicyRole);
this.securityStrategyComplex1.UserType = typeof(PermissionPolicyUser);
this.authenticationStandard1.LogonParametersType = typeof(DevExpress.ExpressApp.Security.AuthenticationStandardLogonParameters);
this.authenticationStandard1.UserType = typeof(PermissionPolicyUser);
this.Security = this.securityStrategyComplex1;
this.Modules.Add(this.securityModule1);
this.Modules.Add(this.reportsModuleV21);
this.Modules.Add(this.validationModule1);
this.Modules.Add(this.auditTrailModule1);

```

This code automatically does the following for XAF developers:

-   Adds Reports, Users, Roles and other navigation and main menu items automatically, so that application users can view and modify data in CRUD list and detail forms.  [Documentation](https://docs.devexpress.com/eXpressAppFramework/113198/concepts/system-module/navigation-system?p=netframework)
-   Adds a logon form with user and password fields, creates required security tables in the database and allows app users to configure users, roles, and permissions at runtime.  [Documentation](https://docs.devexpress.com/eXpressAppFramework/113366/concepts/security-system)
-   Integrates the report preview and runtime designer functions for all supported platforms and also stores report definitions in the database.  [Documentation](https://docs.devexpress.com/eXpressAppFramework/113591/concepts/extra-modules/reports-v2/reports-v2-module-overview)
-   Highlights required editors, does not allow users to enter null or invalid data. Allows users to add, remove and modify built-in or custom validation rules visually or declaratively via attributes.  [Documentation](https://docs.devexpress.com/eXpressAppFramework/113008/concepts/extra-modules/validation/validation-rules)
-   Adds change history for required data tables - every data modification is associated with an application user for the optimum safety.  [Documentation](https://docs.devexpress.com/eXpressAppFramework/112782/concepts/extra-modules/audit-trail-module)

With these few lines of code, XAF developers can build the foundations of a CRM or ERP app (desktop or web) in  **hours instead of months**.

Here is a testimonial from David Desiderà, Solution Architect at  [SpecTec](https://www.spectec.net/). David successfully integrated XAF's security system APIs with a legacy WinForms app:

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/e4ff578f-f78c-4eb9-b570-b68bdc624816)


## David Desiderà

More than one year ago I explained to my collaborators that - in my opinion - it was possible to integrate XAF's security layer with UI interface into an existing WinForms enterprise application that was 10 years old. We successfully implemented it! It took 40 man-days of job in total instead of at least 400 if I had decided to start from scratch. You guys saved my life!

### Category #2 (Advanced): Customization of Underlying non-XAF Components

This task category relates to DevExpress components wrapped by  [XAF UI elements](https://docs.devexpress.com/eXpressAppFramework/112607/concepts/ui-construction/ui-element-overview)  or non-visual XAF abstractions. In 99% of cases, standard solutions for non-XAF components apply (XAF specificities are very rare). Examples:

-   Customize the grid control to enable a feature not exposed in the Application Model, GridListEditor or ListView APIs.
-   Modify default form templates and offer different menu positions and appearance.
-   Highlight table cells conditionally within a report detail band or dashboard view item.

To access these non-XAF components inside an XAF app (across supported platforms), it is important to understand  [how XAF scaffolds the UI](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction)  (its MVC architecture) and its data layer. Developers who understand where to draw the line between XAF and non-XAF components can address customization requirements much faster. They can find answers in existing learning materials for non-XAF components or contact non-XAF component support.

### Example

XAF developers may want to customize grid control options in default XAF list forms. These options are not available in the Model Editor or in XAF's default API, because they are rarely used. A typical solution is to write a ViewController that injects required customization logic once XAF's ListView controls are created. Below is an example of a custom controller:

-   C#

```csharp
using System.Drawing;
using DevExpress.ExpressApp.Win.Editors;
using DevExpress.XtraGrid.Views.Grid;

//...

private void WinAlternatingRowsController_ViewControlsCreated(object sender, EventArgs e) {
    GridListEditor listEditor = ((ListView)View).Editor as GridListEditor;
    if (listEditor != null) {
        GridView gridView = listEditor.GridView;
        gridView.OptionsView.EnableAppearanceOddRow = true;
        gridView.Appearance.OddRow.BackColor = Color.FromArgb(244, 244, 244);
    }
}

```

To write this code, XAF developers need to know the following:

-   The fundamentals of XAF UI elements (ListView or ListEditor) and ways to access underlying DevExpress UI controls for WinForms or WebForms.
-   Recommended customization methodologies for Microsoft WinForms and WebForms platforms.
-   The API of underlying DevExpress UI controls like  [WinForms Data Grid Control](https://www.devexpress.com/products/net/controls/winforms/grid/).

XAF has an amazingly high ceiling. The following testimonial from of  [CTL Computertechnik Lang](https://www.ctl.de/)  speaks to its potential in the hands of the right team.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/8c72b638-89fb-4471-904c-7b2781b1a9f2)


## Michael Lang

### CTL Computertechnik Lang

After understanding the MVC developing method of DevExpress XAF, we learned to use it and experienced, that almost anything is easier to do with it, but it is really different from all other usual methods. We love it.

To learn more about Michael and his team – why he chose XAF and XPO for his WinForms project - and the difficulties he encountered, please review the following DevExpress Case Study:  [CTL Computertechnik Lang: XAF and WinForms Controls](https://www.devexpress.com/aboutus/testimonials/ctl/).

### Category #3 (Advanced+): Custom Control Integration and Component Implementation

Over the years, we have learned that many XAF developers wish to integrate DevExpress, Microsoft or  [third-party controls within XAF's UI](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default). We have also learned that many developers wish to implement custom UI components, app modules, and functionality unavailable by default. Examples:

-   Create a custom List Editor based on a gallery widget for ListView records.
-   Create a custom Property Editor based on a token box to view and edit collection properties in DetailView.
-   Create a custom Action control based on two date pickers in the main menu.

These tasks are often done at a lower framework level and require more knowledge and experience with XAF (when compared to Category #1 and #2). This is the same knowledge required if you were to code an app without our framework. XAF-related benefits and time savings are minimal for those who want to integrate custom controls. As a rule of thumb, know how to solve and optionally implement your requirement in a non-XAF app first. XAF integration will be much easier as a result.

### Example: VenDoc by PraKom Software GmbH

VenDoc is an ERP software solution built by Martin Praxmarer of  [PraKom Software GmbH](https://prakom.net/). The app addresses the business needs of over 750 companies in both the DACH and South Tyrol regions of Europe. This application has many custom components or fully custom non-XAF forms.

The screenshot below displays a panel on the right that was built using a custom template and controls.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/edf3d4fb-9dbe-4ebf-8d93-deed0c1204e2)


[PraKom Software GmbH Case Study: XAF and WinForms Controls](https://www.devexpress.com/aboutus/testimonials/prakom/)

### Example: Autodesk Forge Integration by Bahalddin Elsayed

Please review an interesting screenshot from Bahalddin Elsayed, an experienced and longtime XAF user from Dubai. His XAF-powered WinForms app integrates Autodesk Forge. This is a perfect example of what's possible with XAF's extensive UI customization and extensibility options. To maximize XAF's potential, Bahalddin and his team reviewed XAF's source code and extended its capabilities as needed.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/0c66c446-0bca-4631-9bde-3e2f9f9f3836)


[UI Construction](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction)  |  [Using a Custom Control that is not Integrated by Default](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default)

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/6c834699-a335-4435-9a66-660ee0b3957e)



## Santiago Moscoso

I have become a UI superhero mainly by the powerful XtraGrid features, users are fascinated of how easy it is to filter, group, add summaries, move columns around, and XAF makes it easy to get columns from related objects which has saved a lot of time on the creation of custom views, every user can create their custom views, and that makes them feel smart.

## Advanced UI Customization Tips

The following tips will help you implement tasks from categories #2 and #3:

### Obtain Experience within the Target Platform

-   Research WinForms, ASP.NET WebForms, ASP.NET Core, HTML/JavaScript/CSS and related technologies like XPO, SQL Server, WCF, OData, Web API, etc.
-   Understand the differences between a “fat” desktop client and a client-server Web or a client-side mobile app (through the underlying UI framework, architecture, application life cycle, visual controls, programming languages, etc.).
-   Search public community resources for possible solutions and development concepts.

### Familiarize Yourself with Underlying non-XAF Components

-   Note that XAF uses DevExpress WinForms, ASP.NET WebForms, ASP.NET Core Blazor, DevExtreme components for each corresponding platform
-   Research standard solutions for non-XAF components within DevExpress documentation, demos, code examples, and knowledge base articles. Feel free to use  [our search engine](https://search.devexpress.com/)  or Google. You have a higher chance to locate solutions in the component section of the DevExpress help system/docs than within XAF learning materials (that only describe XAF-related concepts).
-   If your case is not covered by DevExpress component learning materials, submit questions to the corresponding DevExpress Support Team.

### Study XAF's UI Infrastructure and Elements that Wrap Underlying Components

-   Check community extensions to see if someone has already completed an XAF integration for you.
-   Research XAF integration using the online documentation at  [UI Construction](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction)  |  [Using a Custom Control that is not Integrated by Default](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default),  [Task-Based Help](https://docs.devexpress.com/eXpressAppFramework/112682/task-based-help)  (in particular, search for "Control") as well as knowledge base examples (for instance:  [Ways to Access UI Elements and Their Controls](https://docs.devexpress.com/eXpressAppFramework/120092/concepts/ui-construction/ways-to-access-ui-elements-and-their-controls)).
-   Always remember that XAF creates visual controls dynamically in code (at runtime, not in the form designer).
-   Research the  [source code](https://supportcenter.devexpress.com/Ticket/Details/ka18677/where-can-i-get-demo-source-code-folder-installed-assemblies-or-source-code-on-machines)  for built-in XAF UI elements in the following folders:
    
    ...\DevExpress.ExpressApp.Wxx\Editors\  
    ...\DevExpress.ExpressApp.Wxx\Templates\  
    ...\DevExpress.ExpressApp.Wxx\Layout\
    
    These real-world examples will help you better understand how things work under the hood and to quickly master best patterns and practices.
    
-   Compare your custom implementation with standard XAF implementations to detect errors.  [Read the blog post](https://dennisgaravsky.blogspot.com/2018/02/learning-through-reading-source-code.html)
-   Debug DevExpress component or XAF source code when you encounter issues.  [Read the documentation](https://docs.devexpress.com/GeneralInformation/403656/support-debug-troubleshooting/debug-controls-with-debug-symbols)
-   Use our search engine or Google to locate information. You can search against API name, topmost methods in the error call stack, keywords describing a feature or task.

## Technical Support Scope

We make a few assumptions in regards to our learning materials and support services. We want to clarify these assumptions so as not to cause confusion or to frustrate your development efforts.

Our support service goals are:

-   Help customers learn our products more quickly.
-   Resolve technical issues associated with shipping features.
-   Improve our knowledge base.

Custom programming and consulting services are outside the scope of our services. Examples of custom programming and consulting include: creating customized components upon request (for instance, an XAF Property Editor or Action Container); debugging or profiling an entire customer project or database.

We do not offer support for general programming issues that are unrelated to DevExpress products. For instance, if you wish to discuss Entity Framework class library design or ASP.NET Core best practices, you should refer to public community resources like StackOverflow, CodeProject, or contact experienced  [third-party consultants](https://www.devexpress.com/products/net/application_framework/#community)  to assist you with general programming issues.

Advanced, rare, or extremely specific tasks are often complex and always resource intensive. We may not have the appropriate background knowledge and may not be able to provide guidance and examples. We are more than happy to go the extra mile to try and get to the bottom of each complex issue. Your help will ensure that this is done expeditiously. The following highly-rated help topics can be of use when troubleshooting issues:

-   [How do I ask a good question?](https://stackoverflow.com/help/how-to-ask)
-   [How to create a Minimal, Complete, and Verifiable example?](https://stackoverflow.com/help/mcve)
-   [How to Report Bugs Effectively?](https://www.chiark.greenend.org.uk/~sgtatham/bugs.html)
-   [A request for simple example programs](https://community.devexpress.com/blogs/ctodx/archive/2009/01/08/a-request-for-simple-example-programs.aspx)
-   [Collect and Analyze the Diagnostic Information](https://docs.devexpress.com/eXpressAppFramework/117344/concepts/debugging-testing-and-error-handling/collect-and-analyze-the-diagnostic-information)

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/05786fa4-ad02-4d2f-bb13-37e6e1bd4f5a)


## Paul Jacoby

### Iatric Systems, Inc.

My company recently decided to do more development using the DevExpress XAF/XPO framework. We have worked with DevExpress controls for many other business needs to ease the burden on developing in .NET, so it was pretty straight forward to move to XAF/XPO. There is a learning curve, but for the most part the tutorials and demos answer many questions. However, on a couple occasions I just couldn't get it figured out. I contacted the DevExpress support, expecting at least a few days delay, if not weeks. However, I was pleasantly surprised in the quickness of their responses. The answers were quick, and to the point to allow me to easily implement what was needed. It's a joy to work with DevExpress controls, and now, it's been a joy to work with their support team! Thanks to DevExpress a lot of the frustrations in software development are removed.

## Let's Get Started

If you are ready to begin your journey with XAF, feel free to download our free 30-day trial today. If you need additional guidance on whether XAF is the right choice for your next project, please email  [support@devexpress.com](mailto:support@devexpress.com). We'll be happy to follow-up and give you a straight answer.

Until we speak next, please review additional  [comments and case-studies](https://www.devexpress.com/aboutus/testimonials/)  from happy XAF users.
