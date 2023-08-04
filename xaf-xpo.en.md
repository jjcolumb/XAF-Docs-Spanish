
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/xaf-xpo.es.md)

[Back](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/README.en.md)

# Why We Recommend EF Core over XPO for New Development

XAF supports two Object-Relational Mapping tools:  [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/)  and  [DevExpress XPO](https://docs.devexpress.com/XPO/1998/express-persistent-objects). As you might expect, we often receive comparison requests from XAF UI and Web API Service users: which ORM should I choose? The answer, of course, depends on your tasks, and on how familiar you are with XPO and EF Core. Review the information in this topic to choose the ORM that suits your business needs best in the following scenarios:

-   You are new to our application frameworks and have no knowledge of either ORM and do not yet know what to choose.
    
-   You are starting a new project, have earlier experience with XPO or EF Core, and want to re-evaluate your choice due to ORM issues or new opportunities.
    

EF Core is the default choice in the  [Solution Wizard](https://docs.devexpress.com/eXpressAppFramework/113624/installation-upgrade-version-history/visual-studio-integration/solution-wizard)  and  [Getting Started Tutorials](https://docs.devexpress.com/eXpressAppFramework/113577/getting-started)  since v23.1. We made that change because we consider EF Core the best choice for new XAF and Web API Service development.

However, if you have experience with both ORMs and prefer XPO to EF Core, you can continue to use XPO as long as it meets your business needs.


## XPO vs EF Core: Similarities
#### Tools and Extensions

Both  [EF Core](https://learn.microsoft.com/en-us/ef/core/extensions/)  and  [XPO](https://docs.devexpress.com/XPO/14809/design-time-features)  support Code-First, Model-First, and Database-First development. Both include logging and profiling tools, a visual designer for data model, and scaffolding tools that allow you to generate data model classes from existing databases.

EF Core has an advantage when it comes to available tools and extensions implemented by 3rd parties or Microsoft. You can use a large set of paid extensions from DevArt, as well as built-in extensions in Microsoft frameworks and products such as Blazor, OData, and Visual Studio, and so on.

#### Database Schema Migration

Both  [EF Core](https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli)  and  [XPO](https://docs.devexpress.com/XPO/2632/create-a-data-model/when-and-why-xpo-extends-the-database-schema#important-notes)  can update database tables after your data model structure changes. EF Core requires that you explicitly execute CLI  [migrations](https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli)  each time you add new classes or properties at design time (you can automate this behavior). XPO can automatically add tables and columns for new classes and properties. XPO does not modify existing tables, columns, indexes, or foreign keys, nor does it respond to property/column size or type changes, deletions, etc. Handle these changes manually as you would with EF Core.

#### Performance

EF Core and XPO show comparable performance in popular cases. Advanced scenarios may perform better with either EF Core or XPO. We cannot declare a clear winner in this category.

Benchmarks:

-   [EF Core 7 vs XPO](https://github.com/DevExpress-Examples/XAF_Security_E4908/tree/23.1.1+/Benchmarks)
-   [EF Core 6 vs XPO](https://github.com/DevExpress-Examples/XAF_Security_E4908/tree/22.2.4%2B/Benchmarks)
-   [Dapper.Tests.Performance](https://github.com/DapperLib/Dapper/tree/main/benchmarks/Dapper.Tests.Performance).

Both  [EF Core](https://learn.microsoft.com/en-us/ef/core/querying/related-data/)  and  [XPO](https://docs.devexpress.com/XPO/2024/query-and-shape-data/delayed-loading)  allow developers to control delayed/lazy, eager and explicit loading of related data. Both ORMs support XAF’s  [Data Access Modes](https://docs.devexpress.com/eXpressAppFramework/113683/ui-construction/views/list-view-data-access-modes), complex LINQ queries, LINQ data projections, and Free Joins.

#### XAF Module Support

Popular XAF  [modules](https://docs.devexpress.com/eXpressAppFramework/118046/application-shell-and-base-infrastructure/application-solution-components/modules)  support both EF Core and XPO. You can use the following modules with any ORM:  **Security**  (including Middle Tier Security[[1]](https://docs.devexpress.com/eXpressAppFramework/404186/why-we-recommend-ef-core-over-xpo#fn:1)),  **Validation**,  **Conditional Appearance**,  **Reports**,  **Audit Trail**,  **File Attachments**,  **Office**,  **Dashboards**, and  **Web API Service**. The  **Clone Object**  module support XPO only at the moment. This is by far not our most popular module and you can  [implement similar funtionality with ease](https://stackoverflow.com/questions/45914736/how-to-clone-an-entity-in-entity-framework-core).

Despite being a DevExpress ORM, XPO has no integration advantages when used with XAF or other DevExpress products.

In 2023, we reached comparable levels of DevExpress Documentation and GitHub Examples that describe XAF integration with XPO or EF Core.

#### Soft Deletion

Both  [EF Core](https://supportcenter.devexpress.com/ticket/details/t1130343/xaf-ef-delete-issue)  and  [XPO](https://docs.devexpress.com/XPO/2026/crud/deleting-persistent-objects#deferred-object-deletion)  support soft or deferred object deletion. In this case, ORM marks objects as deleted and does not physically remove them from a database right away. This technique helps you avoid database exceptions when deleting objects that are referenced by other entities.

## XPO vs EF Core: Differences

### Product Type

#### EF Core
- Free and  [open-source](https://github.com/dotnet/efcore/blob/main/LICENSE.txt)  product.

- Maintained by Microsoft.

- EF Core source code is available on  [GitHub](https://github.com/dotnet/efcore).

#### XPO
- The product is free, but proprietary. For more information, refer to the following page -  [EULA](https://www.devexpress.com/Support/EULAs/xpo.xml).

- Maintained by DevExpress.

- XPO full source code is available to owners of DevExpress  [Universal](https://www.devexpress.com/subscriptions/universal.xml)  and  [DXperience](https://www.devexpress.com/subscriptions/dxperience.xml)  Subscriptions.
----
### Status
#### EF Core
- A mature ORM, heavily promoted by Microsoft, with active development on GitHub.

- Product releases include yearly major feature updates and monthly minor updates with bug fixes.

#### XPO
- A mature ORM in maintenance mode.

- Yearly major updates include support for new version of .NET, Visual Studio, and top 5 ADO.NET database drivers. Monthly minor updates contain bug fixes.
---

### Popularity

#### EF Core
- The  [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore)  package has 650M total downloads and an average of 250K per day[[2]](https://docs.devexpress.com/eXpressAppFramework/404186/why-we-recommend-ef-core-over-xpo#fn:2).

- It is easy to find and hire developers/contractors with EF knowledge.

#### XPO

- The  [DevExpress.Xpo](https://www.nuget.org/packages/DevExpress.Xpo)  NuGet package has 6.3M total downloads and an average of 3.6K per day[[2]](https://docs.devexpress.com/eXpressAppFramework/404186/why-we-recommend-ef-core-over-xpo#fn:2).

- It is difficult to find and hire developers/contractors with XPO knowledge.
---

### Community / Knowledge Base

#### EF Core
- Entity Framework has over 135K public questions answered by the community on Stack Overflow for different versions (many solutions from older EF versions apply to the latest versions).

- Comprehensive online documentation is available at  [https://learn.microsoft.com/en-us/ef/](https://learn.microsoft.com/en-us/ef/).

- You can find thousands of 3rd party educational resources for EF Core: community videos, tutorials, articles, and consulting/training materials.

#### XPO
- Stack Overflow contains less than 100 questions for XPO. The DevExpress Support Center lists about 16K of public questions.

- Comprehensive online documentation is available on the  [DevExpress website](https://docs.devexpress.com/XPO/1998/express-persistent-objects).

- A limited number of 3rd party educational resources are available.
---

### Database Provider Support

#### EF Core
- [EF Core supports](https://learn.microsoft.com/en-us/ef/core/providers/?tabs=dotnet-core-cli)  multiple popular relational database providers for both .NET and the .NET Framework.

- Free and paid providers exist, both developed by Microsoft or 3rd parties. You can also create custom database providers.

- EF Core supports NoSQL databases (not currently used in XAF applications).

- Native support for spatial data,  `DateTimeOffset`,  `DateOnly`,  `TimeOnly`, and JSON types.

#### XPO
- [XPO supports](https://docs.devexpress.com/XPO/2114/product-information/database-systems-supported-by-xpo)  multiple popular relational database providers for both .NET and the .NET Framework.

- All existing providers are free and developed by DevExpress. You can create custom database providers.

- XPO does not support NoSQL databases.

- Support for spatial data,  `DateTimeOffset`,  `DateOnly`,  `TimeOnly`, JSON types is available via custom solutions.
---

### Data Model Design

#### EF Core
- EF Core has simple naming  [conventions](https://learn.microsoft.com/en-us/ef/core/modeling/relationships/conventions) to define  [relationships](https://learn.microsoft.com/en-us/ef/core/modeling/relationships), keys, and other property and entity types implicitly (without attributes).

- EF Core implicitly implements notifications when a property changes. Data model code allows virtual auto properties (`get;set;`) and does not require you to implement the  `INotifyPropertyChanged`  and  `INotifyPropertyChanging`  interfaces. For more information, refer to the following topic:  [Change Tracking in EF Core DbContext and Performance Considerations](https://docs.devexpress.com/eXpressAppFramework/404292/business-model-design-orm/business-model-design-with-entity-framework-core/change-tracking-performance-considerations).

- EF Core supports  [aliased/calculated properties](https://learn.microsoft.com/en-us/ef/core/modeling/generated-properties?tabs=data-annotations#computed-columns)  that can be computed using SQL on the database server side. This functionality has  [limited](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.DC.CalculatedAttribute)  support for XAF Data Access Modes.

- You can also customize  [the entity type structure or metadata using Fluent API](https://learn.microsoft.com/en-us/ef/core/modeling/)  and  [XAF Types info](https://docs.devexpress.com/eXpressAppFramework/113583/business-model-design-orm/types-info-subsystem/use-metadata-to-customize-business-classes-dynamically).

#### XPO
- XPO requires you to define  [relationships](https://docs.devexpress.com/XPO/2041/create-a-data-model/relationships-between-objects)  and  [keys](https://docs.devexpress.com/eXpressAppFramework/113665/business-model-design-orm/data-types-supported-by-built-in-editors/key-properties#express-persistent-objects-xpo)  explicitly (with attributes).

- XPO ships with built-in  [Base Persistent Classes](https://docs.devexpress.com/eXpressAppFramework/113146/business-model-design-orm/business-model-design-with-xpo/base-persistent-classes)  that save time and lines of code for common scenarios.

- XPO requires explicit notification when a property value changes. Data model code requires properties to include  `SetPropertyValue`  calls. For more information, refer to the following help section:  [PropertyChanged Event in XPO](https://docs.devexpress.com/eXpressAppFramework/117395/business-model-design-orm/property-changed-event-in-business-classes#propertychanged-event-in-xpo).

- XPO supports  [aliased/calculated properties](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentAliasAttribute)  that can be computed using SQL on the database server side. This functionality has full support for XAF Data Access Modes.

- You can also customize the entity type structure or metadata using  [XAF Types info](https://learn.microsoft.com/en-us/ef/core/modeling/)  and  [Model Editor](https://docs.devexpress.com/eXpressAppFramework/113583/business-model-design-orm/types-info-subsystem/use-metadata-to-customize-business-classes-dynamically#1).
---

### Control Concurrency Conflicts

#### EF Core
- EF Core does not check whether an object has been modified before a commit in XAF applications. If two users change the same object simultaneously, the latest change overrides all other changes. However, you can enable the  [Optimistic Concurrency](https://learn.microsoft.com/en-us/ef/core/saving/concurrency?tabs=data-annotations)  control and other strategies manually.

#### XPO
- XPO enables the [Optimistic Concurrency](https://docs.devexpress.com/eXpressAppFramework/113596/business-model-design-orm/business-model-design-with-xpo/optimistic-concurrency-control)  control in XAF applications by default.
---

### Miscellaneous

#### EF Core
- XAF does not support a nested  `IObjectSpace`  when EF Core is used as ORM. Each view has its independent Object Space. On the one hand this offers a simpler UI and programming model. On the other hand it may lack the flexibility of XPO in certain advanced scenarios. XAF also does not currently have an asynchronous version of  `IObjectSpace`  for EF Core.

- EF Core does not allow you to add new properties to an existing data model dynamically (at runtime).

- The Security System requires  [Multiple Active Result Sets](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/enabling-multiple-active-result-sets) (MARS) in EF Core-based XAF applications connected to the Microsoft SQL Server and other databases. For example, the ADO.NET provider supports MARS itself, but PostreSQL does not support it and requires  [workarounds](https://supportcenter.devexpress.com/ticket/details/t1153336/ef-core-postgresql-a-command-is-already-in-progress).

- Web API Service powered by EF Core does not currently support creation and modification of nested collections and reference properties.

#### XPO
- XPO allows you to  [create a nested IObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Xpo.XPObjectSpace.CreateNestedObjectSpace). When you commit changes made in a nested Object Space, changes are merged back into the parent Object Space. This technique allows you to treat multiple related operations as a single unified operation. XAF also has an asynchronous version of  `IObjectSpace`  for XPO.

- XPO allows you to add new properties to an existing data model dynamically through  `XPDictionary`  or  [XAF Types info](https://docs.devexpress.com/eXpressAppFramework/113583/business-model-design-orm/types-info-subsystem/use-metadata-to-customize-business-classes-dynamically)  (for advanced scenarios).

- XPO does not require ADO.NET providers to support  [Multiple Active Result Sets](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/enabling-multiple-active-result-sets)  (MARS) for the correct XAF operation.

- Web API Service powered by  [XPO](https://docs.devexpress.com/eXpressAppFramework/403715/backend-web-api-service/use-odata-to-send-requests/use-http-client-to-access-web-api#modify-an-object-assigned-to-a-reference-property-xpo-only)  ships with better support for creation and modification of nested collections and reference properties.
---

SEE ALSO

[EF Core vs XPO in XAF Applications (Community-Based Comparison)](https://xafmarin.com/entity-framework-core-and-devexpress-xpo-two-orm-solutions/)
