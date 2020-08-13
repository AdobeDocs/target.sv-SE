---
keywords: audience;audience rules;create audience;creating audience;targeting audience;reporting audience;report audience;segment;custom profile parameters;audience definition;audiences list
description: Publiken i Adobe Target avgör vilka som får se innehåll och upplevelser i en målinriktad aktivitet.
title: Skapa målgrupper i Adobe Target
feature: audiences
topic: Advanced,Standard,Classic
uuid: 994eed40-11ca-460e-827c-75a4db8a942d
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---


# Skapa målgrupper{#create-audiences}

Publiken i Adobe Target avgör vilka som får se innehåll och upplevelser i en målinriktad aktivitet.

Målgrupperna används överallt där målgruppsanpassning finns tillgänglig. När du riktar in dig på en aktivitet kan du antingen välja en återanvändbar målgrupp i [!UICONTROL Audiences] listan, [skapa en aktivitetsspecifik målgrupp](/help/c-target/creating-activity-only-audience.md) och rikta in den på den eller [kombinera flera målgrupper](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) för att skapa en ad hoc-målgrupp.

Ni kan också använda målgruppsdata som samlats in av [!DNL Analytics] för målgruppsanpassning i realtid och personalisering i [!DNL Adobe Target] och andra [!DNL Experience Cloud] lösningar. Se [Målgrupper](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) i *användarhandboken* för bastjänsterna.

[!DNL Target] definierar två typer av målgrupper:

* **Målgrupper:** Används för att leverera olika innehåll till olika typer av besökare.
* **Rapporterande målgrupper:** Används för att avgöra hur olika typer av besökare svarar på samma innehåll så att du kan analysera testresultaten.

   I [!DNL Target]kan du bara konfigurera rapportmålgrupper om du använder [!DNL Target] som rapportkälla. Om du använder [Adobe Analytics som rapportkälla](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) måste du konfigurera dina rapportmålgrupper i [!DNL Analytics].

## Använda publiklistan

Du öppnar [!UICONTROL Audiences] listan genom att klicka **[!UICONTROL Audiences]** på den övre menyraden:

![Publiklista](assets/audiences_list.png)

Listan innehåller alla målgrupper som du kan använda i dina aktiviteter. [!UICONTROL Audiences] Använd [!UICONTROL Audiences] listan för att skapa, redigera, ta bort, kopiera eller kombinera målgrupper. Listan visar också källan till målgruppen ([!DNL Target], [!DNL Target Classic], [!DNL Adobe Audience Manager (AAM),] [!DNL Experience Cloud]och så vidare). Det går inte att byta namn på fördefinierade målgrupper, t.ex.&quot;Nya besökare&quot; och&quot;Återkommande besökare&quot;.

När du arbetar med målgrupper som ursprungligen skapades i AAM får du ett varningsmeddelande från Target om du refererar till en målgrupp i Target-aktiviteter som senare har tagits bort i AAM.

* Om en målgrupp togs bort i AAM visas en varningsikon både i [!UICONTROL Audience] listan och i målgruppsväljaren. Ett verktygstips i användargränssnittet anger också att målgruppen togs bort i AAM.
* Om du försöker kombinera flera målgrupper med en borttagen målgrupp, eller om du försöker spara en aktivitet som refererar till en borttagen målgrupp, visas ett varningsmeddelande.

Du kan också ange anpassade profilparametrar och `user.` parametrar som mål. När du lägger till en målgrupp klickar du på **[!UICONTROL Add Rule]** > **[!UICONTROL Visitor Profile]** och väljer sedan den parameter som du vill använda som mål för aktiviteten. Om den önskade parametern inte visas har parametern inte utlösts av en mbox. Andra anpassade mbox-parametrar finns i den [!UICONTROL Custom Parameters] nedrullningsbara listan.

Använd sökrutan för att söka i din [!UICONTROL Audiences] lista. Du kan söka efter valfri del av ett målgruppsnamn eller omge en viss sträng med citattecken.

