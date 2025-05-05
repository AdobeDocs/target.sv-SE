---
keywords: css-väljare;anpassad kod;kodredigerare;Mobile Web Experience Editor
description: Lär dig hur du använder panelen Ändringar i Adobe [!DNL Target]  för att visa sidändringar och lägga till ytterligare ändringar (CSS-väljare, Mbox och anpassad kod).
title: Vilka ändringar kan jag göra på min sida?
feature: Visual Experience Composer (VEC)
exl-id: 23456a4b-9457-4f05-989e-a7c39ce17cc2
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '2207'
ht-degree: 0%

---

# Ändringar

Information om sidan [!UICONTROL Modifications] i [!DNL Adobe Target] som gör att du kan visa ändringar på sidan och lägga till ytterligare ändringar (CSS-väljare, Mbox och anpassad kod).

På sidan [!UICONTROL Modifications] visas alla ändringar som har gjorts på sidan i Visual Experience Composer (VEC). Du kan göra ytterligare ändringar genom att klicka på varje element på sidan och [välja en åtgärd](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81). Varje ändring du gör visas som en separat åtgärd eller ett separat element i listan [!UICONTROL Modifications]. Du kan också lägga till ändringar, inklusive följande ändringssätt: CSS-väljare, Mbox. och anpassad kod.

## Översikt över ändringar {#section_EE27E7572AA74397BBDED563B2B3D509}

På sidan [!UICONTROL Modifications] visas alla ändringar som har gjorts på sidan i VEC. Varje ändring du gör visas som en separat åtgärd eller ett separat element i listan [!UICONTROL Modifications].

![codeeditor_page_mods image](assets/codeeditor_page_mods.png)

Använd sidan Modifications (Ändringar) för att göra små ändringar i väljaren som Target väljer när du använder VEC för att konfigurera hur innehåll levereras. Du kan ändra antingen innehållet eller ett HTML-attribut. Du kan också redigera koden och skapa motsvarigheten till ett HTML-erbjudande i en mbox.

Använd sidan Ändringar för att:

* Visa en åtgärd som har utförts i den visuella dispositionen.

  ![codeeditor_viewÄndra bild](assets/codeeditor_viewchange.png)

* Redigera en befintlig åtgärd. Håll pekaren över den önskade ändringen och klicka sedan på ikonen **[!UICONTROL Edit]**.

  ![codeeditor_edit image](assets/codeeditor_edit.png)

  Gör ändringarna.

  ![codeeditor_changeChange1 image](assets/codeeditor_changechange1.png)

* Ta bort en befintlig åtgärd. Håll pekaren över den önskade ändringen och klicka sedan på ikonen **[!UICONTROL Delete]**.

  ![codeditor_delete image](assets/codeditor_delete.png)

* Lägg till en ny ändring. Klicka på **[!UICONTROL Add Modification]** eller ikonen + och ange sedan dina ändringar enligt beskrivningen nedan.

  ![codeeditor_new image](assets/codeeditor_new.png)

  Observera att när en ändring har skapats visas en +-ikon längst upp på panelen Ändringar i stället för knappen Lägg till ändring längst ned på panelen.

* Docka ändringspanelen lodrätt längs sidan av målgränssnittet eller vågrätt längst ned. Klicka på ikonen [!UICONTROL Dock] för att växla mellan de två inställningarna.

  ![codeditor_dock_image](assets/codeditor_dock.png)

  I följande bild visas panelen Ändringar som är dockad längst ned på skärmen:

  ![codeeditor_dock_bottom image](assets/codeeditor_dock_bottom.png)

## Lägg till ändringar {#section_C7ABCD5731A048CB8F90EDC31A32EDF9}

1. Om du vill visa sidan [!UICONTROL Modifications] för en vald upplevelse klickar du på ikonen **[!UICONTROL Modifications]** &lt;/> i VEC.

   ![codeeditor_icon_big image](assets/codeeditor_icon_big.png)

   >[!NOTE]
   >
   >Skapa eller redigera ett erbjudande från HTML om du vill öppna panelen Ändringar i den formulärbaserade Experience Composer. Mer information finns i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E).

   Sidan [!UICONTROL Modifications] öppnas och skärmen delas mellan det visuella läget till vänster och panelen Ändringar till höger. Klicka på ikonen [!UICONTROL Dock] om du vill docka panelen Ändringar lodrätt längs sidan av målgränssnittet eller vågrätt längst ned. Observera att Experience A i följande bild inte har några tidigare ändringar.

   ![codeeditor_page image](assets/codeeditor_page.png)

   Experience B visar de tidigare ändringarna på panelen [!UICONTROL Modifications] till höger.

   ![codeeditor_page_mods image](assets/codeeditor_page_mods.png)

