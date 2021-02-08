---
keywords: automatiserad personalisering;ap;målgrupper;ensemble;random forest;rest variance;error variance;livstidsvärde
description: Lär dig hur du skapar en Automated Personalization-aktivitet (AP) i Adobe Target med Visual Experience Composer (VEC).
title: Hur skapar jag en Automated Personalization-aktivitet?
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMCkapa en Automated Personalization-aktivitet

Arbetsflödet för aktiviteten [!UICONTROL Automated Personalization] (AP) i [!DNL Adobe Target] skiljer sig från arbetsflödet för de andra aktivitetstyperna.

1. I listan [!DNL Target] [!UICONTROL Activities] klickar du på **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**.

   ![Skapa aktivitet: Automated Personalization](/help/c-activities/t-automated-personalization/assets/ap_create-new.png)

1. Om du vill använda [!UICONTROL Visual Experience Composer] (VEC) klickar du på **[!UICONTROL Visual (Default)]**.

   ![Skapa Automated Personalization Activity (dialogruta)](/help/c-activities/t-automated-personalization/assets/ap_url-new.png)

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer] väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md).

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] [!UICONTROL Single Page Application VEC] och VEC för mobilappar. Mer information om de olika dispositionerna finns i [Upplevelser och erbjudanden](/help/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) om du har problem.
   >
   >Alternativet [!UICONTROL Choose Workplace] i föregående bild är en [Target Premium](/help/c-intro/intro.md)-funktion. Din organisation har en Target Standard-licens om du inte ser det här alternativet.

