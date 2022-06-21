---
keywords: målanvändargränssnitt;användargränssnitt;ui;notiser;händelser
description: Bekanta dig med användargränssnittet och hitta länkar till mer detaljerad information som hjälper dig att få ut det mesta av [!DNL Target].
title: Hur jag använder [!DNL Target] UI?
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 6df387b22e9ef0ee56649057c37f474a8e4fe128
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 0%

---

# Förstå [!DNL Target] UI

Användargränssnittet är ordnat i ett logiskt och användarvänligt format så att du får ut det mesta av [!DNL Adobe Target]. I följande korta översikt får du hjälp att bekanta dig med [!DNL Target] och innehåller länkar för mer ingående information och stegvisa instruktioner.

Rubriken högst upp i [!DNL Target] Gränssnittet innehåller flikar och alternativ som hjälper dig att navigera i lösningens olika funktioner. Du kan också växla mellan organisationer och [!DNL Adobe Experience Cloud] lösningar, få hjälp och meddelanden, hantera [!DNL Adobe] profil och logga ut från [!DNL Target].

![Målhuvud](/help/main/c-intro/assets/target-header.png)

Med flikarna till vänster kan du komma åt de olika funktionerna i [!DNL Target]som diskuteras senare. Låt oss börja med att diskutera alternativen till höger innan vi går in på flikarna.

## Organisationer

An *organisation* är den enhet som gör det möjligt för en administratör att konfigurera grupper och användare samt att styra enkel inloggning i [!DNL Adobe Experience Cloud]. Organisationen fungerar som ett inloggningsföretag som omfattar alla [!DNL Experience Cloud] produkter och lösningar. Oftast är en organisation ditt företagsnamn. Ett företag kan dock ha många organisationer.

Välj önskad organisation i [!UICONTROL Organization] nedrullningsbar lista om företaget har flera organisationer:

![Listruta för organisation](/help/main/c-intro/assets/organizations.png)

## Appar

Med Apps-väljaren kommer du snabbt åt [!DNL Adobe Experience Cloud] lösningar som ni har tillgång till.

![Appväljaren](/help/main/c-intro/assets/apps.png)

## Hjälp

Med hjälp av hjälpikonen kan du komma åt information, videoklipp, bloggar och annat som kan hjälpa dig att använda [!DNL Target] effektivare. Du kan skapa en supportanmälan, hitta telefonnummer till supporten, ställa frågor via Twitter eller lämna feedback om [!DNL Target] för att vi ska veta hur [!DNL Target] Det går bra för laget.

![Hjälp](/help/main/c-intro/assets/help.png)

## Meddelanden

The [!UICONTROL Notifications] och [!UICONTROL Announcements] paneler hjälper dig att hålla dig uppdaterad om allt [!DNL Adobe Target]. Proaktiva meddelanden hjälper dig att hålla dig à jour med statusen för [!DNL Adobe Experience Cloud] lösningar och [!DNL Target] händelser. Proaktiva meddelanden varnar dig för driftavbrott och underhållshändelser.

>[!NOTE]
>
>Information om de förbättrade [!UICONTROL Notifications and Announcements] panelen i det här avsnittet gäller för [!DNL Target] och kommer att lanseras för alla kunder de närmaste månaderna.

Klicka på klockikonen i sidhuvudet för att visa meddelanden:

![Bell-ikon för meddelanden och meddelanden](assets/bell-icon.png)

Panelen innehåller flikar för [!UICONTROL Notifications] och [!UICONTROL Announcements].

![Meddelanden](assets/notifications.png)

Följande avsnitt innehåller information om varje flik och hur du konfigurerar meddelanden och meddelanden.

### Meddelanden

[!DNL Target] händelsemeddelanden innehåller följande:

