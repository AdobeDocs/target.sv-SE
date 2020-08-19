---
keywords: global mbox;target classic;use global mbox from target classic
description: Som standard skapar Target Standard en global mbox med namnet target-global-mbox, som används för att köra aktiviteter som skapats i Target Standard. Om du redan har skapat en global mbox på sidorna för dina tidigare implementeringar kan du använda den mbox-filen för dina Target Standard-aktiviteter.
title: Använd en global mbox från en äldre implementering
feature: null
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Använd en global mbox från en äldre implementering{#use-a-global-mbox-from-a-legacy-implementation}

Som standard [!DNL Target] skapar en global mbox med namnet target-global-mbox, som används för att köra aktiviteter som skapas i [!DNL Target]. Om du redan har skapat en global mbox på dina sidor för dina tidigare implementeringar kan du använda den mbox för dina [!DNL Target] aktiviteter.

>[!NOTE]
>
>Du kan bara ha en global mbox per konto.

Om du vill använda din befintliga globala mbox för både [!DNL Target] och den gamla implementeringen måste du ange några parametrar.

1. Gå till [!DNL Target]och klicka sedan på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   Som standard **[!UICONTROL Page load enabled (Auto-create global mbox]** är aktiverad och den anpassade globala mbox namnges `target-global-mbox`.

1. Om du vill använda en befintlig mbox inaktiverar du **[!UICONTROL Page load enabled (Auto-create global mbox]** och anger namnet på en tidigare skapad global mbox i **[!UICONTROL Global Mbox]** fältet.

   I den [!UICONTROL Global Mbox] nedrullningsbara listan visas alla kryssrutor på ditt konto. Om du vill använda en mbox som ännu inte finns skapar du mbox-filen.

1. Klicka på **[!UICONTROL Save]**.

   Inställningarna för mbox.js för ditt konto uppdateras.

1. Hämta den nya filen at.js och referera till den på din webbplats.

   Alla befintliga aktiviteter uppdateras till att använda den angivna globala mbox, inklusive aktiviteter som tidigare har skapats och implementerats.

## Felsöka global mbox-implementering

Följande vanliga frågor och svar kan användas för att felsöka din globala mbox-implementering:

### Varför läses inte den globala mbox in, eller varför finns det fördröjning i inläsningen av den globala mbox när sidan läses in?*

Kontrollera att referensen at.js är det första JavaScript-anropet på sidan. Andra lösningar på det här problemet finns i Vanliga frågor och svar [om](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)Global Mbox.
