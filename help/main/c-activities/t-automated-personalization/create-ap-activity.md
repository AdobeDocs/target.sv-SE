---
keywords: automatiserad personalisering;ap;målgrupper;ensemble;random forest;rest variance;error variance;livstidsvärde
description: Lär dig hur du skapar en [!UICONTROL Automated Personalization] (AP) aktivitet i [!DNL Adobe Target] med [!UICONTROL Visual Experience Composer].
title: Hur skapar jag en [!UICONTROL Automated Personalization] Aktivitet?
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: b3be11cda61b5bf54ee390a192d9f60273f8f12e
workflow-type: tm+mt
source-wordcount: '1716'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Skapa en [!UICONTROL Automated Personalization] aktivitet

Skapa en [!UICONTROL Automated Personalization] (AP) aktivitet i [!DNL Adobe Target] med [!UICONTROL Visual Experience Composer] (VEC).

The [!UICONTROL Automated Personalization] (AP) aktivitetsarbetsflöde i [!DNL Adobe Target] skiljer sig från arbetsflödet för de andra aktivitetstyperna.

1. Från [!DNL Target] [!UICONTROL Activities] lista, klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**.

   ![Skapa aktivitet: Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. Klicka på **[!UICONTROL Visual (Default)]**.

   ![Skapa Automated Personalization Activity (dialogruta)](/help/main/c-activities/t-automated-personalization/assets/ap_url-new.png){width="300"}

   Så här använder du [!UICONTROL Form-Based Experience Composer], markera [!UICONTROL Form]. Se [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) för mer information.

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer], [!DNL Target] erbjuder [!UICONTROL Single Page Application VEC]. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) [Välj en arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Verifiera eller ange aktivitets-URL:en och klicka sedan på **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Som en följd av detta [!DNL `http://www.adobe.com`] och [!DNL `https://wwww.adobe.com`] båda matchar.

   Sidan med den angivna URL:en öppnas i VEC.

1. Om du vill namnge aktiviteten klickar du på **[!UICONTROL Name]** och skriv ditt aktivitetsnamn.

   ![Namnfält](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

   Dessutom kan aktivitetsnamnet inte innehålla någon av följande teckensekvenser: &#39;;=&#39;, &#39;;+&#39;, &#39;;-&#39;, &#39;;@&#39;, &#39;,=&#39;, &#39;,+&#39;, &#39;,-&#39;, &#39;,@&#39;, &#39;[&quot;&#39;, &#39;&quot;]&#39;, &#39;[&#39;&#39;, &#39;&#39;]&#39;.

1. Ändra sidelement enligt [Alternativ för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Du kan välja flera bilder samtidigt i resurshanteraren. På så sätt kan du snabbt visa sidan med varje bild som är konfigurerad för aktiviteten. Du kan också enkelt redigera textelement i dina erbjudanden. När du redigerar ett element visas staplar på det elementet för att ange att du har ändrat det.

1. Klicka **[!UICONTROL Manage Content]** för att konfigurera tillgängliga kombinationer.

   ![Alternativet Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   En dialogruta med tre alternativ visas högst upp på skärmen: [!UICONTROL Experiences], [!UICONTROL Offers]och [!UICONTROL Exclusion Groups].

   ![Dialogrutan Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Även om ni kan skapa upp till 30 000 upplevelser i en AP-aktivitet fungerar aktiviteten bäst när färre än 5 000 upplevelser används. Samma gräns gäller även när aktiviteten har aktiverat [!UICONTROL Dissalow Duplicates] alternativ.

   The [!UICONTROL Experiences] visar varje del av innehållet som har valts för aktiviteten och platsen som den är tilldelad till.

   Du kan utesluta specifika upplevelser genom att hålla muspekaren över den önskade upplevelsen och sedan klicka på [!UICONTROL Exclude] ikon.

   ![Uteslut ikonhovring](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Du kan gruppera uteslutning/inkludering av upplevelser genom att markera kryssrutan för relevanta upplevelser och sedan klicka på [!UICONTROL Exclude] i dialogrutans övre högra hörn.

   ![Alternativ för uteslutning av grupp](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Du kan filtrera den här listvyn så att endast uteslutna eller endast inkluderade aktiviteter visas genom att klicka på [!UICONTROL Status] nedrullningsbar lista.

1. (Villkorligt) Klicka **[!UICONTROL Offers]** för att markera delar av innehållet och tilldela dem till rapporteringsgrupper eller bara tillåta vissa besökare att se vissa erbjudanden med målinriktning.

   Mer information om rapportgrupper finns i [Erbjud rapportgrupper i Automated Personalization](/help/main/c-reports/personalization-reports/offer-reporting-groups-in-automated-personalization.md).

1. (Villkorligt) Klicka **[!UICONTROL Exclusion Groups]** om du vill välja en kombination av element som du vill utesluta från aktiviteten.

   ![Fliken Uteslutningsgrupper i dialogrutan Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Även om ni kan skapa upp till 30 000 upplevelser i ett AP-test fungerar algoritmen bäst när färre än 10 000 distinkta upplevelser används. Samma gräns gäller även när aktiviteten har aktiverat [!UICONTROL Dissalow Duplicates] alternativ.

   Om du inte har någon exkluderingsgrupp med i din aktivitet klickar du på **Skapa exkluderingsgrupp**. Du kan filtrera för att skapa en lista som endast visar de kombinationer som du vill utesluta. Namnge exkluderingsgruppen och klicka på **Spara**.

   Om du vill redigera en befintlig exkluderingsgrupp håller du pekaren över gruppen som du vill redigera och klickar sedan på pennikonen.

1. Klicka **[!UICONTROL Done]** när du är klar med inställningarna för aktiviteten.

1. The **Målinriktning** om du har använt andra [!DNL Target] aktivitetstyper. Här kan du välja en målgrupp och ange hur många besökare som ska se kontrollupplevelsen genom att klicka på **[!UICONTROL Custom Allocation]** nedrullningsbar lista och klicka sedan på **Nästa**.

   The [!UICONTROL Custom Allocation] I den nedrullningsbara listan kan du välja mellan följande alternativ:

   ![Listruta för trafikallokeringsmål](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:** Om målet är att testa algoritmen ska du använda en 50/50-procentig delning av besökare mellan kontrollen och målalgoritmen. Denna delning ger den mest korrekta uppskattningen av hissen. Föreslagna för användning med&quot;slumpmässiga upplevelser&quot; som er kontroll.
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:** Om målet är att skapa en&quot;alltid aktiverad&quot; aktivitet får 10 % av besökarna kontrollen. Det här alternativet ser till att det finns tillräckligt med data för att algoritmerna ska kunna fortsätta inlärningen över tid. Observera att i utbyte mot personalisering av en större andel av trafiken har ni mindre precision i det exakta lyftet. Oavsett vilket mål du har är detta den rekommenderade trafikdelningen när du använder en specifik upplevelse som kontroll.
   * **[!UICONTROL Custom Allocation]:** Dela procentandelen manuellt efter behov.

1. (Villkorligt) Från [!UICONTROL Control] nedrullningsbar lista, [välja en specifik upplevelse som ska användas som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md) eller markera [!UICONTROL Random Experience.]

   Kontrollupplevelsen ger en jämförelse för att avgöra hur mycket lyft det automatiserade testet ger.

   [!UICONTROL Automated Personalization] mäter alltid prestanda mot en kontrollgrupp. Det bästa är att placera minst 10 % av deltagarna i kontrollgruppen. Om ditt mål är att testa om personaliseringsalgoritmen för de data den ges fungerar bättre än ingen personalisering (dvs. den slumpmässigt hanterade kontrollen), är en trafikdelning på 50/50 procent mellan kontrollen och personaliseringsalgoritmen det snabbaste och mest korrekta sättet att uppnå detta mål. Om ni vill maximera den mängd trafik som personaliseras och ni inte är lika intresserade av att förstå exakt hur mycket aktiviteten genererar, skulle en trafikdelning på 10/90 procent mellan kontrollen och personaliseringsalgoritmen vara det snabbaste och mest korrekta sättet att uppnå detta mål.

   >[!NOTE]
   >
   >I [!UICONTROL Automated Personalization] aktiviteter, anmälningskriterier (URL-adress, mallregler och målgruppsmål) utvärderas för varje begäran. I tidigare versioner utvärderades tävlingsvillkoren en gång per session.

1. Klicka **[!UICONTROL Next]** för att visa **[!UICONTROL Goals & Settings]** sida.
1. Konfigurera aktiviteten med följande inställningar och klicka sedan på **[!UICONTROL Save & Close]**.

   | Inställning | Beskrivning |
   |--- |--- |
   | [!UICONTROL Name] | Namnge aktiviteten. Ge aktiviteten ett namn som är tillräckligt beskrivande för att teammedlemmarna ska kunna känna igen den i [!UICONTROL Activities] lista. Läs igenom tabellen ovan för att se vilka tecken som inte tillåts i ett aktivitetsnamn. |
   | [!UICONTROL Objective] | (Valfritt) Ange målet för provningen. Målet hjälper dig att komma ihåg syftet med aktiviteten. |
   | [!UICONTROL Priority] | Beroende på dina inställningar kan användargränssnittet och alternativen för [!UICONTROL Priority] varierar. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.<br>Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.<br>Om det här alternativet inte är aktiverat i [!UICONTROL Administration] > [!UICONTROL Reporting] (standard), ange en prioritet: Låg, Medel eller Hög.<br>Om du vill aktivera detaljerade prioriteringar klickar du på [!UICONTROL Administration] > [!UICONTROL Reporting]och sedan växla [!UICONTROL Enable Fine-Grained Priorities] till På-positionen.<br>Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:<ul><li>0 = Låg</li><li>999 = Hög</li></ul>För aktiviteter som skapats i tidigare versioner av [!DNL Target Standard/Premium], Låg prioritet konverteras till 0, Medel konverteras till 5 och Hög konverteras till 10. Du kan justera dessa värden om det behövs.<br>**Anteckning**: Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10. |
   | [!UICONTROL Duration] | Ange start- och slutdatum för aktiviteten. Du kan välja [!UICONTROL When Activated] Du kan också ange ett specifikt datum och en viss tid. |
   | [!UICONTROL Optimization Goal] | Ange optimeringsmålet, som består av två parametrar:<ul><li>Vad du vill mäta med aktiviteten</li><li>En deltagares åtgärd som visar att målet har uppnåtts.</li></ul>Du kan välja att namnge optimeringsmålet genom att markera de tre punkterna till höger om [!UICONTROL My Primary Goal]. [!UICONTROL Automated Personalization] aktiviteter kan mäta konvertering, RPV och AOV. Du kan konvertera genom att visa en sida eller en mbox. Klickningar kan också spåras.<br>Det primära målet blir också det modelleringsmått som används av modelleringssystemet för att beräkna hur framgångsrik upplevelsen är.<br>Besökare kan behållas i aktiviteten för spårningsändamål när modelleringsmålet har uppnåtts. Ofta är [!UICONTROL Automated Personalization] används för att förbättra klickfrekvenser, och det anges som modelleringsmål. Men det är viktigt att se hur ökade klickfrekvenser leder till slutgiltig konvertering, så att det är viktigt att spåra genom den slutliga konverteringen.<br>Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.<br>Du måste definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.<br>The [!UICONTROL Add Dependency] gör det möjligt för framgångsmåttet att öka om ett annat framgångsmått har nåtts eller inte har nåtts.<br>Så här lägger du till ett beroende:<ol><li>När du har lagt till ytterligare mätvärden klickar du på **[!UICONTROL Advanced Settings]** under menyn med tre punkter till höger om [!UICONTROL Additional Goal].</li><li>Klicka på **[!UICONTROL Add Dependency]** längst ned i [!UICONTROL Reporting Settings] -avsnitt.</li><li>Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på [!UICONTROL Reached] för att växla mellan [!UICONTROL Reached] och [!UICONTROL Not Reached]</li></ol>Du kan redigera eller ta bort beroenden när du har lagt till dem. |
   | [!UICONTROL Conversion Metric] | Som standard är konverteringsmåttet samma som optimeringsmålmåttet. Du kan dock definiera ett separat konverteringsmått genom att avmarkera [!UICONTROL Same as Optimization Goal] alternativ. |
   | [!UICONTROL Additional Metrics] | Lägg till ytterligare rapporteringsmått som du vill använda. Du kan lägga till konverterings- eller intäktsmått.<br>**Anteckning**: The [!UICONTROL Engagement] Mått stöds inte som ytterligare mått. Du kan använda gränssnittet till att välja [!UICONTROL Engagement] mätvärden, men data visas inte korrekt i rapporter. |
   | [!UICONTROL Audiences for Reporting] | Lägg till målgrupper för att aktivera filtrering efter målgrupper i rapporter. Som standard visar rapporten resultat för alla kvalificerade besökare. Lägg till målgrupper för att filtrera resultaten efter mer specifika delar av besökarna.<br>**Anteckning**: Till skillnad från andra aktivitetstyper [!UICONTROL Automated Personalization] kan inte använda [!UICONTROL Adobe Analytics] som sin rapportkälla (A4T). |
   | [!UICONTROL Notes] | Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. The [!UICONTROL Notes] fönstret kan storleksändras. |

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

När du har klickat **[!UICONTROL Save & Close]**, aktivitetens [!UICONTROL Overview] visas. Klicka **Förhandsgranska upplevelser** för att förhandsgranska hur upplevelserna ser ut när de levereras. Ett popup-fönster visas som du kan använda för att visa och dela länkar till dina AP-upplevelser på din webbplats för att få en&quot;riktig förhandsvisning&quot; av upplevelserna utanför [!UICONTROL Target]&#39;s Visual Experience Composer (VEC). Du måste dela länkarna från meddelandet för att kunna dela förhandsgranskningen. Det går inte att klicka på en länk och sedan kopiera URL-adressen direkt från webbläsaren. Om du kopierar länken innehåller URL-adressen en parameter som visar sidan korrekt endast när du öppnar sidan från länken i meddelandet.

Mer information om rapportering finns i [Automated Personalization Reports](/help/main/c-reports/personalization-reports/reports-ap.md).
