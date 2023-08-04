
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/README.en.md)

[Back](https://github.com/jjcolumb/XAF-Docs-Spanish/blob/master/README.en.md)

# Frequently Asked Questions - Blazor UI (FAQ)


## Reuse Existing .NET Framework Code

**Q:**  I want to create a Blazor UI application based on an existing XAF .NET Framework application. How do I proceed?

**A:**  You can re-use most of ORM data models and platform-agnostic controllers in Blazor UI with minimal or no changes. The basic CRUD and data view XAF APIs are platform-agnostic, for example,  [IObjectSpace](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.IObjectSpace),  [ViewController](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.ViewController),  [View](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.View), or  [Frame](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.Frame).

You can add existing platform-independent modules to an XAF Blazor UI project. Convert required modules to .NET Standard 2.0 or .NET 6:  [.NET 6+ Support and Migration from .NET Framework](https://docs.devexpress.com/eXpressAppFramework/401253/overview/net-5-support-and-migration). Once conversion is complete, refer to the following article for further instructions: ([Add a Module in Code](https://docs.devexpress.com/eXpressAppFramework/118047/application-shell-and-base-infrastructure/application-solution-components/ways-to-register-a-module#code)).

All platform-dependent code should be rewritten. Blazor applications have a different architecture and life cycle, the code that was common for ASP.NET Web Forms and Windows Forms may need to be changed for Blazor. Refer to the following article for more information:  [An introduction to Blazor for ASP.NET Web Forms developers](https://docs.microsoft.com/en-us/dotnet/architecture/blazor-for-web-forms-developers/introduction).

## Add a Custom XAF Module

**Q:**  How do I add a new custom XAF module into an existing Blazor solution?

**A:**  Use the  **Add DevExpress Item | New Project**  menu to add a new custom XAF module to an existing XAF .NET 6+ app.

## Integrate Custom UI Components

**Q:**  How do I use components that are not integrated in the Blazor UI by default?

**A:**  Review the list of DevExpress  [Blazor](https://demos.devexpress.com/blazor/)  and  [JavaScript (DevExtreme)](https://js.devexpress.com/Demos/)  UI components and the following XAF integration articles:

-   [Implement a List Editor Based on a Custom Component](https://docs.devexpress.com/eXpressAppFramework/403258/ui-construction/list-editors/how-to-use-a-custom-component-to-implement-list-editor-blazor)
    -   [Pivot Grid](https://supportcenter.devexpress.com/ticket/details/t994515/blazor-how-to-integrate-the-pivot-grid-into-an-xaf-app)
    -   [TreeList](https://supportcenter.devexpress.com/ticket/details/t1023129/xaf-blazor-how-to-implement-a-treelist-editor-to-display-hierarchical-data)
    -   [Scheduler](https://github.com/jjcolumb/ListEditorScheduler)
-   [Access Grid Control Settings](https://docs.devexpress.com/eXpressAppFramework/402154/ui-construction/list-editors/how-to-access-list-editor-control)
-   [Implement a Property Editor Based on a Custom Component](https://docs.devexpress.com/eXpressAppFramework/402189/ui-construction/view-items-and-property-editors/property-editors/implement-a-property-editor-based-on-custom-components-blazor)
    -   [Color Property Editor](https://supportcenter.devexpress.com/ticket/details/t957324/blazor-how-to-display-and-edit-color-properties-in-the-ui)
    -   [Simple Button](https://docs.devexpress.com/eXpressAppFramework/113653/ui-construction/view-items-and-property-editors/add-a-button-to-a-detail-view-using-custom-view-item)
    -   [Multiple File Upload, Tag Box, Lookup, Markup Content Property Editors](https://github.com/eXpandFramework/Reactive.XAF/tree/master/src/Modules/Blazor)
    -   [Progress Bar in Grid List Editor Cells](https://supportcenter.devexpress.com/ticket/details/t1003220/blazor-how-to-implement-a-progress-bar-in-grid-list-editor-cells)
-   [Access Detail View Property Editor Settings](https://docs.devexpress.com/eXpressAppFramework/402153/getting-started/in-depth-tutorial-blazor/customize-data-display-and-view-layout/access-editor-settings)  |  [Customize a Built-in Property Editor](https://docs.devexpress.com/eXpressAppFramework/402188/ui-construction/view-items-and-property-editors/property-editors/customize-a-built-in-property-editor-blazor)
-   [Add DevExtreme Widgets to an Application](https://docs.devexpress.com/Blazor/403578/common-concepts/add-devextreme-widgets-to-application)
-   [Integrate a custom DevExtreme component and bind it to a data source](https://supportcenter.devexpress.com/ticket/details/t943982/blazor-how-to-integrate-a-custom-devextreme-component-and-bind-it-to-a-data-source)
    
-   [Show a fully custom non-XAF web form (with custom controls, JavaScript, Razor components, etc.)](https://supportcenter.devexpress.com/ticket/details/t939883/blazor-how-to-show-a-fully-custom-non-xaf-web-page-with-custom-controls-javascript-razor)
    
-   [How to implement a QR / barcode scanner using a camera of a mobile device](https://supportcenter.devexpress.com/ticket/details/t867142/xaf-blazor-how-to-implement-a-qr-barcode-scanner-using-a-camera-of-a-mobile-device)
-   [Create a Custom Blazor Application Template](https://docs.devexpress.com/eXpressAppFramework/403452/ui-construction/templates/in-blazor/custom-blazor-application-template)
-   [Implement a custom Action type](https://supportcenter.devexpress.com/ticket/details/t1101292/xaf-blazor-implement-a-custom-action-type)

You can review how we implement List and Property Editors. This may help you integrate custom components. See the files in the following folder:  _%PROGRAMFILES%\DevExpress  23.1\Components\Sources\DevExpress.ExpressApp\DevExpress.ExpressApp.Blazor\Editors\_.

## Access ASP.NET Core DI Services via IServiceProvider

**Q:**  How do I access services from a built-in ASP.NET Core service container (IServiceProvider)?

**A:**  To access  [BlazorApplication.IServiceProvider](https://docs.devexpress.com/eXpressAppFramework/DevExpress.ExpressApp.AspNetCore.AspNetCoreApplication.ServiceProvider), use the following code:  `Application.ServiceProvider`. For more information, see the following topic:  [Dependency Injection (DI)](https://docs.devexpress.com/eXpressAppFramework/404364/application-shell-and-base-infrastructure/dependency-injection-in-xaf-applications).

You may find the following examples helpful:

-   Download files or navigate to a URL using custom XAF Actions:  [a code example](https://supportcenter.devexpress.com/ticket/details/t944452/blazor-how-to-provide-a-file-download-or-open-an-external-hyper-link-using-an-xaf-action)  that uses the standard ASP.NET Core  [NavigationManager](https://docs.microsoft.com/en-us/aspnet/core/blazor/fundamentals/routing#uri-and-navigation-state-helpers)  service.
-   Read a connection string or other values from appsettings.json in code using a ViewController:  [a code example](https://supportcenter.devexpress.com/ticket/details/t957990/blazor-how-to-read-connection-string-and-other-values-from-the-configuration-file)  that uses the standard ASP.NET Core  [IConfiguration](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/configuration)  service.
-   Access HttpContext to get cookies, user agent, client IP address, query string and other request information:  [a ticket](https://supportcenter.devexpress.com/ticket/details/t975297/blazor-obtain-request-information-from-httpcontext-query-string-parameter-for-auto-login)  with more information on the standard ASP.NET Core  [IHttpContextAccessor](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.http.ihttpcontextaccessor)  service.
-   Access JSRuntime to call JavaScript from .NET code:  [a code example](https://docs.devexpress.com/eXpressAppFramework/403531/analytics/dashboards/open-a-detail-view-when-the-grid-row-is-clicked-in-the-dashboard-blazor#create-a-server-side-controller)  that uses the standard ASP.NET Core  [IJSRuntime](https://docs.microsoft.com/en-us/aspnet/core/blazor/call-javascript-from-dotnet)  service.
-   [Access IHttpClientFactory to make HTTP requests](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests).

## Using GPS and Camera on Mobile Devices

**Q:**  Can I upload photos from a mobile device camera in XAF Blazor apps?

**A:**  Yes. Evolved web development standards and modern browsers made it possible to accomplish many hardware-related tasks (GPS, camera, etc.) in such applications. See also:  [How to implement a QR / barcode scanner using a camera of a mobile device](https://supportcenter.devexpress.com/ticket/details/t867142/xaf-blazor-how-to-implement-a-qr-barcode-scanner-using-a-camera-of-a-mobile-device).

![XAF Blazor Server Mobile Upload Files](https://docs.devexpress.com/eXpressAppFramework/images/XAF_Blazor_Server_Mobile_Upload_Files.png)

## Deployment

**Q:**  Can I deploy XAF Blazor apps to Cloud platforms (Azure, AWS, etc.), Linux (with Nginx or Apache), Windows (with IIS), Docker, and Kubernetes?

**A:**  Yes, absolutely. For more information, refer to the following articles:  [Host and deploy ASP.NET Core Blazor Server](https://docs.microsoft.com/en-us/aspnet/core/blazor/host-and-deploy/server)  |  [Deployment Recommendations for XAF Blazor UI Applications](https://docs.devexpress.com/eXpressAppFramework/403362/deployment/deployment-recommendations-blazor).

## High Load and Scaling

**Q:**  Is Blazor UI appropriate for applications with thousands of concurrent users?

**A:**  We cannot recommend XAF’s Blazor UI for high-load applications that should serve hundreds or thousands of concurrent web clients on a single web server. Refer to the following article for details:  [Deployment Recommendations for XAF Blazor UI Applications](https://docs.devexpress.com/eXpressAppFramework/403362/deployment/deployment-recommendations-blazor).

## Offline Mode Support

**Q:**  Does XAF Blazor UI support offline mode?

**A:**  No. The current Blazor Server platform requires a permanent connection to a server.

## Supported Identity Providers

**Q:**  Does XAF’s Blazor UI support OAuth2 (Azure AD, Microsoft 365, Google Firebase, etc.) or JWT authentication (Identity Server, Auth0, etc.)?

**A:**  Yes, XAF supports these identity providers with the help of built-in ASP.NET Core capabilities and XAF’s security system extensibility. You may find the following examples helpful:

-   [How to: Use Active Directory and OAuth2 Authentication Providers in Blazor Applications](https://docs.devexpress.com/eXpressAppFramework/402197/data-security-and-safety/security-system/authentication/oauth-and-custom-authentication/active-directory-and-oauth2-authentication-providers-in-blazor-applications)
-   [Identity Server usage example](https://github.com/biohazard999/IDSDemoXaf)  and  [video](https://www.youtube.com/watch?v=9Nlq2HCfMFU).

## Customize Pop-Up Dialogs

**Q:**  How do I resize popup dialogs? Can I increase the default window width if it contains a complex form?

**A:**  [How to: Adjust the Size and Style of Pop-up Dialogs (Blazor)](https://docs.devexpress.com/eXpressAppFramework/404014/ui-construction/templates/in-blazor/change-popup-window-dimensions).

## “Save & New” and “Save & Close” Buttons

**Q:**  How do I return the “Save & New” and “Save & Close” buttons in DetailView (as it was in WinForms and WebForms)?

**A:**  [Blazor - How to implement the “Save & New” and “Save & Close” buttons](https://supportcenter.devexpress.com/ticket/details/t951115/xaf-blazor-how-to-implement-the-save-new-and-save-close-buttons-in-detailview-as-it-was).

## Supported Browsers

**Q:**  What are the supported desktop and mobile web browsers?

**A:**  You can find the supported browser list in the following Microsoft article:  [https://docs.microsoft.com/en-us/aspnet/core/blazor/supported-platforms](https://docs.microsoft.com/en-us/aspnet/core/blazor/supported-platforms)  (Microsoft Internet Explorer 11 and older versions are not supported).

We test XAF Blazor UI in the following environments:

-   The latest desktop Google Chrome and Mozilla FireFox versions (automated tests and screenshot-based tests with EasyTest and Selenium).
-   The latest versions of Google Chrome on Android, Safari (including iOS), and Microsoft Edge (manual testing).

## VB.NET Support

**Q:**  Can I create a VB.NET Blazor UI application?

**A:**  You can attach your VB.NET modules converted to .NET Standard 2.0 to a C# Blazor application.

XAF does not ship a VB.NET project template for the Blazor UI. You cannot create a VB.NET Blazor application because Microsoft does not support this functionality:  [Support VB.NET in ASP.NET Core 3.0 and Blazor](https://developercommunity.visualstudio.com/idea/468570/support-vbnet-in-aspnet-core-30-and-blazor.html).

## Keep Connection Alive

The XAF Blazor UI is a regular ASP.NET Core Blazor Server application that uses  `SignalR`  to keep a connection to the server alive. Use the following solution to manage this behavior:  [Timeout and keepalive settings](https://learn.microsoft.com/en-us/aspnet/signalr/overview/guide-to-the-api/handling-connection-lifetime-events#timeoutkeepalive).