* **Verksamhet**: Meddelanden för alla aktivitetstyper när en aktivitet har godkänts eller inaktiverats, antingen manuellt eller när start- eller slutdatumet nås. Meddelandet innehåller namnet på aktiviteten med en länk till aktivitetens översiktssida.

   Meddelanden kan konfigureras och tas emot som standard av produktadministratörer, utgivare och godkännare på aktivitetens arbetsyta för [!DNL Target Premium] konton. För [!DNL Target Standard] konton, meddelanden tas emot av alla utgivare och godkännare.

   Meddelanden formateras enligt följande exempel:

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **Profilskript**: Meddelanden när ett profilskript aktiveras eller inaktiveras, antingen manuellt eller av [!DNL Target].

   Meddelanden kan konfigureras och tas emot som standard av produktadministratörer och godkännare för båda [!DNL Target Premium] och [!DNL Target Standard] konton.

   Meddelanden formateras enligt följande exempel:

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Recommendations-flöden**: Meddelanden när en [!DNL Recommendations] feed aktiveras eller inaktiveras, antingen manuellt eller genom [!DNL Target]. Meddelanden skickas också när en [!DNL Recommendations] feed misslyckas.

   Meddelanden kan konfigureras och tas emot som standard av produktadministratörer och godkännare för [!DNL Target Premium] konton. [!DNL Recommendations] är en [!DNL Target Premium] och är inte tillgänglig i [!DNL Target Standard].

   Meddelanden formateras enligt följande exempel:

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed to import from source`

Du kan markera alla meddelanden som lästa eller visa alla meddelanden längst ned på panelen.

### Meddelanden

Proaktiva meddelanden varnar dig för driftavbrott och underhållshändelser.

Mer information finns på [Status för Adobe](https://status.adobe.com/) sida.

### Konfigurera meddelanden och meddelanden

Så här redigerar du aviseringsinställningarna:

1. Klicka på kugghjulsikonen och sedan på **[!UICONTROL Notifications]**.
1. Under **[!UICONTROL Target]**, klicka **[!UICONTROL Customize]**.
1. Markera eller avmarkera de kategorier för vilka du vill få meddelanden:

   * Begäranden: När någon skickar en begäran till dig om att godkänna ett objekt eller bevilja åtkomst till ett objekt. Du kan inte avbryta prenumerationen på den här kategorin.
   * Tilldelad mig: När någon tilldelar dig ett objekt.
   * Omnämnanden: När någon talar om dig i en kommentar.
   * Nya versioner: När en ny release finns tillgänglig för en produkt eller tjänst som du har tillgång till.
   * Delas med mig: När någon delar ett objekt med dig.
   * Uppdateringar av innehåll: När någon redigerar, tar bort eller kommenterar ett objekt som du har skapat eller följt.
   * Övrigt:

1. Välj de kategorier som du vill ska ha hög prioritet.
1. Välj de meddelanden som du vill visa aviseringar för i webbläsaren.

   Dessa varningar visas i webbläsarens övre högra hörn under några sekunder. Du kan välja att visa kategorier med hög prioritet, alla kategorier eller att dölja alla popup-meddelanden. Du kan också konfigurera om du vill att meddelandena ska vara synliga tills du stänger dem eller om du kan konfigurera meddelandets varaktighet.

1. Ange hur ofta du vill få e-postmeddelanden:

   * Skicka inte e-post
   * Snabbmeddelanden
   * Daglig sammandrag
   * Veckosammandrag

## Profil

Klicka på din profilavatar för att redigera din [!DNL Adobe Experience Cloud] inställningar eller logga ut från [!DNL Target]. Du kan även komma åt eller redigera [!DNL Adobe] profil.

![Profilavatar](/help/main/c-intro/assets/change-language.png)

Nu ska vi diskutera flikarna till vänster i [!DNL Target] header.

## Verksamhet

The **[!UICONTROL Activities]** är standardvyn när du öppnar [!DNL Target]. Du kan skapa aktiviteter från den här sidan och hantera befintliga aktiviteter.

![Aktivitetslista](/help/main/c-intro/assets/activities-list.png)

Se [Verksamhet](/help/main/c-activities/activities.md) för detaljerad information om aktivitetstyperna i [!DNL Target] och få mer information om [!UICONTROL Activity] listans användargränssnitt.

## Målgrupper

Klicka på **[!UICONTROL Audiences]** för att visa [!UICONTROL Audiences] lista där ni kan skapa målgrupper och hantera befintliga målgrupper.

![Målgruppslista](/help/main/c-intro/assets/audience-list.png)

En målgrupp är en grupp liknande aktivitetsdeltagare som ser en riktad aktivitet. En målgrupp är en grupp människor med samma egenskaper, till exempel en ny besökare, en återkommande besökare eller återkommande besökare från mellanvästern. The [!UICONTROL Audience] kan ni rikta olika innehåll och upplevelser till specifika målgrupper för att optimera er digitala marknadsföring genom att visa rätt budskap till rätt personer vid rätt tidpunkt. Om en besökare identifieras som en del av en målgrupp, [!DNL Target] avgör vilken upplevelse som ska visas, baserat på kriterier som definieras när aktiviteten skapas.

Se [Skapa målgrupper](/help/main/c-target/c-audiences/create-audience.md) för ingående information om målgruppstyper i [!DNL Target] och få mer information om [!UICONTROL Audience] listans användargränssnitt.

## Erbjudanden

Klicka på **[!UICONTROL Offers]** för att visa [!UICONTROL Offers] lista där ni kan skapa upplevelser och erbjudanden och hantera befintliga upplevelser och erbjudanden.

![Erbjudandelista](/help/main/c-intro/assets/offers.png)

En upplevelse kan vara ett erbjudande, en bild, text, knapp, video, en kombination av dessa olika element på en sida, en hel webbsida eller en uppsättning sidor som kanske utgör en inköpstratt eller någon annan logisk sekvens av sidor. Det kan också vara svaret från en röstassistent, ett kundskript eller till och med en personlig smak från en dryckesmaskin. Ni testar eller personaliserar upplevelser i [!DNL Target] verksamhet.

Se [Erbjudanden](/help/main/c-experiences/c-manage-content/manage-content.md) om du vill ha detaljerad information om olika erbjudandetyper i [!DNL Target] och få mer information om [!UICONTROL Offer] listans användargränssnitt.

## Recommendations

Klicka på **[!UICONTROL Recommendations]** flik för åtkomst [!DNL Target Recommendations].

>[!NOTE]
>
>Recommendations-aktiviteter är tillgängliga som en del av [!DNL Target Premium] lösning. De är inte tillgängliga i [!DNL Target Standard] utan [!DNL Target Premium] licens. Mer information finns i [Mål Premium](/help/main/c-intro/intro.md#premium) in *Introduktion till Target*.

![Recommendations](/help/main/c-intro/assets/recommendations.png)

[!UICONTROL Recommendations] aktiviteter visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter eller andra algoritmer. Recommendations hjälper kunderna att hänvisa till relevanta objekt som de annars kanske inte känner till.

Se [Recommendations](/help/main/c-recommendations/recommendations.md) för ingående information om [!UICONTROL Recommendations] in [!DNL Target] och få mer information om [!UICONTROL Recommendations] användargränssnitt.

## Administration

Klicka på **[!UICONTROL Administration]** -fliken för att komma åt [!UICONTROL Administration] sidor.

![Administrationssidor](/help/main/c-intro/assets/administration.png)

The [!UICONTROL Administration] sidor som du kan administrera [!DNL Target], inklusive konfigurationsinställningar för [!UICONTROL Visual Experience Composer] (VEC), rapportering, [!DNL Scene7] konfiguration, implementering, värdar, miljöer, svarstoken och användare.

Se [Administrera målöversikt](/help/main/administrating-target/administrating-target.md) om du vill ha detaljerad information och lära dig mer om användargränssnittet.
