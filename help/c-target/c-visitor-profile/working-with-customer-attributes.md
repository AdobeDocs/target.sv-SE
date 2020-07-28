---
keywords: customer relationship management;customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm;adobe experience cloud people
description: Information om hur man använder kunddata från CRM-databaser (customer relationship management) för innehåll i Adobe Target med hjälp av kundattribut i Adobe Experience Cloud persontjänst.
title: Kundattribut i Adobe Target
subtopic: Getting Started
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: 68bfa65011b7af493cd28849bce23a64c0ec3e48
workflow-type: tm+mt
source-wordcount: '1496'
ht-degree: 0%

---


# Kundattribut {#customer-attributes}

Information om hur man använder kunddata från CRM-databaser (Customer Relationship Management) för målgruppsanpassning i [!DNL Adobe Target] genom att använda kundattribut i [!DNL Adobe Enterprise Cloud People] bastjänsten.

Företagskunddata som samlas in via flera olika källor och lagras i CRM-databaser kan användas för [!DNL Target] att leverera det mest relevanta innehållet till kunder på ett strategiskt sätt, med särskild inriktning på återkommande kunder. Målgrupper och kundattribut i [!DNL People] bastjänsten (tidigare Profiles and Audiences) sammanför datainsamling och analys med testning och optimering, vilket gör data och insikter användbara.

## Översikt över kundattribut {#section_B4099971FA4B48598294C56EAE86B45A}

[Kundattribut](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) i den [!DNL People] centrala tjänsten ingår i [!DNL Adobe Experience Cloud] och ger företagen ett verktyg för att överföra kunddata till [!DNL Experience Cloud] plattformen.

Data som skickas till [!DNL Experience Cloud] är tillgängliga för alla [!DNL Experience Cloud] arbetsflöden. [!DNL Target] använder dessa data för att målinrikta returnerade kunder baserat på attribut. [!DNL Adobe Analytics] använder dessa attribut och kan användas för analys och segmentering.

![crs-exempel](/help/c-target/c-visitor-profile/assets/crs.png)

Tänk på följande när du arbetar med kundattribut och [!DNL Target]:

* Du måste uppfylla vissa krav innan du kan använda [!UICONTROL Customer attributes] funktionen i [!DNL People] bastjänsten. Mer information finns i&quot;Krav för överföring av kundattribut&quot; i [Kundattribut](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) i produktdokumentationen för *Experience Cloud och bastjänster*.

   >[!NOTE]
   >
   >[!DNL at.js] (valfri version) eller [!DNL mbox.js] version 58 eller senare krävs.

* [!DNL Adobe] garanterar inte att 100 % av kundattributdata (besökarprofil) från CRM-databaser kommer att överföras till [!DNL Experience Cloud] och därför vara tillgängliga för användning i [!DNL Target]. I vår nuvarande design finns det en möjlighet att en liten andel data (upp till 0,1 % av stora tillverkningssatser) inte tas med.
* Livslängden för kundattributdata som importeras från [!DNL Experience Cloud] till [!DNL Target] beror på besökarprofilens livstid, som är 14 dagar som standard. Mer information finns i [Livstid](../../c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)för besökarprofiler.
* Om `vst.*` parametrarna är det enda som identifierar besökaren, kommer den befintliga autentiserade profilen inte att hämtas så länge som `authState` är OAUENTICATED (0). Profilen spelas endast upp om `authState` ändras till AUTENTISERAD (1).

   Om parametern till exempel används för att identifiera besökaren (där `vst.myDataSource.id` är datakällalias) och det inte finns något MCID eller tredjeparts-ID, kommer parametern `myDataSource` `vst.myDataSource.authState=0` inte att hämta profilen som kan ha skapats via en import av kundattribut. Om det önskade beteendet är att hämta den autentiserade profilen, måste `vst.myDataSource.authState` värdet vara 1 (AUTENTISERAD).

* Du kan inte skicka följande tecken i `mbox3rdPartyID`: plustecken (+) och snedstreck (/).

