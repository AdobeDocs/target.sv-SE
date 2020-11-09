---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: Information om Adobe Target API:er, inklusive API:erna för administration, leverans, rapportering och profil.
title: Adobe Target API - översikt
feature: api
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---


# Adobe Target API - översikt

[!DNL Adobe Target] API:er kan grupperas efter typ.

| API-typ | Vad du kan göra | Hämta länk | Andra praktiska länkar |
| --- | --- | --- |--- |
| Administratör | Skapa, ändra och ta bort aktiviteter, målgrupper, erbjudanden och andra objekt (inklusive [!DNL Recommendations] enheter, kriterier, design osv.). API: [!DNL Recommendations] erna är en typ av admin-API.) | <UL><li>[Target Admin API Postman Collection](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Använda Recommendations-API:er](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) i *Adobe Target Tutorials* |
| Leverans | Hämta optimerat och personaliserat innehåll från [!DNL Target] för leverans till slutanvändare. | [Target Delivery API Postman Collection](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Rapportering | Exportera aktivitetsresultat och andra rapportresultat. | Rapporterings-API:er ingår i [Target Admin API Postman-samlingen](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Profil | Hämta och ändra användarprofiler som lagras i Adobe Target. | [Målprofil-API Postman Collection](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Det finns viktiga skillnader mellan [!DNL Target] Admin API:er (inklusive [!DNL Recommendations] API:er) och [!DNL Target] Delivery API:er:
>
>* Med Admin API:er kan du konfigurera olika aspekter av [!DNL Target] som du också kan konfigurera i [!DNL Target] användargränssnittet. Admin-API:er kräver autentisering.
   >
   >
* Med leverans-API:er kan du hämta innehåll. Leverans-API:er kräver inte autentisering.
>
>
Om du vill använda [!DNL Target] Admin API:er måste du först konfigurera autentiseringen med Adobe I/O. Mer information finns i [Konfigurera autentisering](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) i *Adobe Target Tutorials*.
