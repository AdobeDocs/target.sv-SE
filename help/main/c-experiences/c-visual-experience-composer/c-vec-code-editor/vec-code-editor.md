---
keywords: css-väljare;egen kod;kodredigerare;Mobile Web Experience Editor
description: Lär dig hur du använder panelen Ändringar i Adobe [!DNL Target] om du vill visa sidändringar och lägga till ytterligare ändringar (CSS-väljare, Mbox och anpassad kod).
title: Vilka ändringar kan jag göra på min sida?
feature: Visual Experience Composer (VEC)
exl-id: 23456a4b-9457-4f05-989e-a7c39ce17cc2
source-git-commit: 23d4ce21d6c262d36e406b149f93781a1a37ff8b
workflow-type: tm+mt
source-wordcount: '2101'
ht-degree: 0%

---

# Ändringar

Information om [!UICONTROL Modifications] sida in [!DNL Adobe Target] som gör att du kan visa ändringar på sidan och lägga till ytterligare ändringar (CSS-väljare, Mbox och anpassad kod).

På sidan Ändringar visas alla ändringar som har gjorts på sidan i Visual Experience Composer (VEC). Du kan göra ytterligare ändringar genom att klicka på varje element på sidan och [välja en åtgärd](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81). Varje ändring du gör visas som en separat åtgärd eller ett separat element i [!UICONTROL Modifications] lista. Du kan också lägga till ändringar, bland annat följande ändringstyper: CSS-väljare, Mbox. och anpassad kod.

## Översikt över ändringar {#section_EE27E7572AA74397BBDED563B2B3D509}

The [!UICONTROL Modifications] visas alla ändringar som har gjorts på sidan i VEC. Varje ändring du gör visas som en separat åtgärd eller ett separat element i [!UICONTROL Modifications] lista.

![](assets/codeeditor_page_mods.png)

Använd sidan Modifications (Ändringar) för att göra små ändringar i väljaren som Target väljer när du använder VEC för att konfigurera hur innehåll levereras. Du kan ändra antingen innehållet eller ett HTML-attribut. Du kan också redigera koden och skapa motsvarigheten till ett HTML-erbjudande i en mbox.

Använd sidan Ändringar för att:

* Visa en åtgärd som har utförts i den visuella dispositionen.

   ![](assets/codeeditor_viewchange.png)

* Redigera en befintlig åtgärd. Håll pekaren över den önskade ändringen och klicka sedan på **[!UICONTROL Edit]** ikon.

   ![](assets/codeeditor_edit.png)

   Gör ändringarna.

   ![](assets/codeeditor_changechange1.png)

* Ta bort en befintlig åtgärd. Håll pekaren över den önskade ändringen och klicka sedan på **[!UICONTROL Delete]** ikon.

   ![](assets/codeditor_delete.png)

* Lägg till en ny ändring. Klicka **[!UICONTROL Add Modification]** eller ikonen + anger du ändringarna enligt nedan.

   ![](assets/codeeditor_new.png)

   Observera att när en ändring har skapats visas en +-ikon längst upp på panelen Ändringar i stället för knappen Lägg till ändring längst ned på panelen.

* Docka ändringspanelen lodrätt längs sidan av målgränssnittet eller vågrätt längst ned. Klicka på [!UICONTROL Dock] för att växla mellan de två inställningarna.

   ![](assets/codeditor_dock.png)

   I följande bild visas panelen Ändringar som är dockad längst ned på skärmen:

   ![](assets/codeeditor_dock_bottom.png)

## Lägg till ändringar {#section_C7ABCD5731A048CB8F90EDC31A32EDF9}

