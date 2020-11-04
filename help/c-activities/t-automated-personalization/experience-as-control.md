---
keywords: experience;control;automated personalization;auto-target
description: Välj en upplevelse som ska användas som kontroll när du skapar en Automated Personalization- (AP) eller Auto-Target-aktivitet i Adobe Target.
title: Använd en specifik upplevelse som kontroll i Adobe Target
feature: ap
solution: Target,Analytics
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Välj kontroll för din Automated Personalization- eller Automatisk målaktivitet

Du kan välja en slumpmässigt hanterad upplevelse eller en specifik upplevelse som ska användas som kontroll när du skapar en [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) - (AP) eller [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md) -aktivitet (AT).

Med den här funktionen kan du dirigera kontrolltrafiken till relevanta upplevelser, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Du kan sedan utvärdera prestandarapporter för den personaliserade trafiken mot kontrolltrafiken till den kontrollen.

Alternativen för att ställa in en kontroll i AP- och AT-aktiviteter skiljer sig lite från andra aktivitetstyper. I en manuell A/B-test kan du ändra vad som visas som din kontroll, och lyften beräknas baserat på konverteringsgraden för den kontrollupplevelsen. Ni kan enkelt göra den här ändringen eftersom trafiken betjänas slumpmässigt för var och en av de upplevelser ni tog med i er aktivitet, oavsett vilken kontroll som ursprungligen är inställd på. Det betyder att om du väljer kontrollen påverkas inte trafiken. I AP- och AT-aktiviteter påverkar ditt beslut vad du ska välja när kontrollen är hur besökstrafiken betjänas. Därför måste du tänka mer noga på ditt beslut.

Det finns två alternativ som du kan styra i dina AP- och AT-aktiviteter: slumpmässigt hanterade upplevelser eller en specifik upplevelse.

* **Slumpmässigt serverad**: För en slumpmässig kontroll visar kontrollprocenten av trafiken slumpmässigt alla upplevelser i aktiviteten, utan att ta hänsyn till besökarens profil. Du kan tänka dig kontrollen som ett sätt att besvara frågan:&quot;Om jag bara slumpmässigt skickar ut en upplevelse (eller ett erbjudande) till besökarna och inte ser deras profiler, hur stor konverteringsgraden är för upplevelsen (eller erbjudandet)?&quot; Kontrollen är som ett A/B-test i AI-aktiviteten. Att ha denna information om den icke-personaliserade konverteringsgraden för varje upplevelse eller erbjudande kan vara praktiskt när du analyserar aktivitetsresultaten.

* **Specifik upplevelse**: Med en specifik upplevelsekontroll kan du jämföra den trafik som betjänas av Target personaliseringsmodeller med en specifik marknadsföringsdefinierad upplevelse (till exempel din standardhemsida). Med det här alternativet betjänar kontrollprocenten av trafiken slumpmässigt bara trafiken för den upplevelsen.

## Ange en specifik upplevelse som kontroll

1. När du skapar en [AP-aktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md) eller en [AT-aktivitet](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)konfigurerar du upplevelserna efter behov.
1. På [!UICONTROL Targeting] sidan (steg 2 i det guidade arbetsflödet i tre delar) väljer du önskad upplevelse som kontroll.
1. Ange önskad trafikallokering för kontrollupplevelsen och andra upplevelser.

   För en specifik upplevelsekontroll rekommenderas 10 till 30 procent.

1. Fortsätt med [!UICONTROL Goals & Settings] sidan.

## Kända begränsningar och överväganden

Tänk på följande när du använder en specifik upplevelse som kontroll:

* Att ändra kontrollupplevelsen i en redan aktiv aktivitet rekommenderas inte. Den senaste kontrollupplevelsen som valts namnges i rapporter (även om äldre rapporter är baserade på en annan upplevelse).
* Du bör inte ta bort kontrollfunktionen.
* Du bör inte lägga till ett stort antal nya erbjudanden/upplevelser till en aktiv aktivitet med en specifik upplevelse eftersom kontrollen inte rekommenderas.
* I AP-aktiviteter, inklusive målinriktning på kontrollupplevelsen som ytterligare skulle kunna begränsa vem som kan se att upplevelsen inte är tillrådlig.
* I AP-aktiviteter är lyftnings- och förtroendeinformation *INTE* tillgänglig i rapporten på erbjudandenivå om en specifik upplevelse väljs. Information om lyft och förtroende finns tillgänglig på den övergripande&quot;målgruppsanpassningen&quot; jämfört med trafiknivån&quot;control&quot; för AP-aktiviteten. Lyft- och förtroendeinformation är tillgänglig om &quot;random&quot; är valt som kontroll. Skillnaden beror på att det inte är logiskt att jämföra konverteringsgraden för en viss upplevelse med konverteringsgraden för ett erbjudande på grund av enhetsavvikelsen. Informationen som är tillgänglig i en AT-aktivitet är densamma, oavsett vilken typ av kontroll som väljs.
* Eftersom all kontrolltrafik går till en enda upplevelse eller en uppsättning erbjudanden när du väljer upplevelsen som kontroll (jämfört med slumpmässig, där mängden kontrolltrafik delas över antalet upplevelser eller erbjudanden i din aktivitet) behöver du vanligtvis inte så mycket trafik som flödar till kontrollen. 10 % är ett bra ställe att börja på.
* Om du gör något av följande för en aktiv aktivitet med en specifik upplevelse som kontroll återställs kontrollen automatiskt till slumpmässigt hanterade upplevelser (i stället för den tidigare valda specifika upplevelsen):

   * Ta bort en upplevelse
   * Ta bort en plats eller ett erbjudande (endast AP)
   * Uteslut en upplevelse manuellt via borttagning av dubbletterbjudanden eller via en exkluderingsgrupp (endast AP)

