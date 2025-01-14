---
title: Itemcatalogus
description: Leer hoe u met de itemcatalogus werkt
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: 2d118f5a-32ee-407c-9513-fe0ebe3ce8f0
source-git-commit: 5a64190203563d66309c897fe3ee806a74e8bfc9
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# Itemcatalogus {#catalog}

In Beslissing, dienen de catalogi als centrale containers voor het organiseren van besluitvormingspunten. Elke catalogus is gekoppeld aan een Adobe Experience Platform-schema, dat alle kenmerken omvat die aan een beslissingsitem kunnen worden toegewezen.

Vooralsnog worden alle gemaakte beslissingsitems geconsolideerd in één catalogus met &quot;aanbiedingen&quot;, die toegankelijk is via het menu **[!UICONTROL Catalogs]** .

![](assets/catalogs-list.png)

Ga als volgt te werk om het schema van de catalogus te openen waarin de kenmerken van de beslissingsitems zijn opgeslagen:

1. Klik in de lijst met items op de knop **[!UICONTROL Edit schema]** naast de knop **[!UICONTROL Create item]** .

1. Het schema van de catalogus wordt op een nieuw tabblad geopend, volgens de onderstaande structuur:

   * Het knooppunt **`_experience`** bevat standaardkenmerken voor besluitvormingsitems, zoals naam, begin- en einddatum en beschrijving.
   * Het knooppunt **`_<imsOrg>`** bevat kenmerken voor aangepaste beslissingsitems. Standaard zijn er geen aangepaste kenmerken geconfigureerd, maar u kunt er zo veel toevoegen als nodig is om aan uw vereisten te voldoen. Zodra gedaan, verschijnen de douanekenmerken in het scherm van de verwezenlijking van het besluitpunt naast de standaardattributen.

   ![](assets/catalogs-schema.png)

1. Als u een aangepast kenmerk aan het schema wilt toevoegen, vouwt u het knooppunt **`_<imsOrg>`** uit en klikt u op de knop &quot;+&quot; op de gewenste locatie in de structuur.

   ![](assets/catalogs-add.png)

1. Vul de vereiste velden voor het toegevoegde kenmerk in en klik op **[!UICONTROL Apply]** .

   >[!CAUTION]
   >
   >Momenteel worden bij Beslissing uitsluitend de volgende gegevenstypen ondersteund: String, Integer, Boolean, Date, DateTime en Decisioning Asset. Een veld dat buiten deze gegevenstypen valt, is niet beschikbaar voor gebruik bij het ontwerpen van een beslissingsitem of een catalogus.

   De waarde die op een attribuut met het besluit activaattribuut wordt ingevoerd is een openbare url. Meestal wijst dit naar een afbeelding.

   De gedetailleerde informatie over hoe te met de schema&#39;s van Adobe Experience Platform te werken is beschikbaar in de [ documentatie van het Systeem XDM ](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html).

1. Sla het schema op wanneer u de gewenste aangepaste kenmerken hebt toegevoegd. Het nieuwe veld is nu beschikbaar in het scherm voor het maken van een besluit-item, in de sectie **[!UICONTROL Custom attributes]** .

>[!NOTE]
>
>Een besluitpunt kan een maximum van 100 douanekenmerken omvatten. [ leer meer op het Beslissen van gidsen &amp; beperkingen ](gs-experience-decisioning.md#guardrails)
