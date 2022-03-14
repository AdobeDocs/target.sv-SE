---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: Sök Adobe [!DNL Target] API:er, inklusive API:erna för administration, leverans, rapportering och profil.
title: Var kan jag hitta [!DNL Target] API- och SDK-dokumentation?
feature: APIs/SDKs
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Adobe [!DNL Target] API-översikt

[!DNL Adobe Target] API:er kan grupperas efter typ: API:er för administration, leverans, rapportering och profil.

| API-typ | Vad du kan göra | Hämta länk | Andra praktiska länkar |
| --- | --- | --- |--- |
| Administratör | Skapa, ändra och ta bort aktiviteter, målgrupper, erbjudanden och andra objekt (inklusive [!DNL Recommendations] entiteter, kriterier, designer och så vidare. The [!DNL Recommendations] API:er är en typ av admin-API.) | <UL><li>[Target Admin API Postman Collection](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Använda Recommendations API:er](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) in *Adobe Target Tutorials* |
| Leverans | Hämta optimerat och personaliserat innehåll från [!DNL Target] för leverans till en slutanvändare. | [Target Delivery API Postman Collection](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Rapportering | Exportera aktivitetsresultat och andra rapportresultat. | Rapporterings-API:er ingår i [Måladministratörs-API Postman-samling](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Profil | Hämta och ändra användarprofiler som lagras i Adobe Target. | [Målprofil-API Postman Collection](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Det finns viktiga skillnader mellan [!DNL Target] Admin-API:er (inklusive [!DNL Recommendations] API:er) och [!DNL Target] Leverans-API:er:
>
>* Med administratörs-API:er kan du konfigurera olika aspekter av [!DNL Target] som du också kan konfigurera i [!DNL Target] Gränssnitt. Admin-API:er kräver autentisering.
>
>* Med leverans-API:er kan du hämta innehåll. Leverans-API:er kräver inte autentisering.
>
>Används [!DNL Target] Admin-API:er måste du först konfigurera autentisering med Adobe I/O. Mer information finns i [Konfigurera autentisering](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) in *Adobe Target Tutorials*.
