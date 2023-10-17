---
keywords: arbetsytor;hantera egenskap;behörigheter;produktkonfiguration;produktprofil;roller;projekt;observatör;redigerare;godkännare;utgivare
description: Lär dig hur du skapar separata arbetsytor (produktprofiler) och sedan tilldelar användare olika roller och behörigheter för enskilda sidor, egenskaper eller webbplatser.
title: Vad är företagsanvändarbehörigheter och hur använder jag dem?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 838abe87-dba7-4274-97b4-31a7905846dc
source-git-commit: d414f1554e1875e873f1ce557a7edf86b88ee79e
workflow-type: tm+mt
source-wordcount: '3180'
ht-degree: 0%

---

# Enterprise-användarbehörigheter

Enterprise-användarbehörigheter är ett sätt att formellt administrera företagsövergripande användaråtkomst till [!DNL Adobe Target]. Lägg till användare i [!DNL Target], tilldela behörigheter baserat på deras roller och skapa arbetsytor för team baserat på olika avdelningar, globala platser, kanaler och andra logiska grupper. Du kan tilldela användare rollerna för [!UICONTROL Observer], [!UICONTROL Editor], [!UICONTROL Approver], eller [!UICONTROL Publisher].

## Avgör om du har åtkomst till företagsanvändarbehörigheter

>[!NOTE]
>
>[!UICONTROL Properties and Permissions] finns som en del av [!DNL Target] Premiumlösning. De är inte tillgängliga i [!DNL Target] Standard utan [!DNL Target] Premiumlicens.
>
>Dina [!DNL Target] kan implementeras med valfri version av at.js eller [!DNL Adobe Experience Platform Web SDK].

Du kan se om din organisation har en Standard- eller Premium-licens genom att klicka på [!UICONTROL Administration] länk högst upp i [!DNL Target] Gränssnitt.

* **[!DNL Target Standard]Kunder**: Om [!UICONTROL Users] tab ([!UICONTROL Administration > Users]) (och inte [!UICONTROL Properties] -fliken) har din organisation en [!DNL Target Standard] licens. [!DNL Target Standard] ska kunderna följa instruktionerna i [Användare](/help/main/administrating-target/c-user-management/c-user-management/user-management.md) för att lägga till användare och tilldela behörigheter i [!DNL Adobe Admin Console].

