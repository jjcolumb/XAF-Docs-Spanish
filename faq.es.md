[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/faq.en.md)

[Back](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/README.md)

# Preguntas frecuentes - Blazor UI (FAQ)


## Reutilizar código existente de .NET Framework

**P:**  Quiero crear una aplicación Blazor UI basada en una aplicación XAF .NET Framework existente. ¿Cómo procedo?

**Un:**  Puede reutilizar la mayoría de los modelos de datos ORM y controladores independientes de la plataforma en la interfaz de usuario de Blazor con cambios mínimos o nulos. Las API básicas de CRUD y XAF de vista de datos son independientes de la plataforma, por ejemplo,  [IObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace),  [ViewController](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ViewController),  [View](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.View)  o  [Frame](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Frame).

Puede agregar módulos independientes de la plataforma existentes a un proyecto de interfaz de usuario de XAF Blazor. Convierta los módulos necesarios a .NET Standard 2.0 o .NET 6:  [compatibilidad con .NET 6+ y migración desde .NET Framework.](https://docs.devexpress.com/eXpressAppFramework/401253/overview/net-5-support-and-migration)  Una vez completada la conversión, consulte el siguiente artículo para obtener más instrucciones: ([Agregar un módulo en el código](https://docs.devexpress.com/eXpressAppFramework/118047/application-shell-and-base-infrastructure/application-solution-components/ways-to-register-a-module#code)).

Todo el código dependiente de la plataforma debe ser reescrito. Las aplicaciones Blazor tienen una arquitectura y un ciclo de vida diferentes, es posible que sea necesario cambiar el código que era común para ASP.NET formularios Web Forms y Windows Forms para Blazor. Consulte el artículo siguiente para obtener más información:  [Introducción a Blazor para desarrolladores de formularios Web Forms ASP.NET](https://docs.microsoft.com/en-us/dotnet/architecture/blazor-for-web-forms-developers/introduction).

## Agregar un módulo XAF personalizado

**P:**  ¿Cómo agrego un nuevo módulo XAF personalizado a una solución Blazor existente?

**Un:**  Usar el  **elemento Agregar DevExpress | Nuevo menú Proyecto**  para agregar un nuevo módulo XAF personalizado a una aplicación XAF .NET 6+ existente.

## Integrar componentes de interfaz de usuario personalizados

**P:**  ¿Cómo utilizo componentes que no están integrados en la interfaz de usuario de Blazor de forma predeterminada?

**Un:**  Revise la lista de componentes de interfaz de usuario de DevExpress  [Blazor](https://demos.devexpress.com/blazor/)  y  [JavaScript (DevExtreme)](https://js.devexpress.com/Demos/)  y los siguientes artículos de integración de XAF:

-   [Implementar un editor de listas basado en un componente personalizado](https://docs.devexpress.com/eXpressAppFramework/403258/ui-construction/list-editors/how-to-use-a-custom-component-to-implement-list-editor-blazor)
    -   [Cuadrícula dinámica](https://supportcenter.devexpress.com/ticket/details/t994515/blazor-how-to-integrate-the-pivot-grid-into-an-xaf-app)
    -   [Lista de árboles](https://supportcenter.devexpress.com/ticket/details/t1023129/xaf-blazor-how-to-implement-a-treelist-editor-to-display-hierarchical-data)
    -   [Programador](https://github.com/jjcolumb/ListEditorScheduler)
-   [Configuración de control de cuadrícula de acceso](https://docs.devexpress.com/eXpressAppFramework/402154/ui-construction/list-editors/how-to-access-list-editor-control)
-   [Implementar un editor de propiedades basado en un componente personalizado](https://docs.devexpress.com/eXpressAppFramework/402189/ui-construction/view-items-and-property-editors/property-editors/implement-a-property-editor-based-on-custom-components-blazor)
    -   [Editor de propiedades de color](https://supportcenter.devexpress.com/ticket/details/t957324/blazor-how-to-display-and-edit-color-properties-in-the-ui)
    -   [Botón simple](https://docs.devexpress.com/eXpressAppFramework/113653/ui-construction/view-items-and-property-editors/add-a-button-to-a-detail-view-using-custom-view-item)
    -   [Múltiples editores de propiedades de contenido de carga de archivos, cuadro de etiquetas, búsqueda, marcado](https://github.com/eXpandFramework/Reactive.XAF/tree/master/src/Modules/Blazor)
    -   [Barra de progreso en las celdas del Editor de listas de cuadrícula](https://supportcenter.devexpress.com/ticket/details/t1003220/blazor-how-to-implement-a-progress-bar-in-grid-list-editor-cells)
-   [Configuración del editor de propiedades de la vista de detalles de Access](https://docs.devexpress.com/eXpressAppFramework/402153/getting-started/in-depth-tutorial-blazor/customize-data-display-and-view-layout/access-editor-settings)  |  [Personalizar un editor de propiedades integrado](https://docs.devexpress.com/eXpressAppFramework/402188/ui-construction/view-items-and-property-editors/property-editors/customize-a-built-in-property-editor-blazor)
-   [Agregar widgets de DevExtreme a una aplicación](https://docs.devexpress.com/Blazor/403578/common-concepts/add-devextreme-widgets-to-application)
-   [Integrar un componente DevExtreme personalizado y enlazarlo a un origen de datos](https://supportcenter.devexpress.com/ticket/details/t943982/blazor-how-to-integrate-a-custom-devextreme-component-and-bind-it-to-a-data-source)
    
-   [Mostrar un formulario web totalmente personalizado que no sea XAF (con controles personalizados, JavaScript, componentes Razor, etc.)](https://supportcenter.devexpress.com/ticket/details/t939883/blazor-how-to-show-a-fully-custom-non-xaf-web-page-with-custom-controls-javascript-razor)
    
-   [Cómo implementar un escáner QR / código de barras utilizando una cámara de un dispositivo móvil](https://supportcenter.devexpress.com/ticket/details/t867142/xaf-blazor-how-to-implement-a-qr-barcode-scanner-using-a-camera-of-a-mobile-device)
-   [Crear una plantilla de aplicación de Blazor personalizada](https://docs.devexpress.com/eXpressAppFramework/403452/ui-construction/templates/in-blazor/custom-blazor-application-template)
-   [Implementar un tipo de acción personalizado](https://supportcenter.devexpress.com/ticket/details/t1101292/xaf-blazor-implement-a-custom-action-type)

Puede revisar cómo implementamos los editores de listas y propiedades. Esto puede ayudarle a integrar componentes personalizados. Consulte los archivos de la carpeta siguiente: %_PROGRAMFILES%\DevExpress  23.1\Components\Sources\DevExpress.ExpressApp\DevExpress.ExpressApp.Blazor\Editors\._

## Acceso a ASP.NET servicios principales de DI a través de IServiceProvider

**P:**  ¿Cómo puedo acceder a los servicios desde un contenedor de servicios ASP.NET Core integrado (IServiceProvider)?

**Un:**  Para acceder a  [BlazorApplication.IServiceProvider](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.AspNetCore.AspNetCoreApplication.ServiceProvider), utilice el código siguiente: . Para obtener más información, consulte el tema siguiente:  [Inserción de dependencias (DI).](https://docs.devexpress.com/eXpressAppFramework/404364/application-shell-and-base-infrastructure/dependency-injection-in-xaf-applications)`Application.ServiceProvider`

Puede encontrar útiles los siguientes ejemplos:

-   Descargar archivos o navegar a una URL mediante acciones XAF personalizadas:  [un ejemplo de código](https://supportcenter.devexpress.com/ticket/details/t944452/blazor-how-to-provide-a-file-download-or-open-an-external-hyper-link-using-an-xaf-action)  que utiliza el servicio estándar ASP.NET Core  [NavigationManager](https://docs.microsoft.com/en-us/aspnet/core/blazor/fundamentals/routing#uri-and-navigation-state-helpers).
-   Lea una cadena de conexión u otros valores de appsettings.json en código mediante ViewController:  [un ejemplo de código](https://supportcenter.devexpress.com/ticket/details/t957990/blazor-how-to-read-connection-string-and-other-values-from-the-configuration-file)  que usa el servicio  [IConfiguration](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/configuration)  estándar ASP.NET Core.
-   Acceda a HttpContext para obtener cookies, agente de usuario, dirección IP del cliente, cadena de consulta y otra información de solicitud:  [un ticket](https://supportcenter.devexpress.com/ticket/details/t975297/blazor-obtain-request-information-from-httpcontext-query-string-parameter-for-auto-login)  con más información sobre el servicio estándar ASP.NET Core  [IHttpContextAccessor](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.http.ihttpcontextaccessor).
-   Acceda a JSRuntime para llamar a JavaScript desde código .NET:  [un ejemplo de código](https://docs.devexpress.com/eXpressAppFramework/403531/analytics/dashboards/open-a-detail-view-when-the-grid-row-is-clicked-in-the-dashboard-blazor#create-a-server-side-controller)  que usa el servicio estándar ASP.NET Core  [IJSRuntime](https://docs.microsoft.com/en-us/aspnet/core/blazor/call-javascript-from-dotnet).
-   [Acceda a IHttpClientFactory para realizar solicitudes HTTP](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests).

## Uso del GPS y la cámara en dispositivos móviles

**P:**  ¿Puedo subir fotos desde la cámara de un dispositivo móvil en las aplicaciones XAF Blazor?

**Un:**  Sí. Los estándares de desarrollo web evolucionados y los navegadores modernos hicieron posible realizar muchas tareas relacionadas con el hardware (GPS, cámara, etc.) en tales aplicaciones. Ver también:  [Cómo implementar un escáner QR / código de barras usando una cámara de un dispositivo móvil](https://supportcenter.devexpress.com/ticket/details/t867142/xaf-blazor-how-to-implement-a-qr-barcode-scanner-using-a-camera-of-a-mobile-device).

![XAF Blazor Server Mobile Cargar archivos](https://docs.devexpress.com/eXpressAppFramework/images/XAF_Blazor_Server_Mobile_Upload_Files.png)

## Despliegue

**P:**  ¿Puedo implementar aplicaciones XAF Blazor en plataformas en la nube (Azure, AWS, etc.), Linux (con Nginx o Apache), Windows (con IIS), Docker y Kubernetes?

**Un:**  Sí, absolutamente. Para obtener más información, consulte los siguientes artículos:  [Hospedar e implementar ASP.NET Core Blazor Server](https://docs.microsoft.com/en-us/aspnet/core/blazor/host-and-deploy/server)  |  [Recomendaciones de implementación para aplicaciones de interfaz de usuario de XAF Blazor](https://docs.devexpress.com/eXpressAppFramework/403362/deployment/deployment-recommendations-blazor).

## Alta carga y escalado

**P:**  ¿Es Blazor UI adecuada para aplicaciones con miles de usuarios simultáneos?

**Un:**  No podemos recomendar la interfaz de usuario Blazor de XAF para aplicaciones de alta carga que deberían servir a cientos o miles de clientes web simultáneos en un único servidor web. Consulte el siguiente artículo para obtener más información:  [Recomendaciones de implementación para aplicaciones de interfaz de usuario de XAF Blazor](https://docs.devexpress.com/eXpressAppFramework/403362/deployment/deployment-recommendations-blazor).

## Compatibilidad con el modo sin conexión

**P:**  ¿La interfaz de usuario de XAF Blazor admite el modo sin conexión?

**R:**  No. La plataforma actual de Blazor Server requiere una conexión permanente a un servidor.

## Proveedores de identidad admitidos

**P:**  ¿La interfaz de usuario de Blazor de XAF admite OAuth2 (Azure AD, Microsoft 365, Google Firebase, etc.) o autenticación JWT (Identity Server, Auth0, etc.)?

**Un:**  Sí, XAF admite estos proveedores de identidad con la ayuda de las capacidades integradas de ASP.NET Core y la extensibilidad del sistema de seguridad de XAF. Puede encontrar útiles los siguientes ejemplos:

-   [Cómo: Usar proveedores de autenticación de Active Directory y OAuth2 en aplicaciones Blazor](https://docs.devexpress.com/eXpressAppFramework/402197/data-security-and-safety/security-system/authentication/oauth-and-custom-authentication/active-directory-and-oauth2-authentication-providers-in-blazor-applications)
-   [Ejemplo de uso de Identity Server](https://github.com/biohazard999/IDSDemoXaf)  y  [vídeo](https://www.youtube.com/watch?v=9Nlq2HCfMFU).

## Personalizar cuadros de diálogo emergentes

**P:**  ¿Cómo cambio el tamaño de los cuadros de diálogo emergentes? ¿Puedo aumentar el ancho de ventana predeterminado si contiene un formulario complejo?

**R**:  [Cómo: Ajustar el tamaño y el estilo de los cuadros de diálogo emergentes (Blazor).](https://docs.devexpress.com/eXpressAppFramework/404014/ui-construction/templates/in-blazor/change-popup-window-dimensions)

## Botones "Guardar y nuevo" y "Guardar y cerrar"

**P:**  ¿Cómo devuelvo los botones "Guardar y nuevo" y "Guardar y cerrar" en DetailView (como en WinForms y WebForms)?

**R:**  [Blasor - Cómo implementar los botones "Guardar y nuevo" y "Guardar y cerrar".](https://supportcenter.devexpress.com/ticket/details/t951115/xaf-blazor-how-to-implement-the-save-new-and-save-close-buttons-in-detailview-as-it-was)

## Navegadores compatibles

**P:**  ¿Cuáles son los navegadores web de escritorio y móviles compatibles?

**Un:**  Puede encontrar la lista de exploradores compatibles en el siguiente artículo de Microsoft:  [https://docs.microsoft.com/en-us/aspnet/core/blazor/supported-platforms](https://docs.microsoft.com/en-us/aspnet/core/blazor/supported-platforms)  (Microsoft Internet Explorer 11 y versiones anteriores no son compatibles).

Probamos XAF Blazor UI en los siguientes entornos:

-   Las últimas versiones de escritorio de Google Chrome y Mozilla FireFox (pruebas automatizadas y pruebas basadas en capturas de pantalla con EasyTest y Selenium).
-   Las últimas versiones de Google Chrome en Android, Safari (incluido iOS) y Microsoft Edge (pruebas manuales).

## Soporte VB.NET

**P:**  ¿Puedo crear una aplicación VB.NET Blazor UI?

**Un:**  Puede adjuntar los módulos VB.NET convertidos a .NET Standard 2.0 a una aplicación C# Blazor.

XAF no incluye una plantilla de proyecto VB.NET para la interfaz de usuario de Blazor. No puede crear una aplicación VB.NET Blazor porque Microsoft no admite esta funcionalidad:  [admite VB.NET en ASP.NET Core 3.0 y Blazor.](https://developercommunity.visualstudio.com/idea/468570/support-vbnet-in-aspnet-core-30-and-blazor.html)

## Mantenga viva la conexión

La interfaz de usuario de XAF Blazor es una aplicación normal de ASP.NET Core Blazor Server que se utiliza para mantener activa una conexión con el servidor. Utilice la siguiente solución para administrar este comportamiento:  [Configuración de tiempo de espera y keepalive](https://learn.microsoft.com/en-us/aspnet/signalr/overview/guide-to-the-api/handling-connection-lifetime-events#timeoutkeepalive).`SignalR`
