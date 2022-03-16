---
product: adobe campaign
title: inNextDays
description: Meer informatie over de functie in NextDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0cb3e0db-dc5b-4d4e-a057-af030d9bdb21
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# inNextDays {#inNextDays}

Retourneert true als een bepaalde datum of dateTime zich tussen nu en nu + delta dagen bevindt.

## Categorie

Datum

## Functiesyntaxis

`inNextDays(<dateTime>,<delta>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd | dateTime |
| delta | integer |

## Handtekeningen en type geretourneerd

`inNextDays(<dateTime>,<integer>)`

Retourneert een Booleaanse waarde.

## Voorbeelden

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retourneert true.