* **[!DNL Target Premium]Kunder**: Om [!UICONTROL Properties] tab ([!UICONTROL Administration > Properties]) och [!UICONTROL Users] har din organisation en [!DNL Target Premium] licens. [!DNL Target Premium] ska kunderna följa instruktionerna i den här artikeln och i [Konfigurera företagsbehörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

## Innan du börjar använda företagsbehörigheter

>[!IMPORTANT]
>
>Läs [Caveats](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) innan du fortsätter med företagsbehörigheter.

## Termer och definitioner som används i detta avsnitt {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

Följande termer används i hela det här avsnittet och kan vara nya för användare som vill använda funktionerna Egenskaper och Behörigheter i [!DNL Target] Premium.

### Egenskap

Egenskaper liknar till sin natur egenskaper i [!DNL Adobe Experience Platform] på så sätt att de använder ett unikt kodfragment för att särskilja dem.

En webbegenskap är ett bibliotek med regler och en inbäddningskod. En webbegenskap kan vara vilken gruppering som helst av en eller flera domäner och underdomäner.

Egenskaper aktiveras genom att ett specifikt namn/värde-par läggs till som en parameter med ett anrop (Target call, api call, osv.) till [!DNL Target].

Egenskaperna tillhör specifika kanaler (webb, mobil, e-post eller API/annan).

### Arbetsyta (produktprofil)

Med en arbetsyta kan en organisation tilldela en viss uppsättning användare till en viss uppsättning egenskaper. På många sätt liknar en arbetsyta en rapportserie i [!DNL Adobe Analytics].

Obs! Arbetsytor kallas [!UICONTROL Product Profiles] i [!DNL Adobe Admin Console for Enterprise].

Om du är en del av en flernationell organisation kan du ha en arbetsyta för dina europeiska webbsidor, egenskaper eller webbplatser och en annan arbetsyta för dina amerikanska webbsidor, egenskaper eller webbplatser. Om du är en del av en organisation med flera varumärken kan du ha en separat arbetsyta för varje varumärke.

Användare kan ingå i flera arbetsytor och kan till och med ha olika roller inom varje arbetsyta.

Användare kan ha olika vyer av [!DNL Adobe Target] genom att flytta mellan arbetsytor, ungefär som [!DNL Analytics] användare har olika vyer av [!DNL Analytics] genom att gå mellan olika rapportsviter.

Arbetsytor kan innehålla helt olika målgrupper, koderbjudanden och aktiviteter.

Alla målgrupper och aktiviteter som skapats före migreringen av den nya Enterprise Permissions-modellen grupperas i &quot;Default Workspace&quot;, vilket beskrivs nedan.

Alla aktiviteter skapade via [!DNL Adobe Experience Manager] (AEM) [!DNL Adobe Mobile Services]och [!DNL Adobe Target Classic] är en del av&quot;Standardarbetsyta&quot;.

### Standardarbetsyta

Alla befintliga arbetsytor (produktprofiler) inom [!DNL Admin Console] sammanfogas till en enda arbetsyta som kallas&quot;standardarbetsyta&quot; när din organisation migrerar till den nya modellen för företagsbehörigheter.

>[!IMPORTANT]
>
>Ta inte bort standardarbetsytan.

Alla användarroller och åtkomst till alla [!DNL Target] funktionerna är desamma som de var innan migreringen till den nya Enterprise Permissions-modellen.

### Användargrupper

Du kan skapa användargrupper, till exempel utvecklare, analytiker, marknadsförare och chefer. Du kan sedan tilldela behörigheter för flera Adobe-produkter och arbetsytor. Att utse en ny teammedlem kan vara lika enkelt som att lägga till dem i en viss användargrupp.

### Roller och behörigheter {#roles-permissions}

Roller och behörigheter avgör vilka åtkomstnivåer användare har för att skapa och hantera aktiviteter i din [!DNL Target] implementering. I [!DNL Target]omfattar rollerna följande:

| Roll | Beskrivning |
|--- |--- |
| [!UICONTROL Approver] | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
| [!UICONTROL Editor] | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
| [!UICONTROL Observer] | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
| [!UICONTROL Publisher] | Liknar [!UICONTROL Observer] roll (kan visa aktiviteter, men inte skapa eller redigera dem). Men [!UICONTROL Publisher] rollen har ytterligare behörighet att aktivera aktiviteter. |

### Kanal

Kanalen refererar till innehållstypen där [!DNL Target] aktiviteter levereras: webbsidor, mobilappar, e-postmeddelanden och så vidare.

När du skapar en aktivitet skapas den i den markerade arbetsytan. Du ser alternativ för kanalval i den första dialogrutan där du kan välja önskad kanal för aktiviteten: Web, Mobile App, Email eller Other/API.

## Översikt över behörigheter {#section_DC2172520DA84605B218A5E9FB6D187A}

Följande information förklarar hur behörigheter tillämpades tidigare i [!DNL Target] och hur de används med [!UICONTROL Properties] och [!UICONTROL Permissions] funktionalitet.

Den nya [!UICONTROL Permissions] kan du skapa olika projekt (så kallade&quot;produktprofiler&quot;) i [!DNL Adobe Admin Console for Enterprise]). Med projekt kan du tilldela olika behörigheter till en enskild användare som bestämmer den användarens åtkomstbehörighet för varje projekt. Dessa distinkta projekt kan jämföras med hur rapportsviterna fungerar i [!DNL Adobe Analytics]. Varje projekt kan ha specifika användare med specifika roller som gäller för en uppsättning egenskaper. Resultatet är att kunderna kan begränsa åtkomst till vy, redigering och godkännande för sina användare baserat på region, miljö (dev/stage/prod), kanal eller andra anpassade kriterier, vilket visas nedan:

![permissions image](assets/permissions.png)

En viss användare kan till exempel ha åtkomst till&quot;godkännande&quot; på amerikanska webbplatser, men bara visa åtkomst på den europeiska mobilappen. Samma användare kanske inte har tillgång till ens de aktiviteter som erbjuds på webb- och mobilsajter i APAC-regionen.

The [!DNL Target] [!UICONTROL Permissions] modellen har följande behörighetsroller (observatör, redigerare, godkännare och observatör). Observerrollen visas inte i illustrationer i den här artikeln.