1. Så här lägger du till en ändring:

   * Om inga tidigare ändringar av upplevelsen har gjorts klickar du på knappen **[!UICONTROL Add Modification]** längst ned på panelen [!UICONTROL Modifications] till höger.
   * Om det finns tidigare ändringar för upplevelsen klickar du på +-ikonen längst upp på panelen [!UICONTROL Modifications] till höger.

   På panelen Ändringar visas:

   ![codeeditor_page_mods_add image](assets/codeeditor_page_mods_add.png)

1. Välj önskad typ i listrutan **[!UICONTROL Modifications Type]**:

   | Ändringstyp | Information |
   |--- |--- |
   | CSS-väljare | I rutan CSS-elementväljare anger du önskat CSS-element som du vill ändra, väljer en åtgärdstyp ( Ange innehåll eller Ange attribut) och fyller sedan i den obligatoriska informationen och det önskade innehållet. |
   | Mbox | Ange mbox-namnet och önskat innehåll.<p>**Obs!**: Mboxes stöds inte längre i VEC på sidor som använder at.js 2.*x*.<p>Som tillfälliga lösningar:<ul><li>Om at.js 2 används.*x*, lägg till en CSS-väljarändring i stället för en Mbox-ändring och lägg till innehållet i väljaren som din mbox använde. </li><li>Använd formulärbaserade aktiviteter (fungerar med mboxes och at.js 1.)*x* och at.js 2.*x*).</li><li>Använd at.js 1.*x* i VEC.</li></ul> |
   | Egen kod | Ange ett valfritt namn, markera eller avmarkera kryssrutan [!UICONTROL Add Code in the `<HEAD>` Avsnitt &#x200B;] efter behov och lägg sedan till din egen kod.<p>Om du väljer [!UICONTROL Add Code in the `<HEAD>` Avsnitt &#x200B;] läggs anpassad kod till i avsnittet `<head>` och körningen väntar inte på body- eller page-load-händelser. Lägg endast till `<script>`- och `<style>`-element. Om du lägger till `<div>`-taggar och andra element kan det leda till att återstående `<head>`-element visas i `<body>`. Om du använder at.js kommer alla erbjudanden att levereras asynkront.<p> Om du avmarkerar [!UICONTROL Add Code in the `<HEAD>` Section &#x200B;] körs anpassad kod omedelbart efter taggen `<body>`. Lägg all kod i en enda `<div>` för att bevara DOM-strukturen. Om du använder at.js kommer alla erbjudanden att levereras asynkront.<p>Om HTML för `<BODY>` innehåller `<SCRIPT>` och `<DIV>` läggs `<DIV>` till i `<BODY>` och `<SCRIPT>` körs i `<HEAD>`. Dessutom läggs `<SCRIPT>` som läser in en extern fil till i `<HEAD>`.<p>**Obs!**: Skript körs asynkront. Det innebär att du till exempel inte kan använda `document.write` eller liknande skriptmetoder.<p>Anpassad kod ger ett icke-visuellt gränssnitt för att visa, redigera och lägga till nya åtgärder i VEC, den formulärbaserade Experience Composer och HTML erbjuder redigerare. Panelen innehåller en kodvy med en upplevelse som hjälper dig att skapa mer komplexa upplevelser, finjustera befintliga upplevelser och felsöka problem.<p>Anpassad kod är avsedd för avancerade användare som känner sig bekväma med HTML, JavaScript och CSS. I kodvyn kan du finjustera eller finjustera ändringar eller åtgärda väljarproblem. Den kan också användas för att lägga till ny anpassad kod och åtgärder. Du kan lägga till mer än en anpassad kod och eventuellt namnge varje anpassad kod.<p>**Obs!**: Anpassad kod är för närvarande endast tillgänglig för A/B- och Experience Targeting-aktiviteter (XT). Anpassad kod inaktiveras för övertäckning och om ett omdirigeringserbjudande används.<p>Anpassad kod har stöd för följande användningsexempel:<ul><li>Lägg till anpassade JavaScript, HTML eller CSS som ska köras högst upp på sidan</li><li>Visa eller redigera koden som genererats av VEC efter att ha gjort ändringar</li><li>Ange HTML-innehåll för en väljare (endast CSS-väljare)</li><li>Ange ett attribut för ett HTML-element</li><li>Lägg till erbjudandeinnehåll som ska levereras i en regional mbox</li><li>Växla på DOM-klar, med jQuery</li><li>Växla på DOM-klar, ingen jquery (stöder inte Internet Explorer 8)</li><li>Växla med DOM-avsökning via plugin-programmet &quot;elementOnLoad&quot;</li><li>Anpassad omdirigering</li></ul>Anpassad kod ger:<ul><li>Radnummer ger bättre användbarhet.</li><li>Syntaxmarkering hjälper dig att undvika felaktig syntax för erbjudanden från HTML.</li><li>Möjlighet att skapa flera anpassade koder och ange ett valfritt namn för var och en. Om du skapar flera anpassade koder blir det enklare att felsöka i framtiden. I stället för att skapa en enda anpassad kod för att utföra flera ändringar kan du skapa en separat anpassad kod för varje ändring med ett beskrivande namn. Om du har separata anpassade koder blir ändringarna mer modulära och hanterbara. Observera att det inte är säkert att flera anpassade koder körs i den sekvens i vilken de skapades.</li></ul>Panelen Ändringar delar upp skärmen mellan det visuella läget och kodläget. Båda lägena är synkroniserade. Alla ändringar som görs visuellt har en motsvarande rad i kodvyn. På samma sätt visas alla ändringar som implementeras i kodvyn i den visuella upplevelsen. Om du klickar på en rad i kodvyn markeras motsvarande element på den visuella sidan.<p>Anpassad kod stöder HTML, skript och format. All giltig HTML-kod eller skript kan läggas till eller redigeras. |

1. Lägg till ytterligare ändringar efter behov.

## Användningsexempel för anpassad kod {#section_26CB3360097D400FB02E20AE5FDBA352}

Panelen **[!UICONTROL Custom Code]** innehåller kod som körs i början av sidinläsningen.

Du kan köra JavaScript-koden i taggen `<head>`. Kodkörningen väntar inte på att taggen `<body>` ska finnas i DOM.

Väljare för efterföljande visuella åtgärder beror på vilka HTML-element som läggs till på den här fliken.

Panelen Anpassad kod används ofta för att lägga till JavaScript eller CSS högst upp på sidan.

![codeeditor_custom image](assets/codeeditor_custom.png)

Använd fliken **[!UICONTROL Custom Code]** för att:

* Använd JavaScript inline eller länka till en extern JavaScript-fil

  Om du till exempel vill ändra ett elements färg:

  ```javascript
  <script type="text/javascript"> 
  document.getElementById("element_id").style.color = "blue"; 
  </script> 
  ```

* Konfigurera en infogad formatmall eller länka till en extern formatmall

  Så här definierar du en klass för ett övertäckningselement:

  ```html
  <style> 
  .overlay 
  { position: absolute; top:0; left: 0; right: 0; bottom: 0; background: red; } 
  </style> 
  ```

* Lägga till HTML-fragment för att definiera nya element

  Använd till exempel följande HTML-kodfragment för att skapa en övertäckning `<div>` med den CSS-klass som definieras ovan:

  ```html
  <div class="overlay"></div>
  ```

* Växla på DOM-klar, med jQuery

  I följande exempel där JQuery används förutsätts att kundens webbplats har jQuery tillgängligt på sidan när [!DNL Target] utför erbjudandena.

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  jQuery( document ).ready(function() { 
      jQuery("#default_content").html( "<span style='color:red'>Hello <strong>Again</strong></span>" ); 
      jQuery("#default_content").css("visibility","visible"); 
  }); 
  </script> 
  ```

* Växla på DOM-klar, ingen jQuery (stöder inte Internet Explorer 8)

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  document.addEventListener("DOMContentLoaded", function(event) {  
      document.getElementById("default_content").innerHTML = "<span style='color:red'>Hello <strong>Again</strong></span>"; 
      document.getElementById("default_content").style.visibility="visible"; 
  }); 
  </script> 
  ```

* Anpassad omdirigering som skickar befintliga parametrar, `s_tnt` param (för äldre integration till Analytics), referensparam och mbox-session

  ```javascript
  <style type="text/css">body{display:none!important;}</style> 
  <script type="text/javascript"> 
   var qs='';window.location.search?qs=window.location.search+'&':qs='?'; 
   window.location.replace('//www.mywebsite.com/'+qs+'s_tnt=${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}&s_tntref='+encodeURIComponent(document.referrer)+'&mboxSession='+mboxFactoryDefault.getSessionId().getId()+''+window.location.hash+''); 
  </script> 
  ```

* Lägg till Adobe Target Experience Templates för användning i anpassad kod. Target Experience Templates är förkodade exempel med konfigurerbara indata som används för att köra vanliga marknadsföringsfall. Dessa Experience Templates är kostnadsfria för utvecklare och marknadsförare som en startpunkt för vanliga användningsfall, antingen via VEC eller den formulärbaserade Experience Composer. Användningsexempel är ljusbord, karuseller, räkningar med mera.

  Mer information finns i [Experience Templates](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/experience-templates.md#concept_109BBD7EABC04DD39E6B7B1687786652).

## Bästa praxis för anpassad kod {#section_10DFFD9FB92A43C1BB444A45E0272B28}

**Radbryt alltid den anpassade koden i ett element.**

Exempel:

```html
<div id="custom-code"> 
// My Code goes here 
</div>
```

Om några ändringar behövs gör du ändringarna i behållaren.

Om du inte behöver den anpassade koden längre lämnar du den här behållaren tom, men tar inte bort den. Detta säkerställer att andra upplevelseändringar inte påverkas.

**Använd inte element-ID:t &quot;CDQID&quot; för ändringar av sidan som har gjorts i kodredigeraren.**

Målet använder ett nytt element-ID med värdet &quot;CDQID&quot; för alla element på sidan som ändras av Target. Eftersom detta ID används av Target bör det inte användas för ytterligare ändringar eller justeringar i kodredigeraren.

**Utför inte document.write-åtgärder i egna kodskript.**

Skript körs asynkront. Detta medför ofta att `document.write` åtgärder visas på fel plats på sidan. Du bör inte använda `document.write` i skript som skapas i anpassad kod.

**Om du skapar ett element och sedan ändrar det ska du inte ta bort det ursprungliga elementet.**

Varje ändring skapar ett nytt element på panelen Ändringar. Eftersom den andra åtgärden ändrar element 1 har den åtgärden inte längre något att ändra om du tar bort element 1, så ändringen fungerar inte längre. Mer information finns i Felsökning nedan.

**Var försiktig om du använder den anpassade kodfunktionen för två aktiviteter som har samma URL som mål.**

Om du använder den anpassade kodfunktionen för två aktiviteter som har samma URL som mål, kommer JavaScript att matas in på sidan från båda aktiviteterna. Målet bestämmer automatiskt ordningen för levererat innehåll. Kontrollera att koden inte är beroende av placering. Det är upp till dig att se till att det inte finns några konflikter i koden.

## Felsökning av anpassad kod {#section_6C965CBC31C348D7AA5B57B63DAB9E7F}

**Anpassad kod körs inte när `triggerView` används.**

Anpassade koderbjudanden i VEC återges inte om när `triggerView()` anropas med `{page: false}` som alternativ.

**Jag fick en varning om att en åtgärd inte kan användas på grund av strukturella ändringar på en sida. Vad betyder detta?**

Det här meddelandet anger att sidans struktur har ändrats sedan aktiviteten senast sparades.

De saknade väljarna kan nås i bläddringsläge. Vi rekommenderar att du tar bort och sedan återskapar varje upplevelse så att innehållet ser ut som du tänkt dig, vilket visas i varningsmeddelandet.

![code_editor_2 bild](assets/code_editor_2.png)

***När jag tar bort ett element visas ett varningsmeddelande som säger&quot;Om du tar bort den här åtgärden kan det påverka efterföljande åtgärder&quot;. Vad betyder detta?***

Om du till exempel har vidtagit två åtgärder:

* En klass har lagts till i Element 1
* HTML för element 1 har redigerats

Varje ändring skapar ett nytt element på panelen Ändringar. Eftersom den andra åtgärden ändrar element 1 har den andra åtgärden inte längre något att ändra om du tar bort element 1, så ändringen fungerar inte längre.

Om du lägger till ett element med text och sedan redigerar elementet med annan text i en separat åtgärd, visas båda åtgärderna som separata element på panelen Ändringar. När du redigerade elementet skapade du ett nytt element som ändrar det ursprungliga elementet som du skapade och som innehåller den redigerade texten. Om du sedan tar bort det ursprungliga elementet kommer den redigerade texten inte att kunna hitta det element som redigerades och kommer inte att visas. Det andra elementet finns kvar i listan med element, men det påverkar inte sidan eftersom elementet det ändras inte längre finns.

***Ett element som jag skapade med `document.write` i ett skript visas inte där jag förväntade mig det.***

Skript körs asynkront. Detta medför ofta att `document.write` åtgärder visas på fel plats på sidan. Adobe rekommenderar inte att du använder `document.write` i skript som skapas i den anpassade koden.

***Min JavaScript visar fel i den anpassade koden.***

Alla infogade JavaScript som inte är en giltig JavaScript visar fel i den anpassade koden.

***Jag kan inte ångra en ändring i min egen kod.***

Ångra stöds för närvarande inte för redigerings- och borttagningsåtgärder från panelen Ändringar och i anpassad kod. Om du ångrar någon av dessa åtgärder kan det leda till att upplevelsen i VEC inte överensstämmer med de faktiska åtgärder som visas i den anpassade koden. Åtgärderna i den anpassade koden är emellertid i rätt läge och påverkar inte leveransen. Det här är ett gränssnittsproblem. Om du vill uppdatera upplevelsen sparar du den och öppnar den igen, eller går till nästa steg och går tillbaka. Båda dessa åtgärder läser in upplevelsen på nytt, så den ser ut som förväntat och överensstämmer med åtgärderna på panelen Ändringar.

**Anpassad kod ger inte det förväntade resultatet i Internet Explorer 8.**

Target har inte längre stöd för IE8.
