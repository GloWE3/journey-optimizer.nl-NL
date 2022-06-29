---
title: Een reis naar een andere sandox kopiëren
description: Leer hoe u een reis naar een andere sandox kopieert
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: 6c9e4920f57a7f52cf52da706f309ef3a9f8f5fc
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 0%

---

# Een reis naar een andere sandbox kopiëren {#copy-to-sandbox}

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_main"
>title="Een reis naar een andere sandbox kopiëren"
>abstract="Met Journey Optimizer kunt u een volledige reis van de ene naar de andere sandbox kopiëren. U kunt bijvoorbeeld een reis kopiëren van de zandbakomgeving van het werkgebied naar uw productiefandbox. Naast de Reis zelf kopieert Journey Optimizer ook de meeste objecten waarvan de reis afhankelijk is."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_sandbox_details"
>title="Details van sandbox"
>abstract="Selecteer de doelsandbox waarnaar u de reis wilt kopiëren. Alleen sandboxen binnen uw IMS-organisatie zijn beschikbaar."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_object_details"
>title="Objectdetails"
>abstract="Dit is de reis die je gaat kopiëren."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_dependent_objects"
>title="Afhankelijke objecten"
>abstract="Dit is de lijst van bijbehorende voorwerpen die in de reis worden gebruikt. In deze lijst worden de naam, het objecttype en de interne Journey Optimizer-id weergegeven."

Met Journey Optimizer kunt u een volledige reis van de ene naar de andere sandbox kopiëren. U kunt bijvoorbeeld een traject kopiëren van de zandbakomgeving van het werkgebied naar de productiefandbox. Naast de reis zelf kopieert Journey Optimizer ook de meeste objecten die de reis afhangt van: berichten, segmenten, voorinstellingen, schema&#39;s, gebeurtenissen en acties. Zie de [beperkingen](../event/about-events.md)

>[!CAUTION]
>
>We garanderen niet dat alle gekoppelde elementen naar de doelsandbox worden gekopieerd. We raden u ten zeerste aan een grondige controle uit te voeren voordat u de reis publiceert. Hierdoor kunt u elk mogelijk ontbrekend object identificeren.

De gekopieerde objecten in de doelsandbox zijn uniek en er bestaat geen risico dat bestaande elementen worden overschreven. Zowel de reis als alle berichten binnen de reis worden in de ontwerpmodus overgenomen. Hierdoor kunt u een grondige validatie uitvoeren voordat deze wordt gepubliceerd in de doelsandbox. Het kopieerproces kopieert alleen de metagegevens over de reis en de objecten in die reis. Er worden geen profiel- of gegevenssetgegevens gekopieerd als onderdeel van dit proces.

Ga als volgt te werk om een reis naar een andere sandbox te kopiëren:

1. Klik in de menusectie JOURNEY MANAGEMENT op **[!UICONTROL Journeys]**. De lijst met reizen wordt weergegeven.

2. Zoek naar de reis u wilt kopiëren, klik **Meer handelingen** pictogram (de drie punten naast de naam van de rit) en klik op **Kopiëren naar sandbox**.

   ![](assets/copy-sandbox1.png)

   De **Kopiëren naar sandbox** wordt weergegeven.

   ![](assets/copy-sandbox2.png)

3. Selecteer **Doelsandbox** in het vervolgkeuzeveld. Alleen sandboxen binnen uw IMS-organisatie zijn beschikbaar.

4. Controleer de **Afhankelijke objecten** sectie. Dit is de lijst van bijbehorende voorwerpen die in de reis worden gebruikt. In deze lijst worden de naam, het objecttype en de interne Journey Optimizer-id weergegeven.

5. Klik op de knop **Kopiëren** in de rechterbovenhoek, om het pad naar de doelsandbox te kopiëren.

   ![](assets/copy-sandbox3.png)

   Het kopiëren begint en de voortgang van elk afzonderlijk object wordt weergegeven. Het kopiëren is afhankelijk van de complexiteit van de reis en het aantal objecten dat moet worden gekopieerd. Als een fout wordt aangetroffen, wordt een bericht weergegeven voor het verwante object.

   ![](assets/copy-sandbox4.png)

6. Als het kopiëren is voltooid, klikt u op **Sluiten**.

7. Open de doelsandbox en voer een grondige controle uit van alle gekopieerde objecten.

## Verwerking en beperkingen kopiëren {#limitations}

We garanderen niet dat alle gekoppelde elementen naar de doelsandbox worden gekopieerd. We raden u ten zeerste aan een grondige controle uit te voeren. Identificeer om het even welk potentieel ontbrekend voorwerp en creeer hen manueel alvorens de reis te publiceren.

De volgende objecten worden gekopieerd:

* Segment

   Een segment kan slechts eenmaal van de ene naar de andere sandbox worden gekopieerd. Als een segment eenmaal is gekopieerd, kan het niet worden bewerkt in de doelsandbox.

* Schema

   De schema&#39;s die in deze reis worden gebruikt worden gekopieerd.

* Bericht

   De fysieke berichten die tijdens de reis worden gebruikt (e-mail- of pushberichten). De gebieden die voor verpersoonlijking in het bericht worden gebruikt worden niet gecontroleerd op volledigheid. Inhoudsblokken worden niet gekopieerd.

* Reis - canvasdetails

   De representatie van de reis op het canvas, inclusief de objecten op de reis, zoals voorwaarden, handelingen, gebeurtenissen, gelezen segmenten, enz. De sprongactiviteit wordt uitgesloten van het exemplaar.

* Gebeurtenis

   De gebeurtenissen en de gebeurtenisdetails die in de reis worden gebruikt worden gekopieerd.

* Actie

   De acties en actiedetails die in de reis worden gebruikt worden gekopieerd.

Voorinstellingen worden niet gekopieerd. Het systeem selecteert automatisch de best mogelijke overeenkomst op de bestemmingszandbak, die op berichttype en vooraf ingestelde naam wordt gebaseerd. Als er geen voorinstellingen worden gevonden in de doelsandbox, mislukt het kopiëren van de voorinstelling. Dit betekent dat het bericht ook niet kan worden gekopieerd omdat een bericht vereist dat er een voorinstelling beschikbaar is voor installatie. In dit geval moet ten minste één voorinstelling worden gemaakt voor het rechterkanaal van het bericht, zodat de kopie werkt.

Voor schema&#39;s, het Beleid en de Segmenten van de Fusie, de tweede keer deze voorwerpen proberen om worden gekopieerd, zullen zij slechts van verwijzingen worden voorzien. Deze worden behandeld als objecten die al bestaan en worden opnieuw gekopieerd. Dit betekent dat deze objecten slechts eenmaal kunnen worden gekopieerd.

Er is een vertraging van vijf minuten voordat Adobe Journey Optimizer naar schema&#39;s, beleid en segmenten samenvoegen kan verwijzen zonder een fout op het canvas te zien. Wacht vijf minuten en deze referenties zijn beschikbaar.