Du kan sortera listan efter målgruppsnamn eller efter det datum då den senast ändrades. [!UICONTROL Audiences] Om du vill sortera efter namn eller datum klickar du på kolumnrubriken och väljer sedan att visa målgrupper i stigande eller fallande ordning.

## Visa målgruppsdefinitioner {#section_11B9C4A777E14D36BA1E925021945780}

Du kan visa information om målgruppsdefinitioner på ett popup-kort på olika platser i målgränssnittet utan att öppna målgruppen. Den här funktionen gäller målgrupper som skapats i Target Standard/Premium och målgrupper som importerats från Target Classic eller skapats via API.

Du kommer till exempel åt följande grafikkort genom att hovra över en målgrupp i publiklistan och sedan klicka på ikonen Visa:

![Verksamheter > Målgruppsdefinition](assets/audience_definition_list.png)

Du kommer åt följande målgruppsdefinitionskort genom att klicka på ikonen Visa på en aktivitets översiktssida:

![Verksamheter > Målgruppsdefinition](assets/audience_definition_list.png)

Klicka på [!UICONTROL Audience Usage] fliken för att se andra aktiviteter som refererar till den målgruppen, om tillämpligt. På så sätt kan du undvika oavsiktlig påverkan på andra aktiviteter när du redigerar målgrupper. Informationen omfattar live-aktiviteter, inaktiva aktiviteter, arkiverade aktiviteter och synkroniseringsaktiviteter. Den här funktionen är tillgänglig för alla målgrupper (biblioteksmålgrupper och [målgrupper](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)som endast är aktiva).

Om en målgrupp kombineras med en annan målgrupp och den kombinerade målgruppen används för att skapa en aktivitet, kommer användarinformationen för båda målgrupperna att visa den nyskapade aktiviteten.

![](assets/audience_definition_list_usage.png)

Följande grafikkort är avsett för en publik som importerats från Adobe Experience Cloud. I det här fallet importerades målgruppen från Adobe Audience Manager (AAM).

![Fliken Användning på Audience Definition-kort](assets/audience_definition_mc.png)

Följande information finns för de importerade publiktyperna:

| Målgruppstyp | Detaljer |
|--- |--- |
| Mobila målgrupper | Marknadsföringsnamn, leverantör och modell.<br>Operatorn `matches | does not match` visas i stället för `equals | does not equal`<br>![Importerad mobil publik](/help/c-target/c-audiences/assets/imported_mobile_audience.png). |
| Besökarnas beteendemönster | **user.categoryAffinity:** `categoryAffinity` med `FAVORITE` parameter.<br>![Tillhörighetsövervakning ](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**för importerad kategori:** Övervakningstjänsten är lika med true.<br>**Ingen övervakningstjänst:** Övervakningstjänsten är lika med false.<br>![Importerad övervakning](/help/c-target/c-audiences/assets/imported_monitoring.png) |
| Målgrupper som använder operatorn NOT | **Enkel regel:** Target visar målgruppen i formatet `[All Visitor AND [NOT [rule]`. En NOT-regel visas med AND med `AllVisitor` målgrupp.<br>![Importerad publik ej](/help/c-target/c-audiences/assets/imported_not_audience.png) |

Tänk på följande när du arbetar med importerade målgrupper:

* Målgrupper för uttryck stöds inte längre i Target Standard/Premium.
* Target Standard/Premium stöder inte vissa inaktuella målgrupper eller har förbättrade operatorer som är enkla att använda. Därför betyder definitionen av en importerad målgrupp, även om den fungerar enligt definitionen, inte att den nu är tillgänglig för att skapas i gränssnittet Standard/Premium. Sociala målgrupper är till exempel synliga med sina regler, men Target Standard/Premium tillåter inte att sociala målgrupper skapas.

## Utbildningsvideo: Använda märket för ![självstudiekurser för publiker](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgrupper.

* Förklara termen&quot;publik&quot;
* Förklara de två sätt på vilka målgrupper används för optimering
* Hitta målgrupper i publiklistan
* Rikta en aktivitet mot en målgrupp
* Använd målgrupper för passiv rapportering i en aktivitet

>[!VIDEO](https://video.tv.adobe.com/v/17398)
