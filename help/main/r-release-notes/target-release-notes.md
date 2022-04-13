---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: a03975f8f14db3cb8be0850130aab8d34c4c7fc0
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 13 april 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target Standard/Premium] 22.3.1 (stegvis frisättning, datum som ska fastställas)

Den här versionen innehåller följande ändringar och förbättringar:

* Korrigerade ett problem som fick redigeringar av profilskript att återgå till det ursprungliga oredigerade skriptet efter att skriptet redigerats, aktiverats och sedan inaktiverats. Profilskriptet förblir nu redigerat. (TGT-43249)
* Ett problem som orsakade följande felmeddelande i [!DNL Target] Gränssnitt när en målgrupp som används i en aktivitet med statusen&quot;utkast&quot; flyttas: &quot;Vi kan inte slutföra din begäran. Kontakta Adobe kundtjänst om problemet kvarstår.&quot; (TGT-43212)
* Ett problem som orsakade [!UICONTROL Include] och [!UICONTROL Exclude] alternativ som ska inaktiveras för kombinerade målgrupper när en aktivitet redigeras. (TGT-43422)
* Ett problem som gjorde att vissa kunder inte kunde se listan över tillgängliga målgrupper när en aktivitet redigerades har åtgärdats. (TGT-43404)
* Ett problem som gjorde att vissa kunder inte kunde ta bort en IP-adress från mappen har åtgärdats[!UICONTROL IPs to exclude from [!DNL Target] reporting data]&quot; i [!UICONTROL Administration] > [!UICONTROL Reporting]. (TGT-43384)
* Korrigerade ett problem som förhindrade användning av negativa tal i målgruppskriteriet som kontrollerar att variabeln är &quot;större än&quot;, &quot;större än eller lika med&quot;, &quot;mindre än&quot; eller &quot;mindre än eller lika med&quot;. (TGT-43367)
* Ett problem som gjorde att kunderna inte kunde se [!UICONTROL Audience Details] när ni skapar kombinerade målgrupper. (TGT-43303)
* Ett problem som orsakade [!DNL Target] Gränssnitt eller nytt [!UICONTROL Audiences] för vissa kunder. (TGT-42590 &amp; TGT-43273)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
