---
uid: web-forms/overview/ajax-control-toolkit/animation/animating-in-response-to-user-interaction-cs
title: Animieren in Reaktion auf Benutzerinteraktionen (c#) | Microsoft Docs
author: wenz
description: Animation-Steuerelement in ASP.NET AJAX-Steuerelement-Toolkit ist nicht nur ein Steuerelement, aber eine gesamte Framework Animationen an ein Steuerelement hinzufügen. Die Animationen können Stern...
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/02/2008
ms.topic: article
ms.assetid: ea26549d-fbbf-4973-a108-b14cd1d6de26
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/animation/animating-in-response-to-user-interaction-cs
msc.type: authoredcontent
ms.openlocfilehash: 783563f4e33087e99a071cf829ca6bab246ba3b0
ms.sourcegitcommit: f8852267f463b62d7f975e56bea9aa3f68fbbdeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2018
---
<a name="animating-in-response-to-user-interaction-c"></a>Animieren in Reaktion auf Benutzerinteraktionen (c#)
====================
durch [Christian Wenz](https://github.com/wenz)

[Herunterladen von Code](http://download.microsoft.com/download/f/9/a/f9a26acd-8df4-4484-8a18-199e4598f411/Animation6.cs.zip) oder [PDF herunterladen](http://download.microsoft.com/download/6/7/1/6718d452-ff89-4d3f-a90e-c74ec2d636a3/animation6CS.pdf)

> Animation-Steuerelement in ASP.NET AJAX-Steuerelement-Toolkit ist nicht nur ein Steuerelement, aber eine gesamte Framework Animationen an ein Steuerelement hinzufügen. Die Animationen können automatisch starten, oder es können ausgelöst werden durch eine Benutzerinteraktion, z. B. indem Sie mit der Maus auf.


## <a name="overview"></a>Übersicht

Animation-Steuerelement in ASP.NET AJAX-Steuerelement-Toolkit ist nicht nur ein Steuerelement, aber eine gesamte Framework Animationen an ein Steuerelement hinzufügen. Die Animationen können automatisch starten, oder es können ausgelöst werden durch eine Benutzerinteraktion, z. B. indem Sie mit der Maus auf.

## <a name="steps"></a>Schritte

Erstens sind die `ScriptManager` auf der Seite; klicken Sie dann die ASP.NET AJAX-Bibliothek geladen ist, wodurch das Steuerelement-Toolkit verwenden:

[!code-aspx[Main](animating-in-response-to-user-interaction-cs/samples/sample1.aspx)]

Die Animation wird auf einen Bereich des Texts angewendet werden, die wie folgt aussieht:

[!code-aspx[Main](animating-in-response-to-user-interaction-cs/samples/sample2.aspx)]

Definieren Sie in der zugehörigen CSS-Klasse für den Bereich eine gute Hintergrundfarbe und auch festlegen Sie eine feste Breite für den Bereich:

[!code-css[Main](animating-in-response-to-user-interaction-cs/samples/sample3.css)]

Fügen Sie dann die `AnimationExtender` auf der Seite "Bereitstellen einer `ID`, die `TargetControlID` Attribut und der Auswahlparameter `runat="server"`:

[!code-aspx[Main](animating-in-response-to-user-interaction-cs/samples/sample4.aspx)]

Innerhalb der `<Animations>` Knoten, es gibt fünf Möglichkeiten zum Starten der Animation über die Interaktion des Benutzers (ist das fehlende Element `<OnLoad>` das ausgeführt wird, nachdem die ganze Seite vollständig geladen wurde):

- `<OnClick>` (Mausklick auf das Steuerelement)
- `<OnHoverOut>` (verlassen hat das Steuerelement der Maus)
- `<OnHoverOver>` (Maus bewegt wird, über ein Steuerelement, das Beenden der `<OnHoverOut>` Animation)
- `<OnMouseOut>` (ein Steuerelement verlässt Maus)
- `<OnMouseOver>` (Maus bewegt wird, über ein Steuerelement, Beenden nicht die `<OnMouseOut>` Animation)

In diesem Szenario `<OnClick>` verwendet wird. Klickt der Benutzer im Bereich wird skaliert, und gleichzeitig ausgeblendet.

[!code-aspx[Main](animating-in-response-to-user-interaction-cs/samples/sample5.aspx)]


[![Startet die Animation, klicken mit der Maus](animating-in-response-to-user-interaction-cs/_static/image2.png)](animating-in-response-to-user-interaction-cs/_static/image1.png)

Startet die Animation, klicken mit der Maus ([klicken Sie hier, um das Bild in voller Größe angezeigt](animating-in-response-to-user-interaction-cs/_static/image3.png))

> [!div class="step-by-step"]
> [Zurück](picking-one-animation-out-of-a-list-cs.md)
> [Weiter](disabling-actions-during-animation-cs.md)