![permissions_1 image](assets/permissions_1.png)

Varje roll har olika behörighetsnivåer:

| Roll | Beskrivning |
|--- |--- |
| Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
| Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
| Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
| Utgivare | Liknar observatörsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |

Det är viktigt att notera att varje användares roll gäller för varje sida, egenskap eller webbplats i ditt konto som innehåller [!DNL Target] taggar, enligt nedan:

![permissions_2 image](assets/permissions_2.png)

Den nya [!DNL Target] [!UICONTROL Permissions] Modellen har samma tre behörighetsroller (observatör, redigerare och godkännare), men du kan tilldela en användares behörighetsroller separat för enskilda sidor, egenskaper eller platser, vilket visas nedan:

![permissions_3 image](assets/permissions_3.png)

I det här exemplet har Jan godkännarbehörighet till USA:s hemsida och behörigheten US Site och Observer till Frankrikes webbplats.

Jan kan inte heller se sidor, egenskaper eller webbplatser i [!DNL Target] att hon inte har behörighet att se, vilket visas nedan:

![permissions_4 image](assets/permissions_4.png)

I det här exemplet kan Jan inte se produktsidorna, Rysslands webbplats och karriärwebbplatsen.

## Användningsscenarier {#section_F3CE8576959E4F4CB13BEEED38311DD8}

Följande användningsexempel kan vara användbara för att förstå hur egenskaper, projekt, roller och behörigheter kan hjälpa dig att uppnå dina marknadsföringsmål med [!DNL Target]:

### Flernationell organisation

Om du är en del av en flernationell organisation kan du ha en arbetsyta för dina europeiska webbsidor, egenskaper eller webbplatser och en annan arbetsyta för dina amerikanska webbsidor, egenskaper eller webbplatser.
Efter en omorganisering, med hjälp av de profiler som visas på bilderna ovan, kan du skapa arbetsytor och behörigheter som liknar följande:

* **Jan**: Jan är chef för optimering vid Center of Excellence för organisationens amerikanska webbsidor, egendomar och webbplatser. Hon har antagligen systemadministratörsbehörighet i Adobe Experience Cloud.

  I sin roll har hon godkännarbehörighet för den amerikanska hemsidan och den amerikanska webbplatsen. Med godkännarbehörighet kan hon skapa, redigera och aktivera eller stoppa aktiviteter.

  Jan samarbetar också med optimeringsteamet i Frankrike och har därför observatörsbehörighet för Frankrikes webbplats som ger henne skrivskyddad åtkomst till aktiviteter. Jan kan visa aktiviteter, men kan inte skapa eller redigera dem.

  Eftersom Jan inte har någon roll som gör att hon måste se produktsidor, Rysslands webbplats eller karriärsajten, kan hon inte se aktiviteter för dessa sajter.

* **Ernie**: Ernie är marknadschef för organisationen med ansvar för marknadsföring i USA.

  Eftersom Ernie är ganska ny i organisationen och oerfaren av Target har han redigeringsbehörighet för USA:s hemsida, amerikanska webbplats och produktsidor. Med redigeringsbehörigheter kan Ernie skapa och redigera aktiviteter innan de publiceras. Han kan inte godkänna lanseringen av en aktivitet - någon med godkännande, t.ex. Jan, måste godkänna aktiviteten innan den kan tas i produktion.

  Eftersom Ernie inte har någon roll som gör det nödvändigt att han ser Rysslands webbplats, Frankrikes webbplats eller karriärsajten, kan han inte se aktiviteter för dessa sajter.

* **Diana**: Diana är nu analytiker för organisationen och har fått observationsbehörigheter för USA:s hemsida, produktsidor, Rysslands webbplats och Frankrikes webbplats som ger henne skrivskyddad åtkomst till aktiviteter. Diana kan visa aktiviteter, men kan inte skapa eller redigera dem.

  Eftersom Diana inte har någon roll som gör det nödvändigt att hon ser karriären, kan hon inte se aktiviteter för dessa webbplatser.

### Organisering av flera varumärken

Om du är en del av en organisation med flera varumärken kan du ha en separat arbetsyta för varje varumärkes webbsidor, egenskaper eller webbplatser.

Efter en omorganisering, med hjälp av personerna i illustrationerna ovan, kan du skapa projekt och behörigheter som liknar följande:

