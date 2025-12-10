---
keywords: kundrelationshantering;kundposttjänst;crm;mbox3rdpartyid;kundattribut;målinriktning;csv;crm;adobe experience cloud cloud personer
description: Lär dig hur du använder företagskunddata från en CRM-databas (customer relationship management) för innehåll som är riktat i  [!DNL Adobe Target].
title: Vad är kundattribut och hur använder jag dem?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 0b17b61bb60162af6bc35246219355077ab6bf44
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 0%

---

# Kundattribut

Information om hur du använder företagskunddata från CRM-databaser (Customer Relationship Management) för innehåll i [!DNL Adobe Target] med hjälp av kundattribut i tjänsten [!DNL Adobe Experience Cloud People].

Företagskunddata som samlas in via flera olika källor och lagras i CRM-databaser kan användas i [!DNL Target] för att leverera det mest relevanta innehållet till kunder strategiskt, med särskild inriktning på återkommande kunder. Målgrupper och kundattribut i tjänsten [!DNL People] (tidigare Profiler och Publiker) sammanför datainsamling och analys med testning och optimering, vilket gör data och insikter användbara.

## Översikt över kundattribut {#section_B4099971FA4B48598294C56EAE86B45A}

[Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) i tjänsten [!DNL People] är en del av [!DNL Adobe Experience Cloud] och ger företag ett verktyg för att överföra kunddata till plattformen [!DNL Experience Cloud].

Data som är inskrivna i [!DNL Experience Cloud] är tillgängliga för alla [!DNL Experience Cloud]-arbetsflöden. [!DNL Target] använder dessa data för att returnera kunder baserat på attribut. [!DNL Adobe Analytics] använder dessa attribut och kan användas för analys och segmentering.

![crs-exempel](/help/main/c-target/c-visitor-profile/assets/crs.png)

Tänk på följande information när du arbetar med kundattribut och [!DNL Target]:

* Du måste uppfylla vissa krav innan du kan använda funktionen [!UICONTROL Customer Attributes] i tjänsten [!DNL People]. Mer information finns i&quot;Krav för överföring av kundattribut&quot; i [Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) i *Experience Cloud-gränssnittet och -administrationsguiden*.
* Tänk på begränsningarna för filöverföringar, som beskrivs i [Kundattributdatafiler och -källor](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en) i *Experience Cloud-gränssnittet och -administrationsguiden*. Bästa praxis:

   * Överför enstaka stora filer (inom de [gränser som anges](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en)). Enstaka stora filer är att föredra framför flera mindre filer.
   * Om du måste dela upp överföringen i flera filer måste du se till att filerna bearbetas fullständigt innan du skickar in nya filer. Se till att alla filer i en grupp bearbetas fullständigt innan du skickar in nästa fil i gruppen.