## Få åtkomst till kundattribut i huvudtjänsten Personer

1. I [!DNL Adobe Experience Cloud]klickar du på menyikonen ( ![menyikonen](/help/c-target/c-visitor-profile/assets/menu-icon.png) ) och sedan på **[!UICONTROL People]**.

   ![Folk](/help/c-target/c-visitor-profile/assets/people.png)

1. Klicka på **[!UICONTROL Customer Attributes]** fliken.

   ![Fliken Kundattribut](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Arbetsflöde för kundattribut för Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Utför följande steg för att använda CRM-data i [!DNL Target]:

![crm-arbetsflöde](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Detaljerade anvisningar för hur du utför följande uppgifter finns i [Skapa en kundattributkälla och överför datafilen](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) i produktdokumentationen *för* Experience Cloud och bastjänster.

1. Skapa en datafil.

   Exportera kunddata från CRM till CSV-format för att skapa en CSV-fil. Alternativt kan en zip- eller gzip-fil skapas för överföring. Kontrollera att den första raden i CSV-filen är rubriken och att alla rader (kunddata) har samma antal poster.

   Följande bild visar ett exempel på en företagsdatafil:

   ![crs-exempel](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   Följande bild visar ett exempel på en CSV-fil för en företagskund:

   ![csv-exempel](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Skapa attributkällan och överför datafilen.

   Ange namn och beskrivning för datakällan och alias-ID:t. Aliaset-ID är ett unikt ID som ska användas i kundattributkoden i `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >Datakällans namn och attributnamnet får inte innehålla en punkt.

   Datafilen måste uppfylla kraven för filöverföring och får inte överstiga 100 MB. Om filen är för stor eller om du har data som behöver överföras regelbundet kan du FTP-överföra filerna i stället.

   * **HTTPS:** Du kan dra och släppa .csv-datafilen eller klicka på **[!UICONTROL Browse]** för att överföra den från filsystemet.
   * **FTP:** Klicka på FTP-länken för att [överföra filen via FTP](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). Det första steget är att ange ett lösenord för FTP-servern som tillhandahålls av Adobe. Ange lösenordet och klicka sedan på **[!UICONTROL Done]**.

   Överför nu CSV-/ZIP-/GZIP-filen till FTP-servern. När filöverföringen är klar skapar du en ny fil med samma namn och filnamnstillägget .fin. Överför den här tomma filen till servern. Detta anger att överföringen är slut och datafilen börjar bearbetas [!DNL Experience Cloud] .

1. Validera schemat.

   Med valideringsprocessen kan du mappa visningsnamn och beskrivningar till överförda attribut (strängar, heltal, tal och så vidare). Mappa varje attribut till rätt datatyp, visningsnamn och beskrivning.

   Klicka **[!UICONTROL Save]** när schemavalideringen är klar. Filens överföringstid varierar beroende på storleken.

   ![Validera schema](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Överför schema](/help/c-target/c-visitor-profile/assets/upload1.png)

1. Konfigurera prenumerationer och aktivera attributkällan.

   Klicka **[!UICONTROL Add Subscription]** och välj sedan lösningen för att prenumerera på attributen. [När du konfigurerar prenumerationer](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html) anges dataflödet mellan [!DNL Experience Cloud] och lösningar. Genom att aktivera attributkällan kan data flöda till prenumererade lösningar. De kundposter som du har överfört matchas med inkommande ID-signaler från webbplatsen eller tillämpningen.

   ![Konfigurera lösning](/help/c-target/c-visitor-profile/assets/solution.png)

   ![Aktivera](/help/c-target/c-visitor-profile/assets/activate.png)

   Tänk på följande begränsningar när du utför det här steget:

   * Den största filstorleken för varje överföring med HTTP-metoden är 100 MB.
   * Den största filstorleken för varje överföring med FTP-metoden är 4 GB.
   * Antal attribut som tillåts prenumerera: 5 for [!DNL Target Standard] och 200 for [!DNL Target Premium].

## Använd kundattribut i Target {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Du kan använda kundattribut på [!DNL Target] följande sätt:

### Skapa målgrupper

I [!DNL Target]kan du välja ett kundattribut i [!UICONTROL Visitor Profile] sektionen när du skapar en målgrupp. Alla kundattribut har prefixet &lt; data_source_name > i listan. Kombinera dessa attribut efter behov med andra dataattribut för att skapa målgrupper.

![Target Audience](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### Skapa profilskript med hjälp av variabler

Kundattribut kan refereras i profilskript med hjälp av format `crs.get('<Datasource Name>.<Attribute name>')`.

Profilskriptet kan användas direkt i erbjudanden för att leverera attribut som tillhör den aktuella besökaren.

### Använda mbox3rdPartyID på webbplatsen för att implementera och använda det

Skicka `mbox3rdPartyId` som en parameter till den globala mbox inuti `targetPageParams()` metoden. Värdet för `mbox3rdPartyId` ska anges till det kund-ID som fanns i CSV-datafilen.

```
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Använda Experience Cloud ID-tjänsten

Om du använder tjänsten Experience Cloud ID måste du ange ett kundID och autentiseringstillstånd för att använda kundattribut vid målanpassning. Mer information finns i [Kund-ID:n och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html) i hjälpen *för* Experience Cloud Identity Service.

Mer information om hur du använder kundattribut i [!DNL Target]finns i följande resurser:

* [Skapa en källa för kundattribut och ladda upp datafilen](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) i produktdokumentationen för *Experience Cloud*
* [Kundattribut: Ju mer du vet, desto bättre kontakt](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) får du i bloggen om *digital marknadsföring*

## Problem som kunderna ofta stöter på {#section_BE0F70E563F64294B17087DE2BC1E74C}

Följande problem kan uppstå när du arbetar med kundattribut och [!DNL Target].

>[!NOTE]
>
>Problem 1 och 2 orsakar ungefär 60 procent av problemen i det här området. Problem 3 orsakar ungefär 30 procent av problemen. Problem 4 orsakar ungefär 5 procent av problemen. De återstående 5 % beror på diverse fel.

### Utgåva 1: Kundattribut tas bort eftersom profilen är för stor

Det finns ingen teckenbegränsning för ett visst fält i användarens profil, men om profilen blir större än 64 kB trunkeras den genom att de äldsta attributen tas bort tills profilen är under 64 kB igen.

### Utgåva 2: Attribut som inte finns med i Audience Library i [!DNL Target], även efter flera dagar

Det här är vanligtvis ett anslutningsproblem i pipeline. Som lösning ber du ditt kundattributsteam att publicera om flödet.

### Utgåva 3: Leveransen fungerar inte baserat på attributet

Profilen har ännu inte uppdaterats på kanten. Som lösning ber du ditt kundattributsteam att publicera om flödet.

### Utgåva 4: Implementeringsproblem

Tänk på följande implementeringsproblem:

* Besökar-ID:t skickades inte korrekt. ID:t skickades `mboxMCGVID` i stället för `setCustomerId`.
* Besökar-ID:t skickades korrekt, men autentiseringstillståndet angavs inte till Autentiserat.
* `mbox3rdPartyId` skickades inte korrekt.

### Utgåva 5: `mboxUpdate` inte korrekt

`mboxUpdate`  har inte utförts korrekt med `mbox3rdPartyId`.

### Utgåva 6: Kundattribut importeras inte till [!DNL Target]

Om du inte hittar kundattributsdata i Target kontrollerar du att importen inträffade inom de *x* -dagar där *x* är Target [Visitor-profilens livstidsvärde](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) (14 dagar som standard).

## Utbildningsvideo: Ladda upp offlinedata med {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8} ![självstudiekursen för kundattribut](/help/assets/tutorial.png)

I den här videon visas hur du importerar CRM-data offline, helpdesk-data, försäljningsdata och andra marknadsföringsdata till [!DNL Experience Cloud People] tjänsten och associerar dem med besökare med deras kända ID:n.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