* **Jan**: Jan är chef för optimeringen vid Center of Excellence för en hälso- och sjukvårdsorganisation som är verksam på sjukhus- och konsumentproduktioner. Hon har antagligen systemadministratörsbehörighet i Adobe Experience Cloud.

  I sin roll har hon godkännarbehörighet för webbplatsen. Med godkännarbehörighet kan hon skapa, redigera och aktivera eller stoppa aktiviteter.

  Jan samarbetar också med optimeringsteamet för konsumentprodukter och har därför administratörsbehörighet för webbplatsen som ger läsbehörighet för aktiviteter. Jan kan visa aktiviteter, men kan inte skapa eller redigera dem.

* **Ernie**: Ernie är marknadschef för organisationen med ansvar för marknadsföring på konsumentproduktområdet.

  Eftersom Ernie är ganska ny i organisationen och oerfaren av Target har han redigeringsbehörighet för konsumentwebbplatsen. Med redigeringsbehörigheter kan Ernie skapa och redigera aktiviteter innan de publiceras. Han kan inte godkänna lanseringen av en aktivitet. Någon med behörigheten Godkännanden för konsumentwebbplatsen, men inte Jan i det här scenariot, måste godkänna aktiviteten innan den kan tas i produktion.

  Eftersom Ernie inte har någon roll som gör det nödvändigt att han ser webbplatsen kan han inte se aktiviteter för den sajten.

* **Diana**: Diana är nu analytiker för organisationen och har fått observatörsbehörighet för sjukhuswebbplatsen och konsumentwebbplatsen som ger henne skrivskyddad åtkomst till aktiviteter. Diana kan visa aktiviteter, men kan inte skapa eller redigera dem.

## Kontaktpunkter för gränssnittsegenskaper och behörigheter {#section_3414371393BB42999A268628B5456EC9}

Den nya behörighetsfunktionen kan visas på olika platser i [!DNL Target] Gränssnitt.

* **Listruta för arbetsyta (produktprofil):** Listrutan Arbetsyta visas högst upp i [!UICONTROL Activities], [!UICONTROL Audiences]och [!UICONTROL Offers] sidor. Välj önskad arbetsyta för att filtrera listan så att endast objekt i den markerade arbetsytan visas.

  ![workspace_drop-down image](assets/workspace_drop-down.png)

* **Skapa aktivitet:** När du skapar en aktivitet skapas den i den markerade arbetsytan. Du ser alternativ för kanalval i den första dialogrutan där du kan välja önskad kanal för aktiviteten: Web, Mobile App, Email eller Other/API.

  ![channel_options, bild](assets/channel_options.png)

* **Målgrupper:** När du skapar en målgrupp skapas den i den markerade arbetsytan.
* **Mållista:** Du kan flytta målgrupper mellan arbetsytor med [!UICONTROL More Actions] > [!DNL Move] på [!UICONTROL Audiences] sida.
* **Skapa erbjudande:** När du skapar ett erbjudande skapas det i den valda arbetsytan.
* **Sidan Egenskaper (Administration > Egenskaper):** Du kan använda [!UICONTROL Search] sökruta [!UICONTROL Property] lista.

  ![properties_list image](assets/properties_list.png)

## Caveats {#section_9714311B1CD9497A86F4910F8AE635E2}

Tänk på följande när du använder eller konfigurerar egenskaper och behörigheter i [!DNL Target] Premium:

* **Viktigt**: Ta inte bort arbetsytor med aktiviteter. Om du tar bort en arbetsyta med aktiviteter kan du arbeta med kundtjänst för att återställa dessa aktiviteter.
* När du använder vyn Alla arbetsytor:

   * Du kan se aktiviteter, målgrupper och erbjudanden för alla arbetsytor som du har rätt roller och behörigheter att komma åt.
   * När du väljer [!UICONTROL All My Workspaces] en ny kolumn läggs till på sidan för aktiviteter, målgrupper och erbjudanden. I den här kolumnen visas objektets arbetsyta och din användarbehörighet som är kopplad till det objektet (observatör, redigerare eller godkännare),
   * När du skapar en aktivitet, målgrupp eller ett erbjudande i vyn Alla arbetsytor måste du välja den arbetsyta där objektet ska skapas. Endast de arbetsytor som du har behörighet att redigera eller godkänna kan väljas.
   * När du kopierar en aktivitet, målgrupp eller ett erbjudande i vyn Alla arbetsytor måste du välja den arbetsyta där objektet ska kopieras. Endast de arbetsytor som du har behörighet att redigera eller godkänna kan väljas.