* [!DNL Adobe] garanterar inte att 100 % av kundattributdata (besökarprofil) från CRM-databaser kommer att överföras till [!DNL Experience Cloud] och därför vara tillgängliga för användning i [!DNL Target]. I den aktuella designen finns det en möjlighet att en liten andel data (upp till 0,1 % av stora tillverkningssatser) inte tas med.
* Livslängden för kundattributdata som importeras från [!DNL Experience Cloud] till [!DNL Target] beror på besökarprofilens livstid, som är 14 dagar som standard. Mer information finns i [Livstid för besökarprofil](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Om parametrarna `vst.*` är det enda som identifierar besökaren, kommer den befintliga autentiserade profilen inte att hämtas så länge `authState` är OAUENTICATED (0). Profilen spelas bara upp om `authState` ändras till AUTENTISERAD (1).

  Om parametern `vst.myDataSource.id` till exempel används för att identifiera besökaren (där `myDataSource` är datakällalias) och det inte finns något MCID eller tredje parts-ID, hämtar parametern `vst.myDataSource.authState=0` inte profilen som kan ha skapats med en import av kundattribut. Om det önskade beteendet är att hämta den autentiserade profilen måste `vst.myDataSource.authState` ha värdet 1 (AUTENTISERAD).

* Du kan inte skicka följande tecken i `mbox3rdPartyID`: plustecken (+) och snedstreck (/).

## Öppna kundattribut i tjänsten Kontakter

1. I [!DNL Experience Cloud] klickar du på menyikonen ( ![menyikon](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ) och sedan på **[!UICONTROL People]**.

   ![Personer](/help/main/c-target/c-visitor-profile/assets/people.png)

1. Klicka på **[!UICONTROL Customer Attributes]**.

   ![Fliken Kundattribut](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Arbetsflöde för kundattribut för [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Utför följande steg för att använda CRM-data i [!DNL Target], enligt bilden nedan:

![crm-arbetsflöde](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

Detaljerade instruktioner för hur du utför följande åtgärder finns i [Skapa en kundattributkälla och överför datafilen](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) i *Experience Cloud-gränssnittet och administrationsguiden*.

1. Skapa en datafil.

   Exportera kunddata från CRM till CSV-format för att skapa en CSV-fil. Alternativt kan en zip- eller gzip-fil skapas för överföring. Kontrollera att den första raden i CSV-filen är rubriken och att alla rader (kunddata) har samma antal poster.

   Följande bild visar ett exempel på en företagsdatafil:

   ![crs sample](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   Följande bild visar ett exempel på en CSV-fil för en företagskund:

   ![csv-exempel](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Skapa attributkällan och överför datafilen.

   Ange namn och beskrivning för datakällan och alias-ID:t. Alias-ID är ett unikt ID som ska användas i kundattributskoden i `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >Datakällans namn och attributnamnet får inte innehålla en punkt.

   Datafilen måste uppfylla kraven för filöverföring och får inte överstiga 100 MB. Om filen är för stor, eller om du har data som måste överföras regelbundet, kan du FTP-överföra filerna i stället.

   * **HTTPS:** Du kan dra och släppa CSV-datafilen eller klicka på **[!UICONTROL Browse]** om du vill överföra den från filsystemet.
   * **FTP:** Klicka på FTP-länken för att [överföra filen via FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). Det första steget är att ange ett lösenord för den FTP-server som tillhandahålls av Adobe. Ange lösenordet och klicka sedan på **[!UICONTROL Done]**.

   Överför nu CSV-/ZIP-/GZIP-filen till FTP-servern. När den här filöverföringen har slutförts skapar du en fil med samma namn och ett `.fin`-tillägg. Överför den här tomma filen till servern. Detta anger att överföringen är slut och att [!DNL Experience Cloud] börjar bearbeta datafilen.

1. Validera schemat.

   Med valideringsprocessen kan du mappa visningsnamn och beskrivningar till överförda attribut (strängar, heltal, tal och så vidare). Mappa varje attribut till rätt datatyp, visningsnamn och beskrivning.

   Klicka på **[!UICONTROL Save]** när schemavalideringen är klar. Filens överföringstid varierar beroende på storleken.

   ![Verifiera schema](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Överför schema](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. Konfigurera prenumerationer och aktivera attributkällan.

   Klicka på **[!UICONTROL Add Subscription]** och välj sedan lösningen för att prenumerera på dessa attribut. [Konfigurera prenumerationer](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) ställer in dataflödet mellan [!DNL Experience Cloud] och lösningar. Genom att aktivera attributkällan kan data flöda till prenumererade lösningar. De kundposter som du har överfört matchas med inkommande ID-signaler från webbplatsen eller tillämpningen.

   ![Konfigurera lösning](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![Aktivera](/help/main/c-target/c-visitor-profile/assets/activate.png)

   Tänk på följande begränsningar när du utför det här steget:

   * Den största filstorleken för varje överföring med HTTP-metoden är 100 MB.
   * Den största filstorleken för varje överföring med FTP-metoden är 4 GB.
   * Antal attribut som tillåts prenumerera: 5 för [!DNL Target Standard] och 200 för [!DNL Target Premium].

## Använd kundattribut i [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Du kan använda kundattribut i [!DNL Target] på följande sätt:

### Skapa målgrupper

I [!DNL Target] kan du välja ett kundattribut i avsnittet [!UICONTROL Visitor Profile] när du skapar en målgrupp. Alla kundattribut har prefixet &lt; data_source_name > i listan. Kombinera dessa attribut efter behov med andra dataattribut för att skapa målgrupper.

![Målgrupp](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### Skapa profilskript med hjälp av variabler

Kundattribut kan refereras i profilskript med formatet `crs.get('<Datasource Name>.<Attribute name>')`.

Profilskriptet kan användas direkt i erbjudanden för att leverera attribut som tillhör den aktuella besökaren.

### Använd mbox3rdPartyID på webbplatsen för att implementera och använda det

Skicka `mbox3rdPartyId` som en parameter till den globala mbox inuti metoden `targetPageParams()`. Värdet för `mbox3rdPartyId` ska anges till det kund-ID som fanns i CSV-datafilen.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Använda Experience Cloud ID-tjänsten

Om du använder tjänsten Experience Cloud ID måste du ange ett kund-ID och autentiseringstillstånd så att kundattribut används vid målanpassning. Mer information finns i [Kund-ID:n och autentiseringstillstånd](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) i handboken *Experience Cloud ID Service*.

Mer information om hur du använder kundattribut i [!DNL Target] finns i följande resurser:

* [Skapa och överför kundattributdata](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) i *Experience Cloud-gränssnittet och administrationsguiden*

## Problem som kunderna ofta stöter på {#section_BE0F70E563F64294B17087DE2BC1E74C}

Följande problem kan uppstå när du arbetar med kundattribut och [!DNL Target].

>[!NOTE]
>
>Problem 1 och 2 orsakar ungefär 60 procent av problemen i det här området. Problem 3 orsakar ungefär 30 procent av problemen. Problem 4 orsakar ungefär 5 procent av problemen. De återstående 5 % beror på diverse fel.

### Problem 1: Kundattribut tas bort eftersom profilen är för stor

Det finns ingen teckenbegränsning för ett visst fält i användarens profil, men om profilen blir större än 64 kB trunkeras den genom att de äldsta attributen tas bort tills profilen är under 64 kB igen.

### Utgåva 2: Attribut som inte finns med i målgruppsbiblioteket i [!DNL Target], även efter flera dagar

Det här är vanligtvis ett anslutningsproblem i pipeline. Som lösning ber du ditt kundattributsteam att publicera om flödet.

### Problem 3: Leveransen fungerar inte baserat på attributet

Profilen har ännu inte uppdaterats på kanten. Som lösning ber du ditt kundattributsteam att publicera om flödet.

### Problem 4: Implementeringsproblem

Tänk på följande implementeringsproblem:

* Besökar-ID:t skickades inte korrekt. ID skickades i `mboxMCGVID` i stället för `setCustomerId`.
* Besökar-ID:t skickades korrekt, men autentiseringstillståndet angavs inte till Autentiserat.
* `mbox3rdPartyId` skickades inte korrekt.

### Utgåva 5: `mboxUpdate` har inte utförts korrekt

`mboxUpdate` utfördes inte korrekt med `mbox3rdPartyId`.

### Problem 6: Kundattribut importeras inte till [!DNL Target]

Om du inte kan hitta kundattributsdata i Target kontrollerar du att importen inträffade inom de *x* dagar där *x* är målvärdet för [besökarprofilens livstid](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) (14 dagar som standard).

## Utbildningsvideo: Överför offlinedata med kundattribut ![Självstudiekurs](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

I den här videon visas hur du importerar CRM, helpdesk, försäljningspunkter och andra marknadsföringsdata offline till tjänsten [!DNL Experience Cloud People] och associerar dem med besökare med deras kända ID:n.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
