
# Filtrado de datos


Varios escenarios de aplicación requieren filtrar  [vistas de lista](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views). Por ejemplo, el  [sistema de seguridad](https://docs.devexpress.com/eXpressAppFramework/113366/data-security-and-safety/security-system)  de una aplicación puede prohibir la visualización de una colección completa en una vista de lista. Es posible que también deba filtrar el origen de datos de un informe cuando utilice el  [módulo Informes](https://docs.devexpress.com/eXpressAppFramework/113591/shape-export-print-data/reports/reports-v2-module-overview).  **eXpressApp Framework**  proporciona varios enfoques para el filtrado. Busque el escenario necesario y elija una solución adecuada mediante este tema.

## Básico

Para obtener información sobre cómo crear criterios de filtro, consulte los siguientes temas:

-   [Formas de crear criterios](https://docs.devexpress.com/eXpressAppFramework/113052/filtering/in-list-view/ways-to-build-criteria)
-   [Operadores de criterios de función](https://docs.devexpress.com/eXpressAppFramework/113307/filtering/in-list-view/function-criteria-operators)
-   [Operadores de criterios de función personalizados](https://docs.devexpress.com/eXpressAppFramework/113480/filtering/in-list-view/custom-function-criteria-operators)
-   [Parámetros del objeto](https://docs.devexpress.com/eXpressAppFramework/113278/filtering/in-list-view/object-parameters)

## Vistas de lista

Una vista de lista se puede filtrar mediante las siguientes técnicas.

-   [Propiedad Criteria del origen de colección de una vista de lista](https://docs.devexpress.com/eXpressAppFramework/112988/filtering/in-list-view/criteria-property-of-a-list-views-collection-source)
-   [Propiedad Criteria en el modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112990/filtering/in-list-view/criteria-property-in-the-application-model)
-   [Nodo modelo de aplicación de filtros](https://docs.devexpress.com/eXpressAppFramework/112992/filtering/in-list-view/filters-application-model-node)
-   [Atributo ListViewFilter](https://docs.devexpress.com/eXpressAppFramework/112991/filtering/in-list-view/list-view-filter-attribute)
-   [Acción FullTextSearch](https://docs.devexpress.com/eXpressAppFramework/112997/filtering/in-list-view/full-text-search-action)
-   [Técnicas de filtrado específicas de la interfaz de usuario](https://docs.devexpress.com/eXpressAppFramework/112999/filtering/in-list-view/ui-specific-filtering-techniques)

## Vistas de lista en editores de propiedades de búsqueda

Las vistas de lista de los editores de propiedades de búsqueda se pueden filtrar mediante las siguientes técnicas.

-   [Ajustar orígenes de datos para propiedades de referencia y colección](https://docs.devexpress.com/eXpressAppFramework/112993/filtering/in-list-view/adjust-data-sources-for-reference-and-collection-properties)
-   [Propiedad Criteria del origen de colección de una vista de lista](https://docs.devexpress.com/eXpressAppFramework/112988/filtering/in-list-view/criteria-property-of-a-list-views-collection-source)
-   [Propiedad Criteria en el modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112990/filtering/in-list-view/criteria-property-in-the-application-model)
-   [Cómo: Agregar una acción de búsqueda a editores de propiedades de búsqueda y ventanas emergentes de vínculos](https://docs.devexpress.com/eXpressAppFramework/112925/ui-construction/controllers-and-actions/actions/how-to-add-a-search-action-to-lookup-property-editors-and-link-pop-up-windows)
-   [Parámetro de objeto actual](https://docs.devexpress.com/eXpressAppFramework/113204/filtering/in-list-view/current-object-parameter)
-   [Técnicas de filtrado específicas de la interfaz de usuario](https://docs.devexpress.com/eXpressAppFramework/112999/filtering/in-list-view/ui-specific-filtering-techniques)

## Vistas de lista en las ventanas emergentes de la acción Vínculo

Las vistas de lista en las ventanas emergentes invocadas al usar la acción  **Vincular**  (consulte  [LinkUnlinkController.LinkAction](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.LinkUnlinkController.LinkAction)) se pueden filtrar mediante las siguientes técnicas:

-   [Ajustar orígenes de datos para propiedades de referencia y colección](https://docs.devexpress.com/eXpressAppFramework/112993/filtering/in-list-view/adjust-data-sources-for-reference-and-collection-properties)
-   [Propiedad Criteria del origen de colección de una vista de lista](https://docs.devexpress.com/eXpressAppFramework/112988/filtering/in-list-view/criteria-property-of-a-list-views-collection-source)
-   [Propiedad Criteria en el modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112990/filtering/in-list-view/criteria-property-in-the-application-model)
-   [Cómo: Agregar una acción de búsqueda a editores de propiedades de búsqueda y ventanas emergentes de vínculos](https://docs.devexpress.com/eXpressAppFramework/112925/ui-construction/controllers-and-actions/actions/how-to-add-a-search-action-to-lookup-property-editors-and-link-pop-up-windows)
-   [Técnicas de filtrado específicas de la interfaz de usuario](https://docs.devexpress.com/eXpressAppFramework/112999/filtering/in-list-view/ui-specific-filtering-techniques)

## Filtrado de datos en informes

-   [Filtrado de datos en informes](https://docs.devexpress.com/eXpressAppFramework/113594/filtering/in-reports/data-filtering-in-reports)
-   [Cómo: Filtrar la búsqueda de un parámetro de informe](https://docs.devexpress.com/eXpressAppFramework/115617/filtering/in-reports/how-to-filter-a-report-parameters-lookup)


# Filtrado de datos en ListView


# Propiedad Criteria del origen de colección de una vista de lista


La propiedad  [CollectionSourceBase.Criteria](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.CollectionSourceBase.Criteria)  de  [ListView.CollectionSource](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ListView.CollectionSource)  de una vista de lista permite filtrar la vista de lista en el nivel de origen de datos. Esto significa que sólo los objetos que satisfacen los criterios especificados se recuperan de la base de datos. En este tema se explica cómo usar este enfoque si necesita aplicar un filtro que no cambie en tiempo de ejecución o en tiempo de diseño.

Haga lo siguiente para tener acceso a la propiedad  **Criteria**  de CollectionSource de una vista de lista:

1.  Cree un  [controlador de vistas](https://docs.devexpress.com/eXpressAppFramework/112621/ui-construction/controllers-and-actions/controllers).
2.  Reemplace el método  **OnActivated**  del controlador para tener acceso al objeto  [ViewController.View actual.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ViewController.View)
3.  Utilice  [ListView.CollectionSource](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ListView.CollectionSource)  de la vista de lista para recuperar los objetos necesarios del almacén de datos.
4.  Agregue el filtro a la colección de filtros  [CollectionSourceBase.Criteria.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.CollectionSourceBase.Criteria)

El código siguiente muestra cómo mostrar sólo objetos cuyo  **FullName**  comienza con una "A" en vistas de lista de persona:



```csharp
using DevExpress.ExpressApp;
using DevExpress.Data.Filtering;
using DevExpress.Persistent.BaseImpl;
// ...
public class FilterPersonListViewController : ObjectViewController<ListView, Person> {
    protected override void OnActivated() {
        base.OnActivated();
        View.CollectionSource.Criteria["Filter1"] = CriteriaOperator.Parse("StartsWith([FullName], 'A')");
    }
}

```

Este enfoque se puede aplicar a cualquier vista de lista que pueda definir en el código. En el código anterior, se filtran todas las vistas de lista que muestran objetos  **de tipo persona**.

Un objeto persistente utilizado en los criterios del origen de la colección no se vuelve a cargar cuando se actualiza el  [espacio de objetos](https://docs.devexpress.com/eXpressAppFramework/113707/data-manipulation-and-business-logic/object-space), lo que genera la excepción  [SessionMixingException](https://docs.devexpress.com/XPO/DevExpress.Xpo.Exceptions.SessionMixingException). Para evitar esto, utilice la propiedad key de un objeto persistente en lugar del propio objeto.



```csharp
View.CollectionSource.Criteria["Filter1"] = CriteriaOperator.Parse("Manager.Oid = ?", ObjectSpace.GetKeyValue(manager));

```

>NOTA
>
>-   En las vistas de lista anidadas, **Criteria** no se aplica directamente a la colección asociada. En su lugar, se crea una colección separada y se le aplican los criterios; La colección asociada original no se modifica. Una vista de lista anidada en el [modo de acceso a datos](https://docs.devexpress.com/eXpressAppFramework/113683/ui-construction/views/list-view-data-access-modes)  **de cliente** con una colección de proxy deshabilitada (consulte [XafApplication.DefaultCollectionSourceMode](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication.DefaultCollectionSourceMode)) es una excepción. En este caso, los criterios se aplican directamente a la colección asociada.
    
>-   Actualmente, [TreeListEditor](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.TreeListEditors.Win.TreeListEditor) tiene capacidades de filtrado limitadas. Sólo se filtran los nodos del árbol raíz si se especifica la propiedad Criterios del origen de la colección al filtrar la vista de lista.



# Propiedad Criteria en el modelo de aplicación

La propiedad  **Criteria**  del nodo  [IModelListView](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Model.IModelListView)  del  [modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112580/ui-construction/application-model-ui-settings-storage/how-application-model-works)  permite filtrar vistas de lista mediante el  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor). Esto significa que los usuarios finales que tengan acceso al modelo de aplicación podrán cambiar esta propiedad. Sin embargo, no habrá una capacidad para hacer esto sin el Editor de modelos. En este tema se explica cómo utilizar esta propiedad.

Utilice la propiedad  **Criteria**  de un nodo Vista de lista para especificar un criterio de filtrado que se aplicará a la vista de lista actual. Puede utilizar el cuadro de diálogo  **Generador de filtros**  para diseñar visualmente la expresión necesaria. Para invocar este cuadro de diálogo, haga clic en el botón de puntos suspensivos (![EllipsisButton](https://docs.devexpress.com/eXpressAppFramework/images/ellipsisbutton116182.png)) situado a la derecha del valor de la propiedad.

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/3142802c-9717-4ca3-9152-0ca1b6d1e6a3)

El valor de esta propiedad se agrega a la colección  **Criteria**  de  [ListView.CollectionSource](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ListView.CollectionSource)  de la vista de lista. Esto se realiza cuando se activa  [FilterController](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController). Por lo tanto, si desactiva este Controller, la propiedad  **Criteria**  no se tendrá en cuenta para ninguna vista de lista.

Este enfoque se puede aplicar a cualquier vista de lista, ya sea una raíz, anidada en la ventana desplegable de un editor de propiedades de búsqueda, o una ventana emergente de acción de vínculo, cualquier vista de lista que pueda encontrar en el modelo de aplicación.

>NOTA
>
>En las vistas de lista anidadas, **Criteria** no se aplica directamente a la colección asociada. En su lugar, se crea una colección separada y se le aplican los criterios; La colección asociada original no se modifica. Una vista de lista anidada en el [modo de acceso a datos](https://docs.devexpress.com/eXpressAppFramework/113683/ui-construction/views/list-view-data-access-modes)  **de cliente** con una colección de proxy deshabilitada (consulte [XafApplication.DefaultCollectionSourceMode](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.XafApplication.DefaultCollectionSourceMode)) es una excepción. En este caso, los criterios se aplican directamente a la colección asociada.


# Nodo modelo de aplicación de filtros


El  [nodo Modelo de aplicación de](https://docs.devexpress.com/eXpressAppFramework/112580/ui-construction/application-model-ui-settings-storage/how-application-model-works)  **filtros**  permite agregar criterios predefinidos a la acción  **SetFilter**  integrada. Al seleccionar un criterio en la ventana desplegable de la acción, la vista de lista actual se filtra utilizando este criterio.

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/c9fb36fc-dab6-44ff-b3d5-946d10bfa03d)

Utilice esta técnica para filtrar las vistas de lista cuando necesite que un usuario final pueda seleccionar el filtro necesario. Además, los usuarios finales que tengan acceso al modelo de aplicación podrán agregar o cambiar filtros predefinidos a través del  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor).

La acción  **SetFilter**  no está activada para las vistas de lista que no tienen filtros especificados en el nodo  **Filtros**. Además, esta acción se puede activar para las vistas de lista raíz y anidadas, ya que las  [plantillas](https://docs.devexpress.com/eXpressAppFramework/112609/ui-construction/templates)  de formularios Windows Forms  **MainForm**  y  **DetailViewForm**  y la plantilla de formularios Web  **Forms ASP.NET predeterminada**  contienen el  [contenedor de acciones](https://docs.devexpress.com/eXpressAppFramework/112610/ui-construction/action-containers)  **Filtros**  que muestra esta acción. Para obtener información sobre cómo mostrar la acción de filtrado en una ventana emergente, consulte el tema  [Agregar acciones a una ventana emergente](https://docs.devexpress.com/eXpressAppFramework/112804/ui-construction/controllers-and-actions/add-actions-to-a-popup-window).

Para personalizar el comportamiento de la acción  **SetFilter**, acceda a ella en código. Esta acción está contenida en  [FilterController](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController)  y se puede tener acceso a ella a través de su propiedad  [FilterController.SetFilterAction.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController.SetFilterAction)

## Agregar filtros a través del editor de modelos

Para agregar elementos a la acción  **SetFilter**, haga lo siguiente.

-   Invocar el menú contextual para las  **vistas**  requeridas |  **_<ListView>_**  |  **Filtra**  y selecciona el botón  **Agregar**  | Elemento de menú  **ListViewFilterItem**.
-   Para el nuevo nodo  **Filtro**, especifique las propiedades  **ID,**  **Caption**  y  **Criteria**. El valor  **Criteria**  debe especificarse mediante la  [sintaxis del lenguaje Criteria](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax). Para simplificar esta tarea, puede invocar el cuadro de diálogo  **Generador de filtros**  haciendo clic en un botón de puntos suspensivos (![EllipsisButton](https://docs.devexpress.com/eXpressAppFramework/images/ellipsisbutton116182.png)) situado a la derecha del valor  **Criterios**. Dentro de este cuadro de diálogo, puede diseñar visualmente una expresión de criterio.
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/9db69b47-ff5f-4b0b-8424-87b7e1b0f6b2)

    
-   Repita los dos pasos anteriores si es necesario.
-   Vuelva al nodo  **Filtros**, especifique el filtro predeterminado mediante la propiedad  **CurrentFilter**, si es necesario.

## Agregar filtros en el código

Puede agregar filtros predefinidos en el código a través de  [ListViewFilterAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.ListViewFilterAttribute). Los filtros especificados mediante este atributo se agregan al nodo  **Filters**  del nodo  **ListView**  cuya propiedad  [IModelObjectView.ModelClass](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Model.IModelObjectView.ModelClass)  se establece en la clase a la que se aplica el atributo.

**EF Core**

```csharp
using DevExpress.ExpressApp.Model;
using DevExpress.ExpressApp.SystemModule;
//...
[DefaultClassOptions]
[ListViewFilter("Today", "GetDate([DueDate]) = LocalDateTimeToday()")]
[ListViewFilter("In three days", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -3) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("In two weeks", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -14) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("The last week", @"GetDate([DueDate]) > LocalDateTimeLastWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeLastWeek(), 5)")]
[ListViewFilter("This week", @"GetDate([DueDate]) > LocalDateTimeThisWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeThisWeek(), 5)")]
public class Task : BaseObject {
    [ModelDefault("EditMask","d")]
    public virtual DateTime DueDate { get; set; }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.
```


**XPO**

```csharp
using DevExpress.ExpressApp.Model;
using DevExpress.ExpressApp.SystemModule;
//...
[DefaultClassOptions]
[ListViewFilter("Today", "GetDate([DueDate]) = LocalDateTimeToday()")]
[ListViewFilter("In three days", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -3) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("In two weeks", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -14) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("The last week", @"GetDate([DueDate]) > LocalDateTimeLastWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeLastWeek(), 5)")]
[ListViewFilter("This week", @"GetDate([DueDate]) > LocalDateTimeThisWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeThisWeek(), 5)")]
public class Task : BaseObject {
   public Task(Session session) : base(session) {}
   private DateTime dueDate;
   [ModelDefault("EditMask","d")]
   public DateTime DueDate {
      get {
         return dueDate;
      }
      set {
         SetPropertyValue(nameof(DueDate), ref dueDate, value);      }
   }
}

```

Si va a agregar un filtro complejo, que es difícil de escribir como una cadena, agregue el nodo  [IModelListViewFilterItem](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.IModelListViewFilterItem)  Application Model en el código implementando un descendiente  [ModelNodesGeneratorUpdater<T> (Generator Updater](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Model.ModelNodesGeneratorUpdater-1)) para el generador de nodos  [ModelListViewFiltersGenerator](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.ModelListViewFiltersGenerator):



```csharp
using DevExpress.ExpressApp.Model;
using DevExpress.ExpressApp.Model.Core;
using DevExpress.ExpressApp.SystemModule;
//...
public sealed class Module : ModuleBase {
   // ...   
    public override void AddGeneratorUpdaters(ModelNodesGeneratorUpdaters updaters) {
        base.AddGeneratorUpdaters(updaters);
        updaters.Add(new MyFilterUpdater());          
    }
}
public class MyFilterUpdater : ModelNodesGeneratorUpdater<ModelListViewFiltersGenerator> {
    public override void UpdateNode(ModelNode node) {                
        IModelListViewFilters filtersNode = (IModelListViewFilters)node;
        if(((IModelListView)filtersNode.Parent).ModelClass.TypeInfo.Type == 
            typeof(MyBusinessClass)) {
            IModelListViewFilterItem myFilter = 
                filtersNode.AddNode<IModelListViewFilterItem>("MyComplexFilter");
            myFilter.Criteria = "";
            myFilter.Index = 1;
            myFilter.Caption = "My Filter";
            myFilter.Description = "";
            filtersNode.CurrentFilter = myFilter;
        }
    }
}

```

Para obtener información sobre todo el concepto de cómo extender el modelo de aplicación en código, consulte el tema  [Extender y personalizar el modelo de aplicación en código](https://docs.devexpress.com/eXpressAppFramework/112810/ui-construction/application-model-ui-settings-storage/customize-application-model-in-code/access-the-application-model-in-code).

Para obtener información sobre cómo crear criterios, consulte el tema  [Formas de crear criterios](https://docs.devexpress.com/eXpressAppFramework/113052/filtering/in-list-view/ways-to-build-criteria).


# Atributo de filtro de vista de lista


Aplique este atributo a una clase de negocio para especificar un filtro para la vista de lista que mostrará los objetos de esta clase. El filtro especificado se cargará en el modelo de aplicación como un nodo secundario del nodo  [Filtros](https://docs.devexpress.com/eXpressAppFramework/112992/filtering/in-list-view/filters-application-model-node)  adecuado. Todos los filtros agregados a un nodo ListView están representados por los elementos integrados de  **SetFilter**  Action en la ventana desplegable. Un usuario final puede seleccionar un elemento para aplicar el filtro necesario a la vista de lista actual.

**EF Core**

```csharp
using DevExpress.ExpressApp.Model;
using DevExpress.ExpressApp.SystemModule;
//...
[DefaultClassOptions]
[ListViewFilter("Today", "GetDate([DueDate]) = LocalDateTimeToday()")]
[ListViewFilter("In three days", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -3) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("In two weeks", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -14) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("The last week", @"GetDate([DueDate]) > LocalDateTimeLastWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeLastWeek(), 5)")]
[ListViewFilter("This week", @"GetDate([DueDate]) > LocalDateTimeThisWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeThisWeek(), 5)")]
public class Task : BaseObject {
    [ModelDefault("EditMask","d")]
    public virtual DateTime DueDate { get; set; }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

**XPO**



```csharp
using DevExpress.ExpressApp.Model;
using DevExpress.ExpressApp.SystemModule;
//...
[DefaultClassOptions]
[ListViewFilter("Today", "GetDate([DueDate]) = LocalDateTimeToday()")]
[ListViewFilter("In three days", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -3) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("In two weeks", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -14) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("The last week", @"GetDate([DueDate]) > LocalDateTimeLastWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeLastWeek(), 5)")]
[ListViewFilter("This week", @"GetDate([DueDate]) > LocalDateTimeThisWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeThisWeek(), 5)")]
public class Task : BaseObject {
   public Task(Session session) : base(session) {}
   private DateTime dueDate;
   [ModelDefault("EditMask","d")]
   public DateTime DueDate {
      get {
         return dueDate;
      }
      set {
         SetPropertyValue(nameof(DueDate), ref dueDate, value);      }
   }
}
```

Para obtener información detallada, vea  [ListViewFilterAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.ListViewFilterAttribute).

>NOTA
>
>Los filtros especificados mediante el atributo **ListView** Filter se  agregan a todos los nodos de  **ListView**  generados automáticamente cuyo atributo  **ModelClass** se establece en la clase a la que se aplica el atributo. El atributo no agrega filtros a los nodos creados manualmente o clonados en el [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor). La acción  **SetFilter** está activada para las vistas de lista raíz y anidada, ya que sólo el **MainForm**  y la  **DetailViewForm**  de las  [plantillas](https://docs.devexpress.com/eXpressAppFramework/112609/ui-construction/templates)  de  formularios Windows Forms  y la plantilla  **Default**  de  formularios Web Forms ASP.NET  contienen los **Filter**  [Action Container](https://docs.devexpress.com/eXpressAppFramework/112610/ui-construction/action-containers) que muestra esta acción.


# Acción de búsqueda de textocompleto


**eXpressApp Framework**  crea la acción  **FullTextSearch**  en aplicaciones de formularios Windows Forms y ASP.NET formularios Web Forms. Esta acción permite a los usuarios finales filtrar la vista de lista actual. Al escribir una combinación de palabras en el cuadro de texto de la acción, sólo los objetos cuyos valores de propiedad contienen palabras individuales de esta combinación se muestran en la vista de lista. Cuando se vacía el cuadro de texto, se vuelven a mostrar todos los objetos de vista de lista.

**ASP.NET Core Blazor**

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/d77ef546-0997-4317-ae79-cc298ee6d599)

**Windows Forms**

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/2c36f1f5-5b1f-4f8f-92b1-e58ce4d3b54f)

**ASP.NET formularios web**

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/eaa7dd1f-add7-4ce4-9ddb-d0ef2fd556a7)

La acción está disponible para las vistas de lista raíz (que se muestran en las imágenes). Además, puede utilizar esta acción cuando se muestra en la ventana desplegable del Editor de propiedades de búsqueda o en la ventana emergente de la Acción de  **vínculo**. En estos casos, la acción se representa mediante el editor Buscar  **y el botón**  **Ir**. Para que esté disponible, el recuento de los objetos de la vista de lista debe ser mayor que el valor especificado para la propiedad  [IModelOptions.LookupSmallCollectionItemCount](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Model.IModelOptions.LookupSmallCollectionItemCount)  del nodo  **Opciones**  del  [modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112580/ui-construction/application-model-ui-settings-storage/how-application-model-works). Para obtener más información, consulte el tema  [Cómo: Agregar una acción de búsqueda a editores de propiedades de búsqueda y ventanas emergentes de vínculos](https://docs.devexpress.com/eXpressAppFramework/112925/ui-construction/controllers-and-actions/actions/how-to-add-a-search-action-to-lookup-property-editors-and-link-pop-up-windows).

La acción  **FullTextSearch**  se encuentra en  [FilterController](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController). Para tener acceso a la acción en el código, utilice la propiedad  [FilterController.FullTextFilterAction.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController.FullTextFilterAction)

Para obtener información sobre cómo personalizar el motor de búsqueda de  **la acción FullTextSearch**, consulte la descripción del miembro  [FilterController.FullTextFilterAction](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController.FullTextFilterAction)  y el tema  [Cómo: Realizar la búsqueda de la acción FullTextSearch dentro de las propiedades requeridas](https://docs.devexpress.com/eXpressAppFramework/112923/filtering/in-list-view/how-to-make-the-full-text-search-action-search-within-required-properties).



# Técnicas de filtrado específicas de la interfaz de usuario


Puede filtrar una vista de lista mediante la cuadrícula que la muestra. De forma predeterminada, XtraGrid se utiliza para mostrar vistas de lista en aplicaciones de Windows Forms y ASPxGrid en las aplicaciones de formularios Web Forms ASP.NET.

Para aprender las técnicas de filtrado disponibles en XtraGrid, consulte la sección  [Filtrar y buscar](https://docs.devexpress.com/WindowsForms/114635/controls-and-libraries/data-grid/filter-and-search)  de la documentación de XtraGrid.

Para aprender las técnicas de filtrado disponibles en ASPxGrid, consulte la sección  [Filtrado](https://docs.devexpress.com/AspNet/3716/components/grid-view/concepts/filter-data)  de la documentación de ASPxGrid

Hay algunos ejemplos útiles demostrados en:

-   [Cómo: Filtrar vistas de lista en el nivel específico de la interfaz de usuario](https://docs.devexpress.com/eXpressAppFramework/112652/filtering/in-list-view/how-to-filter-list-views-on-the-ui-specific-level)
-   [Cómo: Filtrar vistas de lista grandes mediante la fila de filtro automático](https://docs.devexpress.com/eXpressAppFramework/112919/filtering/in-list-view/how-to-filter-large-list-views-using-the-auto-filter-row)

-   
# Ajustar orígenes de datos para propiedades de referencia y colección


DataSourcePropertyAttribute, DataSourceCriteriaAttribute y  [](https://docs.devexpress.com/eXpressAppFramework/113572/business-model-design-orm/data-types-supported-by-built-in-editors/reference-foreign-key-complex-type-properties)[](https://docs.devexpress.com/eXpressAppFramework/113568/business-model-design-orm/data-types-supported-by-built-in-editors/collection-properties)[DataSourceCriteriaPropertyAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute)  se pueden aplicar  [](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourceCriteriaPropertyAttribute)a las propiedades de referencia y colección de  [las clases empresariales](https://docs.devexpress.com/eXpressAppFramework/113664/business-model-design-orm).  [](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourceCriteriaAttribute)Estos atributos permiten ajustar los orígenes de datos para las siguientes vistas de lista asociadas a las propiedades de destino:

![Sin título](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/018175e4-f993-4e56-91aa-c45c93024719)


Uso de atributos:

-   El atributo  **DataSourceProperty**  acepta el nombre de una propiedad de colección que se utilizará como origen de datos.
-   El atributo  **DataSourceCriteria**  especifica la  [expresión de criterios](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax)  utilizada para filtrar el origen de datos.
-   El atributo  **DataSourceCriteriaProperty**  acepta el nombre de una propiedad de tipo  [CriteriaOperator](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.CriteriaOperator)  que devuelve los criterios de filtro del origen de datos. Esto le permite aplicar dinámicamente filtros personalizados complejos.

>NOTA
>
>-   Cuando estos atributos se aplican a una propiedad de colección, la colección en sí no se filtra. El filtro se utiliza solo para la ventana emergente de  **Link**  Action.
>-   **DataSourceCriteriaProperty** reemplaza los **DataSourceCriteria** cuando ambos atributos se aplican a la misma propiedad.


# Formas de crear criterios

En este tema se muestran las opciones para crear criterios cuando se utiliza cualquiera de las  [técnicas de filtrado](https://docs.devexpress.com/eXpressAppFramework/112998/filtering)  en una aplicación XAF.

## Un objeto Criteria as a CriteriaOperator

Cuando se le pide que establezca un criterio como un objeto  [CriteriaOperator](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.CriteriaOperator), tiene las siguientes opciones:

-   Utilice  [los operadores de criterios](https://docs.devexpress.com/CoreLibraries/2129/devexpress-data-library/criteria-operators)  proporcionados por XPO. Hay varios operadores de criterios XPO que puede utilizar para crear los criterios necesarios. El código siguiente muestra cómo generar un criterio simple mediante BinaryOperator:
    

    
    ```csharp
    using DevExpress.Data.Filtering;
    //...
    // The criteria that represents a logical expression (City <> "Chicago") 
    // is represented by the BinaryOperator and two operands.
    CriteriaOperator criteria = new BinaryOperator(
        new OperandProperty("City"), new OperandValue("Chicago"),
        BinaryOperatorType.NotEqual);
    
    ```
    
-   Utilice el método  [CriteriaOperator.Parse.](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.CriteriaOperator.Parse.overloads)  Puede representar criterios como una cadena legible y analizarla mediante el método estático  **CriteriaOperator.Parse.**
    

    ```csharp
    using DevExpress.Data.Filtering;
    //...
    //The criteria that represents a logical expression (City <> "Chicago") is represented by a string.
    CriteriaOperator criteria = CriteriaOperator.Parse("City != 'Chicago'");
    
    ```
    
    Para obtener información sobre la sintaxis utilizada en el método  **CriteriaOperator.Parse**, consulte el tema de ayuda  [Sintaxis del lenguaje de criterios](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax).
    

Para obtener más información sobre cómo crear criterios utilizando técnicas XPO, consulte los siguientes enlaces:

-   [Creación de criterios](https://docs.devexpress.com/XPO/2036/query-and-shape-data/filtering#creating-criteria)
-   [Cómo: Crear criterios simples](https://docs.devexpress.com/XPO/2132/examples/how-to-build-simple-criteria)
-   [Cómo: Crear criterios complejos](https://docs.devexpress.com/XPO/2047/examples/how-to-build-complex-criteria)

## Un criterio como cadena

En cualquier lugar donde deba especificar un criterio como una cadena, debe establecer una cadena que pueda analizarse mediante el método  [estático CriteriaOperator.Parse.](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.CriteriaOperator.Parse.overloads)  Para obtener información sobre la sintaxis utilizada en este método, consulte el tema de ayuda  [Sintaxis del lenguaje de criterios](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax).

Los lugares donde debe especificar un criterio como cadena incluyen propiedades en el  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor), atributos y diferentes propiedades y métodos en el código.

En el código siguiente se muestra cómo establecer criterios para la propiedad  [ActionBase.TargetObjectsCriteria](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Actions.ActionBase.TargetObjectsCriteria)  de una acción. El controlador siguiente hace que la acción esté disponible cuando el valor de la propiedad  **DueDate**  de la  **tarea**  seleccionada es menor o igual que la fecha y hora del sistema:


```csharp
public partial class MyController : ViewController {
   private void MyController_AfterConstruction(object sender, EventArgs e) {
      TargetObjectType = typeof(Task);
      MyAction.SelectionDependencyType = SelectionDependencyType.RequireMultipleObjects;
      MyAction.TargetObjectsCriteria = "DueDate <= LocalDateTimeNow()";
   }
}

```

La siguiente imagen muestra cómo se especifica la propiedad  **TargetObjectsCriteria**  en el Editor de modelos:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/01784951-e153-4be0-abb2-5cbf7a08393a)

## Obtener la cadena de criterios a través del editor de propiedades Criteria

XAF proporciona los siguientes editores de propiedades de cadena, destinados a construir criterios de filtro visualmente (vea  [Propiedades de criterios](https://docs.devexpress.com/eXpressAppFramework/113564/business-model-design-orm/data-types-supported-by-built-in-editors/criteria-properties)):

-   Editores de propiedades de criterios de formularios Windows Forms:
    
    -   AdvancedCriteriaPropertyEditor
    -   CriteriaPropertyEditor
    -   ExtendedCriteriaPropertyEditor
    -   PopupCriteriaPropertyEditor
-   ASP.NET Editores de propiedades de criterios de formularios Web:
    
    -   ASPxCriteriaPropertyEditor
    -   ASPxPopupCriteriaPropertyEditor

Estos editores de propiedades se pueden utilizar para representar propiedades de cadena decoradas con el atributo  [CriteriaOptionsAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Editors.CriteriaOptionsAttribute). La siguiente imagen ilustra el  **PopupCriteriaPropertyEditor**:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/62b35bcc-51cd-42c8-aae4-97ad54b1337e)

La cadena de criterios correspondiente es:

`[DueDate] <= LocalDateTimeNow() and [Status] = 'Completed'`

El concepto importante es que los editores de propiedades Criteria pueden generar cadenas de criterios que contengan los  [parámetros de objeto](https://docs.devexpress.com/eXpressAppFramework/113278/filtering/in-list-view/object-parameters)  específicos de XAF. Estas cadenas de criterios no se pueden analizar mediante el método  [CriteriaOperator.Parse](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.CriteriaOperator.Parse.overloads), proporcionado por XPO. Debe utilizar el método  **GetCriteriaOperator**  expuesto por la clase auxiliar  **CriteriaEditorHelper**  para obtener el objeto  **CriteriaOperator**  correspondiente:



```csharp
CriteriaOperator criteria = 
    CriteriaEditorHelper.GetCriteriaOperator(criteriaString, dataType, objectSpace);

```

Consulte el tema  [Cómo: Usar editores de propiedades de criterios](https://docs.devexpress.com/eXpressAppFramework/113143/ui-construction/view-items-and-property-editors/property-editors/use-criteria-property-editors)  para ver el ejemplo completo. En este tema también se proporciona una lista de las limitaciones actuales de los editores de propiedades Criteria en ASP.NET aplicaciones de formularios Web Forms.


# Parámetros del objeto


Los parámetros de objeto son compatibles con la compatibilidad heredada. XPO admite de forma nativa la serialización/deserialización de objetos persistentes hacia/desde cadenas. Al serializar un objeto persistente, todas las conversiones se realizan automáticamente. Al deserializar un objeto, debe proporcionar una sesión, que se utilizará para restaurar el objeto. Para ello, utilice el método Session.ParseCriteria en lugar de  **CriteriaOperator.Parse.**  Si ya tiene código que usa el método  **CriteriaOperator.Parse**  normal, puede ajustar la llamada al método con  **Session.CreateParseCriteriaSessionScope.**



```csharp
using(mySession.CreateParseCriteriaSessionScope()) {
    //...
    CriteriaOperator.Parse("...");
    //...
}

```

En este caso, el método  **CriteriaOperator.Parse**  existente restaurará correctamente los objetos persistentes en la sesión "mySession".


# Parámetro de objeto actual


En este tema se describe el propósito del parámetro Current Object e incluye un ejemplo de uso.

Es posible que necesite un parámetro Current Object para filtrar una  [vista de lista](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views)  en un editor de propiedades de búsqueda. Para aplicar un filtro, establezca el atributo para la propiedad de referencia correspondiente. El atributo establece una condición que puede necesitar acceso a los valores de propiedad de objeto de negocio. Utilice el parámetro Current Object para obtener esos valores. `DataSourceCriteria`

>IMPORTANTE
>
>No puede usar la característica Parámetro de objeto actual en escenarios no descritos en este artículo (por ejemplo, con [XPCollection](https://docs.devexpress.com/XPO/DevExpress.Xpo.XPCollection), [reglas de apariencia](https://docs.devexpress.com/eXpressAppFramework/113286/conditional-appearance) o [permisos de seguridad](https://docs.devexpress.com/eXpressAppFramework/113366/data-security-and-safety/security-system)).

Considere un ejemplo con 3 clases: , , y . Ambos y exponer la  [propiedad de referencia](https://docs.devexpress.com/eXpressAppFramework/113572/business-model-design-orm/data-types-supported-by-built-in-editors/reference-foreign-key-complex-type-properties). Además, expone la propiedad reference.`Employee``Position``Department``Employee``Position``Department``Employee``Position`

**EF Core**

```csharp
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl.EF;

namespace YourApplicationName.Module.BusinessObjects;

[DefaultClassOptions]
public class Employee : BaseObject {

    public virtual string Name { get; set; }

    private Department department;

    public virtual Department Department { get; set; }

    public virtual Position Position { get; set; }
}

[DefaultClassOptions]
public class Position : BaseObject {

    public virtual string Title { get; set; }

    public virtual Department Department { get; set; }
}

[DefaultClassOptions]
public class Department : BaseObject {

    public virtual string Title { get; set; }

    public virtual IList<Position> Positions { get; set; } = new ObservableCollection<Position>();

    public virtual IList<Employee> Employees { get; set; } = new ObservableCollection<Employee>();
}

```

**XPO**



```csharp
public class Employee : BaseObject {
    public Employee(Session session) : base(session) { }

    public string Name {
        get { return GetPropertyValue<string>(nameof(Name)); }
        set { SetPropertyValue<string>(nameof(Name), value); }
    }

    [Association("Employee-Department")]
    public Department Department {
        get { return GetPropertyValue<Department>(nameof(Department)); }
        set { SetPropertyValue<Department>(nameof(Department), value); }
    }    

    public Position Position {
        get { return GetPropertyValue<Position>(nameof(Position)); }
        set { SetPropertyValue<Position>(nameof(Position), value); }
    }
}

public class Position : BaseObject {
    public Position(Session session) : base(session) { }

    public string Title {
        get { return GetPropertyValue<string>(nameof(Title)); }
        set { SetPropertyValue<string>(nameof(Title), value); }
    }

    [Association("Department-Position")]
    public Department Department {
        get { return GetPropertyValue<Department>(nameof(Department)); }
        set { SetPropertyValue<Department>(nameof(Department), value); }
    }
}

public class Department : BaseObject {
    public Department(Session session) : base(session) { }

    public string Title {
        get { return GetPropertyValue<string>(nameof(Title)); }
        set { SetPropertyValue<string>(nameof(Title), value); }
    }

    [Association("Employee-Department")]
    public XPCollection<Employee> Employees {
        get { return GetCollection<Employee>(nameof(Employees)); }
    }

    [Association("Department-Position")]
    public XPCollection<Position> Positions {
        get { return GetCollection<Position>(nameof(Positions)); }
    }
}
```

Una interfaz de usuario XAF muestra propiedades de referencia con la ayuda del Editor de propiedades de búsqueda:

![Editor de propiedades de búsqueda sin filtrar, DevExpress](https://docs.devexpress.com/eXpressAppFramework/images/current-object-parameter-lookup-property-editor-unfiltered-devexpress.png)

Es posible que deba filtrar la lista desplegable en un Editor de propiedades de búsqueda. Por ejemplo, es posible que desee mostrar solo los puestos que corresponden al departamento donde trabaja el empleado. Para ello, aplique el atributo a la propiedad y especifique el criterio de filtrado como se muestra en el siguiente fragmento de código:`DataSourceCriteria``Employee.Position`

**EF Core**

```csharp
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl.EF;

namespace YourApplicationName.Module.BusinessObjects;

[DefaultClassOptions]
public class Employee : BaseObject {

    public virtual string Name { get; set; }

    private Department department;

    public virtual Department Department { get; set; }

    [DataSourceCriteria("Department = '@This.Department'")]
    public virtual Position Position { get; set; }
}

```

**XPO**



```csharp
namespace MainDemo.Module.BusinessObjects;

[DefaultClassOptions]
public class Employee : Person, IMapsMarker {
    // ...
    public Employee(Session session) :
        base(session) { }
    // ...
    [DataSourceCriteria("Position.Title = 'Manager' AND Oid != '@This.Oid'")]
    public Employee Manager {
        get {
            return manager;
        }
        set {
            SetPropertyValue(nameof(Manager), ref manager, value);
        }
    }
    // ...
}
```

Sin Current Object Parameter, la condición de filtro solo puede comparar propiedades con valores constantes/predefinidos. Las condiciones también pueden utilizar  [operadores de criterios de función](https://docs.devexpress.com/eXpressAppFramework/113307/filtering/in-list-view/function-criteria-operators). Para definir un criterio que utilice valores de propiedad, utilice el parámetro Current Object. Tenga en cuenta la cadena que comienza con en el ejemplo anterior. `Position``Employee``\@This`

Ahora, la vista de lista desplegable del Editor de propiedades de búsqueda en este ejemplo muestra solo las posiciones que se ajustan al criterio especificado:

![Editor de propiedades de búsqueda filtrada, DevExpress](https://docs.devexpress.com/eXpressAppFramework/images/current-object-parameter-lookup-property-editor-filtered-devexpress.png)

Otro ejemplo de la implementación del parámetro Current Object está disponible en el archivo MainDemo.Module\_BusinessObjects_\_Employee.cs_  de la aplicación  **MainDemo**  incluida con XAF_._

>PROPINA
>
>La aplicación de demostración principalse instala en %PUBLIC%\Documents\DevExpress Demos 23.  1\Components\XAF\MainDemo.  RED.  EFCore por defecto. La versión ASP.NET Core Blazor está disponible en línea en https://demos.  Devexpress.  com/XAF/BlazorDemo.

En el ejemplo siguiente se especifica una condición de filtro para la propiedad. La lista desplegable solo muestra los empleados cuyo "gerente" es "Gerente". El parámetro Current Object ayuda a excluir al empleado actual.`Employee.Manager``Position`

***EF Core**

```csharp
namespace MainDemo.Module.BusinessObjects;

[DefaultClassOptions]
public class Employee : Person {
    // ...
    [DataSourceCriteria("Position.Title = 'Manager' AND ID != '@This.ID'")]
    public virtual Employee Manager { get; set; }
    // ...
}

```

**XPO**



```csharp
namespace MainDemo.Module.BusinessObjects;

[DefaultClassOptions]
public class Employee : Person, IMapsMarker {
    // ...
    public Employee(Session session) :
        base(session) { }
    // ...
    [DataSourceCriteria("Position.Title = 'Manager' AND Oid != '@This.Oid'")]
    public Employee Manager {
        get {
            return manager;
        }
        set {
            SetPropertyValue(nameof(Manager), ref manager, value);
        }
    }
    // ...
}
```


Puede utilizar el parámetro Current Object en las siguientes expresiones o condiciones:

-   La propiedad DataSourceCriteriaAttribute.DataSourceCriteria de  [DataSourceCriteriaAttribute.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourceCriteriaAttribute.DataSourceCriteria)[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourceCriteriaAttribute)
-   La propiedad  [DataSourcePropertyAttribute.DataSourcePropertyIsNullCriteria](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute.DataSourcePropertyIsNullCriteria)  de  [DataSourcePropertyAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute)  (sólo para aplicaciones de formularios Windows Forms y ASP.NET formularios Web Forms).

En , hace referencia al objeto maestro (para el que se muestra el editor de búsquedas) incluso si el editor de búsquedas muestra una propiedad compleja. Por ejemplo, si la propiedad es , entonces se refiere a y no a .`DataSourceCriteria``\@This``Task.Project.Manager``\@This``Task``Project`


# Operadores de criterios de función

**eXpressApp Framework**  proporciona varios enfoques para filtrar las vistas de lista:  [en el nivel de origen de datos](https://docs.devexpress.com/eXpressAppFramework/112988/filtering/in-list-view/criteria-property-of-a-list-views-collection-source),  [a través del modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112992/filtering/in-list-view/filters-application-model-node)  y métodos especiales para filtrar las vistas de lista de los editores de propiedades de búsqueda. En cada enfoque, es posible que deba establecer variables estáticas como valores de criterios de filtro. Por ejemplo, el filtro "Task.DueDate debe establecerse en la fecha actual" necesita la variable CurrentDate (calculada cada vez que sea necesario). Para ello, utilice los operadores de criterios de función que representan funciones que devuelven un valor determinado (como la fecha actual o el usuario actual) o un resultado del tratamiento de los argumentos especificados (como la función de concatenación). En este tema se describen los operadores de criterios de función, se muestra cómo usarlos al filtrar y se explica cómo implementar operadores de funciones personalizados.

## Criterios de función Operadores Básicos

Criterios de función Los operadores forman parte del  [lenguaje de criterios](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax). En las cadenas de criterios, un nombre de operador de criterios de función debe ir seguido de corchetes que contengan operandos que representen argumentos de función, o corchetes vacíos si no toma argumentos. El siguiente criterio muestra cómo utilizar el operador  **LocalDateTimeToday**:

`[Task.DueDate] = LocalDateTimeToday()`

Varios operadores de criterios de función, como  **LocalDateTimeAfterTomorrow**  o  **Replace**, están disponibles de fábrica. Consulte el tema de ayuda  [FunctionOperatorType](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.FunctionOperatorType)  para obtener una lista completa. En la tabla siguiente se enumeran los operadores de criterios de función específicos de XAF disponibles en las aplicaciones XAF:

![Sin título](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/c92d88ea-337e-4e0c-8ccd-42bd80cbfb46)


## Observación importante sobre los operadores de criterios de función de fechay hora

Los parámetros  **DateTime**  no admiten las operaciones de suma y resta. La siguiente expresión es incorrecta:

`[Task.DueDate] > (LocalDateTimeToday() - 3) AND [Task.DueDate] < (LocalDateTimeToday() + 3)`

Para sumar o restar valores de los parámetros DateTime, utilice las funciones de gestión  **DateTime**  que expone  **XPO**, como  **AddDays**  y  **AddYears**.  Por ejemplo, esta es la forma correcta de escribir el criterio anterior:

`[Task.DueDate] > ADDDAYS(LocalDateTimeToday(), -3) AND [Task.DueDate] < ADDDAYS(LocalDateTimeToday(), 3)`

Para obtener una lista completa de las funciones con descripciones, consulte el tema de ayuda  [Sintaxis del lenguaje de criterios](https://docs.devexpress.com/CoreLibraries/4928/devexpress-data-library/criteria-language-syntax).

>NOTA
>
>Los parámetros de  **DateTime** admiten operaciones de suma y resta simples en ciertos sistemas de administración de bases de** datos (DBMS): no hay errores cuando dicha expresión se evalúa en el lado del servidor. Por ejemplo, al filtrar una vista de lista  a través del [ListViewFilterAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.ListViewFilterAttribute)[](https://docs.devexpress.com/eXpressAppFramework/112611/ui-construction/views), el criterio se procesa en el servidor. Si el servidor admite operaciones de suma y resta para los parámetros  **DateTime**  (por ejemplo, Microsoft SQL Server o Microsoft Jet Database Engine (Motor de base de datos Microsoft Jet), el criterio se procesa correctamente.



# Operadores de criterios de función personalizados

Criterios de función integrados  [Los operadores](https://docs.devexpress.com/eXpressAppFramework/113307/filtering/in-list-view/function-criteria-operators)  abordan los escenarios de administración de datos más comunes. Además, puede definir operadores de criterios de función personalizados para aquellas situaciones en las que los operadores integrados no se adaptan a sus necesidades. Por ejemplo, si utiliza con frecuencia una expresión determinada y no desea escribirla una y otra vez, puede implementar un operador de criterios de función personalizado.

## Implementar la interfaz de operador de la funciónICustom

Puede definir un operador de criterios de función en una clase que implemente la interfaz  [ICustomFunctionOperator](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.ICustomFunctionOperator).

>NOTA
>
>La implementación demostrada en esta sección sólo puede acceder al Sistema de Seguridad a través de una API estática (). Esta API no se admite en algunos casos de uso (por ejemplo, en un [servicio de API web](https://docs.devexpress.com/eXpressAppFramework/403394/backend-web-api-service)).`ICustomFunctionOperator``SecuritySystem.Instance`

Consulte la siguiente sección para obtener información sobre cómo superar esta limitación: [Controlar eventos de personalización de criterios (obtener acceso a la información de seguridad en el servicio API web).](https://docs.devexpress.com/eXpressAppFramework/113480/filtering/in-list-view/custom-function-criteria-operators#handle-criteria-customization-events-access-security-information-in-the-web-api-service)

La interfaz expone tres miembros que le permiten especificar una función personalizada y evaluar su valor en el lado del cliente. La propiedad especifica el nombre del operador personalizado. El método calcula el tipo devuelto del operador de criterios de función personalizado, basándose en los tipos de argumentos pasados. El método calcula el valor del operador de criterios de función basándose en los argumentos pasados.`ICustomFunctionOperator``Name``ResultType``Evaluate`



```csharp
public class WeekAgoOperator : ICustomFunctionOperator {
    public string Name {
        get { return "WeekAgo"; }
    }
    public object Evaluate(params object[] operands) {
        return DateTime.Today.AddDays(-7);
    }
    public Type ResultType(params Type[] operands) {
        return typeof(DateTime);
    }
}

```

Para utilizar un operador de criterios de función personalizado, debe registrarlo. Para ello, primero agregue un constructor estático al operador. En el constructor, invoque el método. La invocación de este método desde el constructor estático garantiza que el operador no se registrará dos veces accidentalmente.`CriteriaOperator.RegisterCustomFunction`



```csharp
using DevExpress.Data.Filtering;
//...
public class WeekAgoOperator : ICustomFunctionOperator {
    //...
    static WeekAgoOperator() {
        WeekAgoOperator instance = new WeekAgoOperator();
        if (CriteriaOperator.GetCustomFunction(instance.Name) == null) {
            CriteriaOperator.RegisterCustomFunction(instance);
        }
    }
    public static void Register() { }
}

```

A continuación, invoque este constructor en el constructor estático del módulo principal.

**File:**  _MySolution\Module.cs_



```csharp
public sealed partial class MyModule : ModuleBase {
    static MyModule() {
        WeekAgoOperator.Register();
    }
}

```

After you register a Function Criteria Operator, you can use it anywhere it is required - in List View filters, Validation and Appearance rules, object-level security permissions, and so on. For example, you can configure a List View filter to use your Operator (for example, to select only the objects that were shipped within the last seven days).

`ShippingDate > WeekAgo()`

If your custom Function Criteria Operator is going to be used in server-side filtering, implement the  [ICustomFunctionOperatorFormattable](https://docs.devexpress.com/CoreLibraries/DevExpress.Data.Filtering.ICustomFunctionOperatorFormattable)  interface as well.

Note that a custom Function Criteria Operator can be used in several applications. So, it is recommended that you implement all necessary custom Function Criteria Operators in a separate module.

>NOTE
>
>Consulte el ejemplo  [Cómo: Crear un  operador](https://supportcenter.devexpress.com/ticket/details/e3945/how-to-create-a-custom-function-criteria-operator) de criterios de función personalizado  en el Centro de soporte técnico para obtener información sobre cómo crear un operador de criterios de función personalizado. Según el tipo de plataforma de destino (formularios Web Forms ASP.NET, formularios Win, etc.), puede ejecutar este ejemplo en línea o descargar un ejemplo ejecutable automáticamente.

## Controlar eventos de personalización de criterios (obtener acceso a la información de seguridad en el servicio API web)

Un servicio de API web no puede usar una API estática para obtener acceso a la información de seguridad de una implementación. Si la aplicación contiene un servicio de API web y su escenario de caso de uso requiere que tenga acceso al usuario actual u obtenga acceso a algunos servicios adicionales en la lógica de criterios, use los siguientes eventos para implementar el operador de criterios de función:`ICustomFunctionOperator`

[`OnCustomizeSecurityCriteriaOperator`](https://docs.devexpress.com/eXpressAppFramework/113480/filtering/in-list-view/custom-function-criteria-operators#use-the-oncustomizesecuritycriteriaoperator-event)

Permite escribir la lógica de criterios directamente en el controlador de eventos.

[`OnCreateCustomSecurityFunctionPatcher`](https://docs.devexpress.com/eXpressAppFramework/113480/filtering/in-list-view/custom-function-criteria-operators#use-the-oncreatecustomsecurityfunctionpatcher-event-advanced)

Le permite registrar su descendiente personalizado (avanzado).`SecurityFunctionPatcher`

Puede acceder a estos eventos a través del parámetro de método de XAF Application Builder:`builder.Security.UseIntegratedMode`

**Archivo:**  MySolution.Blazor.Server\Startup.cs (  _MySolution.Win\Startup.cs_.)



```csharp
//..
builder.Security
    .UseIntegratedMode(options => {
        //...
        options.Events.OnCustomizeSecurityCriteriaOperator += (context) => { //...
        };
        options.Events.OnCreateCustomSecurityFunctionPatcher += (context) => { //...
        };
    })
    //...

```

### Usar el evento On Customize Security Criteria Operator (Operador alpersonalizarcriteriosde seguridad)

El delegado toma un parámetro del tipo. Este parámetro expone las siguientes propiedades:`OnCustomizeSecurityCriteriaOperator``CustomCriteriaOperatorPatcherContext`

`Security`

Obtiene una referencia para XAF Security ().`ISecurityStrategyBase`

`Operator`

Obtiene un origen .`CriteriaOperator`

`Result`

Obtiene o establece la personalización resultante . Si se establece en , el origen se utiliza sin personalizaciones.`CriteriaOperator``null``CriteriaOperator`

`ServiceProvider`

Obtiene una referencia para el servicio.`IServiceProvider`

El código siguiente muestra cómo utilizar el evento para personalizar un operador de criterios de función en un escenario de caso de uso básico:`OnCustomizeSecurityCriteriaOperator`

**Archivo:**  _MySolution.WebAPI\Startup.cs_



```csharp
options.Events.OnCustomizeSecurityCriteriaOperator = context => {
    if(context.Operator is FunctionOperator functionOperator) {
        if(functionOperator.Operands.Count == 1 &&
        "CurrentOrgId".Equals((functionOperator.Operands[0] as ConstantValue)?.Value?.ToString(), StringComparison.InvariantCultureIgnoreCase)) {
            context.Result = new ConstantValue(((ApplicationUser)context.Security.User)?.Organization?.Oid ?? Guid.NewGuid());
        }
    }
};

```

Este código de ejemplo procesa una función personalizada. Puede utilizar esta función en una expresión de filtro de forma similar a la función descrita en el tema  [Operadores de criterios de función](https://docs.devexpress.com/eXpressAppFramework/113307/filtering/in-list-view/function-criteria-operators). El código de ejemplo utiliza un tipo personalizado con una propiedad adicional. Los datos de esa propiedad se utilizan en la lógica del operador de criterios de función personalizados.`CurrentOrgId``CurrentUserId``ApplicationUser``Organization`



```csharp
using DevExpress.ExpressApp.Security;
using DevExpress.Persistent.BaseImpl.EF.PermissionPolicy;
// or for XPO
using DevExpress.Persistent.BaseImpl.PermissionPolicy;

public class ApplicationUser : PermissionPolicyUser, ISecurityUserWithLoginInfo {
    public Organization? Organization { get; set; }
    //...
}

```

En el ejemplo de código siguiente se muestra cómo utilizar la función personalizada en una expresión de filtro:`CurrentOrgId`



```csharp
IObjectSpace.FindObject<Organization>(CriteriaOperator.Parse("ID = CurrentOrgId()"))

```

En aplicaciones reales, se recomienda implementar toda la lógica necesaria de una manera que le permita reutilizar esta implementación en un controlador de eventos. Esto le permite tener una única implementación de operador de criterios de función que funciona en todas las plataformas, incluido el servicio de API web (con una configuración adicional mínima). La sección  [Ejemplo](https://docs.devexpress.com/eXpressAppFramework/113480/filtering/in-list-view/custom-function-criteria-operators#example-reuse-an-icustomfunctionoperator-implementation-across-platforms)  muestra esta técnica.`OnCustomizeSecurityCriteriaOperator`

### Usar el evento OnCreateCustomSecurity FunctionPatcher (avanzado)

El delegado toma un parámetro del tipo. Este parámetro expone las siguientes propiedades:`OnCreateCustomSecurityFunctionPatcherContext``OnCreateCustomSecurityFunctionPatcher`

`Security`

Obtiene una referencia para XAF Security ().`ISecurityStrategyBase`

`CustomSecurityFunctionPatcher`

Obtiene o establece un archivo . Si se establece en el valor predeterminado se utiliza.`ICriteriaOperatorPatcher``null``SecurityFunctionPatcher`

`ServiceProvider`

Obtiene una referencia para el servicio.`IServiceProvider`

El evento permite crear un descendiente personalizado que implementa la lógica de criterios necesaria:`OnCreateCustomSecurityFunctionPatcher``SecurityFunctionPatcher`

**Archivo:**  _MySolution.WebAPI\Startup.cs_



```csharp
options.Events.OnCreateCustomSecurityFunctionPatcher = context => {
    context.CustomSecurityFunctionPatcher = new CustomSecurityFunctionPatcher(context.Security);
};

```

Donde el tipo extiende el tipo:`CustomSecurityFunctionPatcher``SecurityFunctionPatcher`



```csharp
using DevExpress.ExpressApp.Security;

public class CustomSecurityFunctionPatcher : SecurityFunctionPatcher {
    public CustomSecurityFunctionPatcher(ISecurityStrategyBase security) : base(security) { }
    //...
}

```

### Ejemplo: reutilizar una implementación de operador de funciónICustomen todas las plataformas

Suponga que tiene la siguiente implementación en la solución:`ICustomFunctionOperator`



```csharp
public class GetCurrentUserName : ICustomFunctionOperator {
    static GetCurrentUserName() {
        GetCurrentUserName instance = new GetCurrentUserName();
        if (CriteriaOperator.GetCustomFunction(instance.Name) == null) {
            CriteriaOperator.RegisterCustomFunction(instance);
        }
    }
    public static void Register() { }

    public const string FUNCTION_NAME = "CurrentOrgId";
    public string Name {
        get { return FUNCTION_NAME; }
    }

    public object Evaluate(params object[] operands) {
        return ((ApplicationUser)SecuritySystem.Instance.User)?.Organization?.ID ?? Guid.Empty;
    }

    public Type ResultType(params Type[] operands) {
        return typeof(Guid);
    }
}

```

Esta función personalizada utiliza la propiedad static para tener acceso a la información sobre el usuario que ha iniciado sesión actualmente (el identificador de la organización de usuarios). Dado que se usa esta API estática, esta función personalizada no funcionaría en el servicio de API web.`SecuritySystem.Instance.User`

Puede volver a escribir esta implementación de la siguiente manera para que la función personalizada se pueda reutilizar en el controlador de eventos  [`OnCustomizeSecurityCriteriaOperator`](https://docs.devexpress.com/eXpressAppFramework/113480/filtering/in-list-view/custom-function-criteria-operators#use-the-oncustomizesecuritycriteriaoperator-event)  del servicio API web:



```csharp
public class GetCurrentUserOrganizationIdFunction : ICustomFunctionOperator {
    static CurrentOrgIdFunction() {
        CurrentOrgIdFunction instance = new CurrentOrgIdFunction();
        if (CriteriaOperator.GetCustomFunction(instance.Name) == null) {
            CriteriaOperator.RegisterCustomFunction(instance);
        }
    }
    public static void Register() { }

    public const string FUNCTION_NAME = "CurrentOrgId";
    public string Name {
        get { return FUNCTION_NAME; }
    }

    // The `ICustomFunctionOperator.Evaluate` method implementation that accesses
    // security information through the static API (suitable for Blazor and WinForms).
    public object Evaluate(params object[] operands) {
        return CurrentOrgIdFunctionCore(SecuritySystem.Instance);
    }

    // Check if the current `ICustomFunctionOperator` can process a given custom function
    // specified by the `context` parameter passed from an `OnCustomizeSecurityCriteriaOperator` event handler.
    public static bool CanEvaluate(CustomCriteriaOperatorPatcherContext context) {
        if (context.Operator is FunctionOperator functionOperator) {
            return functionOperator.Operands.Count == 1 &&
                            FUNCTION_NAME.Equals((functionOperator.Operands[0] as ConstantValue)?.Value?.ToString(), StringComparison.InvariantCultureIgnoreCase);
        }
        return false;
    }

    // An additional `Evaluate` method overload that processes a custom function specified by the `context` parameter
    // passed from the Web API Service's `OnCustomizeSecurityCriteriaOperator` event handler.
    public static void Evaluate(CustomCriteriaOperatorPatcherContext context) {
        context.Result = new ConstantValue(CurrentOrgIdFunctionCore(context.Security));
    }

    // Implements logic used to obtain the required data from the Security System, process it,
    // and return the function's result
    // This method is called from both `Evaluate` method overloads.
    private static Guid CurrentOrgIdFunctionCore(ISecurityStrategyBase security) => ((ApplicationUser)security.User)?.Organization?.ID ?? Guid.Empty;

    public Type ResultType(params Type[] operands) {
        return typeof(Guid);
    }
}

```

Con esta refactorización, puede reutilizar la función personalizada desde un controlador de eventos  [`OnCustomizeSecurityCriteriaOperator`](https://docs.devexpress.com/eXpressAppFramework/113480/filtering/in-list-view/custom-function-criteria-operators#use-the-oncustomizesecuritycriteriaoperator-event)  como se muestra a continuación:

**Archivo:**  _MySolution.WebAPI\Startup.cs_



```csharp
builder.Security
    .UseIntegratedMode(options => {
        // ...
        options.Events.OnCustomizeSecurityCriteriaOperator = context => {
            if (GetCurrentUserOrganizationIdFunction.CanEvaluate(context)) {
                GetCurrentUserOrganizationIdFunction.Evaluate(context);
                return;
            }
            // if (OtherCustomFunction.CanEvaluate(context)) {
            //     OtherCustomFunction.Evaluate(context);
            //     return;
            // }
            // ...
        };
    })
    // ...

```

Después de esto, la función estará disponible en la sintaxis del operador de criterios tanto en el lado de la aplicación Blazor/WinForms como en el lado del servicio API web. Por ejemplo, puede usarlo en el módulo independiente de la plataforma para definir permisos de acceso:`CurrentOrgId`

**Archivo:**  _MySolution.Module\DatabaseUpdate\Updater.cs_


```csharp
// ...
private PermissionPolicyRole CreateDefaultRole() {
    // ...
    defaultRole.AddObjectPermission<Employee>(SecurityOperations.ReadOnlyAccess, CriteriaOperator.Parse($"[{nameof(ApplicationUser.Organization.ID)}] == CurrentOrgId()").ToString(), SecurityPermissionState.Allow);
}
```


# Cómo: Filtrar la vista de lista de un cuadro de diálogo de vínculo


En este tema se muestra cómo filtrar una vista de lista en la ventana emergente de una acción de  **vínculo**. La solución usa  [DataSourcePropertyAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute)  y una colección de orígenes de datos generada sobre la marcha. Puede aplicar este atributo en código o en el  [modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112580/ui-construction/application-model-ui-settings-storage/how-application-model-works).

>NOTA
>
>Puede utilizar [DataSourcePropertyAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute)  y [DataSourceCriteriaAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourceCriteriaAttribute)  para filtrar las vistas de lista del editor de propiedades de búsqueda. Para obtener más información, consulte el tema siguiente:  [Cómo: Implementar el filtrado en cascada para vistas de lista de búsqueda](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views).

## Implementar Business Objects

1.  En la carpeta  _YourSolutionName.Module\BusinessObjects_, cree las siguientes clases: , y . Reemplace el código generado automáticamente por las siguientes declaraciones de clase:`Employee``Position``DemoTask`
    
    -   _YourSolutionName.Module\BusinessObjects\Employee.cs_
        
       **EF Core**
       
      ```csharp
        using DevExpress.Persistent.Base;
        using DevExpress.Persistent.BaseImpl.EF;
        using System.Collections.ObjectModel;
        
        namespace YourSolutionName.Module.BusinessObjects {
           [DefaultClassOptions]
           public class Employee : BaseObject {
              public virtual String FirstName { get; set; }
              public virtual String LastName { get; set; }
              public String FullName {
                 get { return ObjectFormatter.Format("{FirstName} {LastName}", 
                     this, EmptyEntriesMode.RemoveDelimiterWhenEntryIsEmpty);
                 }
              }
              public virtual Position Position { get; set; }
              public virtual IList<DemoTask> Tasks { get; set; } = new ObservableCollection<DemoTask>();
           }
        }
        
        // Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.
        
       ```
        

	**XPO**

	```csharp
	using DevExpress.Persistent.Base;
	using DevExpress.Persistent.BaseImpl;
	using DevExpress.Xpo;

	namespace YourSolutionName.Module.BusinessObjects {
	   [DefaultClassOptions]
	   public class Employee : BaseObject {
	      public Employee(Session session) : base(session) {}

	      private String firstName;
	      public String FirstName {
	         get { return firstName; }
	         set { SetPropertyValue(nameof(FirstName), ref firstName, value); }
	      }

	      private String lastName;
	      public String LastName {
	         get { return lastName; }
	         set { SetPropertyValue(nameof(LastName), ref lastName, value); }
	      }

	      public String FullName {
	         get { return ObjectFormatter.Format("{FirstName} {LastName}", 
	             this, EmptyEntriesMode.RemoveDelimiterWhenEntryIsEmpty);
	         }
	      }

	      private Position position;
	      public Position Position {
	         get { return position; }
	         set { SetPropertyValue(nameof(Position), ref position, value); }
	      }

	      [Association("Employee-DemoTask")]
	      public XPCollection<DemoTask> DemoTasks {
	         get { return GetCollection<DemoTask>(nameof(DemoTasks)); }
	      }
	   }
	}
	```


    -   _YourSolutionName.Module\BusinessObjects\DemoTask.cs_
        
        **EF Core**
        
        ```csharp
        using DevExpress.Persistent.Base;
        using DevExpress.Persistent.BaseImpl.EF;
        using System.Collections.ObjectModel;
        
        namespace YourSolutionName.Module.BusinessObjects {
        
           [DefaultClassOptions]
           public class DemoTask : BaseObject {
              public virtual String Subject { get; set; }
              public virtual Priority Priority { get; set; }
              public virtual IList<Employee> Employees { get; set; } = new ObservableCollection<Employee>();
           }
        
           public enum Priority {
              Low = 0,
              Normal = 1,
              High = 2
           }
        }
        
        // Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.
        
        ```
     

	**XPO**

	```csharp
	using DevExpress.Persistent.Base;
	using DevExpress.Persistent.BaseImpl;
	using DevExpress.Xpo;

	namespace YourSolutionName.Module.BusinessObjects {         

	   [DefaultClassOptions]
	   public class DemoTask : BaseObject {
	      public DemoTask(Session session) : base(session) {}

	      private String subject;
	      public String Subject {
	         get { return subject; }
	         set { SetPropertyValue(nameof(Subject), ref subject, value); }
	      }

	      private Priority priority;
	      public Priority Priority {
	         get { return priority; }
	         set { SetPropertyValue(nameof(Priority), ref priority, value); }
	      }

	      [Association("Employee-DemoTask")]
	      public XPCollection<Employee> Employees {
	         get { return GetCollection<Employee>(nameof(Employees)); }
	      }
	   }
	   public enum Priority {
	      Low = 0,
	      Normal = 1,
	      High = 2
	   }
	}
	``` 




    -   _YourSolutionName.Module\BusinessObjects\Position.cs_
        
        **EF Core**
        
        ```csharp
        using DevExpress.Persistent.Base;
        using DevExpress.Persistent.BaseImpl.EF;
        using System.Collections.ObjectModel;
        
        namespace YourSolutionName.Module.BusinessObjects {
        
           [DefaultClassOptions]
           [DefaultProperty(nameof(Title))]
           public class Position : BaseObject {
              public virtual string Title { get; set; }
           }
        
        }
        
        // Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.
        
        ```
        
        **XPO**
        
        ```csharp
        using DevExpress.Persistent.Base;
		using DevExpress.Persistent.BaseImpl;
		using DevExpress.Xpo;
		using System.ComponentModel;

		namespace YourSolutionName.Module.BusinessObjects {

		   [DefaultClassOptions]
		   [DefaultProperty(nameof(Title))]
		   public class Position : BaseObject {
		      public Position(Session session) : base(session) {}

		      private string title;
		      public string Title {
		         get { return title; }
		         set { SetPropertyValue(nameof(Title), ref title, value); }
		      }
		   }
		}
        ```
        >PROPINA
        >
        >Si la aplicación usa Entity Framework Core, registre las clases de negocio recién creadas en el contexto de base de datos y actualice el esquema de base de datos. Para obtener más información, consulte el tema siguiente:  [Implementar un modelo de datos: conceptos básicos](https://docs.devexpress.com/eXpressAppFramework/402981/getting-started/in-depth-tutorial-blazor/define-data-model-and-set-initial-data/define-data-model-and-set-initial-data-with-ef-core/implement-a-data-model-basics#use-a-dbms-setup-migrations).
        
2.  Ejecute la aplicación. Cree varios objetos de cada tipo. Asegúrese de que haya al menos una tarea de alta prioridad.
    
3.  Abra un objeto y haga clic en la acción  **Vincular**  del grupo. La ventana emergente muestra todos los objetos disponibles.`Employee``Demo Tasks``DemoTask`
    
    ASP.NET Core Blazor
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/bf3dc8f6-3274-4da4-9a46-fe9f274da710)

    
    Windows Forms
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/4728d9b0-5189-4bb0-825f-831cff69d12c)

    

## Rellenar manualmente la vista Lista de acciones de vínculo

Este escenario muestra cómo rellenar la vista de lista de la acción  **Vincular**  en las siguientes condiciones:

-   El filtro Vista de lista de  **vínculos**  sólo se aplica cuando la propiedad actual tiene su propiedad establecida en . En todos los demás casos, la vista de lista muestra todos los objetos existentes.`Employee``Position``"Manager"``DemoTask`
-   Solo puede asignar tareas de alta prioridad a los administradores.

1.  Navegue hasta la clase y reemplace su declaración con el siguiente fragmento de código que introduce una colección adicional para la propiedad. Esta colección se actualiza cada vez que cambia el valor de la propiedad.`Employee``Tasks``Priority`
    
    **EF Core**
    
    ```csharp
    using DevExpress.ExpressApp;
    using DevExpress.Persistent.Base;
    using DevExpress.Persistent.BaseImpl.EF;
    using System.Collections.ObjectModel;
    using System.ComponentModel;
    using System.ComponentModel.DataAnnotations.Schema;
    
    namespace YourSolutionName.Module.BusinessObjects {
       [DefaultClassOptions]
       public class Employee : BaseObject {
          public Employee() {
                ((INotifyPropertyChanged)this).PropertyChanged += Employee_PropertyChanged;
          }
    
          private void Employee_PropertyChanged(object sender, PropertyChangedEventArgs e) {
                if (e.PropertyName == nameof(DemoTask)) {
                   RefreshAvailableTasks();
                }
          }
          public virtual String FirstName { get; set; }
          public virtual String LastName { get; set; }
          public String FullName {
                get { return ObjectFormatter.Format("{FirstName} {LastName}", 
                    this, EmptyEntriesMode.RemoveDelimiterWhenEntryIsEmpty);
                }
          }
    
          [DataSourceProperty(nameof(AvailableTasks))]
          public virtual ObservableCollection<DemoTask> Tasks { get; set; } = new ObservableCollection<DemoTask>();
    
          private readonly ObservableCollection<DemoTask> availableTasks = new ObservableCollection<DemoTask>();
    
          // Prohibit the AvailableTasks collection
          // from being displayed in the UI as a property.
          [NotMapped, Browsable(false)]
          public virtual IList<DemoTask> AvailableTasks {
                get {
                   if (availableTasks == null) {
                      // Filter the retrieved collection according to the specified conditions 
                      RefreshAvailableTasks();
                   }
                   // Return the filtered collection of DemoTask objects 
                   return availableTasks;
                }
          }
    
          private void RefreshAvailableTasks() {
    
                var os = ((IObjectSpaceLink)this).ObjectSpace;
                ObservableCollection<DemoTask> available = new ObservableCollection<DemoTask>();
    
                // Process the situation when there are no tasks.
                if (availableTasks == null)
                   return;
                // Display only high priority tasks if the employee is a manager.
                if ((Position != null) && (Position.Title == "Manager")) {                
                   available = new ObservableCollection<DemoTask>(os.GetObjectsQuery<DemoTask>().Where(d => d.Priority == Priority.High).ToList());
                }
                else {
                   // Remove the applied filter.
                   available.Clear();
                }
                if (available != null) {
                   RefreshAvailableTasks(available);
                }
          }
    
          private void RefreshAvailableTasks(IEnumerable<DemoTask> demotasks) {
                while (availableTasks.Count > 0) {
                   availableTasks.RemoveAt(availableTasks.Count - 1);
                }
                foreach (var d in demotasks) {
                   availableTasks.Add(d);
                }
          }
    
          private Position position;
    
          public virtual Position Position {
                get { return position; }
                set {
                   position = value;
                   // Refresh the Tasks property data source.
                   RefreshAvailableTasks();
                }
          }
       }
    }
    
    // Make sure that you use options.UseChangeTrackingProxies() and options.UseObjectSpaceLinkProxies() in your DbContext settings.
    
    ```
    
    **XPO**
    
    ```csharp
    using DevExpress.Data.Filtering;
	using DevExpress.Persistent.Base;
	using DevExpress.Persistent.BaseImpl;
	using DevExpress.Xpo;
	using System.ComponentModel;

	namespace YourSolutionName.Module.BusinessObjects {
	   [DefaultClassOptions]
	   public class Employee : BaseObject {
	      public Employee(Session session) : base(session) { }

	      private String firstName;
	      public String FirstName {
	            get { return firstName; }
	            set { SetPropertyValue(nameof(FirstName), ref firstName, value); }
	      }

	      private String lastName;
	      public String LastName {
	            get { return lastName; }
	            set { SetPropertyValue(nameof(LastName), ref lastName, value); }
	      }

	      public String FullName {
	            get { return ObjectFormatter.Format("{FirstName} {LastName}", 
	                this, EmptyEntriesMode.RemoveDelimiterWhenEntryIsEmpty);
	            }
	      }

	      [Association("Employee-DemoTask")]
	      [DataSourceProperty(nameof(AvailableTasks))]
	      public XPCollection<DemoTask> DemoTasks {
	            get { return GetCollection<DemoTask>(nameof(DemoTasks)); }
	      }

	      private XPCollection<DemoTask> fDemotasks;

	      [Browsable(false), NotMapped]
	      public XPCollection<DemoTask> AvailableTasks {
	            get {
	               if (fDemotasks == null) {
	                  // Retrieve all Accessory objects.
	                  fDemotasks = new XPCollection<DemoTask>(Session);
	                  // Filter the retrieved collection according to the specified conditions.
	                  RefreshAvailableTasks();
	               }
	               // Return the filtered collection of DemoTask objects
	               return fDemotasks;
	            }
	      }
	      private void RefreshAvailableTasks() {
	            // Process the situation when there are no tasks.
	            if (fDemotasks == null)
	               return;
	            // Display only high priority tasks if the employee is a manager.
	            if ((Position != null) && (Position.Title == "Manager")) {
	               fDemotasks.Criteria = CriteriaOperator.Parse("[Priority] = 'High'");
	            }
	            else {
	               // Remove the applied filter.
	               fDemotasks.Criteria = null;
	            }
	      }

	      private Position position;
	      public Position Position
	      {
	            get { return position; }
	            set
	            {
	               position = value;
	               // Refresh the Tasks property data source.
	               RefreshAvailableTasks();
	            }
	      }
	   }
	}
	```
2.  Ejecute la aplicación y desplácese hasta la vista detallada de un objeto cuya propiedad esté establecida en . En el grupo, haga clic en la acción  **de vínculo**. La ventana emergente debe mostrar solo las tareas de alta prioridad.`Employee``Position``"Manager"``Demo Tasks`
    
    ASP.NET Core Blazor
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/49a7f989-5233-40cc-a30a-c6324155d550)

    
    Windows Forms
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/e1ae80db-57f9-49d5-bb18-351bd946eaa9)



# Cómo: Filtrar vistas de lista grandes con fila de filtro automático

En este tema se muestra cómo utilizar la funcionalidad Fila de filtro automático para impedir que un control de cuadrícula muestre una colección completa de vistas de lista en aplicaciones ASP.NET Core Blazor y Windows Forms.

Imagine una vista de lista enlazada a una tabla de base de datos con una gran cantidad de datos. Cuando un control de cuadrícula contiene millones de registros, los usuarios a menudo no necesitan mostrar estos datos, incluso si la paginación virtual está habilitada para  [un mejor rendimiento](https://docs.devexpress.com/eXpressAppFramework/113683/ui-construction/views/list-view-data-access-modes)  y facilidad de uso. En su lugar, necesitan una aplicación para mostrar inicialmente una vista de lista vacía y permitirles filtrar o buscar datos a petición. Todos los usuarios pueden beneficiarse de este diseño, ya que reduce la carga del servidor de base de datos y de la red porque la aplicación no necesita recuperar grandes cantidades de datos de la base de datos.

## Instrucciones paso a paso

1.  En el proyecto  **YourSolutionName.Module**, invoque el  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor)  y navegue hasta las  **vistas**  necesarias |  **<ListView>**  nodo.
    
2.  Establezca la propiedad IModelListViewShowAutoFilterRow.ShowAutoFilterRow en y la propiedad  [IModelListView.DataAccessMode](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Model.IModelListView.DataAccessMode)  en  [.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.IModelListViewShowAutoFilterRow.ShowAutoFilterRow)`true``Server`
    
3.  En  **el Explorador de soluciones**, navegue a:
    
    -   Un proyecto específico de la plataforma en una aplicación .NET 6+ Windows Forms o ASP.NET Core Blazor.
    -   Un proyecto de módulo específico de la plataforma en una aplicación de Windows Forms.
4.  Agregue un  [controlador de vista](https://docs.devexpress.com/eXpressAppFramework/112621/ui-construction/controllers-and-actions/controllers)  a la carpeta  _Controladores_.
    
5.  Herede el control Controller de la clase y reemplace el método como se muestra en el siguiente ejemplo de código:`ObjectViewController<ViewType, ObjectType>``OnViewControlsCreated`
    
    **ASP.NET Core Blazor**
    
    ```csharp
    using DevExpress.ExpressApp;
    using DevExpress.ExpressApp.Blazor.Editors;
    using DevExpress.Data.Filtering;
    using Microsoft.AspNetCore.Components;
    using DevExpress.Blazor;
    using YourApplicationName.Module.BusinessObjects;
    
    namespace YourApplicationName.Blazor.Server.Controllers;
    
    public class BlazorAutoFilterRowController : ObjectViewController<ListView, TargetClassName> {
        private const string FalseCriteriaKey = "FalseCriteria";
        private CriteriaOperator FalseCriteria = CriteriaOperator.Parse("1=0");
    
        protected override void OnViewControlsCreated() {
            base.OnViewControlsCreated();
            if (View.Editor is DxGridListEditor gridListEditor) {
                IDxGridAdapter dataGridAdapter = gridListEditor.GetGridAdapter();
                View.CollectionSource.Criteria[FalseCriteriaKey] = FalseCriteria;
                dataGridAdapter.GridModel.FilterCriteriaChanged = 
                EventCallback.Factory.Create<GridFilterCriteriaChangedEventArgs>(this, args => {
                    if (ReferenceEquals(args.FilterCriteria, null)) {
                        View.CollectionSource.Criteria[FalseCriteriaKey] = FalseCriteria;
                    }
                    else if (View.CollectionSource.Criteria.ContainsKey(FalseCriteriaKey)) {
                        View.CollectionSource.Criteria.Remove(FalseCriteriaKey);
                    }
                });
            }
        }
    }
    
    ```
    
    **Windows Forms**
    ```csharp
    using DevExpress.ExpressApp;
	using DevExpress.Data.Filtering;
	using DevExpress.ExpressApp.Win.Editors;
	using DevExpress.XtraGrid.Views.Base;
	using YourApplicationName.Module.BusinessObjects;

	namespace YourApplicationName.Win.Controllers;

	public class WinAutoFilterRowController : ObjectViewController<DevExpress.ExpressApp.ListView, TargetClassName> {
	    private const string FalseCriteriaKey = "FalseCriteria";
	    private CriteriaOperator FalseCriteria = CriteriaOperator.Parse("1=0");
	    protected override void OnViewControlsCreated() {
	        base.OnViewControlsCreated();
	        if (View.Editor is GridListEditor gridListEditor) {
	            View.CollectionSource.Criteria[FalseCriteriaKey] = FalseCriteria;
	            gridListEditor.GridView.ActiveFilter.Changed += (s, e) => {
	                if (((ViewFilter)s!).IsEmpty) {
	                    View.CollectionSource.Criteria[FalseCriteriaKey] = FalseCriteria;
	                }
	                else if (View.CollectionSource.Criteria.ContainsKey(FalseCriteriaKey)) {
	                    View.CollectionSource.Criteria.Remove(FalseCriteriaKey);
	                }
	            };
	        }
	    }
	}
    ```
    Si no especificó criterios para filtrar los datos de la vista de lista, el control de cuadrícula recupera todos los objetos existentes. Para evitar este comportamiento, establezca un criterio falso para el  [origen de colección](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.CollectionSource)  de la vista de lista.
    
6.  Ejecute la aplicación. La vista de lista con la fila de filtro automático habilitada no debe mostrar ningún objeto.
    
    ASP.NET Core Blazor
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/203f781c-7b65-4c36-b38b-962eb69801d2)

    
    Windows Forms
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/2ddca703-7cd3-4029-8237-d9ebd14d1d8a)



# Cómo: Filtrar vistas de lista en el nivel específico de la interfaz de usuario


En este tema se describe cómo especificar un filtro que se utilizará en un control que visualice una vista de lista específica (por ejemplo,  [el control GridControl](https://docs.devexpress.com/WindowsForms/DevExpress.XtraGrid.GridControl)  o  [ASPxGridView](https://docs.devexpress.com/AspNet/DevExpress.Web.ASPxGridView?v=23.1)).

>NOTA
>
>Las aplicaciones ASP.NET Core Blazor no admiten la filtración del lado cliente.

Ejecute el  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor)  y navegue hasta el nodo Vista de lista requerido (por ejemplo,  **Vistas**  |  **Contact_ListView**). En la cuadrícula de propiedades de la derecha, busque la propiedad  [IModelListView.Filter](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Model.IModelListView.Filter)  y haga clic en el botón de puntos suspensivos situado a la derecha del valor de la propiedad. En el Generador de filtros invocado, especifique el filtro necesario.

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/2ad46008-a22c-4241-bea2-90e6c9bde5a4)

El resultado se demuestra en las imágenes a continuación.

**WinForms:**

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/b94158e1-aacc-41d0-8886-3bcb066cbde5)

**ASP.NET formularios web:**

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/4f459ae3-71e0-4632-87f9-798b5cfadc18)



# Cómo: Implementar el filtrado en cascada para vistas de lista de búsqueda


La mayoría de las aplicaciones tienen vistas detalladas que contienen editores de propiedades de búsqueda que deben filtrarse. A menudo, debe hacer que el origen de datos Vista de lista de estos editores dependa de los valores de otros editores de propiedades ubicados en la misma Vista de detalles. Para ello,  **eXpressApp Framework**  proporciona  [DataSourcePropertyAttribute y DataSourceCriteriaAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute).[](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourceCriteriaAttribute)  En este tema se muestra cómo usar estos atributos en el código y en el modelo  [de aplicación](https://docs.devexpress.com/eXpressAppFramework/112580/ui-construction/application-model-ui-settings-storage/how-application-model-works). En estos ejemplos, las clases Order, Product y Accessory se implementarán de diferentes maneras.

-   [Implementación inicial](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views#0)
-   [Escenario 1: rellenar la búsqueda con objetos de la propiedad de colección especificada](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views#1)
-   [Escenario 2: aplicar criterios para la colección de propiedades de búsqueda](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views#2)
-   [Escenario 3: usar criterios alternativos si la propiedad de origen de datos especificada está vacía](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views#3)
-   [Escenario 4: rellenar la búsqueda manualmente](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views#4)
-   [Escenario 5: filtrar la colección de propiedades de búsqueda en función de las propiedades del objeto actual](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views#5)

>PROPINA
>
>Un proyecto de ejemplo completo está disponible en la base de datos de ejemplos de código de DevExpress en [https://supportcenter.Devexpress.  com/ticket/details/e218/how-to-filter-lookup-list-views](https://supportcenter.devexpress.com/ticket/details/e218/how-to-filter-lookup-list-views) .

## Implementación inicial

Inicialmente, un Pedido incluye un Producto y un Accesorio. Además, cada Accesorio está relacionado con un Producto en particular. Por lo tanto, los objetos Producto y Accesorio están relacionados por una relación de uno a muchos. El código siguiente muestra cómo se pueden implementar estas clases:

**EF Core**

```
using System.ComponentModel;
using DevExpress.Data.Filtering;
using System.Collections.ObjectModel;
using System.ComponentModel.DataAnnotations;
//...
[DefaultClassOptions]
public class Order : BaseObject {
   public virtual Product Product { get; set; }
   public virtual Accessory Accessory { get; set; }
}
[DefaultClassOptions]
public class Product : BaseObject {
   public virtual String ProductName { get; set; }
   public virtual IList<Accessory> Accessories { get; set; } = new ObservableCollection<Accessory>();
}
[DefaultClassOptions]
public class Accessory : BaseObject {
   public virtual String AccessoryName { get; set; }
   public virtual bool IsGlobal { get; set; }
   public virtual Product Product { get; set; }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

**XPO**
```csharp
using System.ComponentModel;
using DevExpress.Data.Filtering;
//...
[DefaultClassOptions]
public class Order : BaseObject {
   public Order(Session session) : base(session) { }
   private Product fProduct;
   public Product Product {
      get {
         return fProduct;
      }
      set {
         SetPropertyValue(nameof(Product), ref fProduct, value);
      }
   }
   private Accessory fAccessory;
   public Accessory Accessory {
      get {
         return fAccessory;
      }
      set {
         SetPropertyValue(nameof(Accessory), ref fAccessory, value);
      }
   }
}
public class Product : BaseObject {
   public Product(Session session) : base(session) { }
   private String fProductName;
   public String ProductName {
      get { 
         return fProductName;
      }
      set {
         SetPropertyValue(nameof(ProductName), ref fProductName, value);
      }
   }
   [Association("P-To-C")]
   public XPCollection<Accessory> Accessories {
      get { return GetCollection<Accessory>(nameof(Accessories)); }
   }
}
public class Accessory : BaseObject {
   public Accessory(Session session) : base(session) { }
   private String fAccessoryName;
   public String AccessoryName {
      get { 
         return fAccessoryName; 
      }
      set {
         SetPropertyValue(nameof(AccessoryName), ref fAccessoryName, value);
      }
   }
   private bool fIsGlobal;
   public bool IsGlobal {
      get {
         return fIsGlobal;
      }
      set {
         SetPropertyValue(nameof(IsGlobal), ref fIsGlobal, value);
      }
   }
   private Product fProduct;
   [Association("P-To-C")]
   public Product Product { 
      get {
         return fProduct;
      } 
      set {
         SetPropertyValue(nameof(Product), ref fProduct, value);
      } 
   }
}
```

La imagen siguiente muestra la vista de detalles de pedido en una aplicación de Windows Forms:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/ab7407fc-4cae-4a46-b76e-9f7189394d6d)

Aquí, los editores de propiedades de búsqueda de productos y accesorios proporcionan todas las colecciones de objetos de productos y accesorios. Sin embargo, ciertos escenarios pueden requerir que se muestre una colección filtrada en el Editor de propiedades de búsqueda de accesorios.

## Escenario 1: rellenar la búsqueda con objetos de la propiedad de colección especificada

En la Vista de detalles del pedido, sería conveniente que el Editor de propiedades de búsqueda de accesorios solo proporcionara los objetos de accesorios relacionados con el Producto seleccionado actualmente. Para ello, se puede utilizar el atributo  [DataSourcePropertyAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute). El valor de este atributo especifica una propiedad cuyos valores posibles sirven como origen de datos para la propiedad de búsqueda actual. Para la propiedad Accessory de la clase Order, este atributo debe establecerse en la propiedad Accessory de la clase Product:

**EF Core**

```csharp
[DefaultClassOptions]
public class Order : BaseObject {
   // ...
   [DataSourceProperty("Product.Accessories")]
   public virtual Accessory Accessory { get; set; }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

**XPO**

```csharp
[DefaultClassOptions]
public class Order : BaseObject {
   // ...
   [DataSourceProperty("Product.Accessories")]
   public Accessory Accessory {
      get {
         return fAccessory;
      }
      set {
         SetPropertyValue(nameof(Accessory), ref fAccessory, value);
      }
   }
}
```

La siguiente imagen muestra la vista de detalles del pedido resultante:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/9af8793d-9ab2-4506-91d1-9e2ea73cfc95)

Se puede lograr el mismo resultado si especifica la propiedad  **DataSourceProperty**  de Application  **Model |**  **BOModel**  |  **Clase**  |  **Nodo miembro**.

>NOTA
>
>-   Se crea una colección de modo de servidor independiente como origen de datos para un ListView de búsqueda cuando la opción **IModelListView.DataAccessMode** se establece en **Server**, **ServerView**, **InstantFeedback** o **InstantFeedbackView** para ese modelo de **ListView**. Sin embargo, cuando se aplica **DataSourcePropertyAttribute** para la propiedad de búsqueda, la propiedad señalada en el atributo se usa como fuente de datos de búsqueda y la colección de modo de servidor independiente independiente no se crea y no se usa en absoluto. El motivo es que el captador de propiedades de la fuente de datos contiene lógica calculada en el lado del cliente y la fuente de datos la completa la aplicación del cliente en el momento en que el editor de búsqueda solicita mostrar objetos. Por lo tanto, la opción de modo **Server**, **ServerView**, **InstantFeedback** o **InstantFeedbackView** y el atributo **DataSourceProperty** no funcionan simultáneamente.
>
>- Para usar el enfoque demostrado anteriormente para los objetos de **Entity Framework** con una relación de muchos a muchos implementada a través de un objeto intermedio, use el método **Map**﻿ para especificar la tabla de unión, sus nombres de columnas y para aplicar una configuración adicional. Para obtener más información, consulte el tema **Entity Framework Core - Relaciones﻿**.

## Escenario 2: aplicar criterios para la colección de propiedades de búsqueda

Puede ser necesario que una vista de lista de búsqueda contenga objetos cuyas propiedades satisfagan un criterio especificado. Por ejemplo, puede haber accesorios que se pueden elegir para cada producto, los llamados accesorios globales. Para mostrar estos accesorios globales en la vista de detalles del pedido, se puede utilizar el atributo  [DataSourceCriteriaAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourceCriteriaAttribute). El valor de este atributo especifica los criterios necesarios:

**EF Core**

```csharp
[DefaultClassOptions]
public class Order : BaseObject {
   // ...
   [DataSourceCriteria("IsGlobal = true")]
   public virtual Accessory Accessory { get; set; }
}

public class Accessory : BaseObject {
   public virtual bool IsGlobal { get; set; }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

**XPO**

```csharp
[DefaultClassOptions]
public class Order : BaseObject {
   // ...
   [DataSourceProperty("Product.Accessories", 
      DataSourcePropertyIsNullMode.CustomCriteria, "IsGlobal = true")]
   public Accessory Accessory {
      get {
         return fAccessory;
      }
      set {
         SetPropertyValue(nameof(Accessory), ref fAccessory, value);
      }
   }
}
```

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/a7a9ec4d-01da-4f22-8a78-8827f6dcd9c7)

Se puede lograr el mismo resultado si especifica la propiedad  **DataSourceCriteria**  de  **BOModel**  | Clase | Nodo miembro.

## Escenario 3: usar criterios alternativos si la propiedad de origen de datos especificada está vacía

Permitir que un origen de datos de propiedad de búsqueda dependa de un valor de otra propiedad (vea  [Escenario 1](https://docs.devexpress.com/eXpressAppFramework/112681/filtering/in-list-view/how-to-implement-cascading-filtering-for-lookup-list-views#1)). Cuando no se especifica este valor, puede proporcionar otro origen de datos. Por ejemplo, cuando un producto no se especifica en el Editor de propiedades de búsqueda de productos de la vista de detalles del pedido, el Editor de propiedades de búsqueda de accesorios proporcionará la colección de accesorios globales. Para ello, se pueden especificar los parámetros DataSourcePropertyIsNullMode y  **DataSourcePropertyIsNullCriteria**  para el atributo  **DataSourceProperty**.

**EF Core**

```csharp
[DefaultClassOptions]
public class Order : BaseObject {
   // ...
   [DataSourceProperty("Product.Accessories", 
      DataSourcePropertyIsNullMode.CustomCriteria, "IsGlobal = true")]
   public virtual Accessory Accessory { get; set; }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```
**XPO**

```
[DefaultClassOptions]
public class Order : BaseObject {
   // ...
   [DataSourceProperty("Product.Accessories", 
      DataSourcePropertyIsNullMode.CustomCriteria, "IsGlobal = true")]
   public Accessory Accessory {
      get {
         return fAccessory;
      }
      set {
         SetPropertyValue(nameof(Accessory), ref fAccessory, value);
      }
   }
}
```

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/f8b272a0-ff88-4345-8a35-9f244ac31db3)

>NOTA
>
>Además del valor  **Criterios personalizados**, el  parámetro Propiedad de origen de datos  **esnulodel atributo Propiedadde origende datos**  **también puede tener el valor Seleccionar todo y**  **Seleccionar**  **nada** valores. En este caso, no es necesario especificar el **parámetro Data SourcePropertyIsNullCriteria**.

Se puede lograr el mismo resultado si especifica las propiedades DataSourceProperty, DataSourcePropertyIsNullMode y  **DataSourcePropertyIsNullCriteria**  de  **BOModel**  del modelo de aplicación |  Clase | Nodo miembro.

## Escenario 4: rellenar la búsqueda manualmente

Supongamos que el origen de datos de la propiedad de búsqueda de accesorios puede contener accesorios globales (consulte el escenario 2) además de los accesorios del producto seleccionados actualmente (consulte el escenario 1). Además, supongamos que hay una marca llamada IncludeGlobalAccessories. Si está en vigor, el origen de datos de la propiedad de búsqueda de accesorios se compone tanto de los accesorios del producto actual como de los accesorios globales. De lo contrario, se compone únicamente de los Accesorios del Producto actual. Para ello, se debe mostrar una colección adicional para la propiedad Accesorio. Esta colección debe actualizarse cada vez que se cambie la propiedad Product o IncludeGlobalAccessories. En el código siguiente se muestra cómo implementar la clase Order para esta tarea.

**EF Core**

```csharp
[DefaultClassOptions]
public class Order : BaseObject {

    [DataSourceProperty(nameof(AvailableAccessories))]
    public virtual Accessory Accessory { get; set; }

    private EFCoreCollection<Accessory> availableAccessories;

    [NotMapped, Browsable(false)] // Prohibits showing the AvailableAccessories collection separately
    public IList<Accessory> AvailableAccessories {
        get {
            if(availableAccessories == null) {
                // Retrieve all Accessory objects
                availableAccessories = (EFCoreCollection<Accessory>)ObjectSpace.GetObjects<Accessory>();
                // Filter the retrieved collection according to current conditions
                RefreshAvailableAccessories();
            }
            return availableAccessories;
        }
    }

    private void RefreshAvailableAccessories() {
        if(availableAccessories == null)
            return;
        // Process the situation when the Product is not specified (see the Scenario 3 above)
        if(Product == null) {
            // Show only Global Accessories when the Product is not specified
            availableAccessories.Criteria = CriteriaOperator.FromLambda<Accessory>(x => x.IsGlobal);
        }
        else {
            if(IncludeGlobalAccessories) {
                // Show the current Product's Accessories and Global Accessories in the fAvailableAccessories collection
                availableAccessories.Criteria = CriteriaOperator.FromLambda<Accessory>(x => x.IsGlobal || x.Product.ID == this.Product.ID);
            }
            else {
                // Leave only the current Product's Accessories in the fAvailableAccessories collection
                availableAccessories.Criteria = CriteriaOperator.FromLambda<Accessory>(x => x.Product.ID == this.Product.ID);
            }
        }
        // Set null for the Accessory property to allow an end-user 
        //to set a new value from the refreshed data source
        Accessory = null;
    }

    private Product product;

    public virtual Product Product {
        get { return product; }
        set {
            if(product != value) {
                product = value;
                // Refresh the Accessory Property data source
                RefreshAvailableAccessories();
            }
        }
    }

    private bool includeGlobalAccessories;

    [ImmediatePostData] //Use this attribute to refresh the Accessory 
    public virtual bool IncludeGlobalAccessories {
        get { return includeGlobalAccessories; }
        set {
            if(includeGlobalAccessories != value) {
                includeGlobalAccessories = value;
                // Refresh the Accessory Property data source                   
                RefreshAvailableAccessories();
            }
        }
    }
}

// Make sure that you use options.UseChangeTrackingProxies() and options.UseObjectSpaceLinkProxies() in your DbContext settings.

```

**XPO**

```
[DefaultClassOptions]
public class Order : BaseObject {
   // ...
   // Set the AvailableAccessories collection as a data source for the Accessory property
   [DataSourceProperty(nameof(AvailableAccessories))] 
   public Accessory Accessory {
      get {return fAccessory;}
      set {
         SetPropertyValue(nameof(Accessory), ref fAccessory, value);
      }
   }
   private XPCollection<Accessory> fAvailableAccessories;
   [Browsable(false)] // Prohibits showing the AvailableAccessories collection separately
   public XPCollection<Accessory> AvailableAccessories {
      get {
         if(fAvailableAccessories == null) {
            // Retrieve all Accessory objects
            fAvailableAccessories = new XPCollection<Accessory>(Session);
            // Filter the retrieved collection according to current conditions
            RefreshAvailableAccessories();
         }
         // Return the filtered collection of Accessory objects
         return fAvailableAccessories;
      }
   }
   private void RefreshAvailableAccessories() {
      if(fAvailableAccessories == null)
         return;
      // Process the situation when the Product is not specified (see the Scenario 3 above)
      if(Product == null) {
         // Show only Global Accessories when the Product is not specified
         fAvailableAccessories.Criteria = CriteriaOperator.Parse("[IsGlobal]");
      }
      else {
        if(IncludeGlobalAccessories) {
          // Show the current Product's Accessories and Global Accessories in the fAvailableAccessories collection
          fAvailableAccessories.Criteria = CriteriaOperator.Parse("[Product] = ? or [IsGlobal]", Product);
        } else {
          // Leave only the current Product's Accessories in the fAvailableAccessories collection
          fAvailableAccessories.Criteria = CriteriaOperator.Parse("[Product] = ?", Product);
        }
      }
      // Set null for the Accessory property to allow an end-user 
      //to set a new value from the refreshed data source
      Accessory = null;
   }
   private Product fProduct;
   public Product Product {
      get { return fProduct; }
      set {
         SetPropertyValue(nameof(Product), ref fProduct, value);
         // Refresh the Accessory Property data source
         RefreshAvailableAccessories();
      }
   }
   private bool fIncludeGlobalAccessories;
   [ImmediatePostData] //Use this attribute to refresh the Accessory 
   public bool IncludeGlobalAccessories {
      get {return fIncludeGlobalAccessories;}
      set {
         if(fIncludeGlobalAccessories != value) {
            fIncludeGlobalAccessories = value;
            if(!IsLoading) {
               // Refresh the Accessory Property data source                    
               RefreshAvailableAccessories();
               SetPropertyValue(nameof(IncludeGlobalAccessories), ref fIncludeGlobalAccessories, value);
            }
         }
      }
   }
}
```

La siguiente imagen muestra una vista detallada del pedido:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/c2754818-4e44-4de1-90b9-0546c68f9ee2)

>NOTA
>
>Este enfoque para filtrar las vistas de lista de búsqueda es útil cuando no se pueden escribir los criterios necesarios como una cadena para pasarla como parámetro de un atributo. En el código, puede utilizar cualquier operador de criterios y cualquier operandos (incluidos [los operadores de criterios de función](https://docs.devexpress.com/eXpressAppFramework/113307/filtering/in-list-view/function-criteria-operators)).

## Escenario 5: filtrar la colección de propiedades de búsqueda en función de las propiedades del objeto actual

Para tener acceso al registro editado actualmente en los criterios pasados a  [DataSourcePropertyAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.DataSourcePropertyAttribute), utilice el  [parámetro Current Object (](https://docs.devexpress.com/eXpressAppFramework/113204/filtering/in-list-view/current-object-parameter)**@This**). Con el siguiente código, la búsqueda  **Contact.Manager**  mostrará todos los contactos con la posición de "administrador" excepto el contacto actual.

**EF Core**

```csharp
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl.EF;
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace YourSolutionName.Module.BusinessObjects;
[DefaultClassOptions]
public class Contact : BaseObject {

    [DataSourceProperty("Department.Contacts", DataSourcePropertyIsNullMode.SelectAll)]
    [DataSourceCriteria("Title = 'Manager' AND ID != '@This.ID'")]
    public virtual Contact Manager { get; set; }

    public virtual string Title { get; set; }
    public virtual string Name { get; set; }
    public virtual Department Department { get; set; }
}
[DefaultClassOptions]
public class Department : BaseObject {
    public virtual string DepartmentName { get; set; }
    public virtual IList<Contact> Contacts { get; set; } = new ObservableCollection<Contact>();
}



// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

**XPO**

```csharp
using DevExpress.Persistent.Base;
using DevExpress.Persistent.BaseImpl;
// ...
public class Contact : Person {
    // ...
    [DataSourceProperty("Department.Contacts", DataSourcePropertyIsNullMode.SelectAll)]
    [DataSourceCriteria("Position.Title = 'Manager' AND Oid != '@This.Oid'")]
    public Contact Manager {
        get {
            return fManager;
        }
        set {
            SetPropertyValue(nameof(Manager), ref fManager, value);
        }
    }
    // ...
}
```

>NOTA
>
>Este fragmento de código no se incluye en el ejemplo vinculado [Cómo filtrar vistas  de lista de búsqueda](https://supportcenter.devexpress.com/ticket/details/e218/how-to-filter-lookup-list-views). En su lugar, se muestra en _las demostraciones %PUBLIC%\Documents\DevExpress 23.1\Components\XAF\Main Demo\CS\MainDemo.Módulo\Objetos de negocio\Contacto.  cs de la_  solución  **de demostración principal** enviada con XAF. También puede ver un código similar en el tutorial  [Implementar propiedades de referencia dependientes](https://docs.devexpress.com/eXpressAppFramework/402979/getting-started/in-depth-tutorial-blazor/define-data-model-and-set-initial-data/define-data-model-and-set-initial-data-with-ef-core/implement-dependent-reference-properties-ef-core).



# Cómo: Utilizar operadores de criterios de función para filtrar vistas de lista


**eXpressApp Framework**  proporciona varios enfoques para filtrar vistas de lista: en el nivel de  [origen de datos](https://docs.devexpress.com/eXpressAppFramework/112988/filtering/in-list-view/criteria-property-of-a-list-views-collection-source),  [a través del modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112990/filtering/in-list-view/criteria-property-in-the-application-model)  y  [en el nivel específico de la interfaz de usuario](https://docs.devexpress.com/eXpressAppFramework/112652/filtering/in-list-view/how-to-filter-list-views-on-the-ui-specific-level). En cada uno de estos enfoques, es posible que deba establecer variables estáticas como valores de criterios de filtro. Por ejemplo, el filtro "Task.DueDate debe establecerse en la fecha actual" necesita la variable CurrentDate, calculada cada vez que sea necesario. Para ello, se utilizan Operadores de criterios de función. Representan funciones que puede utilizar en criterios. En este tema, aprenderá a utilizar estos operadores de criterios de función al establecer criterios de filtro para la vista de lista de tareas. Para ver una lista completa de los operadores de criterios de función integrados y aprender a implementar los personalizados, consulte el tema  [Operadores de criterios de función](https://docs.devexpress.com/eXpressAppFramework/113307/filtering/in-list-view/function-criteria-operators).

Dado que la técnica para usar operadores de criterios de función es común a cualquier enfoque de filtrado, tanto en el código como en el  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor), se elegirá  [ListViewFilterAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.ListViewFilterAttribute)  para la demostración.

>NOTA
>
>Antes de revisar el ejemplo, asegúrese de leer la sección "Observación importante sobre los operadores de criterios de función de fechay hora" del tema  [Operadores de criterios de función](https://docs.devexpress.com/eXpressAppFramework/113307/filtering/in-list-view/function-criteria-operators).

>PROPINA
>
>Un proyecto de ejemplo completo está disponible en la base de datos de ejemplos de código de DevExpress en [https://supportcenter.Devexpress.  com/ticket/details/e3936/how-to-use-function-criteria-operators-to-filter-list-views](https://supportcenter.devexpress.com/ticket/details/e3936/how-to-use-function-criteria-operators-to-filter-list-views) .

En el código siguiente se muestra cómo implementar varios filtros mediante los operadores de criterios  **de función LocalDateTimeToday**, LocalDateTimeLastWeek y  **LocalDateTimeThisWeek**:

**EF Core**

```csharp
using DevExpress.ExpressApp.Model;
using DevExpress.ExpressApp.SystemModule;
//...
[DefaultClassOptions]
[ListViewFilter("Today", "GetDate([DueDate]) = LocalDateTimeToday()")]
[ListViewFilter("In three days", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -3) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("In two weeks", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -14) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("The last week", @"GetDate([DueDate]) > LocalDateTimeLastWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeLastWeek(), 5)")]
[ListViewFilter("This week", @"GetDate([DueDate]) > LocalDateTimeThisWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeThisWeek(), 5)")]
public class Task : BaseObject {
    [ModelDefault("EditMask","d")]
    public virtual DateTime DueDate { get; set; }
}

// Make sure that you use options.UseChangeTrackingProxies() in your DbContext settings.

```

**XPO**

```csharp
using DevExpress.ExpressApp.Model;
using DevExpress.ExpressApp.SystemModule;
//...
[DefaultClassOptions]
[ListViewFilter("Today", "GetDate([DueDate]) = LocalDateTimeToday()")]
[ListViewFilter("In three days", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -3) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("In two weeks", @"[DueDate] >= ADDDAYS(LocalDateTimeToday(), -14) AND 
    [DueDate] < LocalDateTimeToday()")]
[ListViewFilter("The last week", @"GetDate([DueDate]) > LocalDateTimeLastWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeLastWeek(), 5)")]
[ListViewFilter("This week", @"GetDate([DueDate]) > LocalDateTimeThisWeek() AND 
    GetDate([DueDate]) <= ADDDAYS(LocalDateTimeThisWeek(), 5)")]
public class Task : BaseObject {
   public Task(Session session) : base(session) {}
   private DateTime dueDate;
   [ModelDefault("EditMask","d")]
   public DateTime DueDate {
      get {
         return dueDate;
      }
      set {
         SetPropertyValue(nameof(DueDate), ref dueDate, value);      }
   }
}
```

El código anterior genera varios nodos secundarios de filtro para las  **vistas**  del  [modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112580/ui-construction/application-model-ui-settings-storage/how-application-model-works)  |  **Task_ListView**  nodo:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/a2685f10-a8d1-4a65-a379-a133f2bebf2b)

>NOTA
>
>Puede generar estos nodos manualmente en el Editor de modelos.

La siguiente imagen muestra la acción de filtro que contiene todos los filtros proporcionados por el código anterior:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/8aa8b3b1-b976-4c19-998d-140401520b90)



# Cómo: Realizar la búsqueda de la acción de búsqueda de textocompletodentro de las propiedades necesarias


En este tema se muestra cómo personalizar el comportamiento de la acción  **FullTextSearch**. Esta acción filtra la vista de lista actual estableciendo criterios para su origen de datos de recopilación. De acuerdo con los criterios, las propiedades del objeto deben contener palabras individuales de la combinación de palabras escrita por un usuario final. Haga referencia a varias técnicas sobre cómo modificar el comportamiento de la acción, en la descripción del miembro  [FilterController.FullTextFilterAction.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController.FullTextFilterAction)  Aquí, verá cómo usar una de estas técnicas. Especificaremos una lista personalizada de las propiedades que se utilizarán para generar el criterio de filtro para la vista de lista actual.

>PROPINA
>
>Un proyecto de ejemplo completo está disponible en la base de datos de ejemplos de código de DevExpress en [https://supportcenter.Devexpress.  com/ticket/details/e231/how-to-make-the-filterbytext-action-search-within-required-properties](https://supportcenter.devexpress.com/ticket/details/e231/how-to-make-the-filterbytext-action-search-within-required-properties) .

Para especificar una lista personalizada de las propiedades que se usarán en la búsqueda, el controlador de filtro, que contiene la acción FullTextSearch, expone el evento  [FilterController.CustomGetFullTextSearchProperties.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.FilterController.CustomGetFullTextSearchProperties)  Para controlar este evento, agregaremos un nuevo  [controlador de vista](https://docs.devexpress.com/eXpressAppFramework/112621/ui-construction/controllers-and-actions/controllers)  y nos suscribiremos a su evento  [Controller.Activated.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Controller.Activated)

En el controlador de eventos CustomGetFullTextSearchProperties, asigne una lista de las propiedades necesarias al parámetro  [CustomGetFullTextSearchPropertiesEventArgs.Properties.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.SystemModule.CustomGetFullTextSearchPropertiesEventArgs.Properties)  Además, establezca el parámetro  **CustomGetFullTextSearchPropertiesEventArgs.Handled**  en  **true**, para indicar que no se deben agregar otras propiedades a la lista. En este ejemplo, agregaremos solo la propiedad "LastName" de la clase Person. Por lo tanto, activaremos nuestro controlador solo para vistas de lista de personas.  **MyFilterController**  se muestra a continuación:



```csharp
using System;
using System.Collections.Generic;
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.SystemModule;
//...
public class MyFilterController : ViewController {
    public MyFilterController() {
        TargetObjectType = typeof(DevExpress.Persistent.BaseImpl.Person);
    }
    private FilterController standardFilterController;
    protected override void OnActivated() {
        base.OnActivated();
        standardFilterController = Frame.GetController<FilterController>();
        if(standardFilterController != null) {
            standardFilterController.CustomGetFullTextSearchProperties += standardFilterController_CustomGetFullTextSearchProperties;
        }
    }
    void standardFilterController_CustomGetFullTextSearchProperties(object sender, 
CustomGetFullTextSearchPropertiesEventArgs e) {
        foreach(string property in GetFullTextSearchProperties()) {
            e.Properties.Add(property);
        }
        e.Handled = true;
    }
    private List<string> GetFullTextSearchProperties() {
        List<string> searchProperties = new List<string>();
        searchProperties.Add("LastName");
        return searchProperties;
    }
    protected override void OnDeactivated() {
        if (standardFilterController != null) {
            standardFilterController.CustomGetFullTextSearchProperties -= standardFilterController_CustomGetFullTextSearchProperties;
        }
        base.OnDeactivated();
    }
}

```

La siguiente imagen muestra que  **MyFilterController**  funciona:

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/79910b1e-5764-4222-8282-17133a91e1f4)

La filtración puede ser imposible en caso de que una o más propiedades sean de un tipo particular. Por ejemplo, en el modo  [Servidor](https://docs.devexpress.com/eXpressAppFramework/118450/ui-construction/views/list-view-data-access-modes/server-server-view-instant-feedback-and-instant-feedback-view-modes), filtrar por propiedades del tipo  [DateTime](https://docs.microsoft.com/en-us/dotnet/api/system.datetime), que se almacenan en una base de datos como columnas del tipo  [datetime date,](https://docs.microsoft.com/en-us/sql/t-sql/data-types/datetime-transact-sql) puede provocar excepciones. Para evitarlos, asegúrese de que el texto introducido se puede convertir al tipo correspondiente y de que este valor convertido está dentro del intervalo aceptable, y excluya una propiedad de la lista de filtros predeterminada si es necesario. El código siguiente muestra el controlador que implementa esta lógica.



```csharp
using System;
using System.Collections.Generic;
using DevExpress.ExpressApp;
using DevExpress.ExpressApp.SystemModule;
using DevExpress.ExpressApp.DC;
using DevExpress.Data.Summary;
using System.Data.SqlTypes;
//...
public class MyFilterController : ViewController<ListView> {
    private static readonly DateTime minDate;
    private static readonly DateTime maxDate;
    static MyFilterController() {
        minDate = (DateTime)SqlDateTime.MinValue;
        maxDate = (DateTime)SqlDateTime.MaxValue;
    }
    private Boolean CanFilter(string propertyName, string filterText) {
        IMemberInfo memberInfo = View.ObjectTypeInfo.FindMember(propertyName);
        if (SummaryItemTypeHelper.IsDateTime(memberInfo.MemberType)) {
            DateTime? convertedFilter = null;
            try {
                convertedFilter = Convert.ChangeType(filterText, typeof(DateTime)) as DateTime?;
            }
            catch {
                return false;
            }
            if (convertedFilter.HasValue) {
                if ((convertedFilter.Value < minDate) || (convertedFilter.Value > maxDate)) {
                    return false;
                }
            }
        }
        return true;
    }
    private ICollection<string> GetProcessedRequiredProperties(ICollection<string> searchProperties, 
string filterText) {
        List<string> result = new List<string>();
        foreach (string propertyName in searchProperties) {
           if (CanFilter(propertyName, filterText)) {
               result.Add(propertyName);
            }
        }
        return result;
    }
    private void FilterController_CustomGetFullTextSearchProperties(object sender, 
CustomGetFullTextSearchPropertiesEventArgs e) {
        string filterText = ((FilterController)sender).FullTextFilterAction.Value as string;
        if (!string.IsNullOrEmpty(filterText)) {
            ICollection<string> searchProperties = 
GetProcessedRequiredProperties(((FilterController)sender).GetFullTextSearchProperties(), filterText);
            e.Properties.AddRange(searchProperties);
            e.Handled = true;
        }
    }
    protected override void OnActivated() {
        base.OnActivated();
        FilterController filterController = Frame.GetController<FilterController>();
        if (filterController != null) {
            filterController.CustomGetFullTextSearchProperties += 
FilterController_CustomGetFullTextSearchProperties;
        }
    }
    protected override void OnDeactivated() {
        FilterController filterController = Frame.GetController<FilterController>();
        if (filterController != null) {
            filterController.CustomGetFullTextSearchProperties -= 
FilterController_CustomGetFullTextSearchProperties;
        }
        base.OnDeactivated();
    }
}
```


# Filtrado de datos en informes


Los siguientes enfoques de filtrado de datos están disponibles en  **Reports V2**.

## 1. Propiedad FilterString del informe Xtra

La propiedad  [XtraReportBase.FilterString](https://docs.devexpress.com/XtraReports/DevExpress.XtraReports.UI.XtraReportBase.FilterString)  especifica el filtro aplicado en el cliente antes de que se muestre un informe.

El botón de puntos suspensivos que se muestra junto al valor FilterString en la ventana  **Propiedades**  invoca el cuadro de diálogo  **Editor FilterString**, que simplifica la creación de filtros.

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/53663ae4-3be3-4f4a-b99f-bfc23b6010c6)

## 2. Propiedad Criteria de la fuente de datos

La propiedad  [DataSourceBase.Criteria](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.ReportsV2.DataSourceBase.Criteria)  del  [origen de datos](https://docs.devexpress.com/eXpressAppFramework/113593/shape-export-print-data/reports/data-sources-for-reports-v2)  se utiliza para establecer un filtro en el servidor.

El botón de puntos suspensivos que se muestra junto al valor  **Criterios**  en la ventana  **Propiedades**  invoca el cuadro de diálogo  **Editor FilterString**, que simplifica la creación de criterios.

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/1a005fa2-fb08-4eea-8bfa-0e3ea5dd662b)

También puede utilizar el código siguiente para modificar  [criterios](https://docs.devexpress.com/XPO/2036/query-and-shape-data/filtering#creating-criteria)  de  [scripts de informe](https://docs.devexpress.com/XtraReports/2593/detailed-guide-to-devexpress-reporting/reporting-api/use-report-scripts).


```csharp
private void xtraReport1_BeforePrint(object sender, System.Drawing.Printing.PrintEventArgs e) {
    var report = (DevExpress.XtraReports.UI.XtraReport)sender;
    var dataSource = (DevExpress.Persistent.Base.ReportsV2.ISupportCriteria)report.DataSource;
    dataSource.Criteria = DevExpress.Data.Filtering.CriteriaOperator.Parse(
        "StartsWith(LastName, 'A')");
}

```

## 3. Parámetros del informe Xtra

Puede utilizar  [Parámetros de informe](https://docs.devexpress.com/XtraReports/4812/detailed-guide-to-devexpress-reporting/use-report-parameters)  en Criterios de filtro. Para hacer referencia a un valor de parámetro, preceda el valor del parámetro con un signo de interrogación (por ejemplo, "[Nombre] = ?parameterName"). Para obtener información adicional sobre el uso de parámetros en el Generador de filtros, consulte el artículo siguiente:  [Información general sobre el filtrado de datos](https://docs.devexpress.com/XtraReports/1184/detailed-guide-to-devexpress-reporting/shape-report-data/filter-data/data-filter-overview).

## 4. Objeto Parameters

Puede utilizar una clase  [personalizada no persistente](https://docs.devexpress.com/eXpressAppFramework/116516/business-model-design-orm/non-persistent-objects)  heredada de la clase abstracta  [ReportParametersObjectBase](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ReportsV2.ReportParametersObjectBase)  incluida en el módulo Reports  **V2**, en lugar de los parámetros XtraReports. La vista detallada de este objeto se mostrará en un cuadro de diálogo emergente antes de que se muestre un informe. El filtrado y la ordenación especificados a través de los métodos ReportParametersObjectBase.GetCriteria y  [ReportParametersObjectBase.GetSorting](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ReportsV2.ReportParametersObjectBase.GetSorting)  de este objeto se aplican al origen de datos[.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ReportsV2.ReportParametersObjectBase.GetCriteria)  Este enfoque es útil para definir filtros y ordenación complejos.

Para agregar el objeto Parameters al modelo de aplicación y ajustar el diseño de la vista detallada del objeto en el  [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/ui-construction/application-model-ui-settings-storage/model-editor), aplique  [DomainComponentAttribute](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.DC.DomainComponentAttribute)  a la declaración  [de](https://docs.devexpress.com/eXpressAppFramework/112579/ui-construction/application-model-ui-settings-storage)  la clase.


```csharp
using DevExpress.Xpo;
using DevExpress.Xpo.DB;
using DevExpress.ExpressApp.DC;
using DevExpress.Data.Filtering;
using DevExpress.ExpressApp.ReportsV2;
// ...
[DomainComponent]
public class DemoParameters : ReportParametersObjectBase {
    public bool SortByFirstName { get; set; }
    public bool FilterByFirstName { get; set; }
    public string FirstName { get; set; }
    public bool FilterByPosition { get; set; }
    public Position ContactPosition { get; set; }

    public DemoParameters(IObjectSpaceCreator provider) : base(provider) {
        ContactPosition = ObjectSpace.FirstOrDefault<Position>(position => position.Title == "Developer");
    }

    protected override IObjectSpace CreateObjectSpace() {
        return objectSpaceCreator.CreateObjectSpace(typeof(Contact));
    }

    public override CriteriaOperator GetCriteria() {
        CriteriaOperator criteriaName = null;
        CriteriaOperator criteriaPosition = null;
        if (FilterByFirstName) {
            criteriaName = CriteriaOperator.Parse("FirstName = ?", FirstName);
        }
        if (FilterByPosition) {
            criteriaPosition = CriteriaOperator.Parse("Position.Oid = ?", ContactPosition.Oid);
        }
        return CriteriaOperator.And(criteriaName, criteriaPosition);
    }

    public override SortProperty[] GetSorting() {
        List<SortProperty> sorting = new List<SortProperty>();
        if (SortByFirstName) {
            sorting.Add(new SortProperty(nameof(FirstName), SortingDirection.Ascending));
        }
        return sorting.ToArray();
    }
}

```

### Asociar el objeto Report Parameters al informe

-   Si se crea un informe en tiempo de ejecución, puede asociar el objeto Report Parameters mediante la propiedad  [IReportDataV2.ParametersObjectType.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ReportsV2.IReportDataV2.ParametersObjectType)  Haga clic con el botón secundario en el informe en la vista de lista  **Informes**  y elija  **Editar**. A continuación, elija el  **Tipo de objeto Parámetros**  en la Vista de detalles invocada.
    
    ![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/a08ca9c9-6d78-4ec9-80d7-061279e2717b)

    
-   Si un informe está predefinido (creado en tiempo de diseño), el tipo de objeto Parameters se puede pasar al método  [PredefinedReportsUpdater.AddPredefinedReport.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ReportsV2.PredefinedReportsUpdater.AddPredefinedReport(DevExpress.ExpressApp.ReportsV2.IReportDataV2))
    

    ```csharp
    predefinedReportsUpdater.AddPredefinedReport<ContactsBaseReport>(
        "Contacts by Department", typeof(ContactsReport), typeof(MyParametersObject));
    
    ```
    
    Para obtener más información sobre cómo agregar informes predefinidos, consulte la descripción de la clase  [PredefinedReportsUpdater](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ReportsV2.PredefinedReportsUpdater).
    

>PROPINA
>
>-   Para validar parámetros, puede utilizar el enfoque del tema  [Validación de objetos no persistentes](https://docs.devexpress.com/eXpressAppFramework/113259/validation/validate-report-parameters).
>-   Para admitir la  [apariencia condicional](https://docs.devexpress.com/eXpressAppFramework/113286/conditional-appearance) y otras características de XAF que implican cierta reacción a los cambios en las propiedades del objeto, admita la interfaz  [INotifyPropertyChanged  ](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged)en el descendiente de Base de  **objetosde parámetros de informe**  (consulte  [La importancia de las notificaciones de cambio de propiedad para la interfaz de usuario automática Actualizaciones](https://docs.devexpress.com/eXpressAppFramework/117395/business-model-design-orm/property-changed-event-in-business-classes)



# Cómo: Filtrar la búsqueda de un parámetro de informe


Cuando el informe tiene un parámetro de informe de tipo persistente, el valor del  [parámetro](https://docs.devexpress.com/XtraReports/4812/detailed-guide-to-devexpress-reporting/use-report-parameters)  se especifica mediante un editor de búsquedas. Sin embargo, si hay una gran cantidad de objetos en la búsqueda, puede ser inconveniente desplazarse y seleccionar el valor de parámetro deseado. En este ejemplo se describe cómo filtrar la búsqueda del parámetro para reducir el número de valores disponibles.

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/dba6cbe2-52dd-4223-9f3e-d0279d6e96ca)

>NOTA
>
>-   Este ejemplo se aplica a las aplicaciones de formulariosWindows Forms y ASP.NET Web Forms.  Sin embargo, en las aplicaciones de WinForms, el editor de búsqueda ya tiene el soporte de filtrado incorporado. Por lo tanto, las personalizaciones que se muestran aquí sólo tienen sentido en aplicaciones de formularios Web Forms ASP.NET.
>-   En este tema, se supone que tiene una aplicación XAF que utiliza el módulo Reports V2  y que ha creado uno o más informes (consulte [Información general sobre el módulo Reports](https://docs.devexpress.com/eXpressAppFramework/113591/shape-export-print-data/reports/reports-v2-module-overview)  [V2](https://docs.devexpress.com/eXpressAppFramework/113591/shape-export-print-data/reports/reports-v2-module-overview)).
    

>PROPINA
>
>Un proyecto de ejemplo completo está disponible en la base de datos de ejemplos de código de DevExpress en [https://supportcenter.Devexpress.  com/ticket/details/t319024/how-to-filter-a-report-parameter-s-lookup](https://supportcenter.devexpress.com/ticket/details/t319024/how-to-filter-a-report-parameter-s-lookup) .

## Filtrar el parámetro de búsqueda mediante el origen de datos adicional

Agregue un origen de datos  [CollectionDataSource](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.ReportsV2.CollectionDataSource)  adicional al informe desde el  **Cuadro de herramientas**. En la ventana  **Propiedades**, establezca la propiedad  [DataSourceBase.ObjectTypeName](https://docs.devexpress.com/eXpressAppFramework/DevExpress.Persistent.Base.ReportsV2.DataSourceBase.ObjectTypeName)  en el tipo del parámetro que se va a filtrar. Especifique el filtro deseado mediante la propiedad  [CollectionSourceBase.Criteria.](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.CollectionSourceBase.Criteria)

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/cbe992f1-ec5f-4532-8e72-b7b1e8cc1796)

Determine el tipo de clave utilizado en el tipo del parámetro (pasado a  **ObjectTypeName**  en el paso anterior).  [Cree un parámetro](https://docs.devexpress.com/XtraReports/9998/detailed-guide-to-devexpress-reporting/use-report-parameters/multi-value-report-parameters)  del mismo tipo de clave (por ejemplo,  **Guid**  o  **int**). Habilite "Admitir la recopilación de valores estándar". Especifique el  **DataSource**, creado en el paso anterior.  **Establezca DisplayMember**  en el nombre de la propiedad que almacena el identificador legible del parámetro (por ejemplo,  **Nombre**).  **Establezca ValueMember**  en el nombre de la propiedad clave del parámetro (por ejemplo,  **Oid**).

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/abc0761c-1f31-46b9-9e81-07c4eadfd30d)

Como resultado, la búsqueda del parámetro se filtrará de acuerdo con los criterios especificados.

## Usar parámetros en cascada

En la sección anterior se describía cómo especificar un filtro estático en tiempo de diseño. Sin embargo, la expresión de filtrado puede incluir otros valores de parámetro, por lo que puede usar  [Parámetros en cascada](https://docs.devexpress.com/XtraReports/9997/detailed-guide-to-devexpress-reporting/use-report-parameters/create-a-report-parameter)  para cambiar el filtro y el tiempo de ejecución al obtener una vista previa del informe. Tenga en cuenta que el filtrado se realiza en el lado del cliente en este caso.

Agregue el parámetro  **Filter**  de un tipo de cadena. Pase los criterios que incluían una referencia al parámetro Filter a la propiedad  **FilterString**  del parámetro que se va a filtrar (por ejemplo, "Contains([Name], ?filter)").

![image](https://github.com/jjcolumb/XAF-Docs-Spanish/assets/126447472/eeed8c44-6d4f-42d3-84d2-361592e98b91)

Como resultado, la búsqueda del parámetro irá acompañada del campo  **de entrada Filtro**. La búsqueda se filtrará de acuerdo con el texto de  **filtro**  especificado.