1. Visa [!UICONTROL Modifications] för en vald upplevelse, i VEC, klicka på **[!UICONTROL Modifications]** &lt;/>-ikon.

   ![](assets/codeeditor_icon_big.png)

   >[!NOTE]
   >
   >Skapa eller redigera ett erbjudande från HTML om du vill öppna panelen Ändringar i den formulärbaserade Experience Composer. Mer information finns i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E).

   The [!UICONTROL Modifications] sidan öppnas och skärmen delas mellan det visuella läget till vänster och panelen Ändringar till höger. Klicka på [!UICONTROL Dock] -ikonen om du vill docka panelen Ändringar lodrätt längs sidan av målgränssnittet eller vågrätt längst ned. Observera att Experience A i följande bild inte har några tidigare ändringar.

   ![](assets/codeeditor_page.png)

   Experience B visar de tidigare ändringarna i [!UICONTROL Modifications] till höger.

   ![](assets/codeeditor_page_mods.png)

1. Så här lägger du till en ändring:

   * Om inga tidigare ändringar av upplevelsen har gjorts klickar du på **[!UICONTROL Add Modification]** längst ned på [!UICONTROL Modifications] till höger.
   * Om det finns tidigare ändringar för upplevelsen klickar du på +-ikonen högst upp i [!UICONTROL Modifications] till höger.

   På panelen Ändringar visas:

   ![](assets/codeeditor_page_mods_add.png)

1. Från **[!UICONTROL Modifications Type]** väljer du typ:

   | Ändringstyp | Detaljer |
   |--- |--- |
   | CSS-väljare | I rutan CSS-elementväljare anger du önskat CSS-element som du vill ändra, väljer en åtgärdstyp ( Ange innehåll eller Ange attribut) och fyller sedan i den obligatoriska informationen och det önskade innehållet. |
   | Mbox | Ange mbox-namnet och önskat innehåll.<br>**Anteckning**: Mboxes stöds inte längre i VEC på sidor som använder at.js 2.*x*.<br>Som tillfälliga lösningar:<ul><li>Om at.js 2 används.*x* lägger du till en CSS-väljarändring i stället för en Mbox-ändring och lägger till innehållet i väljaren som din mbox använde. </li><li>Använd formulärbaserade aktiviteter (fungerar med mboxes och at.js 1.)*x* och at.js 2.*x*).</li><li>Använd at.js 1.*x* i VEC.</li></ul> |
   | Egen kod | Ange ett valfritt namn, markera eller avmarkera [!UICONTROL Add Code in the `<HEAD>` Avsnitt] markera kryssrutan efter behov och lägg sedan till din egen kod.<br>Om du väljer [!UICONTROL Add Code in the `<HEAD>` Avsnitt]läggs egen kod till i  `<head>`  -avsnittet och dess körning väntar inte på body- eller page-load-händelser. Lägg endast till `<script>` och  `<style>` -element. Lägger till  `<div>`  taggar och andra element kan orsaka resterande  `<head>`  element som ska visas i  `<body>`. Om du använder at.js kommer alla erbjudanden att levereras asynkront.<br> Om du avmarkerar [!UICONTROL Add Code in the `<HEAD>` Avsnitt], egen kod körs omedelbart efter `<body>` -tagg. Radbryt all kod i en enda `<div>` för att bevara DOM-strukturen. Om du använder at.js kommer alla erbjudanden att levereras asynkront.<br>**Anteckning**: Skript körs asynkront. Det innebär att du inte kan använda `document.write`  eller liknande skriptmetoder.<br>Anpassad kod ger ett icke-visuellt gränssnitt för att visa, redigera och lägga till nya åtgärder i VEC, den formulärbaserade Experience Composer och HTML erbjuder redigerare. Panelen innehåller en kodvy med en upplevelse som hjälper dig att skapa mer komplexa upplevelser, finjustera befintliga upplevelser och felsöka problem.<br>Anpassad kod är avsedd för avancerade användare som känner sig bekväma med HTML, JavaScript och CSS. I kodvyn kan du finjustera eller finjustera ändringar eller åtgärda väljarproblem. Den kan också användas för att lägga till ny anpassad kod och åtgärder. Du kan lägga till mer än en anpassad kod och eventuellt namnge varje anpassad kod.<br>**Anteckning**: Anpassad kod är för närvarande endast tillgänglig för A/B- och Experience Targeting-aktiviteter (XT). Anpassad kod inaktiveras för övertäckning och om ett omdirigeringserbjudande används.<br>Anpassad kod har stöd för följande användningsexempel:<ul><li>Lägg till anpassad JavaScript, HTML eller CSS som ska köras högst upp på sidan</li><li>Visa eller redigera koden som genererats av VEC efter att ha gjort ändringar</li><li>Ange HTML-innehåll för en väljare (endast CSS-väljare)</li><li>Ange ett attribut för ett HTML-element</li><li>Lägg till erbjudandeinnehåll som ska levereras i en regional mbox</li><li>Växla på DOM-klar med jQuery</li><li>Växla på DOM-klar, ingen jquery (stöder inte Internet Explorer 8)</li><li>Växla med DOM-avsökning via plugin-programmet &quot;elementOnLoad&quot;</li><li>Anpassad omdirigering</li></ul>Anpassad kod ger:<ul><li>Radnummer ger bättre användbarhet.</li><li>Syntaxmarkering hjälper dig att undvika felaktig syntax för erbjudanden från HTML.</li><li>Möjlighet att skapa flera anpassade koder och ange ett valfritt namn för var och en. Om du skapar flera anpassade koder blir det enklare att felsöka i framtiden. I stället för att skapa en enda anpassad kod för att utföra flera ändringar kan du skapa en separat anpassad kod för varje ändring med ett beskrivande namn. Om du har separata anpassade koder blir ändringarna mer modulära och hanterbara. Observera att det inte är säkert att flera anpassade koder körs i den sekvens i vilken de skapades.</li></ul>Panelen Ändringar delar upp skärmen mellan det visuella läget och kodläget. Båda lägena är synkroniserade. Alla ändringar som görs visuellt har en motsvarande rad i kodvyn. På samma sätt visas alla ändringar som implementeras i kodvyn i den visuella upplevelsen. Om du klickar på en rad i kodvyn markeras motsvarande element på den visuella sidan.<br>Anpassad kod stöder HTML, skript och format. All giltig HTML-kod eller skript kan läggas till eller redigeras. |