* Alla inställningar för följande [!UICONTROL Administration] kan styras av alla [!UICONTROL Approver] på alla arbetsytor:

   * Visual Experience Composer
   * Rapportering
   * Scene7 Configuration
   * Implementering
   * Egenskaper
   * Värdar
   * Miljö
   * Svarstoken
   * Användare

* Användare kan inte flytta resurser från en arbetsyta (produktprofil) till en annan. Kopiering stöds dock.
* När du visar målgrupper från [!DNL Audiences] sidan läses sidan in långsammare än förväntat. Om du interagerar med sökfältet på något sätt visas målgrupperna snabbare. Problemet är känt och kommer att åtgärdas i en kommande uppdatering. Problemet påverkar inte valet av målgrupper när aktiviteten skapas.
* Följande resurser ingår i den nya Enterprise Permissions-modellen:

   * Verksamheter, målgrupper och koderbjudanden som skapats i [!DNL Target Standard/Premium] är tillgängliga för användning när kunden har aktiverats för behörigheter. (Obs! Kunderna måste ha rätt till [!DNL Target Premium].)
   * Egenskaper kan läggas till i befintliga aktiviteter på standardarbetsytan, men det kan komma att ändras.
   * Endast nya resurser (som aktiviteter, koderbjudanden och målgrupper) som skapats i Target Premium (efter att Enterprise Permissions (Enterprise Permissions)) har aktiverats kan begränsas av behörigheter.
   * Externa resurser är bara tillgängliga för användare på standardarbetsytan. En användares roll i standardarbetsytan används globalt (för alla Target-begäranden och alla Target-resurser).

