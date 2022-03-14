---
keywords: kundrelationshantering;kundposttjänst;crm;mbox3rdpartyid;kundattribut;målinriktning;csv;crm;adobe experience cloud cloud personer
description: Lär dig hur du använder företagsdata från en CRM-databas (customer relationship management) för att målinrikta innehåll i [!DNL Adobe Target].
title: Vad är kundattribut och hur använder jag dem?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1563'
ht-degree: 0%

---

# Kundattribut

Information om hur du använder företagskunddata från CRM-databaser (Customer Relationship Management) för målgruppsanpassning i [!DNL Adobe Target] genom att använda kundattribut i [!DNL Adobe Enterprise Cloud People] service.

Företagskunddata som samlas in via flera olika källor och lagras i CRM-databaser kan användas i [!DNL Target] att strategiskt leverera det mest relevanta innehållet till kunder, med särskild inriktning på att returnera kunder. Målgrupper och kundattribut i [!DNL People] (tidigare Profiles and Audiences) sammanför datainsamling och analys med testning och optimering, vilket gör data och insikter användbara.

## Översikt över kundattribut {#section_B4099971FA4B48598294C56EAE86B45A}

[Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) i [!DNL People] är en del av [!DNL Adobe Experience Cloud] och ger företag ett verktyg för att föra ut sina kunddata till [!DNL Experience Cloud] plattform.

Uppgifter som läggs in på [!DNL Experience Cloud] är tillgängligt för alla [!DNL Experience Cloud] arbetsflöden. [!DNL Target] använder dessa data för att målinrikta returnerade kunder baserat på attribut. [!DNL Adobe Analytics] använder dessa attribut och kan användas för analys och segmentering.

![crs-exempel](/help/main/c-target/c-visitor-profile/assets/crs.png)

Tänk på följande när du arbetar med kundattribut och [!DNL Target]:

* Du måste uppfylla vissa krav innan du kan använda [!UICONTROL Customer attributes] i [!DNL People] service. Mer information finns i&quot;Krav för överföring av kundattribut&quot; i [Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) i *Experience Cloud Services and Administration documentation*.
* Tänk på begränsningarna för filöverföring som beskrivs i [Om datafiler och datakällor för kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en) i *Handbok för gränssnittskomponenter i Experience Cloud Central*. Bästa praxis:

   * Överför enstaka stora filer (i [angivna gränser](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en)). Enstaka stora filer prioriteras framför flera mindre filer.
   * Om du måste dela upp överföringen i flera filer måste du se till att filerna bearbetas fullständigt innan du skickar in nya filer. Se till att alla filer i en grupp bearbetas fullständigt innan du skickar in nästa fil i gruppen.