1. (Villkorligt) Om du är [!DNL Target] Premium-kund [väljer du en arbetsyta](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Verifiera eller ange aktivitets-URL:en och klicka sedan på **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll (  [!DNL https] och  [!DNL http]). Därför matchar både [!DNL `http://www.adobe.com`] och [!DNL `https://wwww.adobe.com`].

   Sidan med den angivna URL:en öppnas i Visual Experience Composer.

1. Om du vill namnge aktiviteten klickar du på fältet **[!UICONTROL Name]** och skriver ditt aktivitetsnamn.

   ![Namnfält](/help/c-activities/t-automated-personalization/assets/ab_newname-new.png)

   Följande tecken tillåts inte i aktivitetsnamn:

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

1. Ändra sidelement enligt beskrivningen i [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Du kan välja flera bilder samtidigt i resurshanteraren. På så sätt kan du snabbt visa sidan med varje bild som är konfigurerad för aktiviteten. Du kan också enkelt redigera textelement i dina erbjudanden. När du redigerar ett element visas staplar på det elementet för att ange att du har ändrat det.

1. Klicka på **[!UICONTROL Manage Content]** för att konfigurera tillgängliga kombinationer.

   ![Alternativet Hantera innehåll](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   En dialogruta med tre alternativ visas högst upp på skärmen: Upplevelser, erbjudanden och exkluderingsgrupper.

   ![Dialogrutan Hantera innehåll](/help/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Även om ni kan skapa upp till 30 000 upplevelser i en AP-aktivitet fungerar aktiviteten bäst när färre än 5 000 upplevelser används.

   Listan [!UICONTROL Experiences] visar varje del av innehållet som har valts för aktiviteten och platsen som den är tilldelad till.

   Du kan exkludera specifika upplevelser genom att hålla pekaren över den önskade upplevelsen och sedan klicka på exkluderingsikonen.

   ![Uteslut ikonhovring](/help/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Du kan gruppexkludera/inkludera upplevelser genom att markera kryssrutan för de relevanta upplevelserna och sedan klicka på ikonen Uteslut i dialogrutans övre högra hörn.

   ![Alternativ för uteslutning av grupp](/help/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Du kan filtrera den här listvyn så att endast uteslutna eller endast inkluderade aktiviteter visas genom att klicka på listrutan **Status**.

1. (Villkorligt) Klicka på **[!UICONTROL Offers]** om du vill markera innehållsdelar och tilldela dem till rapporteringsgrupper eller bara tillåta vissa besökare att se vissa erbjudanden med målinriktning.

   Mer information finns i [Erbjud rapporteringsgrupper i Automated Personalization](/help/c-reports/offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C).

   Använd listan [!UICONTROL Location] för att filtrera erbjudanden efter plats. Använd listan [!UICONTROL Report Group] för att filtrera erbjudanden efter rapporteringsgrupper. Du kan också använda listan [!UICONTROL Report Group] för att filtrera efter [!UICONTROL Unassigned Offers] så att du kan tilldela en rapporteringsgrupp till ett erbjudande som för närvarande inte är tilldelat någon rapporteringsgrupp.

   Du kan lägga till specifika upplevelser i en rapporteringsgrupp genom att hålla markören över önskat erbjudande och sedan klicka på mappikonen.

   ![Pekaren över mappikonen](/help/c-activities/t-automated-personalization/assets/icon-folder.png)

   Du kan batchinkludera upplevelser i en rapporteringsgrupp genom att markera kryssrutan för de relevanta upplevelserna och sedan klicka på mappikonen Rapporteringsgrupp i det övre högra hörnet i dialogrutan.

   ![Alternativ för rapportgrupp](/help/c-activities/t-automated-personalization/assets/report-group-options.png)

   Det är viktigt att förstå att rapportgrupper påverkar hur Target bygger sina modeller. Därför rekommenderar vi att du bara använder rapporteringsgrupper om du tänker ersätta eller lägga till nya erbjudanden medan aktiviteten är aktiv. Om ett nytt erbjudande införs i en liveaktivitet kan man genom att lägga in det nya erbjudandet i en grupp med befintliga liknande erbjudanden använda de data som redan samlats in för de andra erbjudandena i gruppen för att lära sig mer om det nya erbjudandet. Ni bör aldrig lägga alla erbjudanden i en enda rapporteringsgrupp.

   Mer information om att rikta ett erbjudande till specifika målgrupper finns i [Mål-AP-erbjudanden](/help/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

1. (Villkorligt) Klicka på **[!UICONTROL Exclusion Groups]** för att välja de kombinationer av element som du vill utesluta från aktiviteten.

   ![Fliken Uteslutningsgrupper i dialogrutan Hantera innehåll](/help/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Även om ni kan skapa upp till 30 000 upplevelser i ett AP-test fungerar algoritmen bäst när färre än 10 000 distinkta upplevelser används.

   Om du inte har någon exkluderingsgrupp med i din aktivitet klickar du på **Skapa exkluderingsgrupp**. Du kan filtrera för att skapa en lista som endast visar de kombinationer som du vill utesluta. Namnge exkluderingsgruppen och klicka på **Spara**.

   Om du vill redigera en befintlig exkluderingsgrupp håller du pekaren över gruppen som du vill redigera och klickar sedan på pennikonen.

1. Klicka på **[!UICONTROL Done]** när du är klar med inställningarna för din aktivitet.

1. **Målet**-steget kommer att se bekant ut om du har använt andra Target-aktivitetstyper. Här kan du välja en målgrupp och ange hur många besökare som ska se kontrollupplevelsen genom att klicka på listrutan **[!UICONTROL Custom Allocation]** och sedan klicka på **Nästa**.

   I listrutan [!UICONTROL Custom Allocation] kan du välja mellan följande alternativ:

   ![Listruta för trafikallokeringsmål](/help/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **Utvärdera personaliseringsalgoritm (50/50):** Om du vill testa algoritmen ska du använda en 50/50-procentig delning av besökarna mellan kontrollen och den valda algoritmen. Denna delning ger den mest korrekta uppskattningen av hissen. Föreslagna för användning med&quot;slumpmässiga upplevelser&quot; som er kontroll.
   * **Maximera personaliseringstrafiken (90/10):** Om målet är att skapa en&quot;alltid aktiv&quot; aktivitet sätter du 10 % av besökarna i kontrollen för att se till att det finns tillräckligt med data för att algoritmerna ska kunna fortsätta lära sig över tid. Observera att ni i utbyte mot att personalisera en större andel av trafiken har mindre precision i det exakta lyftet. Oavsett vilket mål du har är detta den rekommenderade trafikdelningen när du använder en specifik upplevelse som kontroll.
   * **Anpassad** allokering Dela procentandelen manuellt efter behov.

1. (Villkorligt) I listrutan [!UICONTROL Control] [väljer du en specifik upplevelse som ska användas som kontroll](/help/c-activities/t-automated-personalization/experience-as-control.md) eller väljer [!UICONTROL Random Experience.]

   Kontrollupplevelsen ger en jämförelse för att avgöra hur mycket lyft det automatiserade testet ger.

   Automated Personalization mäter alltid prestanda mot en kontrollgrupp. Det bästa är att placera minst 10 % av deltagarna i kontrollgruppen. Om ditt mål är att testa om personaliseringsalgoritmen för de data den ges fungerar bättre än ingen personalisering (dvs. den slumpmässigt hanterade kontrollen), är en trafikdelning på 50/50 procent mellan kontrollen och personaliseringsalgoritmen det snabbaste och mest korrekta sättet att uppnå detta mål. Om ni vill maximera den mängd trafik som personaliseras och ni inte är lika intresserade av att förstå exakt hur mycket aktiviteten genererar, skulle en trafikdelning på 10/90 procent mellan kontrollen och personaliseringsalgoritmen vara det snabbaste och mest korrekta sättet att uppnå detta mål.

   >[!NOTE]
   >
   >I Automated Personalization-aktiviteter utvärderas tävlingskriterier (URL-mål, mallregler och målgruppsmål) för varje begäran. I tidigare versioner utvärderades tävlingsvillkoren en gång per session.

1. Klicka på **[!UICONTROL Next]** för att visa sidan **[!UICONTROL Goals & Settings]**.
1. Konfigurera aktiviteten med följande inställningar och klicka sedan på **[!UICONTROL Save & Close]**.

   | Inställning | Beskrivning |
   |--- |--- |
   | Namn | Namnge aktiviteten. Ge aktiviteten ett namn som är tillräckligt beskrivande för att teammedlemmarna ska kunna känna igen den i aktivitetslistan.  Läs igenom tabellen ovan för att se vilka tecken som inte tillåts i ett aktivitetsnamn. |
   | Syfte | (Valfritt) Ange målet för provningen. Målet hjälper dig att komma ihåg syftet med aktiviteten. |
   | Prioritet | Beroende på dina inställningar varierar gränssnittet och alternativen för prioritet. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999.<br>Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.<br>Om det här alternativet inte är aktiverat i  [!UICONTROL Administration] >  [!UICONTROL Reporting] (standard) anger du en prioritet: Låg, Medel eller Hög.<br>Om du vill aktivera finkorniga prioriteringar klickar du  [!UICONTROL Administration] >  [!UICONTROL Reporting]och växlar sedan  [!UICONTROL Enable Fine-Grained Priorities] alternativet till läget &quot;På&quot;.<br>Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:<ul><li>0 = Låg</li><li>999 = Hög</li></ul>För aktiviteter som skapats i tidigare versioner av Target Standard/Premium konverteras låg prioritet till 0, Medel konverteras till 5 och Hög konverteras till 10. Du kan justera dessa värden om det behövs.<br>**Obs**: Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10. |
   | Varaktighet | Ange start- och slutdatum för aktiviteten. |
   | Optimeringsmål | Ange optimeringsmålet, som består av två parametrar:<ul><li>Vad du vill mäta med aktiviteten</li><li>En deltagares åtgärd som visar att målet har uppnåtts.</li></ul>Du kan välja att namnge optimeringsmålet genom att markera de tre punkterna till höger om Mitt primära mål. Automated Personalization verksamhet kan mäta konvertering, RPV och AOV. Du kan konvertera genom att visa en sida eller en mbox. Klickningar kan också spåras.<br>Det primära målet blir också det modelleringsmått som används av modelleringssystemet för att beräkna hur framgångsrik upplevelsen är.<br>Besökare kan behållas i aktiviteten för spårningsändamål när modelleringsmålet har uppnåtts. En Automated Personalization-aktivitet används till exempel ofta för att förbättra klickfrekvensen, och detta anges som modelleringsmål. Men det är viktigt att se hur ökade klickfrekvenser leder till slutgiltig konvertering, så att det är viktigt att spåra genom den slutliga konverteringen.<br>Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.<br>Du måste definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.<br>Alternativet Lägg till beroende gör att framgångsmåttet ökar om ett annat framgångsmått har nåtts eller inte har nåtts.<br>Så här lägger du till ett beroende:<ol><li>När du har lagt till ytterligare mått klickar du på [!UICONTROL Advanced Settings] under menyn med tre punkter till höger om Ytterligare mål.</li><li>Klicka på alternativet [!UICONTROL Add Dependency] längst ned i avsnittet [!UICONTROL Reporting Settings].</li><li>Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på [!UICONTROL Reached] för att växla mellan [!UICONTROL Reached] och [!UICONTROL Not Reached]</li></ol>Du kan redigera eller ta bort beroenden när du har lagt till dem. |
   | Konverteringsmått | Som standard är konverteringsmåttet samma som optimeringsmålmåttet. Du kan dock definiera ett separat konverteringsmått genom att avmarkera alternativet [!UICONTROL Same as Optimization Goal]. |
   | Ytterligare mått | Lägg till ytterligare rapporteringsmått som du vill använda. Du kan lägga till konverterings- eller intäktsmått.<br>**Obs**: Det finns inte heller stöd för interaktionsmåttet som ytterligare mått. Med gränssnittet kan du välja engagemangsmått, men data visas inte korrekt i rapporter. |
   | Målgrupper för rapportering | Lägg till målgrupper för att aktivera filtrering efter målgrupper i rapporter. Som standard visar rapporten resultat för alla kvalificerade besökare. Lägg till målgrupper för att filtrera resultaten efter mer specifika delar av besökarna.<br>**Obs**: Till skillnad från andra aktivitetstyper kan Automated Personalization inte använda Adobe Analytics som rapportkälla. |
   | Anteckningar | Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. Anteckningsfönstret kan storleksändras. |

   Observera att följande tecken inte tillåts när du namnger eller byter namn på ett mätresultat:

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

När du har klickat på **[!UICONTROL Create]** visas aktivitetssammanfattningen. Klicka på **Förhandsgranska upplevelser** för att förhandsgranska hur upplevelserna kommer att se ut när de levereras. Ett popup-fönster visas som du kan använda för att visa och dela länkar till dina AP-upplevelser på din webbplats för att få en&quot;riktig förhandsvisning&quot; av upplevelserna utanför Target Visual Experience Composer. Du måste dela länkarna från meddelandet för att kunna dela förhandsgranskningen. Det går inte att klicka på en länk och sedan kopiera URL-adressen direkt från sidan eftersom URL-adressen innehåller en parameter som bara visar sidan korrekt när du öppnar sidan från länken i meddelandet.

Mer information om rapportering finns i [Automated Personalization Reports](/help/c-reports/reports-ap.md#concept_C02BAFC922114A44846998FD956E345A).
