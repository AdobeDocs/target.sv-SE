---
keywords: global mbox;target classic;use global mbox from target classic
description: Lär dig hur du använder en äldre global mbox för Adobe [!DNL Target] om du redan har skapat en global mbox på sidorna för dina tidigare implementeringar.
title: Kan jag använda en global mbox från en äldre implementering?
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# Använd en global mbox från en äldre implementering

Som standard [!DNL Target] skapar en global mbox med namnet target-global-mbox, som används för att köra aktiviteter som skapats i [!DNL Target]. Om du redan har skapat en global mbox på sidorna för dina tidigare implementeringar kan du använda den mbox för [!DNL Target] verksamhet.

>[!NOTE]
>
>Du kan bara ha en global mbox per konto.

Använd din befintliga globala mbox för båda [!DNL Target] och den gamla implementeringen måste du ange några parametrar.

1. Gå till [!DNL Target]och sedan klicka **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   Som standard **[!UICONTROL Page load enabled (Auto-create global mbox]** är aktiverat och den anpassade globala mbox namnges `target-global-mbox`.

1. Om du vill använda en befintlig mbox inaktiverar du **[!UICONTROL Page load enabled (Auto-create global mbox]** och ange namnet på en tidigare skapad global mbox i dialogrutan **[!UICONTROL Global Mbox]** fält.

   The [!UICONTROL Global Mbox] listrutan med alla kryssrutor i ditt konto. Om du vill använda en mbox som ännu inte finns skapar du mbox-filen.

1. Klicka på **[!UICONTROL Save]**.

   Inställningarna för ditt konto uppdateras.

1. Hämta den nya filen at.js och referera till den på din webbplats.

   Alla befintliga aktiviteter uppdateras till att använda den angivna globala mbox, inklusive aktiviteter som tidigare har skapats och implementerats.

## Felsöka global mbox-implementering

Följande vanliga frågor och svar kan användas för att felsöka din globala mbox-implementering:

### Varför läses inte den globala mbox in, eller varför finns det fördröjning i inläsningen av den globala mbox när sidan läses in?

Kontrollera att referensen at.js är det första JavaScript-anropet på sidan. Andra lösningar på det här problemet finns i [Vanliga frågor och svar om Global Mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