* Följande resurser är *not* ingår i den nya Enterprise Permissions-modellen:

   * Bilderbjudanden
   * Alla Recommendations-resurser, inklusive kriteriebibliotek, designbibliotek, katalog, Recommendations Setup.
   * Befintliga resurser (t.ex. aktiviteter, koderbjudanden och målgrupper) som skapats i Target Premium innan Enterprise-behörigheter aktiveras kan kopieras, men kan inte flyttas till andra arbetsytor.
   * Aktiviteter, målgrupper, koderbjudanden, bilderbjudanden eller andra resurser som skapats med följande lösningar eller metoder kan inte styras av modellen Enterprise Permissions, men ingår i standardarbetsytan: Target Classic, Adobe Experience Manager (AEM), Adobe Mobile Services och resurser som skapats med API. Resurser som skapas via API omfattar aktiviteter, målgrupper, koderbjudanden och bilderbjudanden).
   * Bilderbjudanden (resurser lagrade under `https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library` kan för närvarande inte styras av Enterprise Permissions-modellen.
   * clickTracking och omdirigerar arbetet när mållänken eller målsidan är en del av en egenskap som ingår i aktiviteten. ClickTracking kanske inte heller fungerar när du använder `targetPageParams()` funktion. The `targetPageParamsAll()` är den rekommenderade funktionen.

  [!DNL Target] för närvarande kräver `at_property` som ska finnas på alla sidor där spårning sker. Om variabeln (1) inte finns, (2) inte upptäcktes vid tidpunkten för aktivitetsinställningen (inom VEC) eller (3) inte skickades till clickTracking Target-anropet via `targetPageParamsAll()` -funktionen ökas inte måttet och visas som&quot;0&quot;.

  Detsamma gäller för aktiviteter som använder omdirigeringar. Målsidan måste ha en `at_property` och bli igenkänd när konfigurationen görs i VEC.

  I en framtida version kommer Target att fungera på sidor där `at_property` token finns, eller sidor där en annan `at_property` token finns.

* Enterprise-användarbehörigheten stöds inte i Adobe Developer API-anrop.

## Vanliga frågor {#faqs}

Vanliga frågor om Enterprise permissions är:

### Vad händer om en användare har flera roller och behörigheter? [#multiple-roles]

Om en användare har flera roller och behörigheter används rollen med behörigheten för hierarkin. Om en användare till exempel har [!UICONTROL Observer] och [!UICONTROL Approver] roller, [!UICONTROL Approver] roll används.

### Kan jag flytta en aktivitet från en arbetsyta till en annan?

Tyvärr kan du inte flytta aktiviteter från en arbetsyta till en annan. Du kan dock kopiera en aktivitet till valfri arbetsyta i vetskap om att rapportdata inte överförs. Mer information finns i&quot;Kopiera/redigera en aktivitet när du använder arbetsytor&quot; i [Kopiera/redigera en aktivitet när du använder arbetsytor](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6).

Aktiviteter som skapas före migreringen fortsätter att köras på samma sätt i standardarbetsytan, såvida de inte redigeras och tilldelas egenskaper. Aktiviteter under en specifik arbetsyteegenskap som tilldelats den arbetsytan och därför kanske inte beteendet är detsamma som före migreringen.

### Kan jag flytta en målgrupp från en arbetsyta till en annan? {#move-audience}

Ja, du kan flytta målgrupper mellan arbetsytor med [!UICONTROL More Actions] på [!UICONTROL Audiences] sida.

1. Klicka på **[!UICONTROL More Actions]** (de tre ellipserna) och klicka sedan på **[!UICONTROL Move]**.

   ![Fler åtgärder > Flytta](/help/main/administrating-target/c-user-management/property-channel/assets/move-audience.png)

1. Välj önskad arbetsyta på menyn **[!UICONTROL Workspace]** nedrullningsbar lista och klicka sedan på **[!UICONTROL Move]**.

   ![Välj önskad målgrupp för att gå till den nya arbetsytan](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-move.png)

>[!NOTE]
>
>Du måste ha rätt behörighet för att redigera en målgrupp. Dessutom får målgruppen inte användas i andra verksamheter. Om målgruppen används i andra aktiviteter och du fortfarande vill flytta målgruppen till en annan arbetsplats tar du bort målgruppen från de andra aktiviteterna där de används.

### Varför får jag ett felmeddelande om att ingen egenskap är associerad med den här aktiviteten, trots att det finns en egenskap tilldelad?

Om du implementerat [!DNL Target] med taggar i [!DNL Adobe Experience Platform] och få ett felmeddelande som anger att ingen egenskap är associerad med aktiviteten, skicka `at_property` parametern med `targetPageParams` funktion.

### Spelas klickspårskonverteringar in om en omdirigerad sida och aktivitets-URL:en tillhör olika egenskaper?

Klickspårning registreras inte på sidor där sid- och aktivitets-URL:en tillhör olika egenskaper.

Tänk på följande scenario:

* Page1 tillhör Property1.
* Page2 tillhör Property2.
* I aktiviteten dirigeras Page1 om till Page2, som innehåller klickspår.

När en besökare öppnar Page1 i en webbläsare omdirigeras besökaren till Page2. Eftersom Page2 inte är kvalificerat för att leverera aktiviteten innehåller inte Target-anropet några klickspår i sitt svar.

Om omdirigeringssidan och aktivitets-URL:en tillhör samma egenskap fungerar klickningsspåren som förväntat. Mer information finns i [Klickspårning](/help/main/c-activities/r-success-metrics/click-tracking.md).

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Utbildningsvideo: Utbildningsvideo om företagsbehörigheter ![Märket Översikt](/help/main/assets/overview.png)

Utbildningsmål:

* De tre rollnivåerna som Adobe Target-användare kan hantera
* Begreppen Egenskaper och Arbetsytor och hur dessa gränser och grupperingar fungerar för att styra användarnas åtkomstnivåer
* Olika egenskapsexempel som din organisation kan ta hänsyn till

>[!VIDEO](https://video.tv.adobe.com/v/19042/)

### Kontorstid: [!DNL Target] Premium Workspaces

Den här videon är en inspelning av&quot;Office Hours&quot;, ett projekt som leds av kundtjänstteamet på Adobe.

* Skapa en arbetsyta (produktprofil)
* Skapa egenskaper
* Lägga till användare
* Uppdaterar implementering

>[!NOTE]
>
>The [!DNL Target] [!UICONTROL Administration] menygränssnitt (tidigare [!UICONTROL Setup]) har gjorts om för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är korrekt, men alternativen kan finnas på något olika platser.

>[!VIDEO](https://video.tv.adobe.com/v/23643/)