1. Lägg till ytterligare ändringar efter behov.

## Användningsexempel för anpassad kod {#section_26CB3360097D400FB02E20AE5FDBA352}

The **[!UICONTROL Custom Code]** -panelen innehåller kod som körs i början av sidinläsningen.

Du kan köra JavaScript-koden i `<head>` -tagg. Kodkörningen väntar inte på `<body>` -tagg som ska finnas i DOM.

Väljare för efterföljande visuella åtgärder beror på vilka HTML-element som läggs till på den här fliken.

Panelen Egen kod används ofta för att lägga till JavaScript eller CSS högst upp på sidan.

![](assets/codeeditor_custom.png)

Använd **[!UICONTROL Custom Code]** till:

* Använd intern JavaScript-kod eller länka till en extern JavaScript-fil

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

   Använd till exempel följande HTML-utdrag för att skapa en övertäckning `<div>` med den CSS-klass som definieras ovan:

   ```html
   <div class="overlay"></div>
   ```

* Växla på DOM-klar med jQuery

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

* Anpassad omdirigering som skickar befintliga parametrar. `s_tnt` param (för äldre integrering med Analytics), referensparam och mbox-session

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

**Använd inte element-ID:t &quot;CDQID&quot; för ändringar av sidan som görs i kodredigeraren.**

Målet använder ett nytt element-ID med värdet &quot;CDQID&quot; för alla element på sidan som ändras av Target. Eftersom detta ID används av Target bör det inte användas för ytterligare ändringar eller justeringar i kodredigeraren.

**Utför inte document.write-åtgärder i egna kodskript.**

Skript körs asynkront. Detta orsakar ofta `document.write` åtgärder visas på fel plats på sidan. Använda `document.write` i skript som skapas i anpassad kod rekommenderas inte.

