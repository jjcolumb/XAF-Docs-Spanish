[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/ef-xpo.en.md)

[Volver atrás](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/README.md)

# Por qué recomendamos EF Core sobre XPO para nuevos desarrollos

XAF admite dos herramientas de asignación relacional de objetos:  [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/)  y  [DevExpress XPO.](https://docs.devexpress.com/XPO/1998/express-persistent-objects)  Como es de esperar, a menudo recibimos solicitudes de comparación de usuarios de XAF UI y Web API Service: ¿qué ORM debo elegir? La respuesta, por supuesto, depende de sus tareas y de lo familiarizado que esté con XPO y EF Core. Revise la información de este tema para elegir el ORM que mejor se adapte a las necesidades de su empresa en los siguientes escenarios:

-   Usted es nuevo en nuestros marcos de aplicaciones y no tiene conocimiento de ninguno de los ORM y aún no sabe qué elegir.
    
-   Está comenzando un nuevo proyecto, tiene experiencia anterior con XPO o EF Core y desea volver a evaluar su elección debido a problemas de ORM o nuevas oportunidades.
    

EF Core es la opción predeterminada en el  [Asistente para soluciones](https://docs.devexpress.com/eXpressAppFramework/113624/installation-upgrade-version-history/visual-studio-integration/solution-wizard)  y  [Tutoriales de introducción](https://docs.devexpress.com/eXpressAppFramework/113577/getting-started)  desde la versión 23.1. Hicimos ese cambio porque consideramos que EF Core es la mejor opción para el nuevo desarrollo de XAF y Web API Service.

Sin embargo, si tiene experiencia con ambos ORM y prefiere XPO a EF Core, puede seguir utilizando XPO siempre que satisfaga sus necesidades empresariales.

## [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-vs-ef-core-similarities)XPO vs EF Core: similitudes

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#tools-and-extensions)Herramientas y extensiones

Tanto  [EF Core](https://learn.microsoft.com/en-us/ef/core/extensions/)  como  [XPO](https://docs.devexpress.com/XPO/14809/design-time-features)  admiten el desarrollo de Code-First, Model-First y Database-First. Ambos incluyen herramientas de registro y generación de perfiles, un diseñador visual para el modelo de datos y herramientas de scaffolding que permiten generar clases de modelo de datos a partir de bases de datos existentes.

EF Core tiene una ventaja cuando se trata de herramientas y extensiones disponibles implementadas por 3rd parties o Microsoft. Puede usar un gran conjunto de extensiones de pago de DevArt, así como extensiones integradas en marcos y productos de Microsoft como Blazor, OData y Visual Studio, etc.

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#database-schema-migration)Migración de esquemas de base de datos

Tanto  [EF Core](https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli)  como  [XPO](https://docs.devexpress.com/XPO/2632/create-a-data-model/when-and-why-xpo-extends-the-database-schema#important-notes)  pueden actualizar las tablas de base de datos después de que cambie la estructura del modelo de datos. EF Core requiere que ejecute explícitamente  [migraciones](https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli)  de CLI cada vez que agregue nuevas clases o propiedades en tiempo de diseño (puede automatizar este comportamiento). XPO puede añadir automáticamente tablas y columnas para nuevas clases y propiedades. XPO no modifica tablas, columnas, índices o claves externas existentes, ni responde a cambios de tamaño o tipo de propiedad/columna, eliminaciones, etc. Controle estos cambios manualmente como lo haría con EF Core.

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#performance)Rendimiento

EF Core y XPO muestran un rendimiento comparable en casos populares. Los escenarios avanzados pueden funcionar mejor con EF Core o XPO. No podemos declarar un claro ganador en esta categoría.

Referencia:

-   [EF Core 7 frente a XPO](https://github.com/DevExpress-Examples/XAF_Security_E4908/tree/23.1.1+/Benchmarks)
-   [EF Core 6 frente a XPO](https://github.com/DevExpress-Examples/XAF_Security_E4908/tree/22.2.4%2B/Benchmarks)
-   [Dapper.Tests.Performance.](https://github.com/DapperLib/Dapper/tree/main/benchmarks/Dapper.Tests.Performance)

Tanto  [EF Core](https://learn.microsoft.com/en-us/ef/core/querying/related-data/)  como  [XPO](https://docs.devexpress.com/XPO/2024/query-and-shape-data/delayed-loading)  permiten a los desarrolladores controlar la carga retrasada/perezosa, ansiosa y explícita de datos relacionados. Ambos ORM admiten  [los modos de acceso](https://docs.devexpress.com/eXpressAppFramework/113683/ui-construction/views/list-view-data-access-modes)  a datos de XAF, consultas LINQ complejas, proyecciones de datos LINQ y combinaciones libres.

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xaf-module-support)Compatibilidad con módulos XAF

Los  [módulos](https://docs.devexpress.com/eXpressAppFramework/118046/application-shell-and-base-infrastructure/application-solution-components/modules)  XAF populares son compatibles con EF Core y XPO. Puede usar los siguientes módulos con cualquier ORM:  **Seguridad**  (incluida la seguridad de nivel intermedio[[1]](https://docs.devexpress.com/eXpressAppFramework/404186/why-we-recommend-ef-core-over-xpo#fn:1)),  **Validación**,  **Apariencia condicional**,  **Informes**,  **Pista de auditoría**,  **Archivos adjuntos**,  **Office**,  **Paneles**  y  **Servicio de API web**. El módulo  **Clone Object**  solo es compatible con XPO por el momento. Este no es, con mucho, nuestro módulo más popular y puede  [implementar una funcionalidad similar con facilidad](https://stackoverflow.com/questions/45914736/how-to-clone-an-entity-in-entity-framework-core).

A pesar de ser un ORM de DevExpress, XPO no tiene ventajas de integración cuando se utiliza con XAF u otros productos DevExpress.

En 2023, alcanzamos niveles comparables de documentación de DevExpress y ejemplos de GitHub que describen la integración de XAF con XPO o EF Core.

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#soft-deletion)Eliminación suave

Tanto  [EF Core](https://supportcenter.devexpress.com/ticket/details/t1130343/xaf-ef-delete-issue)  como  [XPO](https://docs.devexpress.com/XPO/2026/crud/deleting-persistent-objects#deferred-object-deletion)  admiten la eliminación de objetos suaves o diferidos. En este caso, ORM marca los objetos como eliminados y no los elimina físicamente de una base de datos de inmediato. Esta técnica le ayuda a evitar excepciones de base de datos al eliminar objetos a los que hacen referencia otras entidades.

## [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-vs-ef-core-differences)XPO vs EF Core: Diferencias

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#product-type)Tipo de producto

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core)Núcleo EF

-   Producto gratuito y  [de código abierto](https://github.com/dotnet/efcore/blob/main/LICENSE.txt).
    
-   Mantenido por Microsoft.
    
-   El código fuente de EF Core está disponible en  [GitHub](https://github.com/dotnet/efcore).
    

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo)XPO

-   El producto es gratuito, pero propietario. Para obtener más información, consulte la siguiente página:  [EULA.](https://www.devexpress.com/Support/EULAs/xpo.xml)
    
-   Mantenido por DevExpress.
    
-   El código fuente completo de XPO está disponible para los propietarios de suscripciones  [DevExpress Universal](https://www.devexpress.com/subscriptions/universal.xml)  y  [DXperience](https://www.devexpress.com/subscriptions/dxperience.xml).
    

----------

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#status)Estado

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core-1)Núcleo EF

-   Un ORM maduro, fuertemente promovido por Microsoft, con desarrollo activo en GitHub.
    
-   Las versiones de productos incluyen actualizaciones anuales de funciones principales y actualizaciones menores mensuales con correcciones de errores.
    

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-1)XPO

-   Un ORM maduro en modo de mantenimiento.
    
-   Las principales actualizaciones anuales incluyen compatibilidad con la nueva versión de .NET, Visual Studio y los 5 principales controladores de base de datos ADO.NET. Las actualizaciones menores mensuales contienen correcciones de errores.
    

----------

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#popularity)Popularidad

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core-2)Núcleo EF

-   El paquete  [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore)  tiene 650 millones de descargas totales y un promedio de 250 K por día[[2]](https://docs.devexpress.com/eXpressAppFramework/404186/why-we-recommend-ef-core-over-xpo#fn:2).
    
-   Es fácil encontrar y contratar desarrolladores/contratistas con conocimiento de EF.
    

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-2)XPO

-   El paquete  [NuGet de DevExpress.Xpo](https://www.nuget.org/packages/DevExpress.Xpo)  tiene 6,3 millones de descargas totales y un promedio de 3,6 mil por día[[2]](https://docs.devexpress.com/eXpressAppFramework/404186/why-we-recommend-ef-core-over-xpo#fn:2).
    
-   Es difícil encontrar y contratar desarrolladores/contratistas con conocimientos de XPO.
    

----------

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#community--knowledge-base)Comunidad / Base de conocimientos

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core-3)Núcleo EF

-   Entity Framework tiene más de 135 mil preguntas públicas respondidas por la comunidad en Stack Overflow para diferentes versiones (muchas soluciones de versiones anteriores de EF se aplican a las versiones más recientes).
    
-   La documentación completa en línea está disponible en  [https://learn.microsoft.com/en-us/ef/](https://learn.microsoft.com/en-us/ef/).
    
-   Puede encontrar miles de recursos educativos de 3rd party para EF Core: videos de la comunidad, tutoriales, artículos y materiales de consultoría / capacitación.
    

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-3)XPO

-   Stack Overflow contiene menos de 100 preguntas para XPO. El Centro de soporte de DevExpress enumera alrededor de 16K de preguntas públicas.
    
-   La documentación completa en línea está disponible en el  [sitio web de DevExpress](https://docs.devexpress.com/XPO/1998/express-persistent-objects).
    
-   Un número limitado de recursos educativos de 3rd party están disponibles.
    

----------

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#database-provider-support)Compatibilidad con proveedores de bases de datos

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core-4)Núcleo EF

-   [EF Core admite](https://learn.microsoft.com/en-us/ef/core/providers/?tabs=dotnet-core-cli)  varios proveedores de bases de datos relacionales populares para .NET y .NET Framework.
    
-   Existen proveedores gratuitos y de pago, ambos desarrollados por Microsoft o 3rd parties. También puede crear proveedores de bases de datos personalizados.
    
-   EF Core admite bases de datos NoSQL (no se usan actualmente en aplicaciones XAF).
    
-   Soporte nativo para datos espaciales, , , y tipos JSON.`DateTimeOffset``DateOnly``TimeOnly`
    

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-4)XPO

-   [XPO admite](https://docs.devexpress.com/XPO/2114/product-information/database-systems-supported-by-xpo)  varios proveedores de bases de datos relacionales populares tanto para .NET como para .NET Framework.
    
-   Todos los proveedores existentes son gratuitos y desarrollados por DevExpress. Puede crear proveedores de bases de datos personalizados.
    
-   XPO no admite bases de datos NoSQL.
    
-   La compatibilidad con datos espaciales, , , , tipos JSON está disponible a través de soluciones personalizadas.`DateTimeOffset``DateOnly``TimeOnly`
    

----------

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#data-model-design)Diseño de modelos de datos

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core-5)Núcleo EF

-   EF Core tiene  [convenciones](https://learn.microsoft.com/en-us/ef/core/modeling/relationships/conventions)  de nomenclatura sencillas para definir  [relaciones](https://learn.microsoft.com/en-us/ef/core/modeling/relationships), claves y otros tipos de propiedades y entidades implícitamente (sin atributos).
    
-   EF Core implementa implícitamente notificaciones cuando cambia una propiedad. El código del modelo de datos permite propiedades automáticas virtuales () y no requiere que implemente las interfaces and. Para obtener más información, consulte el tema siguiente:  [Seguimiento de cambios en EF Core DbContext y consideraciones de rendimiento](https://docs.devexpress.com/eXpressAppFramework/404292/business-model-design-orm/business-model-design-with-entity-framework-core/change-tracking-performance-considerations).`get;set;``INotifyPropertyChanged``INotifyPropertyChanging`
    
-   EF Core admite  [propiedades alias/calculadas](https://learn.microsoft.com/en-us/ef/core/modeling/generated-properties?tabs=data-annotations#computed-columns)  que se pueden calcular mediante SQL en el servidor de bases de datos. Esta funcionalidad tiene  [compatibilidad limitada](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.DC.CalculatedAttribute)  con los modos de acceso a datos XAF.
    
-   También puedes personalizar la  [estructura del tipo de entidad o los metadatos mediante la API de Fluent y la](https://learn.microsoft.com/en-us/ef/core/modeling/)  [información de tipos XAF](https://docs.devexpress.com/eXpressAppFramework/113583/business-model-design-orm/types-info-subsystem/use-metadata-to-customize-business-classes-dynamically).
    

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-5)XPO

-   XPO requiere que defina  [relaciones](https://docs.devexpress.com/XPO/2041/create-a-data-model/relationships-between-objects)  y  [claves](https://docs.devexpress.com/eXpressAppFramework/113665/business-model-design-orm/data-types-supported-by-built-in-editors/key-properties#express-persistent-objects-xpo)  explícitamente (con atributos).
    
-   XPO incluye  [clases persistentes base](https://docs.devexpress.com/eXpressAppFramework/113146/business-model-design-orm/business-model-design-with-xpo/base-persistent-classes)  integradas que ahorran tiempo y líneas de código para escenarios comunes.
    
-   XPO requiere una notificación explícita cuando cambia el valor de una propiedad. El código del modelo de datos requiere que las propiedades incluyan llamadas. Para obtener más información, consulte la siguiente sección de ayuda:  [PropertyChanged Event in XPO](https://docs.devexpress.com/eXpressAppFramework/117395/business-model-design-orm/property-changed-event-in-business-classes#propertychanged-event-in-xpo).`SetPropertyValue`
    
-   XPO admite  [propiedades alias/calculadas](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentAliasAttribute)  que se pueden calcular utilizando SQL en el lado del servidor de base de datos. Esta funcionalidad es totalmente compatible con los modos de acceso a datos XAF.
    
-   También puede personalizar la estructura del tipo de entidad o los metadatos mediante Información de  [tipos XAF](https://learn.microsoft.com/en-us/ef/core/modeling/)  y  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/113583/business-model-design-orm/types-info-subsystem/use-metadata-to-customize-business-classes-dynamically#1).
    

----------

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#control-concurrency-conflicts)Conflictos de simultaneidad de control

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core-6)Núcleo EF

-   EF Core no comprueba si un objeto se ha modificado antes de una confirmación en aplicaciones XAF. Si dos usuarios cambian el mismo objeto simultáneamente, el último cambio anula todos los demás cambios. Sin embargo, puede habilitar el control de  [simultaneidad optimista](https://learn.microsoft.com/en-us/ef/core/saving/concurrency?tabs=data-annotations)  y otras estrategias manualmente.

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-6)XPO

-   XPO habilita el control de  [simultaneidad optimista](https://docs.devexpress.com/eXpressAppFramework/113596/business-model-design-orm/business-model-design-with-xpo/optimistic-concurrency-control)  en aplicaciones XAF de forma predeterminada.

----------

### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#miscellaneous)Misceláneo

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#ef-core-7)Núcleo EF

-   XAF no admite un anidado cuando se usa EF Core como ORM. Cada vista tiene su espacio de objetos independiente. Por un lado, esto ofrece una interfaz de usuario y un modelo de programación más simples. Por otro lado, puede carecer de la flexibilidad de XPO en ciertos escenarios avanzados. XAF tampoco tiene actualmente una versión asincrónica de para EF Core.`IObjectSpace``IObjectSpace`
    
-   EF Core no permite agregar nuevas propiedades a un modelo de datos existente dinámicamente (en tiempo de ejecución).
    
-   El sistema de seguridad requiere  [varios conjuntos de resultados activos](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/enabling-multiple-active-result-sets)  (MARS) en aplicaciones XAF basadas en EF Core conectadas a Microsoft SQL Server y otras bases de datos. Por ejemplo, el proveedor de ADO.NET admite MARS, pero PostreSQL no lo admite y requiere  [soluciones alternativas](https://supportcenter.devexpress.com/ticket/details/t1153336/ef-core-postgresql-a-command-is-already-in-progress).
    
-   El Servicio de API web con tecnología de EF Core no admite actualmente la creación y modificación de colecciones anidadas y propiedades de referencia.
    

#### [](https://github.com/lianhdez95/Why-We-Recommend-EF-Core-over-XPO-for-New-Development/blob/main/README.md#xpo-7)XPO

-   XPO le permite  [crear un IObjectSpace anidado](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Xpo.XPObjectSpace.CreateNestedObjectSpace). Cuando se confirman los cambios realizados en un espacio de objetos anidado, los cambios se vuelven a combinar en el espacio de objetos principal. Esta técnica permite tratar varias operaciones relacionadas como una única operación unificada. XAF también tiene una versión asíncrona de para XPO.`IObjectSpace`
    
-   XPO le permite agregar nuevas propiedades a un modelo de datos existente dinámicamente a través de  [información de tipos XAF](https://docs.devexpress.com/eXpressAppFramework/113583/business-model-design-orm/types-info-subsystem/use-metadata-to-customize-business-classes-dynamically)  (para escenarios avanzados).`XPDictionary`
    
-   XPO no requiere que los proveedores de ADO.NET admitan  [varios conjuntos de resultados activos](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/enabling-multiple-active-result-sets)  (MARS) para el funcionamiento correcto de XAF.
    
-   Web API Service con tecnología  [XPO](https://docs.devexpress.com/eXpressAppFramework/403715/backend-web-api-service/use-odata-to-send-requests/use-http-client-to-access-web-api#modify-an-object-assigned-to-a-reference-property-xpo-only)  ofrece un mejor soporte para la creación y modificación de colecciones anidadas y propiedades de referencia.
    

----------

VER TAMBIÉN

[EF Core frente a XPO en aplicaciones XAF (comparación basada en la comunidad)](https://xafmarin.com/entity-framework-core-and-devexpress-xpo-two-orm-solutions/)
