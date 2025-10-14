---
keywords: automatiserad personalisering;ap
description: Lär dig hur du skapar en [!UICONTROL Automated Personalization]-aktivitet (AP) med [!UICONTROL Visual Experience Composer].
title: Hur skapar jag en [!UICONTROL Automated Personalization]-aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 9cc1eb4c5c95ea51bc0a1fc9e89b245a18c9914b
workflow-type: tm+mt
source-wordcount: '1851'
ht-degree: 0%

---

# Skapa en [!UICONTROL Automated Personalization]-aktivitet

Skapa en [!UICONTROL Automated Personalization]-aktivitet (AP) i [!DNL Adobe Target] med hjälp av [!UICONTROL Visual Experience Composer] (VEC).

Arbetsflödet för [!UICONTROL Automated Personalization]-aktivitet (AP) i [!DNL Target] skiljer sig från arbetsflödet för andra aktivitetstyper.

1. Klicka på [!DNL Target] > [!UICONTROL Activities] i listan **[!UICONTROL Create Activity]** **[!UICONTROL Automated Personalization]**.

1. Om du vill använda [!UICONTROL Visual Experience Composer] (VEC) klickar du på **[!UICONTROL Visual]**.

   Om du vill använda [!UICONTROL Form-Based Experience Composer] väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] [!UICONTROL Single Page Application VEC]. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) [Välj en arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange din **[!UICONTROL Enter Activity URL]** aktivitets-URL[&#x200B; i rutan &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Om ditt konto är [konfigurerat med en standard-URL](/help/main/administrating-target/visual-experience-composer-set-up.md) visas den URL:en som standard. Du kan ändra från standardadressen till en annan URL-adress om det behövs.

   [!DNL Target] skiljer inte mellan URL-protokoll ([!DNL https] och [!DNL http]). Därför matchar både [!DNL `http://www.adobe.com`] och [!DNL `https://wwww.adobe.com`].

1. Klicka på **[!UICONTROL Create]**.

   Sidan med den angivna URL:en öppnas i VEC.

1. Om du vill namnge aktiviteten klickar du på ikonen **[!UICONTROL Edit]** ( ![Redigera-ikon](/help/main/assets/icons/Edit.svg) ) bredvid [!UICONTROL Untitled Activity], anger ett beskrivande namn för aktiviteten och klickar sedan på **[!UICONTROL Save]**.

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

   Aktivitetsnamnet får inte innehålla någon av följande teckensekvenser:

   | Teckensekvens | Beskrivning |
   |--- |--- |
   | ;= | Semikolon, lika med |
   | ;+ | Semikolon, Plus |
   | ;- | Semikolon, minus |
   | ;@ | Semikolon, tecken |
   | ,= | Komma, motsvarar |
   | ,+ | komma, plus |
   | ,- | Komma, Minus |
   | ,@ | Komma, Vid tecken |
   | `[`&quot; | Öppen hakparentes, dubbla citattecken |
   | &quot;`]` | Dubbla citattecken, avslutande hakparentes |

1. Ändra sidelement enligt beskrivningen i [alternativen för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Du kan välja flera bilder samtidigt i resurshanteraren. På så sätt kan du snabbt visa sidan med varje bild som är konfigurerad för aktiviteten. Du kan också enkelt redigera textelement i dina erbjudanden. När du redigerar ett element visas staplar på det elementet för att ange att du har ändrat det.

1. Klicka på ikonen **[!UICONTROL Manage Content]** ( ![ikonen Hantera innehåll](/help/main/assets/icons/Experience.svg) ) för att konfigurera tillgängliga kombinationer.

   En dialogruta visas med två alternativ högst upp på skärmen: [!UICONTROL Experiences] och [!UICONTROL Offers].

   >[!NOTE]
   >
   >Även om ni kan skapa upp till 30 000 upplevelser i en AP-aktivitet fungerar aktiviteten bäst när färre än 5 000 upplevelser används. Samma begränsning tillämpas även när aktiviteten har aktiverat alternativet [!UICONTROL Disalow Duplicates].

   Listan [!UICONTROL Experiences] visar varje del av innehållet som har valts för aktiviteten och platsen som den har tilldelats.

   Du kan utesluta specifika upplevelser genom att markera kryssrutan bredvid önskad upplevelse och sedan klicka på ikonen [!UICONTROL Exclude].

   Du kan gruppexkludera eller inkludera upplevelser genom att markera kryssrutan för relevanta upplevelser och sedan klicka på ikonen [!UICONTROL Exclude] .

1. (Villkorligt) Klicka på **[!UICONTROL Offers]** om du vill markera innehållsdelar och tilldela dem till rapporteringsgrupper eller bara tillåta vissa besökare att se vissa erbjudanden med målinriktning.

   Mer information om rapportgrupper finns i [Erbjud rapportgrupper i Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the [!UICONTROL Disalow Duplicates] option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.-->

1. Klicka på **[!UICONTROL Done]** när du har konfigurerat innehållet i din aktivitet.

1. Klicka på **[!UICONTROL Targeting]** överst i [!UICONTROL Visual Experience Composer] för att gå till nästa steg i det guidade arbetsflödet i tre steg.

   Steget **Mål** ser bekant ut om du har använt andra [!DNL Target]-aktivitetstyper. Här kan du välja en målgrupp och ange hur många besökare som ska se varje upplevelse.

   Flödesdiagrammet öppnas.

   ![Riktningssteg för AP-test](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

   Flödesdiagrammet leder dig genom stegen för att tilldela en målgrupp och dess trafikprocent, välja trafikallokeringsmetod och specificera trafikallokeringen för varje upplevelse i aktiviteten.

1. (Villkorligt) Klicka på kontrollen **[!UICONTROL All Visitors]** för att välja en annan målgrupp för aktiviteten.

   [!UICONTROL All Visitors]-målgruppen är inställd som standard. Om du väljer en annan målgrupp visas dess namn längst till vänster.

   Den högra bildrutan visas, vilket gör att du kan lägga till eller ta bort en målgrupp och tilldela besökarprocenten för aktiviteten.

   1. Om du vill ändra målgruppen klickar du på ikonen **[!UICONTROL Replace]** ( ![ikonen Ersätt](/help/main/assets/icons/Retweet.svg) ) i den högra ramen.
   1. I dialogrutan [!UICONTROL Add Audience] [väljer du önskad målgrupp](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) och klickar sedan på **[!UICONTROL Assign Audience]**.

      Du kan klicka på **Kombinera målgrupper** för att [skapa en målgrupp som kombinerar flera målgrupper](/help/main/c-target/combining-multiple-audiences.md).

      Om du behöver skapa en ny målgrupp som inte redan finns i [!UICONTROL Audience Library] klickar du på **Skapa målgrupp**. Under arbetsflödet [skapa målgrupper](/help/main/c-target/c-audiences/audiences.md) kan du välja bland följande alternativ:

      * **[!UICONTROL Audience Library]**: Skapa en målgrupp på begäran som sparas i [!UICONTROL Audience Library] som kan återanvändas i andra aktiviteter.
      * **[!UICONTROL This activity only]**: Skapa en [aktivitetsspecifik målgrupp](/help/main/c-target/creating-activity-only-audience.md) som inte har sparats i [!UICONTROL Audience Library] och som bara kan användas i den aktuella aktiviteten.

   1. Klicka på **[!UICONTROL Visitor Percentage]** i den högra bildrutan och välj sedan den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. Klicka på kontrollen **[!UICONTROL Traffic Allocation]** och välj bland följande alternativ:

   ![Alternativ för trafikallokeringsmål](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:** Om ditt mål är att testa algoritmen ska du använda en 50/50-procentig delning av besökare mellan kontrollen och målalgoritmen. Denna delning ger den mest korrekta uppskattningen av hissen. Föreslagna för användning med&quot;slumpmässiga upplevelser&quot; som er kontroll.
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:** Om ditt mål är att skapa en alltid aktiverad aktivitet ger du 10 % av besökarna kontrollen. Det här alternativet ser till att det finns tillräckligt med data för att algoritmerna ska kunna fortsätta inlärningen över tid. Hantverket här är att i utbyte mot att personalisera en större andel av trafiken har ni mindre precision i det exakta lyftet. Oavsett vilket mål du har är det här alternativet den rekommenderade trafikdelningen när du använder en specifik upplevelse som kontroll.
   * **[!UICONTROL Custom Allocation]:** Dela procentandelen manuellt efter behov.

1. (Villkorligt) I listrutan [!UICONTROL Control] väljer du [en specifik upplevelse som ska användas som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md) eller [!UICONTROL Random Experience.]

   Kontrollupplevelsen ger en jämförelse för att avgöra hur mycket lyft det automatiserade testet ger.

   [!UICONTROL Automated Personalization] mäter alltid prestanda mot en kontrollgrupp. Det bästa är att placera minst 10 % av deltagarna i kontrollgruppen. Om ditt mål är att testa om personaliseringsalgoritmen för de data den ges fungerar bättre än ingen personalisering (till exempel den slumpmässigt hanterade kontrollen) är en trafikdelning på 50/50 procent mellan kontrollen och personaliseringsalgoritmen det snabbaste och mest korrekta sättet att uppnå detta mål. Om ni vill maximera den mängd trafik som personaliseras och ni inte är lika intresserade av att förstå exakt hur mycket aktiviteten genererar, är en trafikdelning på 10/90 procent mellan kontrollen och personaliseringsalgoritmen det snabbaste och mest korrekta sättet att uppnå detta mål.

   >[!NOTE]
   >
   >I [!UICONTROL Automated Personalization] aktiviteter utvärderas anmälningskriterier (URL-mål, mallregler och målgruppsmål) för varje begäran. I tidigare versioner utvärderades tävlingsvillkoren en gång per session.

1. Klicka på **[!UICONTROL Next]** för att visa sidan **[!UICONTROL Goals & Settings]**.
1. Konfigurera aktiviteten med följande inställningar och klicka sedan på **[!UICONTROL Save & Close]**.

   | Inställning | Beskrivning |
   |--- |--- |
   | [!UICONTROL Name] | Namnge aktiviteten. Ge aktiviteten ett namn som är tillräckligt beskrivande för att teammedlemmarna ska kunna känna igen den i listan [!UICONTROL Activities]. Läs igenom tabellen ovan för att se vilka tecken som inte tillåts i ett aktivitetsnamn. |
   | [!UICONTROL Objective] | (Valfritt) Ange målet för provningen. Målet hjälper dig att komma ihåg syftet med aktiviteten. |
   | [!UICONTROL Priority] | Beroende på dina inställningar varierar användargränssnittet för [!DNL Target] och alternativen för [!UICONTROL Priority]. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High], eller så kan du aktivera finjusterade prioriteter från 0 till 999.<P>Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.<P>Om det här alternativet inte är aktiverat i [!UICONTROL Administration] > [!UICONTROL Reporting] (standard) anger du en prioritet: [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High].<P>Om du vill aktivera finkorniga prioriteringar klickar du på [!UICONTROL Administration] > [!UICONTROL Reporting] och växlar sedan alternativet [!UICONTROL Enable Fine-Grained Priorities] till På-positionen.<P>Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:<ul><li>0 = Låg</li><li>999 = Hög</li></ul>För aktiviteter som skapats i tidigare versioner av [!DNL Target Standard/Premium] konverteras [!UICONTROL Low] prioritet till 0, [!UICONTROL Medium] prioritet konverteras till 5 och [!UICONTROL High] prioritet konverteras till 10. Du kan justera dessa värden om det behövs.<P>**Obs!** Innan du kan inaktivera det här alternativet efter att du har använt finkorniga artiklar, måste alla prioriteter återställas till 0, 5 och 10. |
   | [!UICONTROL Duration] | Ange start- och slutdatum för aktiviteten. Du kan välja [!UICONTROL When Activated] eller ange ett specifikt datum och en viss tid. |
   | [!UICONTROL Optimization Goal] | Ange optimeringsmålet, som består av två parametrar:<ul><li>Vad du vill mäta med aktiviteten</li><li>En deltagares åtgärd som visar att målet har uppnåtts.</li></ul>Du kan välja att namnge optimeringsmålet genom att markera de tre punkterna till höger om [!UICONTROL My Primary Goal]. [!UICONTROL Automated Personalization] aktiviteter kan mäta [!UICONTROL Conversion] eller [!UICONTROL Revenue]. Du kan konvertera genom att visa en sida eller en mbox. Klickningar kan också spåras.<P>Det primära målet blir också det modelleringsmått som används av modelleringssystemet för att beräkna hur framgångsrik upplevelsen är.<P>Besökare kan behållas i aktiviteten för spårningsändamål när modelleringsmålet har uppnåtts. Ofta används till exempel en [!UICONTROL Automated Personalization]-aktivitet för att förbättra klickfrekvensen, och det anges som modelleringsmål. Men det är viktigt att se hur ökade klickfrekvenser leder till slutgiltig konvertering, så att det är viktigt att spåra genom den slutliga konverteringen.<P>Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.<P>Du måste definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.<P>Alternativet [!UICONTROL Add Dependency] tillåter att framgångsmåttet ökar om ett annat framgångsmått har nåtts eller inte har nåtts.<P>Så här lägger du till ett beroende:<ol><li>När du har lagt till ytterligare mått klickar du på **[!UICONTROL Advanced Settings]** under menyn med tre punkter till höger om [!UICONTROL Additional Goal].</li><li>Klicka på alternativet **[!UICONTROL Add Dependency]** längst ned i avsnittet [!UICONTROL Reporting Settings].</li><li>Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på [!UICONTROL Reached] för att växla mellan [!UICONTROL Reached] och [!UICONTROL Not Reached].</li></ol>Du kan redigera eller ta bort beroenden när du har lagt till dem. |
   | [!UICONTROL Conversion Metric] | Som standard är konverteringsmåttet samma som optimeringsmålmåttet. Du kan dock definiera ett separat konverteringsmått genom att avmarkera alternativet [!UICONTROL Same as Optimization Goal]. |
   | [!UICONTROL Additional Metrics] | Lägg till ytterligare rapporteringsmått som du vill använda. Du kan lägga till konverterings- eller intäktsmått.<P>**Obs!**: Måttet [!UICONTROL Engagement] stöds inte som ett ytterligare mått. Du kan använda [!DNL Target]-gränssnittet för att välja [!UICONTROL Engagement]-måttet, men data visas inte korrekt i rapporter. |
   | [!UICONTROL Audiences for Reporting] | Lägg till målgrupper för att aktivera filtrering efter målgrupper i rapporter. Som standard visar rapporten resultat för alla kvalificerade besökare. Lägg till målgrupper för att filtrera resultaten efter mer specifika delar av besökarna.<P>**Obs!** Till skillnad från andra aktivitetstyper kan [!UICONTROL Automated Personalization] inte använda [!UICONTROL Adobe Analytics] som rapportkälla (A4T). |
   | [!UICONTROL Notes] | Skriv in information om din aktivitet som är användbar för dig eller andra gruppmedlemmar. Det går att ändra storlek på rutan [!UICONTROL Notes]. |

   När du namnger eller byter namn på ett mätresultat tillåts inte följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | / | Snedstreck |
   | ? | Frågetecken |
   | # | Nummertecken |
   | : | Colon |
   | = | Lika med |
   | + | Plus |
   | - | Minus |
   | @ | Vid tecken |

När du har klickat på **[!UICONTROL Save & Close]** visas aktivitetens [!UICONTROL Overview]-sida. Klicka på **Förhandsgranska upplevelser** om du vill förhandsgranska hur upplevelserna ser ut när de levereras. Ett popup-fönster visas som du kan använda för att visa och dela länkar till dina AP-upplevelser på din webbplats för att få en&quot;riktig förhandsvisning&quot; av upplevelserna utanför [!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC). Du måste dela länkarna från meddelandet för att kunna dela förhandsgranskningen. Det går inte att klicka på en länk och sedan kopiera URL-adressen direkt från webbläsaren. Om du kopierar länken innehåller URL-adressen en parameter som visar sidan korrekt endast när du öppnar sidan från länken i meddelandet.

Mer information om rapportering finns i [Automated Personalization-rapporter](/help/main/c-reports/personalization-reports/reports-ap.md).
