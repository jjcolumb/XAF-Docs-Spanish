[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers#readme)


# Consideraciones de XAF para recién llegados

  
XAF es una potencia, un marco de desarrollo de software como ningún otro. Si es nuevo en XAF y lo está considerando para un próximo proyecto, asegúrese de revisar nuestra página web de productos y los materiales de ayuda introductorios para obtener un resumen de sus beneficios y características de productividad para equipos de desarrollo pequeños y grandes por igual.

[PRUEBA GRATUITA DE 30 DÍAS](https://go.devexpress.com/devexpressdownload_universaltrial.aspx)
[HOJA DE RUTA](https://www.devexpress.com/go/XAF_Roadmap.aspx)

Este artículo de la base de conocimientos documenta algunas de las capacidades de XAF y, lo que es más importante, describe el nivel de experiencia/conocimiento necesario para maximizar su potencial. Al igual que cualquier otro marco de desarrollo avanzado, XAF tiene una curva de aprendizaje y es más adecuado para desarrolladores experimentados que desean crear prototipos y entregar aplicaciones basadas en CRUD de la manera más eficiente posible.

## Lo básico

El eXpressApp Framework (XAF) utiliza un [Flujo de desarrollo de software híbrido](https://docs.devexpress.com/eXpressAppFramework/112558/fundamentals/xaf-overview) - un flujo que se encuentra en algún lugar entre una metodología de desarrollo tradicional "todo manual" y un enfoque totalmente "sin código". A pesar de todas sus fortalezas y ventajas, XAF no es la mejor opción para todos. Aquellos que deseen un marco de desarrollo sin código pueden descubrir que en algún momento del proceso de desarrollo, XAF requiere que los desarrolladores escriban código.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/4d84a4e9-6deb-4b40-a032-c348964e71aa)


En este artículo se definirá el flujo de desarrollo de XAF en términos claros para que no invierta recursos en un proyecto basado en XAF solo para descubrir (en una etapa posterior) que XAF todavía requiere que codifique manualmente partes de su aplicación con tecnología XAF. Además, este artículo ayudará a aclarar los siguientes temas de desarrollo relacionados con XAF:

-   Sugerencias y requisitos previos para desarrolladores de XAF;
-   XAF versus alternativas;
-   El alcance de XAF y sus límites.

## Público objetivo de XAF

XAF fue creado para desarrolladores de software que desean maximizar la productividad. Esto puede sonar como un cliché, pero una vez que use eXpressApp Framework (XAF) durante unas semanas, descubrirá que esta afirmación es cierta.

Antes de profundizar, permítanme enfatizar que XAF no es una herramienta para no programadores o principiantes. XAF es un marco de aplicación de propósito general diseñado para **Desarrolladores de .NET** con experiencia en desarrollo de aplicaciones de línea de negocio. Basándonos en estadísticas internas, sabemos que los equipos de desarrollo prefieren XAF mucho más que las tiendas unipersonales. Por lo tanto, si forma parte de un equipo experimentado, es probable que se beneficie más de las capacidades de XAF.

Estas características son las favoritas entre los desarrolladores de XAF:

-   Generación automática de bases de datos y CRUD UI para plataformas Windows, Web y Mobile, incluida la compatibilidad con más de una docena de RDBMS con bibliotecas EF Core y XPO ORM.
-   Personalización enriquecida de la interfaz de usuario en tiempo de ejecución tanto para desarrolladores como para usuarios finales. Sus aplicaciones pueden abordar los requisitos empresariales cambiantes sin necesidad de volver a implementarlas.
-   Los elementos esenciales comunes del negocio, como informes, seguridad de la información, validación, visualización de datos y análisis, están disponibles de inmediato. Estos módulos son totalmente configurables.
-   La lógica empresarial de .NET y el código de configuración de la interfaz de usuario se comparten entre plataformas y bases de datos.
-   Con XAF, los desarrolladores pueden centrarse en las reglas de negocio, en lugar de en la codificación de bajo nivel, como la administración de bases de datos y UI.

Así es como Martin Praxmarer de PraKom Software GmbH describió los principales beneficios de XAF:

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/105ffb69-4d48-4558-b0ba-5787d6dead19)


## Martín Praxmarer

### PraKom Software GmbH

XAF nos ha ayudado a ofrecer un producto altamente flexible y estable. XAF nos permite ofrecer rápidamente nuevas funcionalidades con un equipo relativamente pequeño. Comenzamos con un desarrollador y ahora tenemos 8 desarrolladores trabajando en nuestro software basado en XAF.

## Prerrequisitos

Aunque la arquitectura de XAF ayuda a los desarrolladores a ahorrar un tiempo de desarrollo significativo, el marco en sí no vigila todos los aspectos del proceso de desarrollo de software. Aún debe seguir procedimientos de desarrollo, prueba, implementación y mantenimiento bien establecidos. Desafortunadamente, el conocimiento de Visual Studio, .NET, administración de bases de datos y conocimientos generales de programación no es opcional. Aquellos que más se benefician de XAF tienen experiencia en algunos o todos los siguientes:

-   Capacidad para usar la sintaxis correcta de C#, VB.NET, SQL, JavaScript, HTML, CSS, XML, JSON.
-   Capacidad para escribir clases, miembros, interfaces, consultas LINQ y SQL, manejar eventos.
-   Capacidad para crear bibliotecas de clases y organizar la estructura y las compilaciones del proyecto, editar archivos de configuración.
-   Capacidad para usar características y comandos estándar de Visual Studio dentro del editor de código, el Explorador de soluciones, el Cuadro de herramientas, etc. (Vaya a Definición, Buscar y reemplazar, agregar y quitar referencias de ensamblado o paquetes NuGet, etc.).
-   Capacidad para resolver errores de compilación y asociados en Visual Studio mediante la documentación de Microsoft o StackOverFlow.
-   Capacidad de captura y [depurar excepciones de .NET y JavaScript](https://docs.devexpress.com/eXpressAppFramework/112572/concepts/debugging-testing-and-error-handling).
-   Capacidad para monitorear, diagnosticar y mitigar posibles [seguridad](https://github.com/DevExpress/aspnet-security-bestpractices/tree/master/SecurityBestPractices.WebForms) y [rendimiento](https://www.devexpress.com/support/center/question/details/t148978/how-to-measure-and-improve-the-application-s-performance) problemas como la complejidad de la aplicación, [base de datos](https://www.devexpress.com/support/center/question/details/t572322/) El tamaño y la carga de usuarios crecen.
-   Capacidad para implementar aplicaciones, configurar y mantener entornos de desarrollo y producción apropiados / hardware y software asociados (por ejemplo, servidores web, bases de datos, configuración de firewall).
-   Capacidad para administrar software de terceros y licencias de servicio y similares.

  
Por supuesto, aquellos que tienen éxito con XAF también están dispuestos a:

-   Siga las prácticas recomendadas para los componentes XAF, XPO, Microsoft y DevExpress.
-   Siga los procedimientos recomendados para las tecnologías subyacentes (.NET, WinForms, ASP.NET WebForms, ASP.NET Core, WCF, SQL Server, IIS, etc.).

Si no ha creado aplicaciones de línea de negocio para plataformas web y de escritorio en el pasado, o si es nuevo en .NET y Visual Studio, entonces sería mejor comenzar su viaje con un producto diferente. La XAF no puede sustituir a la experiencia práctica. En términos reales, los desarrolladores que están familiarizados con las bibliotecas de mapeo relacional de objetos (ORM) (por ejemplo, Hibernar con Java) y el patrón de diseño de interfaz de usuario Mode-View-Controller (MVC) (o han desarrollado marcos de andamiaje internos en el pasado) alcanzan la competencia con XAF con bastante rapidez (incluso si no están familiarizados with.NET sí mismos).

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/7ff31364-96a0-45f1-80fe-ae816b94186e)


## Sven Stening

### PSSP GmbH

Creo que el verdadero poder de XAF es su forma especial de manejar el patrón MVC. Al agregar una propiedad a un objeto de negocio, no importa si lo hace en código o con el Editor de modelos de aplicación, todos los tipos posibles de vistas pueden mostrar los nuevos valores: Vista detallada, Vista de lista, Informes, Estadísticas, etc. Esto es realmente impresionante y me deja atónito cada vez que lo veo. Realmente has hecho un gran trabajo. Para ser honesto, he desarrollado algo muy similar en el pasado y lo he usado ahora durante mucho tiempo para mis proyectos. Pero XAF es mucho más potente y fácil de usar. Sin mencionar sus excelentes componentes de interfaz de usuario.

## Alcance del producto y expectativas del mundo real

XAF produce aplicaciones estándar de .NET WinForms, ASP.NET WebForms o ASP.NET Core Blazor. Estas aplicaciones no son diferentes de otros tipos de aplicaciones creadas para estas plataformas. Para utilizar XAF, debe estar familiarizado con estas plataformas y tecnologías relacionadas en un nivel intermedio.

Debe pensar en XAF como un marco de uso general extensible con un conjunto finito de soluciones para una variedad de escenarios de uso (por supuesto, algunos escenarios de uso no se han considerado y no se han implementado). No debe esperar que XAF envuelva cada control de interfaz de usuario de DevExpress y sus características, o cubra todas las necesidades de los desarrolladores en plataformas compatibles. La funcionalidad no disponible requiere que escriba código. Aunque ampliamos continuamente XAF en función de los comentarios de los usuarios y los requisitos de uso empresarial, si falta algo en XAF, es posible que se vea obligado a implementarlo usted mismo.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/4f6493cc-4bf0-41d8-b431-f911d8e6475a)


## Muhamad Nafis

Después de usar XAF durante cinco años, ya ni siquiera puedo pensar en crear una aplicación compleja sin ella. Es un marco de aplicaciones empresariales muy potente y personalizable basado en los mejores componentes del mercado. Una de las mejores cosas es el fantástico equipo de soporte. Cada vez que pienso que algo no se puede hacer, me explican claramente cómo lograr lo que necesito. Así que gracias de nuevo a todos los involucrados. Desde desarrolladores hasta ventas y soporte, me has hecho más productivo mientras facilitas mi trabajo. ¡No hay mejor resultado que ese!

## Migración de aplicaciones a XAF

En función del diseño y la arquitectura de la aplicación existentes, debe tener en cuenta al menos los siguientes aspectos de migración.

### Almacén de datos

Las aplicaciones XAF .NET pueden funcionar directamente con una docena de motores de base de datos populares. Si tiene bases de datos existentes, puede reutilizar los datos en la mayoría de los casos. Es posible que desee realizar modificaciones mínimas en el esquema de base de datos en función de las características específicas de XAF que espera usar dentro de su aplicación (por ejemplo, agregar columnas para un bloqueo optimista). La interfaz de usuario de XAF también le permite mostrar y editar registros de datos que no están conectados a tablas de base de datos: [Objetos no persistentes](https://docs.devexpress.com/eXpressAppFramework/116516/concepts/business-model-design/non-persistent-objects).

### Modelo de datos ORM

Si tiene clases de modelo de datos XPO o Entity Framework existentes, la mitad del trabajo ya está hecho: puede reutilizar estos modelos de datos dentro de XAF tal como están (o con modificaciones menores). Si no tiene un modelo de datos ORM listo para usar, puede generarlo automáticamente a través de [XPO ORM](https://docs.devexpress.com/eXpressAppFramework/113451/task-based-help/business-model-design/express-persistent-objects-xpo/how-to-generate-xpo-business-classes-for-existing-data-tables) o [Marco de trabajo de entidades](https://docs.microsoft.com/en-us/ef/core/managing-schemas/scaffolding?tabs=dotnet-core-cli) asistentes (mediante ingeniería inversa del esquema de base de datos).

Los datos de procedimientos almacenados (SP) o servicios externos se pueden visualizar y administrar dentro de formularios CRUD XAF mediante el uso de objetos no persistentes. También puede asignar su modelo de datos a vistas de base de datos, una opción utilizada a menudo por aquellos que deben admitir sistemas heredados.

### Lógica de negocios

XAF se basa en metodologías ORM. En la mayoría de los casos, puede manipular datos a través de paradigmas de desarrollo orientados a objetos: consultar y editar objetos ORM frente a objetos de base de datos (tablas, filas, columnas utilizando SQL sin procesar). Si no puede usar metodologías ORM, aún puede ejecutar procedimientos almacenados, llamar a servicios externos o hacer otras cosas comunes a las aplicaciones .NET normales.

Tenga en cuenta que los escenarios que no son ORM no deben dominar su aplicación (hacerlo evitará maximizar el potencial de XAF). Si la mayor parte de su lógica empresarial se maneja a través de SP o RPC heredados, en última instancia, querrá reescribir esta lógica utilizando metodologías ORM.

### Construcción de UI

XAF genera automáticamente [CRUD y formularios de interfaz de usuario auxiliares](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction) basado en estructuras de modelos de datos ORM y metadatos asociados. Por ejemplo, lista predeterminada y detalle [Editores de formularios](https://docs.devexpress.com/eXpressAppFramework/113014/concepts/business-model-design/data-types-supported-by-built-in-editors) se crean en función de los tipos de propiedades y atributos de clase). Puede personalizar esta interfaz de usuario para abordar varios escenarios de uso.

Si va a tardar demasiado tiempo en volver a escribir una interfaz de usuario existente con XAF, puede volver a utilizar los controles de usuario y formularios personalizados dentro de la aplicación XAF. Por ejemplo, puede mostrar un formulario independiente que no sea XAF desde un menú de navegación o mostrar un control de usuario personalizado (o de terceros) en un formulario XAF existente.

Para obtener más información, consulte [Sugerencias de personalización de la interfaz de usuario](https://www.devexpress.com/products/net/application_framework/xaf-considerations-for-newcomers.xml#ui-customization-categories) y [Cómo utilizar un control personalizado que no está integrado de forma predeterminada](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default).

### Módulos reutilizables

XAF está diseñado con una arquitectura modular e incluye docenas de componentes XAF que se pueden reutilizar en aplicaciones que no son XAF. Por ejemplo, puede reutilizar el modelo de datos ORM de XAF, la lógica empresarial, [Sistema de seguridad](https://www.devexpress.com/products/net/application_framework/security.xml), localización, seguimiento de auditoría, validación y otros módulos XAF en formularios que no son XAF dentro de la aplicación existente. [Más información sobre los módulos reutilizables](https://supportcenter.devexpress.com/internal/ticket/details/q94961)

Este puede ser su primer paso si no está listo para ir "all-in" con XAF o simplemente desea explorar las opciones de migración de XAF de forma iterativa (ciertas clases y módulos del modelo de datos ORM) mientras conserva el núcleo de su aplicación .NET heredada.

## Categorías de personalización de la interfaz de usuario por nivel de habilidad

Cuando personalice la interfaz de usuario, el código de acceso a datos o la capa de base de datos predeterminados de XAF, tenga en cuenta las siguientes tres categorías de tareas, ya que varían según el nivel de conocimiento o experiencia.

### Categoría #1 (Intermedio): Personalización de las características y API integradas de XAF

Por lo general, se trata de tareas de código bajo que se completan en un módulo independiente de la plataforma de forma declarativa (con atributos) o visualmente (con diseñadores). Ejemplos:

-   Localice clases empresariales y/o modifique la configuración de Vista en el cuadro [Editor de modelos](https://docs.devexpress.com/eXpressAppFramework/112582/concepts/application-model/model-editor);
-   Utilice y configure módulos adicionales a través de la [Asistente de soluciones, módulos o diseñadores de aplicaciones](https://docs.devexpress.com/eXpressAppFramework/112827/design-time-features/application-designer) o en código;
-   Utilice atributos de código listos para usar y otras API XAF como ListView, ViewController, ASPxGridListEditor.

La mayoría de los usuarios de XAF adquieren los conocimientos necesarios para completar estas tareas mientras navegan por nuestra [Empezar](https://docs.devexpress.com/eXpressAppFramework/113577/getting-started) Tutoriales ([Componentes de la solución de aplicación](https://docs.devexpress.com/eXpressAppFramework/112569/concepts/application-solution-components), [Diseño de Modelo de Negocio](https://docs.devexpress.com/eXpressAppFramework/113461/concepts/business-model-design), [Modelo de aplicación](https://docs.devexpress.com/eXpressAppFramework/112579/concepts/application-model), [Manipulación de datos y lógica empresarial](https://docs.devexpress.com/eXpressAppFramework/113708/concepts/data-manipulation-and-business-logic) entre otros conceptos fundamentales de desarrollo relacionados con la XAF). Es fundamental explorar estos temas porque no se puede lograr una sola tarea sin esta base básica.

### Ejemplo

La aplicación MainDemo de XAF consta de múltiples módulos integrados como seguridad, informes, validación, auditoría de datos, etc. Los desarrolladores de XAF pueden usar asistentes o diseñadores, arrastrar y soltar componentes XAF prefabricados desde Visual Studio Toolbox o escribir manualmente un par de líneas de código:

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

Este código hace automáticamente lo siguiente para los desarrolladores de XAF:

-   Agrega informes, usuarios, roles y otros elementos de navegación y menú principal automáticamente, para que los usuarios de la aplicación puedan ver y modificar datos en formularios de lista y detalle CRUD. [Documentación](https://docs.devexpress.com/eXpressAppFramework/113198/concepts/system-module/navigation-system?p=netframework)
-   Agrega un formulario de inicio de sesión con campos de usuario y contraseña, crea las tablas de seguridad necesarias en la base de datos y permite a los usuarios de la aplicación configurar usuarios, roles y permisos en tiempo de ejecución. [Documentación](https://docs.devexpress.com/eXpressAppFramework/113366/concepts/security-system)
-   Integra las funciones de vista previa de informes y diseñador de tiempo de ejecución para todas las plataformas compatibles y también almacena definiciones de informes en la base de datos. [Documentación](https://docs.devexpress.com/eXpressAppFramework/113591/concepts/extra-modules/reports-v2/reports-v2-module-overview)
-   Resalta los editores requeridos, no permite a los usuarios introducir datos nulos o no válidos. Permite a los usuarios agregar, eliminar y modificar reglas de validación integradas o personalizadas de forma visual o declarativa a través de atributos. [Documentación](https://docs.devexpress.com/eXpressAppFramework/113008/concepts/extra-modules/validation/validation-rules)
-   Agrega el historial de cambios para las tablas de datos requeridas: cada modificación de datos se asocia con un usuario de la aplicación para una seguridad óptima. [Documentación](https://docs.devexpress.com/eXpressAppFramework/112782/concepts/extra-modules/audit-trail-module)

Con estas pocas líneas de código, los desarrolladores de XAF pueden construir las bases de una aplicación CRM o ERP (escritorio o web) en **horas en lugar de meses**.

Aquí hay un testimonio de David Desiderà, arquitecto de soluciones en [SpecTec](https://www.spectec.net/). David integró con éxito las API del sistema de seguridad de XAF con una aplicación WinForms heredada:

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/ca44e311-ef21-445f-b394-d8908b4360e9)


## David Desiderà

Hace más de un año expliqué a mis colaboradores que, en mi opinión, era posible integrar la capa de seguridad de XAF con la interfaz de interfaz de usuario en una aplicación empresarial WinForms existente que tenía 10 años. ¡Lo implementamos con éxito! Me tomó 40 días-hombre de trabajo en total en lugar de al menos 400 si hubiera decidido comenzar desde cero. ¡Ustedes me salvaron la vida!

### Categoría #2 (Avanzado): Personalización de componentes subyacentes que no son XAF

Esta categoría de tarea se refiere a los componentes de DevExpress envueltos por [Elementos de la interfaz de usuario de XAF](https://docs.devexpress.com/eXpressAppFramework/112607/concepts/ui-construction/ui-element-overview) o abstracciones XAF no visuales. En el 99% de los casos, se aplican soluciones estándar para componentes que no son XAF (las especificidades XAF son muy raras). Ejemplos:

-   Personalice el control de cuadrícula para habilitar una característica no expuesta en las API Application Model, GridListEditor o ListView.
-   Modifique las plantillas de formulario predeterminadas y ofrezca diferentes posiciones y apariencia de menú.
-   Resalte las celdas de la tabla condicionalmente dentro de una banda de detalles del informe o un elemento de vista de panel.

Para acceder a estos componentes que no son XAF dentro de una aplicación XAF (en todas las plataformas compatibles), es importante comprender [cómo XAF scaffolds la interfaz de usuario](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction) (su arquitectura MVC) y su capa de datos. Los desarrolladores que entienden dónde trazar la línea entre los componentes XAF y los que no son XAF pueden abordar los requisitos de personalización mucho más rápido. Pueden encontrar respuestas en materiales de aprendizaje existentes para componentes que no son XAF o ponerse en contacto con el soporte de componentes que no son XAF.

### Ejemplo

Es posible que los desarrolladores de XAF deseen personalizar las opciones de control de cuadrícula en formularios de lista XAF predeterminados. Estas opciones no están disponibles en el Editor de modelos ni en la API predeterminada de XAF, porque rara vez se utilizan. Una solución típica es escribir un ViewController que inyecte la lógica de personalización necesaria una vez creados los controles ListView de XAF. A continuación se muestra un ejemplo de un controlador personalizado:

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

Para escribir este código, los desarrolladores de XAF necesitan saber lo siguiente:

-   Los fundamentos de los elementos de la interfaz de usuario de XAF (ListView o ListEditor) y las formas de obtener acceso a los controles de interfaz de usuario de DevExpress subyacentes para WinForms o WebForms.
-   Metodologías de personalización recomendadas para plataformas Microsoft WinForms y WebForms.
-   La API de los controles de interfaz de usuario de DevExpress subyacentes como [Control de cuadrícula de datos de WinForms](https://www.devexpress.com/products/net/controls/winforms/grid/).

XAF tiene un techo increíblemente alto. El siguiente testimonio de de [CTL Computertechnik Lang](https://www.ctl.de/) habla de su potencial en manos del equipo adecuado.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/2f658684-3939-4bef-8a85-0ccd8705082f)


## Michael Lang

### CTL Computertechnik Lang

Después de comprender el método de desarrollo MVC de DevExpress XAF, aprendimos a usarlo y experimentamos que casi cualquier cosa es más fácil de hacer con él, pero es realmente diferente de todos los demás métodos habituales. Nos encanta.

Para obtener más información sobre Michael y su equipo, por qué eligió XAF y XPO para su proyecto WinForms, y las dificultades que encontró, consulte el siguiente caso práctico de DevExpress: [CTL Computertechnik Lang: controles XAF y WinForms](https://www.devexpress.com/aboutus/testimonials/ctl/).

### Categoría #3 (Avanzado+): Integración de controles personalizados e implementación de componentes

A lo largo de los años, hemos aprendido que muchos desarrolladores de XAF desean integrar DevExpress, Microsoft o [controles de terceros dentro de la interfaz de usuario de XAF](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default). También hemos aprendido que muchos desarrolladores desean implementar componentes de interfaz de usuario personalizados, módulos de aplicaciones y funcionalidades que no están disponibles de forma predeterminada. Ejemplos:

-   Cree un editor de listas personalizado basado en un widget de galería para registros ListView.
-   Cree un editor de propiedades personalizado basado en un cuadro de token para ver y editar las propiedades de la colección en DetailView.
-   Cree un control de acción personalizado basado en dos selectores de fecha en el menú principal.

Estas tareas a menudo se realizan en un nivel de marco inferior y requieren más conocimiento y experiencia con XAF (en comparación con las Categorías # 1 y # 2). Este es el mismo conocimiento requerido si tuviera que codificar una aplicación sin nuestro marco. Los beneficios relacionados con XAF y el ahorro de tiempo son mínimos para aquellos que desean integrar controles personalizados. Como regla general, sepa cómo resolver y, opcionalmente, implementar primero sus requisitos en una aplicación que no sea XAF. La integración de XAF será mucho más fácil como resultado.

### Ejemplo: VenDoc de PraKom Software GmbH

VenDoc es una solución de software ERP construida por Martin Praxmarer de [PraKom Software GmbH](https://prakom.net/). La aplicación aborda las necesidades comerciales de más de 750 empresas en las regiones DACH y Tirol del Sur de Europa. Esta aplicación tiene muchos componentes personalizados o formularios totalmente personalizados que no son XAF.

La siguiente captura de pantalla muestra un panel a la derecha que se creó con una plantilla y controles personalizados.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/ab1495ac-ed94-4a39-9329-3023567335d8)


[Caso práctico de PraKom Software GmbH: controles XAF y WinForms](https://www.devexpress.com/aboutus/testimonials/prakom/)

### Ejemplo: integración de Autodesk Forge por Bahalddin Elsayed

Por favor, revise una interesante captura de pantalla de Bahalddin Elsayed, un usuario experimentado y veterano de XAF de Dubai. Su aplicación WinForms con tecnología XAF integra Autodesk Forge. Este es un ejemplo perfecto de lo que es posible con las amplias opciones de personalización y extensibilidad de la interfaz de usuario de XAF. Para maximizar el potencial de XAF, Bahalddin y su equipo revisaron el código fuente de XAF y ampliaron sus capacidades según fuera necesario.

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/f1041e80-7786-4a9b-bd7e-e297fb488abc)


[Construcción de UI](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction) | [Usar un control personalizado que no está integrado de forma predeterminada](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default)

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/b7821556-ea53-40e4-a318-f68615e00983)


## Santiago Moscoso

Me he convertido en un superhéroe de la interfaz de usuario principalmente por las poderosas características de XtraGrid, los usuarios están fascinados de lo fácil que es filtrar, agrupar, agregar resúmenes, mover columnas, y XAF facilita la obtención de columnas de objetos relacionados, lo que ha ahorrado mucho tiempo en la creación de vistas personalizadas, cada usuario puede crear sus vistas personalizadas, Y eso los hace sentir inteligentes.

## Sugerencias avanzadas para personalizar la interfaz de usuario

Los siguientes consejos te ayudarán a implementar tareas de las categorías #2 y #3:

### Obtener experiencia dentro de la plataforma de destino

-   Investigue WinForms, ASP.NET WebForms, ASP.NET Core, HTML / JavaScript / CSS y tecnologías relacionadas como XPO, SQL Server, WCF, OData, API web, etc.
-   Comprender las diferencias entre un cliente de escritorio "gordo" y una Web cliente-servidor o una aplicación móvil del lado del cliente (a través del marco de interfaz de usuario subyacente, la arquitectura, el ciclo de vida de la aplicación, los controles visuales, los lenguajes de programación, etc.).
-   Busque recursos de la comunidad pública para posibles soluciones y conceptos de desarrollo.

### Familiarícese con los componentes subyacentes que no son XAF

-   Tenga en cuenta que XAF utiliza componentes DevExpress WinForms, ASP.NET WebForms ASP.NET Core Blazor, DevExtreme para cada plataforma correspondiente.
-   Investigue soluciones estándar para componentes que no sean XAF en la documentación, demostraciones, ejemplos de código y artículos de la base de conocimientos de DevExpress. Siéntase libre de usar [Nuestro motor de búsqueda](https://search.devexpress.com/) o Google. Tiene más posibilidades de localizar soluciones en la sección de componentes del sistema de ayuda/documentos de DevExpress que en los materiales de aprendizaje de XAF (que solo describen conceptos relacionados con XAF).
-   Si su caso no está cubierto por los materiales de aprendizaje de componentes de DevExpress, envíe sus preguntas al equipo de soporte de DevExpress correspondiente.

### Estudiar la infraestructura de interfaz de usuario de XAF y los elementos que envuelven los componentes subyacentes

-   Compruebe las extensiones de la comunidad para ver si alguien ya ha completado una integración XAF por usted.
-   Investigue la integración de XAF utilizando la documentación en línea en [Construcción de UI](https://docs.devexpress.com/eXpressAppFramework/112638/concepts/ui-construction) | [Usar un control personalizado que no está integrado de forma predeterminada](https://docs.devexpress.com/eXpressAppFramework/113610/concepts/ui-construction/using-a-custom-control-that-is-not-integrated-by-default), [Ayuda basada en tareas](https://docs.devexpress.com/eXpressAppFramework/112682/task-based-help) (en particular, busque "Control"), así como ejemplos de bases de conocimiento (por ejemplo: [Formas de obtener acceso a los elementos de la interfaz de usuario y sus controles](https://docs.devexpress.com/eXpressAppFramework/120092/concepts/ui-construction/ways-to-access-ui-elements-and-their-controls)).
-   Recuerde siempre que XAF crea controles visuales dinámicamente en el código (en tiempo de ejecución, no en el diseñador de formularios).
-   Investigue el [código fuente](https://supportcenter.devexpress.com/Ticket/Details/ka18677/where-can-i-get-demo-source-code-folder-installed-assemblies-or-source-code-on-machines) para elementos de interfaz de usuario XAF integrados en las siguientes carpetas:
    
    ...\DevExpress.ExpressApp.Wxx\Editors\ ...\DevExpress.ExpressApp.Wxx\Templates\  
      
    ...\DevExpress.ExpressApp.Wxx\Layout\
    
    Estos ejemplos del mundo real lo ayudarán a comprender mejor cómo funcionan las cosas bajo el capó y a dominar rápidamente los mejores patrones y prácticas.
    
-   Compare su implementación personalizada con implementaciones XAF estándar para detectar errores. [Lea la publicación del blog](https://dennisgaravsky.blogspot.com/2018/02/learning-through-reading-source-code.html)
-   Depure el componente DevExpress o el código fuente XAF cuando encuentre problemas. [Lea la documentación](https://docs.devexpress.com/GeneralInformation/403656/support-debug-troubleshooting/debug-controls-with-debug-symbols)
-   Utilice nuestro motor de búsqueda o Google para localizar información. Puede buscar por nombre de API, métodos superiores en la pila de llamadas de error, palabras clave que describen una característica o tarea.

## Alcance del soporte técnico

Hacemos algunas suposiciones con respecto a nuestros materiales de aprendizaje y servicios de apoyo. Queremos aclarar estas suposiciones para no causar confusión o frustrar sus esfuerzos de desarrollo.

Nuestros objetivos de servicio de soporte son:

-   Ayude a los clientes a conocer nuestros productos más rápidamente.
-   Resuelva problemas técnicos asociados con las funciones de envío.
-   Mejorar nuestra base de conocimientos.

Los servicios personalizados de programación y consultoría están fuera del alcance de nuestros servicios. Ejemplos de programación y consultoría personalizadas incluyen: crear componentes personalizados a pedido (por ejemplo, un editor de propiedades XAF o un contenedor de acciones); Depurar o generar perfiles de un proyecto o base de datos de cliente completo.

No ofrecemos soporte para problemas generales de programación que no estén relacionados con los productos DevExpress. Por ejemplo, si desea analizar el diseño de bibliotecas de clases de Entity Framework o ASP.NET procedimientos recomendados principales, debe consultar recursos de la comunidad pública como StackOverflow, CodeProject o póngase en contacto con personas experimentadas. [Consultores externos](https://www.devexpress.com/products/net/application_framework/#community) para ayudarle con problemas generales de programación.

Las tareas avanzadas, raras o extremadamente específicas a menudo son complejas y siempre requieren muchos recursos. Es posible que no tengamos el conocimiento de fondo adecuado y que no podamos proporcionar orientación y ejemplos. Estamos más que felices de hacer un esfuerzo adicional para tratar de llegar al fondo de cada problema complejo. Su ayuda se asegurará de que esto se haga rápidamente. Los siguientes temas de ayuda altamente calificados pueden ser útiles para solucionar problemas:

-   [¿Cómo hago una buena pregunta?](https://stackoverflow.com/help/how-to-ask)
-   [¿Cómo crear un ejemplo mínimo, completo y verificable?](https://stackoverflow.com/help/mcve)
-   [¿Cómo reportar errores de manera efectiva?](https://www.chiark.greenend.org.uk/~sgtatham/bugs.html)
-   [Una solicitud de programas de ejemplo simples](https://community.devexpress.com/blogs/ctodx/archive/2009/01/08/a-request-for-simple-example-programs.aspx)
-   [Recopilar y analizar la información de diagnóstico](https://docs.devexpress.com/eXpressAppFramework/117344/concepts/debugging-testing-and-error-handling/collect-and-analyze-the-diagnostic-information)

![image](https://github.com/lianhdez95/XAF-Considerations-for-Newcomers/assets/126447472/5b49c33b-052f-41ff-b273-320c3dd22e8c)


## Paul Jacoby

### Sistemas Iatric, Inc.

Mi empresa decidió recientemente hacer más desarrollo utilizando el marco DevExpress XAF/XPO. Hemos trabajado con controles DevExpress para muchas otras necesidades empresariales para aliviar la carga de desarrollar en .NET, por lo que fue bastante sencillo pasar a XAF/XPO. Hay una curva de aprendizaje, pero en su mayor parte los tutoriales y demostraciones responden muchas preguntas. Sin embargo, en un par de ocasiones simplemente no pude resolverlo. Me puse en contacto con el soporte de DevExpress, esperando al menos unos días de retraso, si no semanas. Sin embargo, me sorprendió gratamente la rapidez de sus respuestas. Las respuestas fueron rápidas y hasta el punto de permitirme implementar fácilmente lo que se necesitaba. Es un placer trabajar con los controles de DevExpress, y ahora, ¡ha sido un placer trabajar con su equipo de soporte! Gracias a DevExpress se eliminan muchas de las frustraciones en el desarrollo de software.

## Comencemos

Si está listo para comenzar su viaje con XAF, no dude en descargar nuestra prueba gratuita de 30 días hoy. Si necesita orientación adicional sobre si XAF es la opción correcta para su próximo proyecto, envíe un correo electrónico [support@devexpress.com](mailto:support@devexpress.com). Estaremos encantados de hacer un seguimiento y darle una respuesta directa.

Hasta que hablemos a continuación, por favor revise [Comentarios y estudios de casos](https://www.devexpress.com/aboutus/testimonials/) de usuarios felices de XAF.
