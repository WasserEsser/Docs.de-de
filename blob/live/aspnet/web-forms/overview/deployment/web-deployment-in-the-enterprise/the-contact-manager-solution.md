---
uid: web-forms/overview/deployment/web-deployment-in-the-enterprise/the-contact-manager-solution
title: "Die Kontakt-Manager-Lösung | Microsoft Docs"
author: jrjlee
description: "Diese Reihe von Lernprogrammen verwendet eine Beispielprojektmappe & #x 2014; die Kontakt-Manager-Lösung & #x 2014; um eine Enterprise-Skalierung-Anwendung mit einer realistischen Leve darzustellen..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 05/04/2012
ms.topic: article
ms.assetid: 4d8c8d19-055b-4b70-9ee1-f748f0db3a01
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/deployment/web-deployment-in-the-enterprise/the-contact-manager-solution
msc.type: authoredcontent
ms.openlocfilehash: b7f691a1ee855788f6a57616aea35d960e4c85c7
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2017
---
<a name="the-contact-manager-solution"></a><span data-ttu-id="8b417-103">Die Kontakt-Manager-Lösung</span><span class="sxs-lookup"><span data-stu-id="8b417-103">The Contact Manager Solution</span></span>
====================
<span data-ttu-id="8b417-104">durch [Jason Lee](https://github.com/jrjlee)</span><span class="sxs-lookup"><span data-stu-id="8b417-104">by [Jason Lee](https://github.com/jrjlee)</span></span>

[<span data-ttu-id="8b417-105">PDF herunterladen</span><span class="sxs-lookup"><span data-stu-id="8b417-105">Download PDF</span></span>](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/63/56/8130.DeployingWebAppsInEnterpriseScenarios.pdf)

> <span data-ttu-id="8b417-106">Dies [Reihe von Lernprogrammen](web-deployment-in-the-enterprise.md) verwendet eine Beispielprojektmappe & #x 2014; die Kontakt-Manager-Lösung & #x 2014; um eine Enterprise-Skalierung-Anwendung mit einer realistischen Maß an Komplexität darzustellen.</span><span class="sxs-lookup"><span data-stu-id="8b417-106">This [series of tutorials](web-deployment-in-the-enterprise.md) uses a sample solution&#x2014;the Contact Manager solution&#x2014;to represent an enterprise-scale application with a realistic level of complexity.</span></span> <span data-ttu-id="8b417-107">Dieses Thema führt die Kontakt-Manager-Lösung, beschreibt die wichtigsten Komponenten der Lösung und identifiziert die Herausforderungen bei der Bereitstellung dieser Art von Anwendung an verschiedenen Ziel Plattformen in einer unternehmensumgebung.</span><span class="sxs-lookup"><span data-stu-id="8b417-107">This topic introduces the Contact Manager solution, describes the key components of the solution, and identifies the challenges in deploying this kind of application to various destination platforms in an enterprise environment.</span></span>
> 
> <span data-ttu-id="8b417-108">Arbeit durch die Themen in diesen Lernprogrammen können Sie die Projektmappe Contact Manager als eine referenzimplementierung verwenden, die zeigt, wie Sie bestimmte Probleme in Bereitstellungsszenarios erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="8b417-108">As you work through the topics in these tutorials, you can use the Contact Manager solution as a reference implementation that demonstrates how you can meet specific challenges in enterprise deployment scenarios.</span></span> <span data-ttu-id="8b417-109">Im nächsten Thema [Einstellung von der Kontakt-Manager-Lösung](setting-up-the-contact-manager-solution.md), herunterladen und Ausführen der Projektmappe auf der Arbeitsstation Developer beschreibt.</span><span class="sxs-lookup"><span data-stu-id="8b417-109">The next topic, [Setting Up the Contact Manager Solution](setting-up-the-contact-manager-solution.md), describes how to download and run the solution on your developer workstation.</span></span>


## <a name="solution-overview"></a><span data-ttu-id="8b417-110">Lösungsübersicht</span><span class="sxs-lookup"><span data-stu-id="8b417-110">Solution Overview</span></span>

<span data-ttu-id="8b417-111">Die Kontakt-Manager-Lösung besteht aus vier einzelne Projekte:</span><span class="sxs-lookup"><span data-stu-id="8b417-111">The Contact Manager solution consists of four individual projects:</span></span>

![](the-contact-manager-solution/_static/image1.png)

- <span data-ttu-id="8b417-112">**ContactManager.Mvc**.</span><span class="sxs-lookup"><span data-stu-id="8b417-112">**ContactManager.Mvc**.</span></span> <span data-ttu-id="8b417-113">Dies ist eine ASP.NET MVC 3-Webanwendungsprojekt, die den Einstiegspunkt für die Projektmappe darstellt.</span><span class="sxs-lookup"><span data-stu-id="8b417-113">This is an ASP.NET MVC 3 web application project that represents the entry point for the solution.</span></span> <span data-ttu-id="8b417-114">Er bietet einige grundlegende Web Application-Funktionen, wie Benutzern die Möglichkeit zum Erstellen und Anzeigen von Details des Kontakts.</span><span class="sxs-lookup"><span data-stu-id="8b417-114">It offers some basic web application functionality, like providing users with the ability to create and view contact details.</span></span> <span data-ttu-id="8b417-115">Die Anwendung verwendet einen Windows Communication Foundation (WCF)-Dienst zum Verwalten von Kontakten und eine Datenbank für ASP.NET-Anwendungsdienste zum Verwalten der Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="8b417-115">The application relies on a Windows Communication Foundation (WCF) service to manage contacts and an ASP.NET application services database to manage authentication and authorization.</span></span>
- <span data-ttu-id="8b417-116">**ContactManager.Database**.</span><span class="sxs-lookup"><span data-stu-id="8b417-116">**ContactManager.Database**.</span></span> <span data-ttu-id="8b417-117">Dies ist ein Visual Studio-Datenbankprojekt.</span><span class="sxs-lookup"><span data-stu-id="8b417-117">This is a Visual Studio database project.</span></span> <span data-ttu-id="8b417-118">Das Projekt definiert das Schema für eine Datenbank, speichert Informationen wenden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="8b417-118">The project defines the schema for a database that stores contact details.</span></span>
- <span data-ttu-id="8b417-119">**ContactManager.Service**.</span><span class="sxs-lookup"><span data-stu-id="8b417-119">**ContactManager.Service**.</span></span> <span data-ttu-id="8b417-120">Dies ist ein WCF-Webdienstprojekt.</span><span class="sxs-lookup"><span data-stu-id="8b417-120">This is a WCF web service project.</span></span> <span data-ttu-id="8b417-121">Die WCF-Dienst verfügbar gemachten ein Endpunkt, der Aufrufern ermöglicht, führen zu erstellen, abrufen, aktualisieren und Löschvorgänge (CRUD) auf die **ContactManager** Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8b417-121">The WCF service exposes an endpoint that allows callers to perform create, retrieve, update, and delete (CRUD) operations on the **ContactManager** database.</span></span> <span data-ttu-id="8b417-122">Der Dienst basiert auf der **ContactManager** Datenbank und die **ContactManager.Common.dll** Assembly.</span><span class="sxs-lookup"><span data-stu-id="8b417-122">The service relies on the **ContactManager** database and the **ContactManager.Common.dll** assembly.</span></span>
- <span data-ttu-id="8b417-123">**ContactManager.Common**.</span><span class="sxs-lookup"><span data-stu-id="8b417-123">**ContactManager.Common**.</span></span> <span data-ttu-id="8b417-124">Dies ist ein Klassenbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="8b417-124">This is a class library project.</span></span> <span data-ttu-id="8b417-125">Der WCF-Dienst basiert auf in dieser Assembly definierten Typen.</span><span class="sxs-lookup"><span data-stu-id="8b417-125">The WCF service relies on types defined in this assembly.</span></span>

<span data-ttu-id="8b417-126">Die Lösung umfasst auch einen Projektmappenordner, der mit dem Namen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8b417-126">The solution also includes a solution folder named Publish.</span></span> <span data-ttu-id="8b417-127">Dieses enthält verschiedene benutzerdefinierte Projektdateien und Befehlsdateien, die veranschaulichen, wie Sie steuern und die Build- und Bereitstellungsprozess Prozess bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="8b417-127">This contains various custom project files and command files that demonstrate how you can control and manipulate the build and deployment process.</span></span> <span data-ttu-id="8b417-128">Diese werden weiter unten in diesem Lernprogramm ausführlicher behandelt.</span><span class="sxs-lookup"><span data-stu-id="8b417-128">These are covered in more detail later in this tutorial.</span></span>

<span data-ttu-id="8b417-129">Auf konzeptioneller Ebene passen die Komponenten der Projektmappe zusammen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8b417-129">At a conceptual level, the components of the solution fit together like this:</span></span>

![](the-contact-manager-solution/_static/image2.png)

> [!NOTE]
> <span data-ttu-id="8b417-130">Während Sie den ASP.NET-Mitgliedschaftsanbieter in ASP.NET MVC 3-Webanwendung verwendet wird, werden alle Seiten innerhalb der Webanwendung anonymen Zugriff zulassen.</span><span class="sxs-lookup"><span data-stu-id="8b417-130">While the ASP.NET MVC 3 web application uses the ASP.NET membership provider, all the pages within the web application allow anonymous access.</span></span> <span data-ttu-id="8b417-131">Dies ist jedoch deutlich keine realistische Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8b417-131">This is clearly not a realistic configuration.</span></span> <span data-ttu-id="8b417-132">Allerdings ist die Lösung einrichten auf diese Weise bereitstellen und testen die Projektmappe ohne Konfiguration der Benutzerkonten und Rollen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="8b417-132">However, the solution is set up in this way to make it easier for you to deploy and test the solution without configuring user accounts and roles.</span></span>


## <a name="deployment-challenges"></a><span data-ttu-id="8b417-133">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8b417-133">Deployment Challenges</span></span>

<span data-ttu-id="8b417-134">Die Kontakt-Manager-Lösung veranschaulicht verschiedene Herausforderung, die zu einer Vielzahl von Bereitstellungsszenarios gemeinsam verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="8b417-134">The Contact Manager solution illustrates several deployment challenges that are common to lots of enterprise deployment scenarios:</span></span>

- <span data-ttu-id="8b417-135">Die Lösung besteht aus mehreren abhängige Projekte.</span><span class="sxs-lookup"><span data-stu-id="8b417-135">The solution consists of multiple dependent projects.</span></span> <span data-ttu-id="8b417-136">Sie müssen diese Projekte gleichzeitig bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8b417-136">You need to deploy these projects simultaneously.</span></span>
- <span data-ttu-id="8b417-137">Verbindungszeichenfolgen und Dienstendpunkte für jede Umgebung aktualisiert werden müssen, und in vielen Fällen diese Informationen werden für den Entwickler verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8b417-137">Connection strings and service endpoints need to be updated for each environment, and in a lot of cases this information will not be available to the developer.</span></span>
- <span data-ttu-id="8b417-138">Bei der Bereitstellung der **ContactManager** Datenbank für Staging und Produktion Umgebungen müssen Sie vorhandene Daten bei nachfolgenden Bereitstellungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8b417-138">When you deploy the **ContactManager** database to staging and production environments, you need to preserve existing data on subsequent deployments.</span></span>
- <span data-ttu-id="8b417-139">Wenn Sie die Datenbank für ASP.NET-Anwendungsdienste bereitstellen, müssen Sie bereitstellen einiger Konfigurationsdaten jedoch weglassen von Benutzerdaten Konto.</span><span class="sxs-lookup"><span data-stu-id="8b417-139">When you deploy the ASP.NET application services database, you need to deploy some configuration data but omit any user account data.</span></span>
- <span data-ttu-id="8b417-140">Die Projekte enthalten einige Dateien und Ordner, die nicht bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8b417-140">The projects include some files and folders that should not be deployed.</span></span> <span data-ttu-id="8b417-141">Sie müssen den Bereitstellungsprozess diese Dateien und Ordner ausschließen.</span><span class="sxs-lookup"><span data-stu-id="8b417-141">You need to exclude these files and folders from the deployment process.</span></span>
- <span data-ttu-id="8b417-142">Die Lösung muss automatisierte Bereitstellung aus einem Build-Server mit Team Foundation Server (TFS) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8b417-142">The solution needs to support automated deployment from a Team Foundation Server (TFS) build server.</span></span>

## <a name="conclusion"></a><span data-ttu-id="8b417-143">Schlussfolgerung</span><span class="sxs-lookup"><span data-stu-id="8b417-143">Conclusion</span></span>

<span data-ttu-id="8b417-144">In diesem Thema eine allgemeine Übersicht über die Projektmappe Contact Manager bereitgestellt und identifiziert einige der inhärenten Bereitstellung Herausforderungen, die zu einer Vielzahl von Bereitstellungsszenarios gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b417-144">This topic provided a high-level overview of the Contact Manager solution and identified some of the inherent deployment challenges that are common to lots of enterprise deployment scenarios.</span></span> <span data-ttu-id="8b417-145">Die übrigen Themen in diesem Lernprogramm werden einige der Methoden, die Sie verwenden können, um diese Auflagen erfüllt werden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b417-145">The remaining topics in this tutorial describe some of the techniques you can use to meet these challenges.</span></span>

<span data-ttu-id="8b417-146">Im nächsten Thema [Einstellung von der Kontakt-Manager-Lösung](setting-up-the-contact-manager-solution.md), herunterladen und Ausführen der Projektmappe auf der Arbeitsstation Developer beschreibt.</span><span class="sxs-lookup"><span data-stu-id="8b417-146">The next topic, [Setting Up the Contact Manager Solution](setting-up-the-contact-manager-solution.md), describes how to download and run the solution on your developer workstation.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="8b417-147">[Zurück](web-deployment-in-the-enterprise.md)
[Weiter](setting-up-the-contact-manager-solution.md)</span><span class="sxs-lookup"><span data-stu-id="8b417-147">[Previous](web-deployment-in-the-enterprise.md)
[Next](setting-up-the-contact-manager-solution.md)</span></span>