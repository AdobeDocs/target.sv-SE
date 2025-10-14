---
keywords: upplevelse;kontrollera;automatiserad personalisering;automatisk målanpassning
description: Lär dig hur du väljer en upplevelse som ska användas som en kontroll när du skapar en [!UICONTROL Automated Personalization] (AP) eller [!UICONTROL Auto-Target]-aktivitet i  [!DNL Adobe Target].
title: Hur kan jag använda en specifik upplevelse som kontroll i en [!UICONTROL Automated Personalization]-aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 0%

---

# Välj kontrollen för din [!UICONTROL Automated Personalization]- eller [!UICONTROL Auto-Target]-aktivitet

Du kan välja en slumpmässigt hanterad upplevelse eller en specifik upplevelse som ska användas som kontroll när en [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) eller [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)-aktivitet skapas.

Med den här funktionen kan du dirigera kontrolltrafiken till relevanta upplevelser, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Du kan sedan utvärdera prestandarapporter för den personaliserade trafiken mot kontrolltrafiken till den kontrollen.

Alternativen för att ställa in en kontroll i [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target]-aktiviteter skiljer sig lite från andra aktivitetstyper. I en handbok [!UICONTROL A/B Test] kan du ändra vad som visas som din kontroll och lyft beräknas baserat på konverteringsgraden för den kontrollupplevelsen. Ni kan enkelt göra den här ändringen eftersom trafiken betjänas slumpmässigt för var och en av de upplevelser ni tog med i er aktivitet, oavsett vilken kontroll som ursprungligen är inställd på. Det betyder att om du väljer kontrollen påverkas inte trafiken. I [!UICONTROL Automated Personalization]- och [!UICONTROL Auto-Target]-aktiviteter påverkar ditt beslut om vad som ska väljas som kontroll hur besökstrafiken hanteras. Därför måste du tänka mer noga på ditt beslut.

Det finns två alternativ för din kontroll i dina [!UICONTROL Automated Personalization]- och [!UICONTROL Auto-Target]-aktiviteter:

* **Slumpmässigt betjänad**: För en slumpmässig kontroll visar kontrollprocenten för trafik slumpmässigt alla upplevelser i aktiviteten, utan att ta hänsyn till besökarens profil. Du kan tänka dig kontrollen som ett sätt att besvara frågan:&quot;Om jag bara slumpmässigt skickar ut en upplevelse (eller ett erbjudande) till besökare och inte ser deras profiler, hur stor konverteringsgraden är för upplevelsen (eller erbjudandet)?&quot; Kontrollen är som en [!UICONTROL A/B Test] i din AI-aktivitet. Att ha denna information om den icke-personaliserade konverteringsgraden för varje upplevelse eller erbjudande kan vara praktiskt när du analyserar aktivitetsresultaten.

* **Specifik upplevelse**: Med en specifik upplevelsekontroll kan du jämföra din trafik som hanteras av [!DNL Target]-personaliseringsmodeller med en specifik marknadsföringsdefinierad upplevelse (till exempel din standardhemsida). Med det här alternativet betjänar kontrollprocenten av trafiken slumpmässigt bara trafiken för den upplevelsen.

## Ange en specifik upplevelse som kontroll

1. När du skapar eller redigerar en [[!UICONTROL Automated Personalization] aktivitet &#x200B;](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) eller [[!UICONTROL Auto-Target] aktivitet &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) konfigurerar du upplevelserna som du vill.
1. På sidan [!UICONTROL Targeting] (steg 2 i det guidade arbetsflödet i tre delar) klickar du på kontrollfunktionen för att visa [!UICONTROL Control] alternativ i den högra rutan.

   ![Kontrollpanelen](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. Välj [!UICONTROL Control] i listrutan [!UICONTROL Random Experience] eller välj önskad upplevelse som du vill använda för kontrollen.

1. Klicka på kontrollen [!UICONTROL Traffic Allocation] och ange sedan önskad trafikallokering för kontrollupplevelsen och andra upplevelser.

   ![Trafikallokeringsspår](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   För en specifik upplevelsekontroll rekommenderas 10 till 30 procent.

1. Fortsätt med sidan [!UICONTROL Goals & Settings].

## Kända begränsningar och överväganden

Tänk på följande när du använder en specifik upplevelse som kontroll:

* Att ändra kontrollupplevelsen i en redan aktiv aktivitet rekommenderas inte. Den senaste kontrollupplevelsen som valts namnges i rapporter (även om äldre rapporter är baserade på en annan upplevelse).
* Du bör inte ta bort kontrollfunktionen.
* Du bör inte lägga till många nya erbjudanden eller upplevelser till en aktiv aktivitet med en specifik upplevelse eftersom kontrollen inte rekommenderas.
* I [!UICONTROL Automated Personalization] aktiviteter, inklusive målinriktning på kontrollupplevelsen som ytterligare skulle kunna begränsa vem som kan se att upplevelsen inte rekommenderas.
* I [!UICONTROL Automated Personalization]-aktiviteter är lift- och förtroendeinformation *INTE* tillgänglig i erbjudandenivårapporten om en viss upplevelse har valts. Information om Lyft och förtroende finns tillgänglig på den övergripande trafiknivån för riktad trafik kontra kontrolltrafik för aktiviteten [!UICONTROL Automated Personalization]. Lyft- och förtroendeinformation är tillgänglig om &quot;random&quot; är valt som kontroll. Skillnaden beror på att det inte är logiskt att jämföra konverteringsgraden för en viss upplevelse med konverteringsgraden för ett erbjudande på grund av enhetsavvikelsen. Informationen som är tillgänglig i en [!UICONTROL Auto-Target]-aktivitet är densamma, oavsett vilken typ av kontroll som har valts.
* Eftersom all kontrolltrafik går till en enda upplevelse eller en uppsättning erbjudanden när du väljer upplevelsen som kontroll (jämfört med slumpmässig, där mängden kontrolltrafik delas över antalet upplevelser eller erbjudanden i din aktivitet) behöver du vanligtvis inte så mycket trafik som flödar till kontrollen. 10 % är ett bra ställe att börja på.
* Om du gör något av följande för en aktiv aktivitet med en specifik upplevelse som kontroll återställs kontrollen automatiskt till slumpmässigt hanterade upplevelser (i stället för den tidigare valda specifika upplevelsen):

   * Ta bort en upplevelse
   * Ta bort en plats eller ett erbjudande ([!UICONTROL Automated Personalization] endast)
   * Uteslut en upplevelse manuellt via borttagning av dubbletterbjudanden eller via en exkluderingsgrupp (endast [!UICONTROL Automated Personalization])