* [!DNL Adobe] garanterar inte att 100 % av kundattributdata (besökarprofil) från CRM-databaser kommer att överföras till [!DNL Experience Cloud] och därmed vara tillgängliga för användning för [!DNL Target]. I den aktuella designen finns det en möjlighet att en liten andel data (upp till 0,1 % av stora tillverkningssatser) inte tas med.
* Livslängden för kundattributdata som importeras från [!DNL Experience Cloud] till [!DNL Target] beror på besökarprofilens livstid, som är 14 dagar som standard. Mer information finns i [Livstid för besökarprofil](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Om `vst.*` parametrar är det enda som identifierar besökaren. Den befintliga autentiserade profilen hämtas inte så länge som `authState` är OAUTENTISERAD (0). Profilen spelas bara upp om `authState` ändras till AUTENTISERAD (1).

   Om `vst.myDataSource.id` -parametern används för att identifiera besökaren (där `myDataSource` är datakällalias) och det finns inget MCID eller tredje parts-ID, som använder parametern `vst.myDataSource.authState=0` hämtar inte profilen som kan ha skapats via en import av kundattribut. Om det önskade beteendet är att hämta den autentiserade profilen `vst.myDataSource.authState` måste ha värdet 1 (AUTENTISERAD).

* Du kan inte skicka följande tecken i `mbox3rdPartyID`: plustecken (+) och snedstreck (/).

## Få åtkomst till kundattribut i tjänsten Kontakter

1. I [!DNL Adobe Experience Cloud]klickar du på menyikonen ( ![menyikon](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ) och klicka sedan på **[!UICONTROL People]**.

   ![Folk](/help/main/c-target/c-visitor-profile/assets/people.png)

1. Klicka på **[!UICONTROL Customer Attributes]** -fliken.

   ![Fliken Kundattribut](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Arbetsflöde för kundattribut för [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Utför följande steg för att använda CRM-data i [!DNL Target], enligt nedan:

![crm-arbetsflöde](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

Detaljerade instruktioner för hur du utför följande uppgifter finns i [Skapa en kundattributkälla och överför datafilen](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) i *Experience Cloud Services and Administration documentation*.

1. Skapa en datafil.

   Exportera kunddata från CRM till CSV-format för att skapa en CSV-fil. Alternativt kan en zip- eller gzip-fil skapas för överföring. Kontrollera att den första raden i CSV-filen är rubriken och att alla rader (kunddata) har samma antal poster.

   Följande bild visar ett exempel på en företagsdatafil:

   ![crs-exempel](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   Följande bild visar ett exempel på en CSV-fil för en företagskund:

   ![csv-exempel](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Skapa attributkällan och överför datafilen.

   Ange namn och beskrivning för datakällan och alias-ID:t. Aliaset-ID är ett unikt ID som ska användas i kundattributkoden i `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >Datakällans namn och attributnamnet får inte innehålla en punkt.

   Datafilen måste uppfylla kraven för filöverföring och får inte överstiga 100 MB. Om filen är för stor, eller om du har data som måste överföras regelbundet, kan du FTP-överföra filerna i stället.

   * **HTTPS:** Du kan dra och släppa CSV-datafilen eller klicka **[!UICONTROL Browse]** för att ladda upp från filsystemet.
   * **FTP:** Klicka på FTP-länken för att [överföra filen via FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). Det första steget är att ange ett lösenord för FTP-servern som tillhandahålls av Adobe. Ange lösenordet och klicka sedan på **[!UICONTROL Done]**.

   Överför nu CSV-/ZIP-/GZIP-filen till FTP-servern. Skapa en fil med samma namn och ett `.fin` tillägg. Överför den här tomma filen till servern. Detta anger att överföringen har avslutats och [!DNL Experience Cloud] börjar bearbeta datafilen.

1. Validera schemat.

   Med valideringsprocessen kan du mappa visningsnamn och beskrivningar till överförda attribut (strängar, heltal, tal och så vidare). Mappa varje attribut till rätt datatyp, visningsnamn och beskrivning.

   Klicka **[!UICONTROL Save]** när schemavalideringen är klar. Filens överföringstid varierar beroende på storleken.

   ![Validera schema](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Överför schema](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. Konfigurera prenumerationer och aktivera attributkällan.

   Klicka **[!UICONTROL Add Subscription]** väljer du sedan den lösning som du vill prenumerera på dessa attribut. [Konfigurera prenumerationer](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) ställer in dataflödet mellan [!DNL Experience Cloud] och lösningar. Genom att aktivera attributkällan kan data flöda till prenumererade lösningar. De kundposter som du har överfört matchas med inkommande ID-signaler från webbplatsen eller tillämpningen.

   ![Konfigurera lösning](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![Aktivera](/help/main/c-target/c-visitor-profile/assets/activate.png)

   Tänk på följande begränsningar när du utför det här steget:

   * Den största filstorleken för varje överföring med HTTP-metoden är 100 MB.
   * Den största filstorleken för varje överföring med FTP-metoden är 4 GB.
   * Antal attribut som tillåts prenumerera: 5 för [!DNL Target Standard] och 200 för [!DNL Target Premium].

## Använd kundattribut i [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Du kan använda kundattribut i [!DNL Target] på följande sätt:

### Skapa målgrupper

I [!DNL Target]kan du välja ett kundattribut i [!UICONTROL Visitor Profile] när du skapar en målgrupp. Alla kundattribut har prefixet &lt; data_source_name > i listan. Kombinera dessa attribut efter behov med andra dataattribut för att skapa målgrupper.

![Målgrupp](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### Skapa profilskript med hjälp av variabler

Kundattribut kan refereras i profilskript med hjälp av format `crs.get('<Datasource Name>.<Attribute name>')`.

Profilskriptet kan användas direkt i erbjudanden för att leverera attribut som tillhör den aktuella besökaren.

### Använda mbox3rdPartyID på webbplatsen för att implementera och använda det

Pass `mbox3rdPartyId` som en parameter till den globala mbox inuti `targetPageParams()` -metod. Värdet för `mbox3rdPartyId` ska anges till det kund-ID som fanns i CSV-datafilen.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Använda Experience Cloud ID-tjänsten

Om du använder Experience Cloud ID-tjänsten måste du ange ett kund-ID och autentiseringstillstånd så att kundattribut används vid målanpassning. Mer information finns i [Kund-ID och autentiseringstillstånd](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) i *Hjälp om tjänsten Experience Cloud ID*.

Mer information om hur du använder kundattribut i [!DNL Target], se följande resurser:

* [Skapa en kundattributkälla och överför datafilen](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) i *Experience Cloud Services and Administration documentation*

## Problem som kunderna ofta stöter på {#section_BE0F70E563F64294B17087DE2BC1E74C}

Följande problem kan uppstå när du arbetar med kundattribut och [!DNL Target].

>[!NOTE]
>
>Problem 1 och 2 orsakar ungefär 60 procent av problemen i det här området. Problem 3 orsakar ungefär 30 procent av problemen. Problem 4 orsakar ungefär 5 procent av problemen. De återstående 5 % beror på diverse fel.

### Utgåva 1: Kundattribut tas bort eftersom profilen är för stor

Det finns ingen teckenbegränsning för ett visst fält i användarens profil, men om profilen blir större än 64 kB trunkeras den genom att de äldsta attributen tas bort tills profilen är under 64 kB igen.

### Utgåva 2: Attribut som inte finns med i målgruppsbiblioteket i [!DNL Target], även efter flera dagar

Det här är vanligtvis ett anslutningsproblem i pipeline. Som lösning ber du ditt kundattributsteam att publicera om flödet.

### Utgåva 3: Leveransen fungerar inte baserat på attributet

Profilen har ännu inte uppdaterats på kanten. Som lösning ber du ditt kundattributsteam att publicera om flödet.

### Utgåva 4: Implementeringsproblem

Tänk på följande implementeringsproblem:

* Besökar-ID:t skickades inte korrekt. ID skickades `mboxMCGVID` i stället för `setCustomerId`.
* Besökar-ID:t skickades korrekt, men autentiseringstillståndet angavs inte till Autentiserat.
* `mbox3rdPartyId` skickades inte korrekt.

### Utgåva 5: `mboxUpdate` inte korrekt

`mboxUpdate`  inte utfördes korrekt med `mbox3rdPartyId`.

### Utgåva 6: Kundattribut importeras inte till [!DNL Target]

Om du inte hittar kundattributsdata i Target kontrollerar du att importen gjordes inom den senaste *x* dagar *x* är målet [Livstid för besökarprofil](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) (14 dagar som standard).

## Utbildningsvideo: Överför offlinedata med kundattribut ![Självstudiemärke](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Den här videon visar hur du importerar CRM, helpdesk, försäljningspunkter och andra marknadsföringsdata offline till [!DNL Experience Cloud People] och associera det med besökare med deras kända ID:n.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
