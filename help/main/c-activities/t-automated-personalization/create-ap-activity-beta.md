---
keywords: automatiserad personalisering;ap
description: Lär dig hur du skapar en [!UICONTROL Automated Personalization]-aktivitet (AP) med [!UICONTROL Visual Experience Composer].
title: Hur skapar jag en [!UICONTROL Automated Personalization]-aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
hide: true
hidefromtoc: true
exl-id: fe6e5130-53a0-4254-8299-b52086c20004
source-git-commit: 8bfad2fe6804c241deec6c8ea70e2f8e7d79d8c6
workflow-type: tm+mt
source-wordcount: '1767'
ht-degree: 0%

---

# Skapa en [!UICONTROL Automated Personalization]-aktivitet

Skapa en [!UICONTROL Automated Personalization]-aktivitet (AP) i [!DNL Adobe Target] med hjälp av [!UICONTROL Visual Experience Composer] (VEC).

Arbetsflödet för [!UICONTROL Automated Personalization]-aktivitet (AP) i [!DNL Target] skiljer sig från arbetsflödet för andra aktivitetstyper.

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]** i listan [!DNL Target] [!UICONTROL Activities].

1. Om du vill använda [!UICONTROL Visual Experience Composer] (VEC) klickar du på **[!UICONTROL Visual]**.

   Om du vill använda [!UICONTROL Form-Based Experience Composer] väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] [!UICONTROL Single Page Application VEC]. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) [Välj en arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange din [aktivitets-URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) i rutan **[!UICONTROL Enter Activity URL]**.

   Om ditt konto är [konfigurerat med en standard-URL](/help/main/administrating-target/visual-experience-composer-set-up.md) visas den URL:en som standard. Du kan ändra från standardadressen till en annan URL-adress om det behövs.

   [!DNL Target] skiljer inte mellan URL-protokoll ([!DNL https] och [!DNL http]). Därför matchar både [!DNL `http://www.adobe.com`] och [!DNL `https://wwww.adobe.com`].

1. Klicka på **[!UICONTROL Create]**.

   Sidan med den angivna URL:en öppnas i VEC.

1. Klicka på ikonen **[!UICONTROL Rename]** ( ![Byt namn ](/help/main/assets/icons/MoreSmallListVert.svg) ), klicka på **[!UICONTROL Rename]**, ange ett namn för aktiviteten och klicka sedan på **[!UICONTROL Save]**.

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

1. Klicka på **[!UICONTROL Manage Content]** för att konfigurera tillgängliga kombinationer.

   ![Hantera innehåll, alternativ](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   En dialogruta visas med tre alternativ högst upp på skärmen: [!UICONTROL Experiences], [!UICONTROL Offers] och [!UICONTROL Exclusion Groups].

   ![Dialogrutan Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Även om ni kan skapa upp till 30 000 upplevelser i en AP-aktivitet fungerar aktiviteten bäst när färre än 5 000 upplevelser används. Samma begränsning tillämpas även när aktiviteten har aktiverat alternativet [!UICONTROL Disalow Duplicates].

   Listan [!UICONTROL Experiences] visar varje del av innehållet som har valts för aktiviteten och platsen som den har tilldelats.

   Du kan utesluta specifika upplevelser genom att hålla markören över den önskade upplevelsen och sedan klicka på ikonen [!UICONTROL Exclude].

   ![Uteslut ikonhovring](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Du kan gruppexkludera eller inkludera upplevelser genom att markera kryssrutan för de relevanta upplevelserna och sedan klicka på ikonen [!UICONTROL Exclude] i dialogrutans övre högra hörn.

   ![Alternativ för uteslutning av grupp](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Du kan filtrera den här listvyn så att endast uteslutna eller endast inkluderade aktiviteter visas genom att klicka på listrutan [!UICONTROL Status].

1. (Villkorligt) Klicka på **[!UICONTROL Offers]** om du vill markera innehållsdelar och tilldela dem till rapporteringsgrupper eller bara tillåta vissa besökare att se vissa erbjudanden med målinriktning.

   Mer information om rapportgrupper finns i [Erbjud rapportgrupper i Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (Villkorligt) Klicka på **[!UICONTROL Exclusion Groups]** för att välja en kombination av element som du vill utesluta från aktiviteten.

   ![Fliken Uteslutningsgrupper i dialogrutan Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Även om ni kan skapa upp till 30 000 upplevelser i ett AP-test fungerar algoritmen bäst när färre än 10 000 distinkta upplevelser används. Samma begränsning tillämpas även när aktiviteten har aktiverat alternativet [!UICONTROL Disalow Duplicates].

   Om du inte har någon exkluderingsgrupp med i din aktivitet klickar du på **Skapa exkluderingsgrupp**. Du kan filtrera för att skapa en lista som endast visar de kombinationer som du vill utesluta. Namnge exkluderingsgruppen och klicka sedan på **Spara**.

   Om du vill redigera en befintlig exkluderingsgrupp håller du pekaren över gruppen som du vill redigera och klickar sedan på pennikonen.

1. Klicka på **[!UICONTROL Done]** när du har konfigurerat innehållet i din aktivitet.

1. Steget **Mål** ser bekant ut om du har använt andra [!DNL Target]-aktivitetstyper. Här kan du välja en målgrupp och ange hur många besökare som ska se kontrollupplevelsen genom att klicka på listrutan **[!UICONTROL Custom Allocation]** och sedan klicka på **Nästa**.

   I listrutan [!UICONTROL Custom Allocation] kan du välja mellan följande alternativ:

   ![Listrutan Mål för trafikallokering](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

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