**Om du skapar ett element och sedan ändrar det, ska du inte ta bort det ursprungliga elementet.**

Varje ändring skapar ett nytt element på panelen Ändringar. Eftersom den andra åtgärden ändrar Element 1 har den åtgärden inte längre något att ändra om du tar bort Element 1, så ändringen fungerar inte längre. Mer information finns i Felsökning nedan.

**Var försiktig om du använder den anpassade kodfunktionen för två aktiviteter som har samma URL som mål.**

Om du använder den anpassade kodfunktionen för två aktiviteter som har samma URL som mål, kommer JavaScript-koden att matas in på sidan från båda aktiviteterna. Målet bestämmer automatiskt ordningen för levererat innehåll. Kontrollera att koden inte är beroende av placering. Det är upp till dig att se till att det inte finns några konflikter i koden.

## Felsökning av anpassad kod {#section_6C965CBC31C348D7AA5B57B63DAB9E7F}

**Jag fick en varning om att en åtgärd inte kan utföras på grund av strukturella ändringar på en sida. Vad betyder det?**

Det här meddelandet anger att sidans struktur har ändrats sedan aktiviteten senast sparades.

De saknade väljarna kan nås i bläddringsläge. Vi rekommenderar att du tar bort och sedan återskapar varje upplevelse så att innehållet ser ut som du tänkt dig, vilket visas i varningsmeddelandet.

![](assets/code_editor_2.png)

***När jag tar bort ett element visas ett varningsmeddelande som säger&quot;Om du tar bort den här åtgärden kan det påverka efterföljande åtgärder&quot;. Vad betyder det?***

Om du till exempel har vidtagit två åtgärder:

* En klass har lagts till i Element 1
* HTML för element 1 har redigerats

Varje ändring skapar ett nytt element på panelen Ändringar. Eftersom den andra åtgärden ändrar element 1 har den andra åtgärden inte längre något att ändra om du tar bort element 1, så ändringen fungerar inte längre.

Om du lägger till ett element med text och sedan redigerar elementet med annan text i en separat åtgärd, visas båda åtgärderna som separata element på panelen Ändringar. När du redigerade elementet skapade du ett nytt element som ändrar det ursprungliga elementet som du skapade och som innehåller den redigerade texten. Om du sedan tar bort det ursprungliga elementet kommer den redigerade texten inte att kunna hitta det element som redigerades och kommer inte att visas. Det andra elementet finns kvar i listan med element, men det påverkar inte sidan eftersom elementet det ändras inte längre finns.

***Ett element som jag skapade med `document.write` i ett skript inte visas där jag förväntar mig det.***

Skript körs asynkront. Detta orsakar ofta `document.write` åtgärder visas på fel plats på sidan. Adobe rekommenderar inte att du använder `document.write` i skript som skapas i den anpassade koden.

***Mitt JavaScript visar fel i den anpassade koden.***

Alla infogade JavaScript som inte är ett giltigt JavaScript-skript visar fel i den anpassade koden.

***Jag kan inte ångra en ändring i min egen kod.***

Ångra stöds för närvarande inte för redigerings- och borttagningsåtgärder från panelen Ändringar och i anpassad kod. Om du ångrar någon av dessa åtgärder kan det leda till att upplevelsen i VEC inte överensstämmer med de faktiska åtgärder som visas i den anpassade koden. Åtgärderna i den anpassade koden är emellertid i rätt läge och påverkar inte leveransen. Det här är ett gränssnittsproblem. Om du vill uppdatera upplevelsen sparar du den och öppnar den igen, eller går till nästa steg och går tillbaka. Båda dessa åtgärder läser in upplevelsen på nytt, så den ser ut som förväntat och överensstämmer med åtgärderna på panelen Ändringar.

**Anpassad kod ger inte det förväntade resultatet i Internet Explorer 8.**

Target har inte längre stöd för IE8.
