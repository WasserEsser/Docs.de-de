---
title: Hosten von ASP.NET Core in Azure App Service
author: guardrex
description: Erfahren Sie, wie Sie ASP.NET Core-Apps in Azure App Service hosten. Entsprechende Informationen werden in diesen nützlichen Ressourcen bereitgestellt.
manager: wpickett
ms.author: riande
ms.custom: mvc
ms.date: 01/29/2018
ms.prod: asp.net-core
ms.technology: aspnet
ms.topic: article
uid: host-and-deploy/azure-apps/index
ms.openlocfilehash: 9e438cef9db61e725b5385da53e8aa2b407218c3
ms.sourcegitcommit: 477d38e33530a305405eaf19faa29c6d805273aa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="host-aspnet-core-on-azure-app-service"></a>Hosten von ASP.NET Core in Azure App Service

[Azure App Service](https://azure.microsoft.com/services/app-service/) ist ein [Microsoft Cloud Computing-Plattformdienst](https://azure.microsoft.com/) zum Hosten von Web-Apps. Dazu gehört auch ASP.NET Core.

## <a name="useful-resources"></a>Nützliche Ressourcen

In der [Web-Apps-Dokumentation](/azure/app-service/) finden Sie die Azure-Apps-Dokumentation, Tutorials, Beispiele und Leitfäden sowie andere Ressourcen. Dies sind zwei erwähnenswerte Tutorials, die auf das Hosten von ASP.NET Core-Apps eingehen:

[Schnellstart: Erstellen von ASP.NET Core-Web-Apps in Azure](/azure/app-service/app-service-web-get-started-dotnet)  
Verwenden Sie Visual Studio, um ASP.NET Core-Web-Apps zu erstellen und in Azure App Service unter Windows bereitzustellen.

[Quickstart: Create a .NET Core web app in App Service on Linux (Schnellstart: Erstellen von .NET Core-Web-Apps in App Service unter Linux)](/azure/app-service/containers/quickstart-dotnetcore)  
Verwenden Sie die Befehlszeile, um ASP.NET Core-Web-Apps zu erstellen und in Azure App Service unter Linux bereitzustellen.

Die folgenden Artikel sind in der ASP.NET Core-Dokumentation verfügbar:

[Veröffentlichen in Azure mit Visual Studio](xref:tutorials/publish-to-azure-webapp-using-vs)  
Erfahren Sie, wie eine ASP.NET Core-App in Azure App Service mit Visual Studio veröffentlicht wird.

[Veröffentlichen in Azure mit CLI-Tools](xref:tutorials/publish-to-azure-webapp-using-cli)  
Erfahren Sie, wie Sie eine ASP.NET Core-App in Azure App Service mithilfe des Git-Befehlszeilenclients veröffentlichen.

[Continuous Deployment in Azure mit Visual Studio und Git](xref:host-and-deploy/azure-apps/azure-continuous-deployment)  
Erfahren Sie, wie Sie mit Visual Studio eine ASP.NET Core-Web-App erstellen und sie unter Verwendung von Git für Continuous Deployment in Azure App Service bereitstellen.

[Continuous Deployment in Azure mit VSTS](https://www.visualstudio.com/docs/build/aspnet/core/quick-to-azure)  
Richten Sie ein CI-Build für eine ASP.NET Core-App ein, und erstellen Sie dann ein Continuous Deployment-Release für Azure App Service.

[Azure Web App-Sandbox](https://github.com/projectkudu/kudu/wiki/Azure-Web-App-sandbox)  
Entdecken Sie die Einschränkungen der Azure App Service-Laufzeitausführung, die durch die Azure Apps-Plattform erzwungen werden.

## <a name="application-configuration"></a>Anwendungskonfiguration

In ASP.NET Core 2.0 und höher bieten drei Pakete im [Metapaket „Microsoft.AspNetCore.All“](xref:fundamentals/metapackage) automatische Protokollierungsfeatures für in Azure App Service bereitgestellte Apps:

* [Microsoft.AspNetCore.AzureAppServices.HostingStartup](https://www.nuget.org/packages/Microsoft.AspNetCore.AzureAppServices.HostingStartup/) verwendet [IHostingStartup](xref:fundamentals/configuration/platform-specific-configuration), um die ASP.NET Core-Lightup-Integration mit Azure App Service bereitzustellen. Die hinzugefügten Protokollierungsfeatures werden vom `Microsoft.AspNetCore.AzureAppServicesIntegration`-Paket bereitgestellt.
* [Microsoft.AspNetCore.AzureAppServicesIntegration](https://www.nuget.org/packages/Microsoft.AspNetCore.AzureAppServicesIntegration/) führt [AddAzureWebAppDiagnostics](/dotnet/api/microsoft.extensions.logging.azureappservicesloggerfactoryextensions.addazurewebappdiagnostics) aus, um Anbieter für die Azure App Service-Diagnoseprotokollierung zum Paket `Microsoft.Extensions.Logging.AzureAppServices` hinzuzufügen.
* [Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices/) stellt Protokollierungsimplementierungen bereit, um die Azure App Service-Features für Diagnoseprotokolle und Protokollstreaming zu unterstützen.

## <a name="proxy-server-and-load-balancer-scenarios"></a>Proxyserver und Lastenausgleichsszenarien

Die Middleware für die Integration von IIS, die ForwardedHeadersMiddleware konfiguriert, und das ASP.NET Core-Modul sind so konfiguriert, dass sie das Schema (HTTP/HTTPS) und die Remote-IP-Adresse an die Stelle weiterleiten, von der die Anforderung stammte. Möglicherweise ist zusätzliche Konfiguration für Apps erforderlich, die hinter weiteren Proxyservern und Lastenausgleichsmodulen (Load Balancer) gehostet werden. Weitere Informationen hierzu feinden Sie unter [Konfigurieren von ASP.NET Core zur Verwendung mit Proxyservern und Lastenausgleich](xref:host-and-deploy/proxy-load-balancer).

## <a name="monitoring-and-logging"></a>Überwachung und Protokollierung

In den folgenden Artikeln finden Sie Informationen zum Überwachen, Protokollieren und zur Problembehandlung:

[Vorgehensweise: Überwachen von Apps in Azure App Service](/azure/app-service/web-sites-monitor)  
Erfahren Sie, wie Sie Kontingente und Metrik für Apps und App Service-Pläne prüfen.

[Aktivieren der Diagnoseprotokollierung für Apps in Azure App Service](/azure/app-service/web-sites-enable-diagnostic-log)  
Erfahren Sie, wie Sie die Diagnosesprotokollierung für HTTP-Statuscodes, fehlgeschlagene Anforderungen und Webserveraktivitäten aktivieren und auf die Protokolle zugreifen.

[Einführung in die Fehlerbehandlung in ASP.NET Core](xref:fundamentals/error-handling)  
Lernen Sie gängige Methoden zur Fehlerbehandlung in ASP.NET Core-Apps kennen.

[Problembehandlung bei ASP.NET Core in Azure App Service](xref:host-and-deploy/azure-apps/troubleshoot)  
Erfahren Sie, wie Sie Probleme mit Azure App Service-Bereitstellungen mit ASP.NET Core-Apps diagnostizieren können.

[Referenz zu häufigen Fehlern bei Azure App Service und IIS mit ASP.NET Core](xref:host-and-deploy/azure-iis-errors-reference)  
Sehen Sie sich häufig auftretende Fehler und entsprechende Hinweise zur Fehlerbehebung bei der Bereitstellungskonfiguration für von Azure App Service/IIS gehosteten Apps an.

## <a name="data-protection-key-ring-and-deployment-slots"></a>Data Protection-Schlüsselbund und -Bereitstellungsslots

[Data Protection-Schlüssel](xref:security/data-protection/implementation/key-management#data-protection-implementation-key-management) werden im Ordner *%HOME%\ASP.NET\DataProtection-Keys* gespeichert. Dieser Ordner wird von einem Netzwerkspeicher unterstützt und mit allen Computern, auf denen die App gehostet wird, synchronisiert. Ruhende Schlüssel werden nicht geschützt. Dieser Ordner stellt den Schlüsselbund für alle Instanzen einer App in einem einzelnen Bereitstellungsslot bereit. Separate Bereitstellungsslots, wie Staging und Produktion, verwenden keinen gemeinsamen Schlüsselbund.

Wenn Sie zwischen Bereitstellungsslots wechseln, können Systeme, die Data Protection verwenden, gespeicherte Daten nicht mit dem Schlüsselbund des vorherigen Slots entschlüsseln. ASP.NET-Cookiemiddleware verwendet Data Protection zum Schutz ihrer Cookies. Dies führt dazu, dass Benutzer in einer App abgemeldet werden, die Standard-ASP.NET-Cookiemiddleware verwendet. Verwende Sie einen externen Schlüsselbundanbieter für eine slotunabhängige Schlüsselbundlösung wie z.B.:

* Azure Blob Storage
* Azure Key Vault
* SQL-Speicher
* Redis Cache

Weitere Informationen finden Sie unter [Schlüsselspeicheranbieter](xref:security/data-protection/implementation/key-storage-providers).

## <a name="deploy-aspnet-core-preview-release-to-azure-app-service"></a>Bereitstellen der ASP.NET Core Vorschauversion für Azure App Service

ASP.NET Core-Vorschau-Apps können mit den folgenden Vorgehensweisen für Azure App Service bereitgestellt werden:

* [Installieren der Websiteerweiterung (Vorschau)](#install-the-preview-site-extension)
* [Bereitstellung der App als eigenständige App](#deploy-the-app-self-contained)
* [Verwenden von Docker mit Web-Apps für Container](#use-docker-with-web-apps-for-containers)

Sollte ein Problem mit dem Verwenden der Vorschau der Websiteerweiterung auftreten, erstellen Sie ein Problem auf [GitHub](https://github.com/aspnet/azureintegration/issues/new).

### <a name="install-the-preview-site-extension"></a>Installieren der Websiteerweiterung (Vorschau)

* Navigieren Sie im Azure-Portal zum Blatt „App Service“.
* Geben Sie „er“ in das Suchfeld ein.
* Wählen Sie **Erweiterungen** aus.
* Wählen Sie „Hinzufügen“ aus.

![Blatt für Azure-Apps mit vorangehenden Schritten](index/_static/x1.png)

* Wählen Sie zwischen der **ASP.NET Core 2.1-Runtime (x86)** und der **ASP.NET Core 2.1-Runtime (x64)**.
* Klicken Sie auf **OK**. Klicken Sie erneut auf **OK**.

Nach Abschluss der Hinzufügevorgänge wird die neueste .NET Core 2.1-Vorschauversion installiert. Überprüfen Sie, ob die Installation erfolgreich war, indem Sie `dotnet --info` in der Konsole ausführen. Führen Sie Folgendes auf dem Blatt **App Service** durch:

* Geben Sie „kon“ in das Suchfeld ein.
* Wählen Sie **Konsole** aus.
* Geben Sie `dotnet --info` in der Konsole ein.

![Blatt für Azure-Apps mit vorangehenden Schritten](index/_static/cons.png)

Die vorherige Abbildung war aktuell zu der Zeit, als dieser Text geschrieben wurde. Sie sehen möglicherweise eine andere Version.

`dotnet --info` zeigt den Pfad zu der Websiteerweiterung an, wo die Vorschauversion installiert wurde. Es ist zu sehen, dass die App aus der Websiteerweiterung statt aus dem Standardspeicherort *ProgramFiles* ausgeführt wird. Wenn *ProgramFiles* angezeigt wird, starten Sie die Website neu, und führen Sie `dotnet --info` aus.

**Verwenden der Vorschau-Websiteerweiterung mit einer ARM-Vorlage**

Wenn Sie eine ARM-Vorlage zum Erstellen und Bereitstellen von Anwendungen verwenden, können Sie den Ressourcentyp `siteextensions` verwenden, um die Websiteerweiterung zu einer Web-App hinzuzufügen. Zum Beispiel:

[!code-json[Main](index/sample/arm.json?highlight=2)]

### <a name="deploy-the-app-self-contained"></a>Bereitstellen der App als eigenständige App

Eine [eigenständige App](/dotnet/core/deploying/#self-contained-deployments-scd), die die Vorschau-Runtime während der Bereitstellung enthält, kann bereitgestellt werden. Wenn Sie eine eigenständige App bereitstellen, gilt Folgendes:

* Die Website muss nicht vorbereitet werden.
* Die App muss anders als beim Veröffentlichen für eine frameworkabhängige Bereitstellung mit der freigegebenen Runtime und dem Host auf dem Server bereitgestellt werden.

Eigenständige Apps sind eine Option für alle ASP.NET Core-Anwendungen.

### <a name="use-docker-with-web-apps-for-containers"></a>Verwenden von Docker mit Web-Apps für Container

Der [Docker-Hub](https://hub.docker.com/r/microsoft/aspnetcore/) enthält die neuesten Images für 2.1-Vorschau-Docker. Die Images können als Basisimage verwendet werden. Verwenden Sie das Image, und führen Sie wie gewohnt eine Bereitstellung für Web-Apps für Container durch.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Web-Apps-Übersicht (fünfminütiges Übersichtsvideo)](/azure/app-service/app-service-web-overview)
* [Azure App Service: The Best Place to Host your .NET Apps (Azure App Service: Ideal zum Hosten von .NET-Apps; 55-minütiges Video)](https://channel9.msdn.com/events/dotnetConf/2017/T222)
* [Azure Friday: Azure App Service Diagnostic and Troubleshooting Experience (Azure Friday: Azure App Service-Diagnose und -Fehlerbehebung; zwölfminütiges Video)](https://channel9.msdn.com/Shows/Azure-Friday/Azure-App-Service-Diagnostic-and-Troubleshooting-Experience)
* [Übersicht: Azure App Service-Diagnose](/azure/app-service/app-service-diagnostics)

Azure App Service auf Windows Server verwendet [Internetinformationsdienste (IIS)](https://www.iis.net/). Die folgenden Artikel gehen auf die zugrunde liegende IIS-Technologie ein:

* [Hosten von ASP.NET Core unter Windows mit IIS](xref:host-and-deploy/iis/index)
* [Einführung in das ASP.NET Core-Modul](xref:fundamentals/servers/aspnet-core-module)
* [Konfigurationsreferenz für das ASP.NET Core-Modul](xref:host-and-deploy/aspnet-core-module)
* [IIS-Module mit ASP.NET Core](xref:host-and-deploy/iis/modules)
* [Microsoft TechNet-Bibliothek: Windows Server](/windows-server/windows-server-versions)
