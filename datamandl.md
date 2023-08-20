
# Manipulación de datos y lógica empresarial


En las aplicaciones XAF, no es necesario consultar datos directamente o a través de un contexto específico de ORM. En cambio, XAF le proporciona una API conveniente y potente independiente de las especificaciones particulares de ORM y DBMS:  [Object Space](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space). Los temas de esta sección le familiarizan con los conceptos del espacio de objetos: describen cómo puede manipular datos e implementar la lógica empresarial.


# Formas de acceder a un espacio de objetos (el contexto de base de datos para operaciones CRUD)


En las aplicaciones XAF, todas las manipulaciones con reconocimiento de datos y la lógica empresarial personalizada se realizan a través del espacio de objetos. El espacio de objetos es una abstracción en el contexto de la base de datos. El espacio de objetos le permite consultar o editar datos en la transacción. Object Space es una implementación independiente de ORM de los conocidos patrones de diseño de  [repositorio](https://docs.microsoft.com/en-us/previous-versions/msp-n-p/ff649690(v=pandp.10)) y  [unidad de trabajo](https://docs.microsoft.com/en-us/archive/msdn-magazine/2009/june/the-unit-of-work-pattern-and-persistence-ignorance).

Los miembros del espacio de objetos se declaran en la interfaz  [IObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace). Las clases BaseObjectSpace y  [CompositeObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.CompositeObjectSpace)  implementan el código común.[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.BaseObjectSpace)  XAF incluye los siguientes descendientes de  **CompositeObjectSpace**:

-   [XPObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Xpo.XPObjectSpace)  - se utiliza para acceder a los datos a través de una  [sesión](https://docs.devexpress.com/XPO/DevExpress.Xpo.Session)  cuando se utiliza el modelo de datos  [XPO](https://docs.devexpress.com/eXpressAppFramework/112600/business-model-design-orm/business-model-design-with-xpo).
-   [EFCoreObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.EFCore.EFCoreObjectSpace): se usa para acceder a los datos a través de  [DbContext](https://learn.microsoft.com/dotnet/api/microsoft.entityframeworkcore.dbcontext) cuando se usa el modelo de datos  [de Entity Framework Core](https://docs.microsoft.com/en-us/ef/core).
-   [NonPersistentObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.NonPersistentObjectSpace): se utiliza para administrar  [objetos no persistentes que no](https://docs.devexpress.com/eXpressAppFramework/116516/business-model-design-orm/non-persistent-objects)  están asignados a la base de datos.

![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/504d6839-f6ec-429c-92f6-3c2f6a9798aa)


En la mayoría de los casos, accederá a Object Space a través de la interfaz  [IObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace)  y no necesitará usar estas clases directamente.

Al implementar lógica empresarial personalizada ([crear, leer, actualizar y eliminar](https://docs.devexpress.com/eXpressAppFramework/113711/data-manipulation-and-business-logic/create-read-update-and-delete-data)  datos), se requiere  **espacio de objetos**  si los datos que expone el objeto de negocio actual son insuficientes para la lógica y necesita consultar más datos. También puede utilizar el espacio de objetos en el código de inicialización de la base de datos, en  [elementos de vista](https://docs.devexpress.com/eXpressAppFramework/112612/ui-construction/view-items-and-property-editors)  complejos, etc. En este tema se describe la API que puede usar para obtener espacio de objetos en varios contextos.

Una vez que haya obtenido o creado un espacio de objetos, puede utilizarlo para consultar o modificar datos (consulte  [Crear, leer, actualizar y eliminar datos](https://docs.devexpress.com/eXpressAppFramework/113711/data-manipulation-and-business-logic/create-read-update-and-delete-data)).

## Obtener un espacio de objetos existente

XAF crea espacios de objetos para cada vista de una aplicación. Para cargar datos o realizar lógica personalizada con objetos ya cargados, utilice los enfoques de la lista siguiente para obtener un espacio de objetos de varios contextos del código.

### Obtener un espacio de objetos existente en un controlador

En las aplicaciones XAF, se asigna automáticamente un espacio de objetos para cada  [vista](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views). Las vistas XAF escuchan los eventos del espacio de objetos asignado a una vista. En un controlador de vista, puede acceder al espacio de objetos con  [View.ObjectSpace.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.View.ObjectSpace)  También puede utilizar la propiedad  **protegida ViewController.ObjectSpace**  que hace referencia al mismo espacio de objetos que  **View.ObjectSpace.**  Un controlador de ventana no expone una vista directamente. Puede tener acceso al Frame actual mediante la propiedad  [Controller.Frame](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Controller.Frame)  y obtener la vista con  [Frame.View.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Frame.View)[](https://docs.devexpress.com/eXpressAppFramework/112608/ui-construction/windows-and-frames)

Las opciones anteriores solo son adecuadas para las manipulaciones de datos más simples que utilizan un espacio de objetos (por ejemplo, modificar una propiedad de un objeto View actual y confirmar cambios). Para procesar grandes cantidades de datos o crear una nueva vista con los métodos XafApplication.CreateListView o  [XafApplication.CreateDetailView](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication.CreateDetailView.overloads),  [cree un nuevo espacio de objetos](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space#create)  que no esté enlazado a una vista actual en lugar de utilizar la propiedad  [View.ObjectSpace.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.View.ObjectSpace)[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication.CreateListView.overloads)

**Ver también:**

-   [Agregar una acción simple mediante un atributo](https://docs.devexpress.com/eXpressAppFramework/402156/getting-started/in-depth-tutorial-blazor/add-actions-menu-commands/add-a-simple-action-using-an-attribute)
-   [Agregar una acción que muestre una ventana emergente](https://docs.devexpress.com/eXpressAppFramework/402158/getting-started/in-depth-tutorial-blazor/add-actions-menu-commands/add-an-action-that-displays-a-pop-up-window)
-   [Agregar una acción con selección de opción](https://docs.devexpress.com/eXpressAppFramework/402159/getting-started/in-depth-tutorial-blazor/add-actions-menu-commands/add-an-action-with-option-selection)
-   [IObjectSpace.ObjectChanged](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.ObjectChanged)

### Obtener un espacio de objeto existente en Business Object

#### [#](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space#in-a-ef-core-business-class)En una clase Business EF Core

Las clases que implementan la interfaz  [IObjectSpaceLink](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink)  pueden tener acceso a un objeto con la propiedad.`IObjectSpace``IObjectSpaceLink.ObjectSpace`

Las clases EF Core persistentes implementan la interfaz en tiempo de ejecución. También puede usar clases de EF Core para implementar esta interfaz de las siguientes maneras:`IObjectSpace`

-   Implemente la interfaz.`IObjectSpaceLink`
-   Heredar de la clase  [DevExpress.Persistent.BaseImpl.EF.BaseObject.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.BaseImpl.EF.BaseObject)
-   Usar el  **objeto de negocio XAF | EF Core Business Object**  de la  [Galería de plantillas](https://docs.devexpress.com/eXpressAppFramework/113455/installation-upgrade-version-history/visual-studio-integration/template-gallery)  para agregar una clase que admita tanto como .`IXafEntityObject``IObjectSpaceLink`

Si implementa adicionalmente un IXafEntityObject, puede colocar la lógica en los métodos IXafEntityObject.OnCreated, IXafEntityObject.OnLoaded y  [IXafEntityObject.OnSaveving](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IXafEntityObject.OnSaving)[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IXafEntityObject)[.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IXafEntityObject.OnCreated)[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IXafEntityObject.OnLoaded)  Puede utilizar el  **objeto de negocio XAF**  |  **EF Core Business**  Object de  [la Galería de plantillas](https://docs.devexpress.com/eXpressAppFramework/113455/installation-upgrade-version-history/visual-studio-integration/template-gallery)  para agregar una clase que admita  **IXafEntityObject**  e  **IObjectSpaceLink**.

#### En una clase ejecutiva XPO

No necesita un espacio de objetos dentro de una clase persistente. No implemente las interfaces  **IObjectSpaceLink**  e  **IXafEntityObject**  en este contexto. En su lugar, utilice la propiedad  **Session**  y reemplace los métodos  **AfterConstruction**,  **OnLoaded y OnSaving**  respectivamente  en una clase XPO. Para obtener más información, revise los siguientes diagnósticos de código:  [XAF0023](https://docs.devexpress.com/eXpressAppFramework/404104/debugging-testing-and-error-handling/code-diagnostics/xaf0023)  |  [XAF0024](https://docs.devexpress.com/eXpressAppFramework/404105/debugging-testing-and-error-handling/code-diagnostics/xaf0024).

#### En una clase Business no persistente

Las clases que implementan la interfaz  [IObjectSpaceLink](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink)  pueden tener acceso a un objeto con la propiedad. Para utilizar esta interfaz en clases no persistentes, utilice una de las siguientes técnicas:`IObjectSpace``IObjectSpaceLink.ObjectSpace`

-   Implemente esta interfaz.
-   Heredar de una clase base no persistente:  [Objetos no persistentes](https://docs.devexpress.com/eXpressAppFramework/116516/business-model-design-orm/non-persistent-objects#1).

**Ver también:**

-   [IObjectSpaceLink](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink)  |  [IXafEntityObject](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IXafEntityObject)
-   [Sesión](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentBase.Session)  |  [AfterConstruction()](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentBase.AfterConstruction)  |  [OnSaving()](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentBase.OnSaving)

### Obtener un espacio de objetos existente en un actualizador de módulos

En un descendiente de ModuleUpdater, puede utilizar la propiedad  **protegida ModuleUpdater.ObjectSpace**  para tener acceso a la instancia de Object Space que se puede utilizar para las operaciones de actualización de la base de datos.[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Updating.ModuleUpdater)  No utilice un nuevo espacio de objetos para actualizar la base de datos.

**Ver también:**

-   [Suministro de datos iniciales (EF Core)](https://docs.devexpress.com/eXpressAppFramework/113631/getting-started/in-depth-tutorial-winforms-webforms/business-model-design/business-model-design-with-entity-framework-6/supply-initial-data-ef?v=21.2)

### Obtener un espacio de objetos existente en un editor de listas

Una referencia al objeto  [CollectionSourceBase](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.CollectionSourceBase)  se pasa automáticamente al método IComplexListEditor.Setup si el Editor de listas personalizado admite la interfaz  [IComplexListEditor.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Editors.IComplexListEditor.Setup(DevExpress.ExpressApp.CollectionSourceBase-DevExpress.ExpressApp.XafApplication))  [](https://docs.devexpress.com/eXpressAppFramework/113189/ui-construction/list-editors)[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Editors.IComplexListEditor)Puede implementar esta interfaz y tener acceso al espacio de objetos mediante la propiedad  [CollectionSourceBase.ObjectSpace.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.CollectionSourceBase.ObjectSpace)

### Obtener un espacio de objetos existente en un elemento de vista o en un editor de propiedades

Una referencia a un espacio de objetos se pasa automáticamente al método IComplexViewItem.Setup si el  [elemento de vista](https://docs.devexpress.com/eXpressAppFramework/112612/ui-construction/view-items-and-property-editors)  personalizado o  [el editor de propiedades](https://docs.devexpress.com/eXpressAppFramework/113097/ui-construction/view-items-and-property-editors/property-editors)  admite la interfaz  [IComplexViewItem.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Editors.IComplexViewItem.Setup(DevExpress.ExpressApp.IObjectSpace-DevExpress.ExpressApp.XafApplication))  [](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Editors.IComplexViewItem)Puede implementar esta interfaz y almacenar la referencia del Espacio de objetos en una variable local para su uso futuro.

**Vea también:**  [IComplexViewItem](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Editors.IComplexViewItem)

### Acceder al espacio de objetos en eventos

El espacio de objetos también está disponible mediante argumentos pasados a varios eventos de la clase  [XafApplication](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication).

![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/77d43bb4-8c86-4182-aec7-6b7a7123af2a)


## Crear un nuevo espacio de objetos

Cree una nueva instancia de Espacio de objetos en los siguientes escenarios:

-   Puede crear una vista mediante los métodos XafApplication.CreateListView o  [XafApplication.CreateDetailView](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication.CreateListView.overloads)  en Controllers, List personalizada o editores de propiedades[.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication.CreateDetailView.overloads)
-   Necesita una vista que no reaccione a las modificaciones que realiza en su lógica empresarial. Por ejemplo, las acciones Guardar y Cancelar se habilitan cuando hay cambios en el espacio de objetos de la vista, porque una vista controla los eventos del espacio de objetos para actualizar la interfaz de usuario. Debe revertir los cambios en un espacio de objetos independiente sin afectar a los cambios en el espacio de objetos de la vista.
-   Procesa grandes cantidades de datos (por ejemplo, carga y modifica cientos de objetos persistentes relacionados).

>NOTA
Con XPO, cuando necesite realizar un montón de operaciones, pero evite actualizar inmediatamente el espacio de objetos de la vista, cree un espacio de objetos anidado utilizando los métodos [IObjectSpace.CreateNestedObjectSpace()](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CreateNestedObjectSpace) o [XPObjectSpace.CreateNestedObjectSpace().](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Xpo.XPObjectSpace.CreateNestedObjectSpace) Cuando se confirma un espacio de objetos anidado, los cambios en él se combinan en el espacio de objetos primario y no se conservan en una base de datos. Para conservar los cambios en una base de datos, confirme el espacio de objetos primario. Los espacios de objetos anidados se implementan en función de la [XPO NestedUnitOfWork](https://docs.devexpress.com/XPO/DevExpress.Xpo.NestedUnitOfWork)  y  heredan su comportamiento y características específicas.

### Crear un nuevo espacio de objetos en un controlador

Utilice el método  [XafApplication.CreateObjectSpace(Type)](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication.CreateObjectSpace(System.Type))  para crear un espacio de objetos. Consulte la descripción de la clase XafApplication para ver cómo obtener una instancia de  [XafApplication](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication)  en varios contextos.  Por ejemplo, la propiedad  [Controller.Application](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Controller.Application)  está disponible en un contexto Controller y puede crear un espacio de objetos de la siguiente manera:


```csharp
IObjectSpace objectSpace = this.Application.CreateObjectSpace(typeof(MyBusinessClass)); 

```

**Ver también:**

-   [Agregar una acción parametrizada](https://docs.devexpress.com/eXpressAppFramework/402155/getting-started/in-depth-tutorial-blazor/add-actions-menu-commands/add-a-parametrized-action)
-   [Agregar una acción que muestre una ventana emergente](https://docs.devexpress.com/eXpressAppFramework/402158/getting-started/in-depth-tutorial-blazor/add-actions-menu-commands/add-an-action-that-displays-a-pop-up-window)
-   [Agregar una acción con selección de opción](https://docs.devexpress.com/eXpressAppFramework/402159/getting-started/in-depth-tutorial-blazor/add-actions-menu-commands/add-an-action-with-option-selection)

### Crear un nuevo espacio de objetos en Business Object

En la mayoría de los casos, es suficiente  [obtener un espacio de objetos existente](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space#get)  para realizar lógica personalizada dentro de EF Core y clases empresariales no persistentes.

No puede crear nuevos espacios de objetos en el contexto de objeto de negocio porque una instancia de  **XafApplication**  no está disponible allí. Tampoco es posible acceder a  [vistas](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views)  y otras entidades relacionadas con la interfaz de usuario XAF dentro del código de clase empresarial, ya que viola el principio de  [separación de preocupaciones](https://en.wikipedia.org/wiki/Separation_of_concerns) y va en contra de la arquitectura  [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller): su modelo de datos no debe estar vinculado a la interfaz de usuario. Para acceder a  [XafApplication](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication),  [Views](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views)  y otras entidades relacionadas con la interfaz de usuario, implemente  [Controllers](https://docs.devexpress.com/eXpressAppFramework/112621/ui-construction/controllers-and-actions/controllers).

### Crear un nuevo espacio de objetos en escenarios avanzados de ASP.NET  Core

Si necesita acceder a una instancia de Espacio de objetos en un middleware o servicio ASP.NET Core personalizado, controladores de API web, páginas Razor personalizadas y componentes, use la  [inyección  de dependencias](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-6.0)  para insertar las interfaces  [IObjectSpaceFactory o INonSecuredObjectSpaceFactory](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Core.IObjectSpaceFactory)  e invocar su método  **CreateNonSecuredObjectSpaceSpace**.[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Core.INonSecuredObjectSpaceFactory)  Consulte los siguientes artículos de ayuda para encontrar los ejemplos:

-   [Acceso al espacio de objetos, el sistema de seguridad, el asistente de subtítulos y los módulos XAF en el entorno central de ASP.NET](https://docs.devexpress.com/eXpressAppFramework/403669/data-manipulation-and-business-logic/access-object-space-security-and-caption-helper-in-asp-net-core-environment)  (interfaz de usuario de XAF)
-   [Acceso al espacio de objetos, al sistema de seguridad y al asistente de subtítulos en métodos de extremo personalizados](https://docs.devexpress.com/eXpressAppFramework/403861/backend-web-api-service/create-custom-endpoints/access-object-space-security-and-caption-helper-in-custom-endpoint)  (servicio API web)

### Crear un nuevo espacio de objetos en aplicaciones que no sean XAF

En una aplicación que no sea XAF, puede crear instancias del proveedor de  [espacio de objetos](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceProvider)  manualmente. A continuación, puede llamar al método  [CreateObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceProvider.CreateObjectSpace)  del proveedor para crear un espacio de objetos. Consulte el siguiente artículo de ayuda para encontrar el ejemplo:  [Acceso a datos de aplicación XAF en una aplicación que no es XAF](https://docs.devexpress.com/eXpressAppFramework/113709/data-manipulation-and-business-logic/access-xaf-application-data-in-a-non-xaf-application)

>IMPORTANTE
Debe [desechar](https://docs.microsoft.com/en-us/dotnet/api/system.idisposable) manualmente  un espacio de objetos cuando haya terminado de usarlo si no lo asigna a una vista. Un espacio de objetos asociado a una vista se elimina automáticamente junto con esta vista.


# Crear, leer, actualizar y eliminar datos

-   Noviembre 11, 2022
-   2 minutos para leer

Puede crear una lógica empresarial en los siguientes lugares:

En Controladores

Puede declarar acciones nuevas y personalizar  [las existentes](https://docs.devexpress.com/eXpressAppFramework/112622/ui-construction/controllers-and-actions/actions)  y controlar otros eventos  [del Controller](https://docs.devexpress.com/eXpressAppFramework/112621/ui-construction/controllers-and-actions/controllers). Una vez que haya obtenido o creado una instancia de Espacio de objetos (como se describe en el tema  [Formas de acceder a un espacio de objetos (el contexto de base de datos para operaciones CRUD)](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space)), puede usarla para la manipulación de datos (crear, leer, actualizar o eliminar datos).

En modelo (clases empresariales)

Puede colocar lógica en los captadores y colocadores de propiedades, implementar métodos que se activan automáticamente cuando se crea, carga, guarda y elimina el objeto (consulte el tema  [IXafEntityObject](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IXafEntityObject)) y declara  [métodos de acción](https://docs.devexpress.com/eXpressAppFramework/112619/ui-construction/controllers-and-actions/actions/how-to-create-an-action-using-the-action-attribute).

En este tema se enumeran los artículos que describen cómo implementar operaciones comunes con reconocimiento de datos en Controllers con los métodos, eventos y clases de negocio correspondientes del Espacio de objetos.

## Tareas

-   Crear un nuevo objeto
-   Cargar objetos
-   Guardar objetos en la base de datos
-   Eliminar objetos de la base de datos
-   Evaluar valores escalares y obtener una parte de los datos
-   Ejecutar lógica empresarial cuando se cambia una propiedad y realizar un seguimiento de las modificaciones en los objetos
-   Actualizar objetos y revertir cambios

## CRUD en XPO

Cuando una aplicación XAF utiliza XPO, se crea un  [XPObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Xpo.XPObjectSpace). Internamente, utiliza un  [UnitOfWork](https://docs.devexpress.com/XPO/DevExpress.Xpo.UnitOfWork)  para crear, actualizar y eliminar objetos de negocio. Desde un , utilice la propiedad  [XPObjectSpace.Session](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Xpo.XPObjectSpace.Session)  para acceder a una instancia. `XPObjectSpace``UnitOfWork`

Al crear un nuevo objeto de negocio XPO, la 's se pasa al constructor de clase empresarial. Puede utilizar la propiedad  [Session](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentBase.Session)  para acceder a la instancia pasada en una clase empresarial. Utilice esta instancia para cargar y crear objetos de negocio en clases de negocio:  [Create-Read-Update-Delete (CRUD).](https://docs.devexpress.com/XPO/2025/crud) `XPObjectSpace``UnitOfWork``UnitOfWork`

Cuando se crea un nuevo, también se crea uno nuevo. An puede crear un nuevo , por ejemplo, al llamar al método  [IObjectSpace.Refresh.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Refresh)  Esto  [se conecta a una capa de datos o capa de objeto](https://docs.devexpress.com/XPO/2123/connect-to-a-data-store)  que corresponde al  [ObjectSpaceProvider](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceProvider)  actual.`XPObjectSpace``UnitOfWork``XPObjectSpace``UnitOfWork``UnitOfWork`

## CRUD en EF Core

Dentro de una clase de negocio EF Core, implemente la interfaz  [IObjectSpaceLink](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink)  en la clase. XAF asigna automáticamente una instancia de Object Space a la propiedad. Para la manipulación de datos en las clases empresariales de EF Core, use las API de espacio de objetos asignadas enumeradas en los temas anteriores.`IObjectSpaceLink.ObjectSpace`.


# Crear un nuevo objeto

## API útil

Puede utilizar los siguientes métodos de espacio de objetos para crear un nuevo objeto:

- [`IObjectSpace.CreateObject`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CreateObject(System.Type))
Crea un objeto del tipo especificado.

- [`IObjectSpace.CreateObject<ObjectType>`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CreateObject--1)
Crea un objeto del tipo designado por el parámetro de tipo genérico especificado.

- [`IObjectSpace.IsNewObject`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.IsNewObject(System.Object))
Indica si se ha creado un objeto especificado pero no se ha guardado en la base de datos.

- [`IObjectSpace.CommitChanges`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CommitChanges)
Guarda en la base de datos todos los cambios realizados en los objetos persistentes que pertenecen al espacio de objetos actual.

## En un controlador (la técnica independiente de ORM)

1.  Cree un nuevo controlador de vistas en un proyecto de módulo (por ejemplo, en  _MySolution.Module_).
2.  Utilice la propiedad  **ViewController.ObjectSpace**  para tener acceso a un espacio de objetos para operaciones compatibles con datos.
3.  Utilice los métodos del Espacio de objetos para crear un nuevo objeto.
4.  Llame al método  [CommitChanges()](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CommitChanges)  para guardar los cambios.

### Ejemplo 1

El siguiente controlador contiene la acción  **AddTask**  que crea un nuevo objeto  **Task**:

**Archivo**:  _MySolution.Module\Controllers\TaskViewController.cs(.vb)._



```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl;
// ...
public class TaskViewController : ObjectViewController<ListView, Task> {
    public TaskViewController() {
        SimpleAction addTaskAction = new SimpleAction(this, "AddTask", PredefinedCategory.Edit);
        addTaskAction.Execute += AddTaskAction_Execute;
    }
    private void AddTaskAction_Execute(object sender, SimpleActionExecuteEventArgs e) {
        Task task = ObjectSpace.CreateObject<Task>();
        task.Subject = "Demo Task";
        View.CollectionSource.Add(task);
        ObjectSpace.CommitChanges();
        View.Refresh();
    }
}

```

### Ejemplo 2

El siguiente control Controller contiene la acción  **AddTask**  que agrega un nuevo objeto  **Task**  **a la colección**  **Employee's Tasks**. Este controlador se activa para la vista de detalles del  **empleado**  y tiene acceso a la vista de lista de  **tareas**  anidada, tal como se describe en el tema siguiente:  [Cómo: Obtener acceso a la vista de detalles maestra y al entorno de vista de lista anidada.](https://docs.devexpress.com/eXpressAppFramework/113161/ui-construction/ways-to-access-ui-elements-and-their-controls/how-to-access-master-detail-view-and-nested-list-view-environment)

**Archivo**:  _MySolution.Module\Controllers\EmployeeViewController.cs(.vb)._


```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl;
using DevExpress.ExpressApp.Editors;
// ...
public class EmployeeViewController : ObjectViewController<DetailView, Employee> {
    public EmployeeViewController() {
        SimpleAction addTaskAction = new SimpleAction(this, "AddTask", PredefinedCategory.Edit);
        addTaskAction.Execute += AddTaskAction_Execute;
    }
    private void AddTaskAction_Execute(object sender, SimpleActionExecuteEventArgs e) {
        ListPropertyEditor listPropertyEditor = View.FindItem(nameof(Employee.Tasks)) as ListPropertyEditor;
        IObjectSpace os = listPropertyEditor.ListView.ObjectSpace;
        Task task = os.CreateObject<Task>();
        task.Subject = "Demo Task";
        listPropertyEditor.ListView.CollectionSource.Add(task);
        os.CommitChanges();
        listPropertyEditor.ListView.Refresh();
    }
}

```

## En una clase ejecutiva XPO

En una clase empresarial XPO, utilice el constructor de clase empresarial necesario para crear un nuevo objeto y pasar la  [sesión](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentBase.Session)  del objeto actual como parámetro constructor. Puede hacerlo en el método  **AfterConstruction**  reemplazado.

El siguiente fragmento  **de código**  muestra cómo inicializar las propiedades de referencia  **Employee's Address1**  y  **Manager**  con objetos nuevos y existentes:

**Archivo**:  _MySolution.Module\BusinessObjects\Contact.cs(.vb)_



```csharp
using DevExpress.Data.Filtering;
using DevExpress.Persistent.BaseImpl;
using DevExpress.Xpo;
// ...
public class Employee : Person {
    //...
    public override void AfterConstruction() {
        base.AfterConstruction();
        Address1 = new Address(Session);
        Address1.Country = Session.FindObject<Country>(CriteriaOperator.Parse("Name = 'USA'"));
        if(Address1.Country == null) {
            Address1.Country = new Country(Session);
            Address1.Country.Name = "USA";
        }
        Manager = Session.FindObject<Employee>(CriteriaOperator.Parse(
            "FirstName = 'John' && LastName = 'Doe'"));
    }
}

```

## En una clase Business EF Core

1.  Las clases persistentes de EF Core implementan la interfaz  [IObjectSpaceLink](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink)  en tiempo de ejecución.
2.  Convierta un objeto persistente en la interfaz y obtenga el valor de la propiedad  [ObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink.ObjectSpace).`IObjectSpaceLink`
3.  Utilice los métodos  [ObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink.ObjectSpace)  para crear un nuevo objeto.

El siguiente fragmento de código muestra cómo inicializar la propiedad  **de referencia Address1**  con un objeto nuevo o existente:

**Archivo**:  _MySolution.Module\BusinessObjects\Employee.cs_



```csharp
using DevExpress.Data.Filtering;
using DevExpress.ExpressApp;
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl.EF;
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace YourSolutionName.Module.BusinessObjects;
[DefaultClassOptions]
public class Employee : IXafEntityObject {
    [Key]
    public virtual Guid ID { get; set; }

    public virtual string Manager { get; set; }
    public void OnCreated() {
        // ...
        var address = ObjectSpace.FindObject<Address>(CriteriaOperator.FromLambda<Address>(a => a.Country == "USA"));
        if(address == null) {
            address = ObjectSpace.CreateObject<Address>();
            address.Country = "USA";
        }
        Address1 = address;
    }
    public virtual Address Address1 { get; set; }
    public void OnLoaded() { }
    public void OnSaving() { }
    public IObjectSpace ObjectSpace {
        get {
            return ((IObjectSpaceLink)this).ObjectSpace;
        }
    }
}
[DefaultClassOptions]
[DefaultProperty(nameof(Country))]
public class Address : BaseObject {
    public virtual string Country { get; set; }
    // ...
}
// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

Como alternativa, puede heredar la clase de la clase  **DevExpress.Persistent.BaseImpl.EF.BaseObject**  de la siguiente manera:


```csharp
using DevExpress.Data.Filtering;
using DevExpress.ExpressApp;
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl.EF;
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace YourSolutionName.Module.BusinessObjects;
[DefaultClassOptions]
public class Employee : BaseObject {
    public virtual string Manager { get; set; }
    public override void OnCreated() {
        // ...
        var address = ObjectSpace.FindObject<Address>(CriteriaOperator.FromLambda<Address>(a => a.Country == "USA"));
        if(address == null) {
            address = ObjectSpace.CreateObject<Address>();
            address.Country = "USA";
        }
        Address1 = address;
    }
    public virtual Address Address1 { get; set; }

}
[DefaultClassOptions]
[DefaultProperty(nameof(Country))]
public class Address : BaseObject {
    public virtual string Country { get; set; }
    // ...
}


// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.
```


# Cargar objetos

En la lógica empresarial, es posible que necesite recuperar otro objeto o una colección de objetos a valores calculados en función de las propiedades de ese objeto. Puede implementar la lógica para obtener un objeto existente en un Controller o en una clase empresarial.

## Cargar objetos en un controlador

### API útil

**Espacio de objetos expone los métodos siguientes para buscar un objeto existente.**

- [`IObjectSpace.FirstOrDefault<ObjectType>`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.FirstOrDefault.overloads)
Busca el primer objeto que coincida con la expresión lambda especificada. El parámetro genérico determina el tipo del objeto.

- [`IObjectSpace.FindObject`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.FindObject.overloads)
Busca el primer objeto que coincida con los criterios especificados y sea del tipo especificado.

- [`IObjectSpace.FindObject<ObjectType>`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.FindObject.overloads)
Busca el primer objeto que coincida con los criterios especificados. El tipo del objeto se designa mediante el parámetro de tipo genérico especificado.

- [`IObjectSpace.GetObject`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObject(System.Object))
Recupera un objeto que corresponde a un contenedor  [IObjectRecord](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectRecord)  u objeto de otro espacio de objetos.

- [`IObjectSpace.GetObjectByKey`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectByKey(System.Type-System.Object))
Devuelve el objeto persistente que tiene el valor especificado para su propiedad key.

- [`IObjectSpace.GetObjectByKey<ObjectType>`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectByKey--1(System.Object))
Devuelve un objeto persistente del tipo designado por el parámetro de tipo genérico especificado, con el valor especificado para su propiedad key.

- [`IObjectSpace.GetObjectByHandle`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectByHandle(System.String))
Devuelve el objeto con el identificador especificado.

- [`IObjectSpace.IsObjectFitForCriteria`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.IsObjectFitForCriteria.overloads)
Especifica si el objeto especificado cumple los criterios especificados.

----------

**Los siguientes métodos de espacio de objetos devuelven una colección de objetos.**

- [`IObjectSpace.GetObjects`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjects.overloads)
Recupera objetos del tipo especificado del espacio de objetos actual. Devuelve una colección  **IList**.

- [`IObjectSpace.GetObjects<T>`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjects.overloads)
Recupera objetos del tipo especificado del espacio de objetos actual. Devuelve una colección  **IList**.

- [`IObjectSpace.CreateCollection`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CreateCollection.overloads)
Crea e inicializa una colección de objetos del tipo especificado, filtrados según los criterios especificados y ordenados según la lista de ordenación especificada.

- [`IObjectSpace.GetObjectsQuery<T>`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectsQuery--1(System.Boolean))
Obtiene una estructura de datos consultable que proporciona funcionalidad para evaluar consultas en un tipo de objeto de negocio específico.

En el ejemplo siguiente se utiliza una  [acción parametrizada](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Actions.ParametrizedAction)  para buscar una persona por  **apellido**  y, a continuación, se asignan todas las tareas aplazadas a esa  **persona**.


```csharp
using System.Collections;
using DevExpress.Data.Filtering;
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;
using DevExpress.Persistent.Base;
using DevExpress.Persistent.Base.General;
using DevExpress.Persistent.BaseImpl;
// ...
public class AssignTasksController : ObjectViewController<ListView, MainDemo.Module.BusinessObjects.DemoTask> {
    public AssignTasksController() {
        ParametrizedAction assignTasksAction = new ParametrizedAction(
            this, "AssignTasks", PredefinedCategory.Edit, typeof(string));
        assignTasksAction.Execute += AssignTasksAction_Execute;
    }
    private void AssignTasksAction_Execute(object sender, ParametrizedActionExecuteEventArgs e) {
        IObjectSpace objectSpace = View.ObjectSpace;
        string personParamValue = e.ParameterCurrentValue as string;
        CriteriaOperator personCriteria = CriteriaOperator.Parse("Contains([LastName], ?)", personParamValue);
        Person person = (Person)objectSpace.FindObject(typeof(Person), personCriteria);
        if(person != null) {
            CriteriaOperator taskCriteria = CriteriaOperator.Parse("[Status] = ?", TaskStatus.Deferred);
            IList tasks = objectSpace.GetObjects(
                typeof(MainDemo.Module.BusinessObjects.DemoTask), taskCriteria);
            foreach(MainDemo.Module.BusinessObjects.DemoTask task in tasks) {
                task.AssignedTo = person;
            }
        }
    }
}

```

Puede utilizar el método  [IObjectSpace.GetObjectsQuery<T>](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectsQuery--1(System.Boolean))  para cargar objetos. Permite usar expresiones  [LINQ](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/) para especificar la solicitud necesaria.



```csharp
IQueryable<Product> query = this.ObjectSpace.GetObjectsQuery<Product>();

```

La lógica empresarial puede depender de varios registros de una base de datos. En este escenario, utilice el método  [IObjectSpace.GetObjectsCount](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectsCount(System.Type-DevExpress.Data.Filtering.CriteriaOperator))  para obtener un número de registros sin obtener registros.

## En un modelo de datos (en una clase empresarial XPO)

Una sesión XPO disponible a través de la propiedad  [Session](https://docs.devexpress.com/XPO/DevExpress.Xpo.PersistentBase.Session)  en una clase empresarial implementa  [métodos](https://docs.devexpress.com/XPO/DevExpress.Xpo.Session._methods)  para buscar y leer un objeto de una base de datos.

El siguiente fragmento  **de código**  muestra cómo inicializar las propiedades de referencia  **Employee's Address1**  y  **Manager**  con objetos nuevos y existentes:

**Archivo**:  _MySolution.Module\BusinessObjects\Contact.cs(.vb)_


```csharp
using DevExpress.Data.Filtering;
using DevExpress.Persistent.BaseImpl;
using DevExpress.Xpo;
// ...
public class Employee : Person {
    //...
    public override void AfterConstruction() {
        base.AfterConstruction();
        Address1 = new Address(Session);
        Address1.Country = Session.FindObject<Country>(CriteriaOperator.Parse("Name = 'USA'"));
        if(Address1.Country == null) {
            Address1.Country = new Country(Session);
            Address1.Country.Name = "USA";
        }
        Manager = Session.FindObject<Employee>(CriteriaOperator.Parse(
            "FirstName = 'John' && LastName = 'Doe'"));
    }
}

```

Para obtener una colección de objetos en una clase empresarial XPO, cree una instancia de un nuevo  [XPCollection](https://docs.devexpress.com/XPO/DevExpress.Xpo.XPCollection).



```csharp
using DevExpress.Persistent.BaseImpl;
using DevExpress.Xpo;
// ...
public class Order : BaseObject {    
    private XPCollection<Accessory> fAvailableAccessories;
    public XPCollection<Accessory> AvailableAccessories {
        get {
            if (fAvailableAccessories == null) {
                fAvailableAccessories = new XPCollection<Accessory>(Session);
            }
            return fAvailableAccessories;
        }
    }
}

public class Accessory : BaseObject { }

```

Es posible usar los métodos  [Session](https://docs.devexpress.com/XPO/DevExpress.Xpo.Session)  como  [GetObjects](https://docs.devexpress.com/XPO/DevExpress.Xpo.Session.GetObjects(XPClassInfo--CriteriaOperator--SortingCollection--Int32--Boolean--Boolean))  para recuperar una colección de objetos.

## En una clase Business EF Core

Dentro de una clase de negocio EF Core, implemente la interfaz  [IObjectSpaceLink](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpaceLink)  en la clase. XAF asignará automáticamente una instancia de Object Space a la propiedad. Utilice las API de espacio de objetos asignadas enumeradas anteriormente para obtener un objeto existente.`IObjectSpaceLink.ObjectSpace`

El siguiente fragmento de código muestra cómo inicializar la propiedad  **de referencia Address1**  con un objeto nuevo o existente:

**Archivo**:  _MySolution.Module\BusinessObjects\Employee.cs_


```csharp
using DevExpress.Data.Filtering;
using DevExpress.ExpressApp;
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl.EF;
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace YourSolutionName.Module.BusinessObjects;
[DefaultClassOptions]
public class Employee : IXafEntityObject {
    [Key]
    public virtual Guid ID { get; set; }

    public virtual string Manager { get; set; }
    public void OnCreated() {
        // ...
        var address = ObjectSpace.FindObject<Address>(CriteriaOperator.FromLambda<Address>(a => a.Country == "USA"));
        if(address == null) {
            address = ObjectSpace.CreateObject<Address>();
            address.Country = "USA";
        }
        Address1 = address;
    }
    public virtual Address Address1 { get; set; }
    public void OnLoaded() { }
    public void OnSaving() { }
    public IObjectSpace ObjectSpace {
        get {
            return ((IObjectSpaceLink)this).ObjectSpace;
        }
    }
}
[DefaultClassOptions]
[DefaultProperty(nameof(Country))]
public class Address : BaseObject {
    public virtual string Country { get; set; }
    // ...
}
// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

Como alternativa, puede heredar la clase de la clase  **DevExpress.Persistent.BaseImpl.EF.BaseObject**  de la siguiente manera:


```csharp
using DevExpress.Data.Filtering;
using DevExpress.ExpressApp;
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl.EF;
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace YourSolutionName.Module.BusinessObjects;
[DefaultClassOptions]
public class Employee : BaseObject {
    public virtual string Manager { get; set; }
    public override void OnCreated() {
        // ...
        var address = ObjectSpace.FindObject<Address>(CriteriaOperator.FromLambda<Address>(a => a.Country == "USA"));
        if(address == null) {
            address = ObjectSpace.CreateObject<Address>();
            address.Country = "USA";
        }
        Address1 = address;
    }
    public virtual Address Address1 { get; set; }

}
[DefaultClassOptions]
[DefaultProperty(nameof(Country))]
public class Address : BaseObject {
    public virtual string Country { get; set; }
    // ...
}


// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.
```


# Guardar objetos en la base de datos


Las tareas empresariales comunes requieren lógica adicional antes de almacenar los cambios en una base de datos. Por ejemplo, es posible que necesite obtener objetos que están a punto de guardarse y escribir información adicional en ellos o guardar objetos de forma personalizada.


## En un controlador

**API útil**

![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/6f922ece-2924-4bb0-b4e2-512e04fe29a7)
![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/872e4bbb-49ae-413c-b117-f86ae30cd346)
![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/61399049-1e1c-4c04-b527-fd346b3601ad)

XAF guarda los cambios en una vista en las siguientes situaciones:

-   Se ejecuta la acción Guardar,  **Guardar y nuevo**, o  **Guardar y cerrar**.
-   En una ventana emergente, se ejecuta la acción Aceptar y la propiedad  [DialogController.SaveOnAccept es .](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.DialogController.SaveOnAccept) `true`

En las aplicaciones de XAF WinForms, puede controlar si XAF guarda o revierte automáticamente los cambios al cambiar el objeto actual o cerrar una vista. La propiedad  [ModificationsController.ModificationsHandlingMode](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.ModificationsController.ModificationsHandlingMode)  especifica este comportamiento.

### Persistir cambios en el código

Para guardar los cambios en el código, llame al método  [IObjectSpace.CommitChanges.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CommitChanges)


```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;

public class MyViewController : ObjectViewController<DetailView, Department> {
    public MyViewController() {
        var action = new SimpleAction(this, "Change Title and Save changes", DevExpress.Persistent.Base.PredefinedCategory.Save);
        action.Execute += Action_Execute;
    }
    private void Action_Execute(object sender, SimpleActionExecuteEventArgs e) {
        Department department = (Department)View.CurrentObject;
        department.Title = "New Title";
        this.ObjectSpace.CommitChanges();
    }
}

```

### Obtener objetos modificados

Para escribir información adicional en un objeto antes de guardarlo en una base de datos, hágalo en el controlador de eventos  [IObjectSpace.Committing.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Committing)  El código siguiente ilustra esto. Un objeto de negocio tiene la propiedad que almacena información de auditoría en una serie de otros objetos que se cambiaron en la transacción actual.`Employee``Notes`


```csharp
using DevExpress.ExpressApp;
using System.Collections;

public class MyViewController : ObjectViewController<DetailView, Employee> {
    protected override void OnActivated() {
        base.OnActivated();
        ObjectSpace.Committing += ObjectSpace_Committing;
    }
    void ObjectSpace_Committing(object sender, System.ComponentModel.CancelEventArgs e) {
        ICollection collection = ObjectSpace.GetObjectsToSave(false);
        Employee owner = (Employee)View.CurrentObject;
        owner.Notes = string.Format("{0};{1} objects changed", owner.Notes, collection.Count);
    }
}

```

### Guardar objetos de proceso

También es posible guardar los cambios de forma personalizada en el controlador de eventos  [IObjectSpace.CustomCommitChanges.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CustomCommitChanges)  Para evitar que la lógica predeterminada conserve objetos, controle el evento IObjectSpace.Commit y llame al método  [IObjectSpace.RemoveFromModifiedObjects](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.RemoveFromModifiedObjects(System.Object))  para quitar un objeto que se confirma en el controlador de eventos[.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Committing)

El código siguiente muestra cómo guardar manualmente los cambios de colección secundaria realizados en la vista de detalles primaria:


```csharp
using DevExpress.ExpressApp;
using System;
using System.Collections.Generic;
using System.ComponentModel;
using YourSolutionName.Module.BusinessObjects;

namespace YourSolutionName.Module.Controllers {
    public class MyViewController : ObjectViewController<DetailView, Parent> {
        List<Child> detailObjectsCache = new List<Child>();
        protected override void OnActivated() {
            base.OnActivated();
            ObjectSpace.CustomCommitChanges += ObjectSpace_CustomCommitChanges;
            ObjectSpace.Committing += ObjectSpace_Committing;
            ObjectSpace.Committed += ObjectSpace_Committed;
            ObjectSpace.Reloaded += ObjectSpace_Reloaded;
        }
        protected override void OnDeactivated() {
            ObjectSpace.CustomCommitChanges -= ObjectSpace_CustomCommitChanges;
            ObjectSpace.Committing -= ObjectSpace_Committing;
            ObjectSpace.Committed -= ObjectSpace_Committed;
            ObjectSpace.Reloaded -= ObjectSpace_Reloaded;
            base.OnDeactivated();
        }
        void ObjectSpace_Reloaded(object sender, EventArgs e) {
            detailObjectsCache.Clear();
        }
        void ObjectSpace_Committed(object sender, EventArgs e) {
            detailObjectsCache.Clear();
        }
        void ObjectSpace_Committing(object sender, CancelEventArgs e) {
            IObjectSpace os = (IObjectSpace)sender;
            for (int i = os.ModifiedObjects.Count - 1; i >= 0; i--) {
                object item = os.ModifiedObjects[i];
                if (typeof(Child).IsAssignableFrom(item.GetType())) {
                    detailObjectsCache.Add(item as Child);
                    os.RemoveFromModifiedObjects(item);
                }
            }
        }
        void ObjectSpace_CustomCommitChanges(object sender, HandledEventArgs e) {
            // Implement custom logic to save Detail objects here. 
            foreach (Child detailObject in detailObjectsCache) {
                //...  
            }
        }
    }
}

```

>NOTA
Se recomienda controlar estos eventos solo para las vistas raíz. Las vistas anidadas utilizan el espacio de objetos de la vista principal. Como resultado, los eventos se manejan varias veces. Puede especificar el ámbito del controlador como se describe en [Definir el ámbito de los controladores y las acciones](https://docs.devexpress.com/eXpressAppFramework/113103/ui-construction/controllers-and-actions/define-the-scope-of-controllers-and-actions). Alternativamente, puede verificar propiedades como [`View.IsRoot`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.View.IsRoot) y [`IObjectSpace.Owner`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Owner) en controladores de eventos para determinar para qué vista se invoca un controlador.

## En un modelo de datos (en una clase empresarial XPO)

En los objetos de negocio XPO, anule el método de una clase de negocio para realizar lógica adicional al guardar datos. Una tarea común es generar un número incrementado automáticamente o una secuencia. Encuentre un ejemplo de cómo implementar esto en  [XAF - Cómo generar un número secuencial para un objeto persistente dentro de una transacción de base de datos con Entity Framework Core](https://github.com/DevExpress-Examples/XAF_generate-a-sequential-number-for-a-persistent-object-within-a-database-transaction) .`OnSaving`

Tenga en cuenta los siguientes detalles al implementar lógica personalizada con  [el modo integrado](https://docs.devexpress.com/eXpressAppFramework/113436/data-security-and-safety/security-system/security-tiers/2-tier-security-integrated-mode-and-ui-level#integrated-mode)  o  [la seguridad de nivel intermedio](https://docs.devexpress.com/eXpressAppFramework/113439/data-security-and-safety/security-system/security-tiers/middle-tier-security-xpo):

-   Se puede llamar a los métodos y de una clase empresarial varias veces porque el  [modo integrado](https://docs.devexpress.com/eXpressAppFramework/113436/data-security-and-safety/security-system/security-tiers/2-tier-security-integrated-mode-and-ui-level#integrated-mode)  y  [la seguridad de nivel intermedio](https://docs.devexpress.com/eXpressAppFramework/113439/data-security-and-safety/security-system/security-tiers/middle-tier-security-xpo)  utilizan más de un objeto /. Si implementa lógica personalizada en estos métodos, compruebe si ya hay un nuevo valor asignado a una propiedad. Esto le ayuda a evitar resultados incorrectos. En el siguiente artículo se describe cómo hacerlo con XPO:  [XPO Best Practices](https://docs.devexpress.com/XPO/403711/best-practices/xpo-best-practices).`OnSaving``OnDeleting``Session``DbContext`
-   Las vistas detalladas no muestran los cambios realizados en un objeto dentro de una transacción (por ejemplo, un  [número secuencial generado automáticamente para un objeto de negocio XPO), incluso si ha guardado este objeto](https://github.com/DevExpress-Examples/XAF_generate-a-sequential-number-for-a-persistent-object-within-a-database-transaction) en una vista. Estos cambios se realizan únicamente en el servidor y no se pasan automáticamente a la aplicación cliente. Para mostrar estos cambios, vuelva a cargar el objeto. Si desea volver a cargar el objeto en cada operación de guardado, invalide el método de la clase empresarial. En el ejemplo siguiente se muestra cómo reemplazar este método para volver a cargar un objeto en el cliente: `OnSaved`
    

    
    ```csharp
    using DevExpress.Persistent.BaseImpl;
    // ...
    public class DemoObject : BaseObject {
        // ...
        protected override void OnSaved() {
            base.OnSaved();
            // 0 is the default value
            if (Number == 0) {
                Session.Reload(this);
            }
        }
    }
    
    ```
    
-   La propiedad  [Session.DataLayer](https://docs.devexpress.com/XPO/DevExpress.Xpo.Session.DataLayer)  es  _null_  en el archivo . En lugar de , se recomienda utilizar la propiedad  [View.ObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.View.ObjectSpace)  para consultar y cambiar los datos de la base de datos. Esta técnica también se recomienda para aplicaciones no seguras.`Session``DataLayer`
    
    Si esta recomendación no se aplica a su escenario, utilice la propiedad  [Session.ObjectLayer](https://docs.devexpress.com/XPO/DevExpress.Xpo.Session.ObjectLayer)  en lugar de .`DataLayer`
    
    También puede ejecutar código diferente en el servidor y el cliente en función de los valores de la propiedad. En el ejemplo siguiente se muestra cómo hacerlo: `DataLayer``ObjectLayer`

    
    ```csharp
    using DevExpress.ExpressApp.Security.ClientServer;
    using DevExpress.Persistent.BaseImpl;
    // ...
    public class DemoObject : BaseObject {
        // ...
        protected override void OnSaving() { 
            if(Session.DataLayer != null && !(Session.ObjectLayer is SecuredSessionObjectLayer)) { 
                // Server-side code
            } 
            else {  
                // Client-side code 
            } 
            base.OnSaving(); 
        }
    }
    ```

    
# Eliminar objetos de la base de datos


## API útil

- [`IObjectSpace.Delete`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Delete.overloads) 
Elimina los objetos persistentes especificados y sus objetos agregados de la base de datos.

- [`IObjectSpace.IsObjectToDelete`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.IsObjectToDelete(System.Object)) 
Indica si el objeto especificado se ha eliminado pero no se ha confirmado en la transacción actualmente en curso.

- [`IObjectSpace.GetObjectsToDelete`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectsToDelete(System.Boolean)) 
Devuelve una colección de objetos persistentes que se eliminarán cuando se confirme la transacción actual, incluidos los objetos que se eliminarán en las transacciones primarias, opcionalmente.

- [`IObjectSpace.CommitChanges`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CommitChanges) 
Guarda en la base de datos todos los cambios realizados en los objetos persistentes que pertenecen al espacio de objetos actual.

- [`IObjectSpace.IsDeleting`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.IsDeleting) 
Indica si el espacio de objetos actual está a punto de eliminar uno o varios objetos.

- [`Evento IObjectSpace.CustomDeleteObjects`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CustomDeleteObjects)
El método  [`IObjectSpace.Delete`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Delete.overloads)  provoca el evento  **CustomDeleteObjects**. Controle este evento para reemplazar la lógica de eliminación de objetos persistentes predeterminada por lógica personalizada.

- [`IObjectSpace.ObjectDeleting`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.ObjectDeleting)
Se produce cuando los objetos especificados están a punto de eliminarse.

- [`Evento IObjectSpace.ObjectDeleted`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.ObjectDeleted)
Se produce después de que los objetos especificados se hayan eliminado del conjunto de datos.

## En un controlador

1.  Cree un nuevo controlador de vistas en un proyecto de módulo (por ejemplo, en  _MySolution.Module_).
2.  Utilice la propiedad  **ViewController.ObjectSpace**  para tener acceso a un espacio de objetos para operaciones compatibles con datos.
3.  Utilice los métodos del Espacio de objetos para eliminar un objeto.
4.  Llame al método  [CommitChanges()](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CommitChanges)  para guardar los cambios.

El siguiente controlador contiene la acción que elimina las tareas completadas:

**Archivo**:  _MySolution.Module\Controllers\TaskViewController.cs(.vb)._


```csharp
using DevExpress.ExpressApp;
using DevExpress.Persistent.BaseImpl;
using DevExpress.ExpressApp.Actions;
using DevExpress.Persistent.Base;
using DevExpress.Data.Filtering;
using DevExpress.Persistent.Base.General;
using System.Collections.Generic;
// ...
public class TaskViewController : ObjectViewController<ListView, Task> {
    public TaskViewController() {
        SimpleAction deleteCompletedTasksAction = 
            new SimpleAction(this, "Delete completed tasks", PredefinedCategory.Edit);
        deleteCompletedTasksAction.Execute += DeleteCompletedTasksAction_Execute;
    }
    private void DeleteCompletedTasksAction_Execute(object sender, SimpleActionExecuteEventArgs e) {
        CriteriaOperator completedTasksCriteria = 
            CriteriaOperator.FromLambda<Task>(t => t.Status == TaskStatus.Completed);
        IList<Task> completedTasks = ObjectSpace.GetObjects<Task>(completedTasksCriteria);
        ObjectSpace.Delete(completedTasks);
        ObjectSpace.CommitChanges();
    }
}

```

### Ejecutar lógica personalizada en lugar de eliminar objetos

1.  Cree un nuevo controlador de vistas en un proyecto de módulo (por ejemplo, en  _MySolution.Module_).
2.  En el método  **OnActivated**  reemplazado, suscríbase al evento  [CustomDeleteObjects](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CustomDeleteObjects).
3.  En el controlador de eventos, implemente la lógica personalizada y establezca la propiedad  **CustomDeleteObjectsEventArgs.Handled**  en  **true**  para evitar la ejecución de la lógica predeterminada.

El controlador siguiente especifica la propiedad  **IsMarkedAsDeleted**  de  **CustomDeleteObjectsEventArgs.Objects**  en lugar de quitarlos:

**Archivo**:  _MySolution.Module\Controllers\CustomDeleteObjectController.cs(.vb)._


```csharp
using DevExpress.ExpressApp;
// ...
public class CustomDeleteObjectController : ObjectViewController<DetailView, Employee> {
    protected override void OnActivated() {
        base.OnActivated();
        ObjectSpace.CustomDeleteObjects += ObjectSpace_CustomDeleteObjects;
    }
    private void ObjectSpace_CustomDeleteObjects(object sender, CustomDeleteObjectsEventArgs e) {
        foreach (object deletingObject in e.Objects) {
            Employee employee = ObjectSpace.GetObject(deletingObject) as Employee;
            // IsMarkedAsDeleted is a custom Employee's property
            employee.IsMarkedAsDeleted = true;
        }
        e.Handled = true;
    }
    protected override void OnDeactivated() {
        ObjectSpace.CustomDeleteObjects -= ObjectSpace_CustomDeleteObjects;
        base.OnDeactivated();
    }
}

```

>NOTA
>-   Este evento sólo se produce cuando se utilizan los métodos de  [IObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace)  para eliminar objetos.
>-   XPO tiene una funcionalidad similar lista para usar: [eliminación diferida e inmediata de objetos](https://docs.devexpress.com/XPO/2026/crud/deleting-persistent-objects).

## En una clase ejecutiva XPO

En la clase empresarial XPO, puede realizar lógica empresarial adicional en el método  **XPBaseObject.OnDeleting**  reemplazado. El siguiente fragmento de código lo demuestra. Cuando se tiene una asociación de uno a varios entre dos clases de negocio XPO y se elimina un objeto de un lado de la asociación, la propiedad reference de un objeto del lado muchos sigue conteniendo la clave de objeto eliminada. Puede establecer este valor de propiedad de referencia en  _null_  (_Nothing_  en VB) como se muestra a continuación.


```csharp
using DevExpress.Persistent.BaseImpl;
// ...
public class Employee : Person {
    // ...
    protected override void OnDeleting() {
        base.OnDeleting();
        foreach (object obj in Session.CollectReferencingObjects(this)) {
            if (Session.GetClassInfo(obj).ClassType == typeof(DemoTask)) {
                ((DemoTask)obj).Notes += 
                string.Format("The assigned employee was removed: {0}.\r\n", FullName);
            }
        }
    }
}

```


# Evaluar valores escalares y obtener una parte de los datos

La lógica empresarial personalizada puede implicar un número limitado de propiedades de clase empresarial o un número limitado de objetos de negocio. Es posible que deba evaluar un valor escalar calculado en el nivel de base de datos sin obtener objetos reales. Para mejorar el rendimiento y el consumo de memoria, es posible obtener el valor de la propiedad de clase empresarial y los valores calculados necesarios para la tarea.

## Usar LINQ

Para obtener datos en pequeñas porciones o evaluar valores escalares, use el método  [IObjectSpace.GetObjectsQuery](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjectsQuery--1(System.Boolean))  para obtener un objeto  [IQueryable<T>](https://docs.microsoft.com/dotnet/api/system.linq.iqueryable-1) y aplicarle una expresión  [LINQ](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/).

### Obtener una parte de los datos de una base de datos

Solo puede obtener un número necesario de primeros registros. Para obtenerlos, utilice el método  [Take](https://docs.microsoft.com/en-us/dotnet/api/system.linq.queryable.take?view=net-6.0#System_Linq_Queryable_Take__1_System_Linq_IQueryable___0__System_Int32_).


```csharp
IQueryable<Product> query = this.ObjectSpace.GetObjectsQuery<Product>();
List<Product> top500 = query.Take(500).ToList();

```

### Obtener solo ciertas propiedades de una base de datos

Para obtener solo propiedades concretas de su clase empresarial, use  [Operaciones  de proyección](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/projection-operations)  para especificar qué propiedades necesita obtener.

En el ejemplo siguiente se obtienen las propiedades  **ID**  y  **Name**  de la clase de negocio  **Product**  y se calcula la cantidad total de productos vendidos de la propiedad de colección  **Sales**.



```csharp
IQueryable<Product> query = this.ObjectSpace.GetObjectsQuery<Product>();
var list = query.Select(p => new { p.ID, p.Name, Total = p.Sales.Sum(s => s.Count * s.Price) }).ToList();
int id = list[0].ID;
decimal total = list[0].Total;

```

Este código genera la siguiente consulta SQL para obtener los datos necesarios que no obtienen las propiedades restantes de la clase de negocio  **Product**.



```sql
SELECT N0."ID",
       N0."Name",
  (SELECT sum((Cast((N1."Count") AS MONEY) * N1."Price")) AS Res0
   FROM "dbo"."Sale" N1
   WHERE ((N0."ID" = N1."Product")
          AND N1."GCRecord" IS NULL))
FROM "dbo"."Product" N0

```

### Evaluar un valor escalar

Puede usar  [las operaciones  de proyección](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/projection-operations)  de LINQ para obtener un valor escalar. En el ejemplo siguiente se muestra cómo calcular un número de  **tareas**  completadas de un  **empleado**  actual.



```csharp
Employee employee = (Employee)View.CurrentObject;
IQueryable<Employee> query = ObjectSpace.GetObjectsQuery<Employee>();
int result = query.Where(e => e.ID == employee.ID).Select(e => e.Tasks.Where(t => t.Status == Status.Completed).Count()).Single();

```

This expression produces the following SQL query to calculate a scalar value at the database level.



```sql
SELECT top 2
  (SELECT count(*) AS Res0
   FROM "dbo"."Task" N1
   WHERE ((N0."ID" = N1."Employee")
          AND (N1."Status" = 0)))
FROM "dbo"."Employee" N0
WHERE (N0."OID" = 1)

```

## Usar la API de espacio de objetos

### Get a Portion of Data from a Database

When you get a collection of objects using the  [IObjectSpace.GetObjects](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.GetObjects.overloads)  method, use the  [IObjectSpace.SetTopReturnedObjectsCount](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.SetTopReturnedObjectsCount(System.Object-System.Int32))  method to limit a number of objects to return.


```csharp
IList objects = objectSpace.GetObjects(typeof(Product));
objectSpace.SetTopReturnedObjectsCount(objects, 500);

```

### Obtener solo ciertas propiedades de una base de datos

Use  [XafDataView](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafDataView)  to fetch particular properties of a business class. Use the  [IObjectSpace.CreateDataView](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.CreateDataView.overloads)  method to create an  instance. The  [XafDataView.Expressions](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafDataView.Expressions)  list specifies what properties and  [expressions](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax)  to fetch.`XafDataView`

The following example creates an  instance to fetch the  **ID**  and  **Name**  properties of the  **Product**  business class and calculated the total amount of sold products from the  **Sales**  collection property.`XafDataView`



```csharp
XafDataView dataView = (XafDataView)objectSpace.CreateDataView(
    typeof(Product), "ID;Name;Sales.Sum([Count] * Price)", null, null);

```

After this, access a data record by  [its index](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafDataView.Item(System.Int32)). An  [XafDataViewRecord](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafDataViewRecord)  object is returned.


```csharp
XafDataViewRecord dataRecord = dataView[0];

```

To get a column value from a data record, use the  [XafDataViewRecord.Item](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafDataViewRecord.Item.overloads)  property as follows:



```csharp
int id = dataView[0]["ID"];
int total = dataView[0]["Sales.Sum(Count * Price)"];

```

### Evaluar un valor escalar

Use the  [IObjectSpace.Evaluate](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Evaluate(System.Type-DevExpress.Data.Filtering.CriteriaOperator-DevExpress.Data.Filtering.CriteriaOperator))  method to calculate an  [expression](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax). The following example illustrates how to calculate a number of completed  **Tasks**  of a current  **Employee**.



```csharp
CriteriaOperator expression = CriteriaOperator.Parse("Tasks[Status = 'Completed'].Count()");
CriteriaOperator criteria = new BinaryOperator(nameof(Employee.ID), ObjectSpace.GetKeyValue(View.CurrentObject));
int result = (int)ObjectSpace.Evaluate(typeof(Employee), expression, criteria);

```

# Ejecutar lógica de negocios cuando se cambia una propiedad


## En un controlador

### Actualizar una propiedad calculada cuando se cambia otra propiedad

Para ejecutar la lógica empresarial cuando se cambia una propiedad de clase empresarial, ejecútela en el controlador de eventos  [IObjectSpace.ObjectChanged.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.ObjectChanged)

En el ejemplo siguiente se muestra cómo actualizar la propiedad  **TotalPrice**  de un objeto  **Sale**  cuando se cambia su propiedad  **Count**.

```csharp
using DevExpress.ExpressApp;

public class MyViewController : ObjectViewController<ObjectView, Sale> {
    protected override void OnActivated() {
        base.OnActivated();
        ObjectSpace.ObjectChanged += ObjectSpace_ObjectChanged;
    }

    private void ObjectSpace_ObjectChanged(object sender, ObjectChangedEventArgs e) {
        if (e.PropertyName == nameof(Sale.Count)) {
            Sale sale = (Sale)e.Object;
            sale.TotalPrice = sale.Count * sale.Price;
        }
    }
    protected override void OnDeactivated() {
        base.OnDeactivated();
        ObjectSpace.ObjectChanged -= ObjectSpace_ObjectChanged;
    }
}

```

>NOTA
Los objetos de negocio deben implementar la interfaz  [`INotifyPropertyChanged`  ](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged). Consulte este artículo para obtener más información: [La importancia de las notificaciones de cambio de propiedad para las actualizaciones automáticas de la interfaz de usuario](https://docs.devexpress.com/eXpressAppFramework/117395/business-model-design-orm/property-changed-event-in-business-classes).

Para los cambios de objeto que no se pueden rastrear a través de mecanismos de notificación expuestos por la capa de datos, se debe llamar al método  [`IObjectSpace.SetModified`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.SetModified.overloads)  después de cambiar un objeto. Este método agrega el objeto pasado como parámetro  _obj_  a la lista de objetos que se van a confirmar.

### Marcar una vista como modificada

La lógica empresarial puede cambiar indirectamente un objeto View actual. Por ejemplo, puede modificar una propiedad de colección de una clase de negocio en código. Esto no habilitará la acción Guardar en la vista detallada de la clase empresarial para confirmar los cambios. Llame al método  [`IObjectSpace.SetModified`](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.SetModified.overloads)  y pase el objeto View actual como parámetro.

En el ejemplo siguiente se borra la colección Tasks de la vista de detalles de contacto y se marca el objeto Contact como modificado:



```csharp
using System;
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;
using DevExpress.ExpressApp.Editors;
using MySolution.Module.BusinessObjects;
//...
namespace MySolution.Module.Controllers {
    public class ClearEmployeeTasksController : ViewController {
        private SimpleAction ClearTasksAction;
        public ClearEmployeeTasksController() {
            ClearTasksAction = new SimpleAction();
            ClearTasksAction.Execute += new SimpleActionExecuteEventHandler(ClearTasksAction_Execute);
        }

        private void ClearTasksAction_Execute(Object sender, SimpleActionExecuteEventArgs e) {
            while(((Employee)View.CurrentObject).Tasks.Count > 0) {
                ((Employee)View.CurrentObject).Tasks.Remove(((Employee)View.CurrentObject).Tasks[0]);
            }
            ObjectSpace.SetModified(View.CurrentObject);
        }
    }
}

```

### Loop Through Modified Objects

It’s possible to traverse through all modified objects in an Object Space to process them in a custom way. The  [IObjectSpace.ModifiedObjects](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.ModifiedObjects)  property returns a collection of modified objects.

The following code shows how to manually save child collection changes made in the parent Detail View:



```csharp
using DevExpress.ExpressApp;
using System;
using System.Collections.Generic;
using System.ComponentModel;
using YourSolutionName.Module.BusinessObjects;

namespace YourSolutionName.Module.Controllers {
    public class MyViewController : ObjectViewController<DetailView, Parent> {
        List<Child> detailObjectsCache = new List<Child>();
        protected override void OnActivated() {
            base.OnActivated();
            ObjectSpace.CustomCommitChanges += ObjectSpace_CustomCommitChanges;
            ObjectSpace.Committing += ObjectSpace_Committing;
            ObjectSpace.Committed += ObjectSpace_Committed;
            ObjectSpace.Reloaded += ObjectSpace_Reloaded;
        }
        protected override void OnDeactivated() {
            ObjectSpace.CustomCommitChanges -= ObjectSpace_CustomCommitChanges;
            ObjectSpace.Committing -= ObjectSpace_Committing;
            ObjectSpace.Committed -= ObjectSpace_Committed;
            ObjectSpace.Reloaded -= ObjectSpace_Reloaded;
            base.OnDeactivated();
        }
        void ObjectSpace_Reloaded(object sender, EventArgs e) {
            detailObjectsCache.Clear();
        }
        void ObjectSpace_Committed(object sender, EventArgs e) {
            detailObjectsCache.Clear();
        }
        void ObjectSpace_Committing(object sender, CancelEventArgs e) {
            IObjectSpace os = (IObjectSpace)sender;
            for (int i = os.ModifiedObjects.Count - 1; i >= 0; i--) {
                object item = os.ModifiedObjects[i];
                if (typeof(Child).IsAssignableFrom(item.GetType())) {
                    detailObjectsCache.Add(item as Child);
                    os.RemoveFromModifiedObjects(item);
                }
            }
        }
        void ObjectSpace_CustomCommitChanges(object sender, HandledEventArgs e) {
            // Implement custom logic to save Detail objects here. 
            foreach (Child detailObject in detailObjectsCache) {
                //...  
            }
        }
    }
}

```

### Track When a View is Changed

If your business logic should be executed after a user starts changing an object or after a user saves changes, handle the  [IObjectSpace.ModifiedChanged](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.ModifiedChanged)  event to catch these moments. For example, you can disable an Action if a user changes an object.

The following code disables an  [Action](https://docs.devexpress.com/eXpressAppFramework/112622/ui-construction/controllers-and-actions/actions)  when business objects in the current  [Object Space](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space)  are changed.



```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;
using System;
// ...
public class ViewController1 : ViewController {
    SimpleAction action1;
    public ViewController1() {
        action1 = new SimpleAction(this, "Action1", DevExpress.Persistent.Base.PredefinedCategory.View);
    }
    protected override void OnActivated() {
        base.OnActivated();
        ObjectSpace.ModifiedChanged += ObjectSpace_ModifiedChanged;
        UpdateActionState();
    }
    void ObjectSpace_ModifiedChanged(object sender, EventArgs e) {
        UpdateActionState();
    }
    protected virtual void UpdateActionState() {
        action1.Enabled["ObjectSpaceIsModified"] = !ObjectSpace.IsModified;
    }
    protected override void OnDeactivated() {
        base.OnDeactivated();
        ObjectSpace.ModifiedChanged -= ObjectSpace_ModifiedChanged;
    }
}

```

## In a Data Model

A common task in business objects is to create a calculated property which value depends on another persistent property. For example, you have the  **Customer**  and  **Order**  business classes that have a one-to-many relationship between them. The  **Order**  business class implements the  **Price**  property. In the  **Customer**  business class, add a calculated property (**Total**) that returns the total price of all customer’s orders.

### EF Core

```csharp
using System.Linq;
using System.Collections.ObjectModel;
using System.ComponentModel.DataAnnotations;
using DevExpress.Persistent.BaseImpl.EF;

namespace MySolution.Module.BusinessObjects {
    public class Customer : BaseObject {
        public decimal Total {
            get {
                return Orders.Sum(c => c.Price);
            }
        }

        public virtual IList<Order> Orders { get; set; } = new ObservableCollection<Order>();
    }

    public class Order : BaseObject { 
        public virtual decimal Price { get; set; }
        public virtual Customer Customer { get; set; }
    }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

### XPO
```csharp
using DevExpress.Persistent.BaseImpl;
using DevExpress.Xpo;
using System.Linq;

namespace MySolution.Module.BusinessObjects {
    public class Customer : BaseObject {
        public Customer(Session session) : base(session) { }

        public decimal Total {
            get {
                return Orders.Sum(c => c.Price);
            }
        }

        [Association]
        public XPCollection<Order> Orders {
            get {
                return GetCollection<Order>(nameof(Orders));
            }
        }
    }

    public class Order : BaseObject { 
        public Order(Session session) : base(session) { }

        decimal price;
        Customer fCustomer;

        public decimal Price {
            get => price;
            set => SetPropertyValue(nameof(Price), ref price, value);
        }

        [Association]
        public Customer Customer {
            get => fCustomer;
            set => SetPropertyValue(nameof(Customer), ref fCustomer, value);
        }
    }
}
```


This code calculates the  **Total**  property value when a  **Customer**  object is loaded. To notify bound editors that the  **Total**  property value changed, subscribe to changes of the  **Orders**  collection and send notifications about the  **Total**  property value changes when they occur:

### EF Core

```csharp
using System.ComponentModel.DataAnnotations;
using System.Collections.ObjectModel;
// ...
public class Customer : BaseObject, INotifyPropertyChanged {
    // ...
    ObservableCollection<Order> orders;
    public virtual IList<Order> Orders { get => orders; }

    public Customer() {
        orders = new ObservableCollection<Order>();
        orders.CollectionChanged += (s, e) => OnPropertyChanged(nameof(Total));
    }

    #region INotifyPropertyChanged implementation

    PropertyChangedEventHandler propertyChanged;
    event PropertyChangedEventHandler INotifyPropertyChanged.PropertyChanged {
        add { propertyChanged += value; }
        remove { propertyChanged -= value; }
    }
    protected void OnPropertyChanged([CallerMemberName] string propertyName = null) {
        propertyChanged.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }

    #endregion
    string customerName;
    public virtual string CustomerName {
        get { return customerName; }
        set {
            customerName = value;
            OnPropertyChanged();
        }
    }    
}

//Note that the Customer class implements the INotifyPropertyChanged interface explicitly. You need to send notifications about changes to all class properties explicitly - UseChangeTrackingProxies does not work in this case.

```
### XPO

```csharp
using DevExpress.Xpo.Metadata;
// ...
public class Customer : BaseObject {
    // ...
    protected override XPCollection<T> CreateCollection<T>(XPMemberInfo property) {
        XPCollection<T> collection = base.CreateCollection<T>(property);
        if (property.Name == nameof(Orders)) {
            collection.CollectionChanged += Collection_CollectionChanged;
        }
        return collection;
    }

    private void Collection_CollectionChanged(object sender, XPCollectionChangedEventArgs e) {
        OnChanged(nameof(Total));
    }
}
```

You can also notify that the  property value is changed from the  business class. Refer to the following article that describes this:  [How to: Calculate a Property Value Based on Values from a Detail Collection](https://docs.devexpress.com/eXpressAppFramework/113179/business-model-design-orm/business-model-design-with-xpo/calculate-a-property-value-based-on-values-from-a-detail-collection).`Total``Order`

# Actualizar objetos y revertir cambios

**API útil**

![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/54d539bc-e2bb-46cf-9b71-1a3ad690ad0d)
![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/e219b064-de62-41a7-8317-1e9d37c03e54)

En el código, puede modificar objetos de negocio para crear otros nuevos, eliminar objetos o editar las propiedades de los objetos. Si realiza esto en un ObjectSpace diferente del ObjectSpace de la Vista actual, actualice el ObjectSpace de la Vista actual para mostrar los cambios en la Vista. Llame al método  [IObjectSpace.Refresh](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Refresh)  para mostrar nuevos datos en la vista.

En el ejemplo siguiente se agrega un nuevo objeto  **Contact**  a una  [vista de lista](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views#listview)  y se actualiza el espacio de objetos para mostrar el nuevo objeto.


```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;
using DevExpress.Persistent.Base;
using MainDemo.Module.BusinessObjects;
// ...
public class AddContactController : ObjectViewController<ListView, Contact> {
    public AddContactController() {
        ParametrizedAction addContactAction = new ParametrizedAction(
            this, "AddContact", PredefinedCategory.Edit, typeof(string));
        addContactAction.Execute += AddContactAction_Execute;
    }
    private void AddContactAction_Execute(object sender, ParametrizedActionExecuteEventArgs e) {
        using(IObjectSpace objectSpace = Application.CreateObjectSpace(typeof(Contact))) {
            Contact contact = objectSpace.CreateObject<Contact>();
            contact.FirstName = e.ParameterCurrentValue as string;
            objectSpace.CommitChanges();
        }
        View.ObjectSpace.Refresh();
    }
}

```

El código siguiente vuelve a cargar la vista detallada primaria cuando se vuelve a cargar uno de los objetos secundarios.


```csharp
using DevExpress.ExpressApp;
using YourSolutionName.Module.BusinessObjects;

namespace YourSolutionName.Module.Controllers {
    public class MyViewController : ObjectViewController<DetailView, Parent> {
        protected override void OnActivated() {
            base.OnActivated();
            ObjectSpace.ObjectReloaded += ObjectSpace_ObjectReloaded;
        }
        private void ObjectSpace_ObjectReloaded(object sender, ObjectManipulatingEventArgs e) {
            Child child = e.Object as Child;
            if (child != null && ReferenceEquals(child.Parent, View.CurrentObject)) {
                View.Refresh();
            }
        }
        protected override void OnDeactivated() {
            ObjectSpace.ObjectReloaded -= ObjectSpace_ObjectReloaded;
            base.OnDeactivated();
        }
    }
}

```

Para volver a cargar un objeto modificado en otro espacio de objetos del espacio de objetos actual, utilice el método  [IObjectSpace.ReloadObject.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.ReloadObject(System.Object))  El siguiente controlador muestra cómo abrir una ventana emergente para editar un objeto  **Task**  y, a continuación, volver a cargar este objeto en la vista Lista de  **tareas**.



```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Actions;
using DevExpress.ExpressApp.Editors;

public class EditTaskController : ObjectViewController<ListView, Task> {
    public EditTaskController() {
        PopupWindowShowAction action = new PopupWindowShowAction(this, "EditTask", DevExpress.Persistent.Base.PredefinedCategory.Edit);
        action.SelectionDependencyType = SelectionDependencyType.RequireSingleObject;
        action.CustomizePopupWindowParams += Action_CustomizePopupWindowParams;
        action.Execute += Action_Execute;
    }
    private void Action_Execute(object sender, PopupWindowShowActionExecuteEventArgs e) {
        e.PopupWindowView.ObjectSpace.CommitChanges();
        ObjectSpace.ReloadObject(e.PopupWindowViewCurrentObject);
    }

    private void Action_CustomizePopupWindowParams(object sender, CustomizePopupWindowParamsEventArgs e) {
        IObjectSpace objectSpace = Application.CreateObjectSpace(typeof(Task));
        Task task = (Task)objectSpace.GetObject(View.CurrentObject);
        DetailView detailView = Application.CreateDetailView(objectSpace, task);
        detailView.ViewEditMode = ViewEditMode.Edit;
        e.View = detailView;
    }
}

```

Cuando utilice un  [modo de acceso a datos](https://docs.devexpress.com/eXpressAppFramework/113683/ui-construction/views/list-view-data-access-modes)  que no cargue objetos reales ([ServerView](https://docs.devexpress.com/eXpressAppFramework/118450/ui-construction/views/list-view-data-access-modes/server-server-view-instant-feedback-and-instant-feedback-view-modes),  [DataView](https://docs.devexpress.com/eXpressAppFramework/118452/ui-construction/views/list-view-data-access-modes/data-view-mode)  e  [InstantFeedbackView](https://docs.devexpress.com/eXpressAppFramework/118450/ui-construction/views/list-view-data-access-modes/server-server-view-instant-feedback-and-instant-feedback-view-modes)), utilice el método  [IObjectSpace.Refresh](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace.Refresh)  para volver a cargar un objeto modificado en la vista de lista actual.


# Acceso a datos de aplicaciones XAF en una aplicación que no es XAF


En determinados escenarios, es posible que deba crear una aplicación auxiliar para el mantenimiento de la base de datos y usar  [el Espacio de objetos](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space)  para consultar los datos principales de la aplicación XAF. En este tema se describe cómo crear y utilizar el espacio de objetos en una aplicación normal que no sea XAF.

>IMPORTANTE
No se recomienda usar el enfoque de este tema en aplicaciones XAF. En su lugar, acceda a un espacio de objetos con opciones dependientes del contexto. Para obtener más información, consulte el tema siguiente: [Formas de acceder a un espacio de objetos (el contexto de base de datos para operaciones CRUD).](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space)

En una aplicación que no es XAF, no hay ningún objeto con el que crear un espacio de objetos. Una aplicación en XAF en sí misma no crea espacios de objetos. Internamente, utiliza el proveedor de  **espacio**  de objetos diseñado para crear espacios de objetos para el ORM utilizado actualmente y los registrados en su método reemplazado. En una aplicación que no sea XAF, puede crear manualmente una instancia del proveedor de espacio de objetos y, a continuación, llamar al método del proveedor para crear un  **espacio de objetos**.`XafApplication` `XafApplication` `XafApplication.CreateDefaultObjectSpaceProvider` `CreateObjectSpace`.

![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/dcadef43-c0d7-4c71-94bf-e2574323d20a)


>NOTA
Si desea utilizar el sistema de seguridad en su aplicación que no es XAF, consulte el siguiente tema de ayuda: [Usar la API de seguridad (control de acceso y autenticación) en aplicaciones que no son XAF ](https://docs.devexpress.com/eXpressAppFramework/113558/data-security-and-safety/security-system/integrate-the-security-system-into-a-non-xaf-application).

## Ejemplo de XPO

En las aplicaciones basadas en XPO, se debe inicializar el  [subsistema Types Info](https://docs.devexpress.com/eXpressAppFramework/113669/business-model-design-orm/types-info-subsystem). En el ejemplo siguiente se muestra cómo obtener acceso a los datos de la aplicación MainDemo (normalmente instalados en %_PUBLIC%\Documents\DevExpress Demos  23.1\Components\XAF\MainDemo_) y escribir la lista de departamentos en la secuencia de salida estándar:



```csharp
using DevExpress.ExpressApp.Xpo;
using DevExpress.ExpressApp;
using MainDemo.Module.BusinessObjects;
// ...
class Program {
    static void Main(string[] args) {
        XpoTypesInfoHelper.GetXpoTypeInfoSource();
        XafTypesInfo.Instance.RegisterEntity(typeof(Department));
        XPObjectSpaceProvider osProvider = new XPObjectSpaceProvider(
        @"integrated security=SSPI;pooling=false;data source=(localdb)\MSSQLLocalDB;initial catalog=MainDemo_", null);
        IObjectSpace objectSpace = osProvider.CreateObjectSpace();
        foreach (Department department in objectSpace.GetObjects<Department>()) {
            Console.WriteLine(department.Title + "\t" + department.Office);
        }
    }
}

```

## Ejemplo de Entity Framework Core

Utilice el siguiente fragmento de código para tener acceso a la consola  **de EFCore**  o a los datos de la aplicación WinForms y escriba la lista de departamentos en la secuencia de salida estándar.



```csharp
var objectSpaceProvider = new EFCoreObjectSpaceProvider<ApplicationDbContext>(
     (builder, _) => builder
        .UseSqlServer("Data Source=(localdb)\\MSSQLLocalDB;Initial Catalog=EFCoreTestDB;Integrated Security=True;MultipleActiveResultSets=True")
        .UseLazyLoadingProxies()
        .UseChangeTrackingProxies()
  );
XafTypesInfo.Instance.RegisterEntity(typeof(Department));
IObjectSpace objectSpace = objectSpaceProvider.CreateObjectSpace();
foreach (Department department in objectSpace.GetObjects<Department>()) {
    Console.WriteLine(department.Title + "\t" + department.Office);
}

```

En el ejemplo siguiente se muestra cómo puede tener acceso a datos XAF en aplicaciones que no son XAF mediante el sistema de seguridad XAF:  [Control de acceso basado en roles, Administración de permisos y Servicios de API OData / Web / REST para Entity Framework y XPO ORM](https://github.com/DevExpress-Examples/XAF_Security_E4908).

## Nota

Para rellenar la base de datos con datos iniciales, utilice el método siguiente: `DatabaseUpdater.Update`


```csharp
using DevExpress.ExpressApp.Updating;
// ...
DatabaseUpdater databaseUpdater = new DatabaseUpdater(
    osProvider, new ModuleBase[0], "", osProvider.ModuleInfoType);
databaseUpdater.Update();
```


# Obtener acceso al espacio de objetos, al sistema de seguridad, al ayudante de subtítulos y a módulos XAF en el entorno de ASP.NET  Core


En este tema se describe cómo acceder a un espacio de objetos, al  [sistema de seguridad](https://docs.devexpress.com/eXpressAppFramework/113366/data-security-and-safety/security-system), al  [asistente de subtítulos](https://docs.devexpress.com/eXpressAppFramework/113298/localization)  y  [a módulos XAF](https://docs.devexpress.com/eXpressAppFramework/118046/application-shell-and-base-infrastructure/application-solution-components/modules#modules-shipped-with-xaf)  desde un servicio o middleware ASP.NET Core, controladores  [de](https://docs.devexpress.com/eXpressAppFramework/113711/data-manipulation-and-business-logic/create-read-update-and-delete-data)  API web, páginas Razor personalizadas y componentes.

### APIs útiles

![image](https://github.com/lianhdez95/Data-Manupulation-and-Logic/assets/126447472/e9d8fe5d-1ba5-4ab0-bf04-285dd0c5fd94)


## Prerrequisitos

Si creó la aplicación en v21.2 o anterior, debe utilizar la propiedad  [ObjectSpaceProviders](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Blazor.ApplicationBuilder.IBlazorApplicationBuilder.ObjectSpaceProviders)  de Application Builder para registrar proveedores de espacio de objetos en lugar del método o evento. Consulte el siguiente tema de ayuda para obtener más información sobre cómo hacerlo:  [Integrar Application Builders en aplicaciones existentes](https://docs.devexpress.com/eXpressAppFramework/403980/application-shell-and-base-infrastructure/application-solution-components/integrate-application-builders-into-existing-applications).`XafApplication.CreateDefaultObjectSpaceProvider``XafApplication.CreateCustomObjectSpaceProvider`

Se recomienda encarecidamente esto porque el uso del método y el evento entran en conflicto con el uso del servicio. `XafApplication.CreateDefaultObjectSpaceProvider``XafApplication.CreateCustomObjectSpaceProvider``IObjectSpaceFactory``IObjectSpaceProviderFactory`

El uso de  [IObjectSpaceFactory](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Core.IObjectSpaceFactory)  en lugar de los miembros de también mejora el rendimiento de la aplicación porque la instancia de la aplicación no se crea en este caso.`XafApplication`

## Ejemplos

### Espacio de objetos

Para crear un espacio de objetos en una aplicación ASP.NET Core, inserte el servicio  [IObjectSpaceFactory](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Core.IObjectSpaceFactory). Tenga en cuenta que este servicio garantiza si un usuario ha iniciado sesión. De lo contrario, produce una excepción de autorización. Para evitar esta excepción, puede utilizar las siguientes técnicas:

-   Utilice el servicio en lugar de . `INonSecuredObjectSpaceFactory``IObjectSpaceFactory`
-   Utilice otra forma de asegurarse de si un usuario ha iniciado sesión (por ejemplo, utilice con ).`AuthorizationPolicyBuilder.RequireXafAuthentication``AuthorizeAttribute`

#### Desde un componente de razor

**Archivo:**  _MySolution.Blazor.Server\Pages\MyComponent.razor._

.razor
```
@page "/MyComponent"
@inject DevExpress.ExpressApp.Core.IObjectSpaceFactory objectSpaceFactory

<h3>MyComponent</h3>

@code {
    protected override async Task OnAfterRenderAsync(bool firstRender) {
        if (!firstRender) {
            return;
        }
        try {
            using(IObjectSpace objectSpace = objectSpaceFactory.CreateObjectSpace<Contact>()) {
                // ...
            }
        }
        catch(Exception ex) {
            // User authentication has failed.
            // ...
        }
    }
}

```

#### Desde Middleware

**Archivo:**  _MySolution.Blazor.Server\CustomMiddleware.cs._



```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Core;
using Microsoft.AspNetCore.Http;
using System.Threading.Tasks;

namespace MySolution.Blazor.Server {
    public class CustomMiddleware {
        private readonly RequestDelegate next;
        public CustomMiddleware(RequestDelegate next) {
            this.next = next;
        }
        public async Task InvokeAsync(HttpContext context, IObjectSpaceFactory objectSpaceFactory) {
            try {
                using(IObjectSpace objectSpace = objectSpaceFactory.CreateObjectSpace<Contact>()) {
                    // ...
                }
            }
            catch(Exception ex) {
                // User authentication is failed.
                // ...
            }
            await next(context);
        }
    }
}

```

#### Desde un controlador principal de ASP.NET

**Archivo**:  _MySolution.Blazor.Server.Controllers\CustomController.cs._



```csharp
using DevExpress.Data.Filtering;
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Core;
using Microsoft.AspNetCore.Mvc;

namespace MySolution.Blazor.Server.Controllers {
    public class CustomController : ControllerBase {
        internal IObjectSpaceFactory objectSpaceFactory;
        public CustomController(IObjectSpaceFactory objectSpaceFactory) {
            this.objectSpaceFactory = objectSpaceFactory;
        }
        [HttpGet]
        public object GetUserObject(string userName) {
            using (IObjectSpace objectSpace = objectSpaceFactory.CreateObjectSpace<ApplicationUser>()) {
                ApplicationUser user = objectSpace.FindObject<ApplicationUser>(
                    CriteriaOperator.FromLambda<ApplicationUser>(u => u.UserName == userName));
                // ...
            }
        }
    }
}

```

### Sistema de seguridad

Para tener acceso al sistema de seguridad en una aplicación ASP.NET Core, inserte el servicio  [ISecurityProvider](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Security.ISecurityProvider). Tenga en cuenta que este servicio garantiza si un usuario ha iniciado sesión. De lo contrario, produce una excepción de autorización. Para evitar esta excepción, puede utilizar las siguientes técnicas:

-   Utilice el servicio en lugar de si no necesita operar con un objeto de usuario autenticado. Este servicio no garantiza si un usuario ha iniciado sesión o no, por lo que es posible que el objeto de usuario actual no esté disponible aquí.`ISecurityStrategyBase``ISecurityProvider`
-   Utilice otra forma de asegurarse de si un usuario ha iniciado sesión (por ejemplo, utilice con .`AuthorizationPolicyBuilder.RequireXafAuthentication``AuthorizeAttribute`

Estas soluciones provisionales no garantizan que no recibirá excepciones de autenticación, incluso si especifica las credenciales de usuario correctas.

#### Desde Middleware

**Archivo**:  _MySolution.Blazor.Server\CustomMiddleware.cs._



```csharp
using DevExpress.ExpressApp.Security;
using DevExpress.Persistent.BaseImpl.PermissionPolicy;
using Microsoft.AspNetCore.Http;
using System.Threading.Tasks;

namespace MySolution.Blazor.Server {    
    public class CustomMiddleware {
        private readonly RequestDelegate next;
        public CustomMiddleware(RequestDelegate next) {
            this.next = next;
        }
        public async Task InvokeAsync(HttpContext context, ISecurityProvider securityProvider) {
            try {
                ISecurityStrategyBase securityStrategy = securityProvider.GetSecurity();
                // If authentication has failed, GetSecurity throws an exception.
                PermissionPolicyUser user = (PermissionPolicyUser)securityStrategy.User;
                // ...
            }
            catch(Exception ex) {
                // User authentication has failed.
                // ...
            }
            await next(context);
        }
    }
}

```

#### Desde un componente de razor

**Archivo:**  _MySolution.Blazor.Server\Pages\MyComponent.razor._

.razor

```
@page "/MyComponent"
@using DevExpress.ExpressApp
@using DevExpress.ExpressApp.Security
@inject DevExpress.ExpressApp.Security.ISecurityStrategyBase securityStrategy
@inject DevExpress.ExpressApp.Security.ISecurityProvider securityProvider

<h3>MyComponent</h3>

@code {
    protected override async Task OnAfterRenderAsync(bool firstRender) {
        if (!firstRender) {
            return;
        }
        try {
            securityStrategy = securityProvider.GetSecurity();
            // If authentication has failed, GetSecurity throws an exception.
            ApplicationUser user = (ApplicationUser)securityStrategy.User;
        }
        catch (Exception ex) {
            // User authentication has failed.
            // ...
        }
    }
}

```

#### Desde un controlador principal de ASP.NET

**Archivo**:  _MySolution.Blazor.Server.Controllers\CustomController.cs._



```csharp
using Microsoft.AspNetCore.Mvc;
using DevExpress.ExpressApp.Security;

namespace MySolution.Blazor.Server.Controllers {
    public class CustomController : ControllerBase {
        internal ISecurityProvider securityProvider;
        public CustomController(ISecurityProvider securityProvider) {
            this.securityProvider = securityProvider;
        }
        [HttpGet]
        public object GetUserObject() {
            ISecurityStrategyBase securityStrategy = securityProvider.GetSecurity();
            // If authentication has failed, GetSecurity throws an exception.
            ApplicationUser user = (ApplicationUser)securityStrategy.User;
            // ...
        }
    }
}

```

### Ayudante de subtítulos

La clase  [auxiliar de subtítulos permite obtener subtítulos](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Utils.CaptionHelper)  localizados para  [controladores](https://docs.devexpress.com/eXpressAppFramework/112621/ui-construction/controllers-and-actions/controllers)  XAF y  [componentes Razor que](https://docs.devexpress.com/eXpressAppFramework/113610/ui-construction/using-a-custom-control-that-is-not-integrated-by-default/using-a-custom-control-that-is-not-integrated-by-default)  se muestran en  [vistas](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views)  XAF. XAF inicializa el modelo de aplicación de esta clase en solicitudes a páginas XAF estándar. Para obtener subtítulos con otras solicitudes (middleware, método de API web, etc.), use el servicio  [ICaptionHelperProvider](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Services.Localization.ICaptionHelperProvider).

Este servicio utiliza un modelo de aplicación compartido y no devuelve cadenas localizadas específicas del usuario desde un almacenamiento de diferencias de modelo de usuario. Si la aplicación no almacena subtítulos diferentes para diferentes usuarios en el modelo de aplicación, use el servicio  [ICaptionHelperProvider](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Services.Localization.ICaptionHelperProvider)  como una forma unificada de obtener subtítulos localizados.

#### Desde un componente de razor

**Archivo**:  _MySolution.Blazor.Server\Pages\MyComponent.razor._

.razor

```
@page "/MyComponent"
@using DevExpress.ExpressApp.Utils
@inject DevExpress.ExpressApp.Services.Localization.ICaptionHelperProvider captionHelperProvider

<h3>MyComponent</h3>

@code {
    protected override async Task OnAfterRenderAsync(bool firstRender) {
        if (!firstRender) {
            return;
        }
        ICaptionHelper helper = captionHelperProvider.GetCaptionHelper();
        string newActionName = helper.GetActionCaption("New");
        // ...
    }
}

```

#### Desde Middleware

**Archivo**:  _MySolution.Blazor.Server\CustomMiddleware.cs._



```csharp
using DevExpress.ExpressApp.AspNetCore.Services.Localization;
using DevExpress.ExpressApp.Utils;

namespace MySolution.Blazor.Server.Pages {
    public class CustomMiddleware {
        private readonly RequestDelegate next;
        public CustomMiddleware(RequestDelegate next) {
            this.next = next;
        }
        public async Task InvokeAsync(HttpContext context, ICaptionHelperProvider captionHelperProvider) {
            ICaptionHelper helper = captionHelperProvider.GetCaptionHelper();
            string newActionName = helper.GetActionCaption("New");
            // ...
            await next(context);
        }
    }
}

```

#### Desde un controlador principal de ASP.NET

**Archivo**:  _MySolution.Blazor.Server.Controllers\CustomLocalizationController.cs._



```csharp
using DevExpress.ExpressApp.AspNetCore.Services.Localization;
using DevExpress.ExpressApp.Utils;
using Microsoft.AspNetCore.Mvc;

namespace MySolution.Blazor.Server.Controllers {
    public class CustomLocalizationController : ControllerBase {
        internal ICaptionHelperProvider captionHelperProvider;
        public CustomLocalizationController(ICaptionHelperProvider captionHelperProvider) {
            this.captionHelperProvider = captionHelperProvider;
        }
        [HttpGet]
        public string GetActionCaption(string actionName) {
            ICaptionHelper helper = captionHelperProvider.GetCaptionHelper();
            return helper.GetActionCaption(actionName);
        }
    }
}

```

El método  [CaptionHelper.GetService](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Utils.CaptionHelper.GetService(System.IServiceProvider))  devuelve una instancia para usarla en otras plataformas, como Win y Web.`ICaptionHelper`



```csharp
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.Utils;

ICaptionHelper helper = CaptionHelper.GetService(Application.ServiceProvider)
string newActionName = helper.GetActionCaption("New");
// ...

```

### Módulos XAF

Consulte el siguiente artículo de ayuda para encontrar el ejemplo:  [Cómo: Imprimir un informe sin mostrar una vista previa](https://docs.devexpress.com/eXpressAppFramework/113601/shape-export-print-data/reports/task-based-help/how-to-print-a-report-without-displaying-a-preview#aspnet-core-controller).
