---
title: Speed Building
description: >-
  Opdracht om gegeven onderwerpen te bouwen zo snel mogelijk in Minecraft met
  Terraform
content_blocks: []
mainContentInfo: ''
tags:
  - 'opdracht '
  - terrameister-2024
categories: []
author: Mark
date: 2024-2-21
image: >-
  minecraft-pocket-edition-terraria-survivalcraft-shelter-free-craft-mine-block-minecraft.jpg

---

### Beoordeling

Bij deze opdracht wordt je beoordeeld op:

- Snelheid
- Design
- Nauwkeurigheid

### Opdrachtomschrijving

Voor deze opdracht moet je zo veel mogelijk verschillende gebouwen ontwerpen die aan bepaalde eisen voldoen:

- Een huis met begane grond, 1e en 2e etage, schuin dak en een tuin.
- Een flat (appartementencomplex) met 7 etages en 25 appartementen.
- Het TechNative kantoor met parkeerplaats.
- Een doorgaande weg naar bovenstaande gebouwen (zodat we naar kantoor en naar huis kunnen :)

### Hoe pak je het aan?

> Hoe maak je muziek in Minecraft en hoe programmeer je dat in Terraform

#### Terraform-instructies

Check allereerst in je Terraform broncode of het provider address klopt in het bestand provider.tf

Om een module voor de puzzel aan te maken zijn er een paar dingen nodig:

1. Voor modules moet je in `main.tf` werken.
2. Geef aan dat het om een `module` gaat, welke module het is (`puzzleP1 t/m puzzleP19`) en geef een unieke naam aan van jouw `module`.
3. Het pad naar de file waar de module aangeroepen wordt (`source`)
4. Geef aan van welk materiaal het blok moet zijn (`material`)
5. Geef het beginpunt aan van het module dat je wilt maken met de coördinaten `x`, `y`, `z`.
6. Geef aan hoe breed, lang en hoog module wil je maken

```terraform
 module "square" {
 source = "./modules/speed_building/square"
 material = "cobblestone"
 position = {
   x = 0,
   y = 0,
   z = 0
 }
 dimensions = {
   width  = 3,
   length = 3,
   height = 3
 }
}
```

> Tip: In het geval dat de coördinaten niet duidelijk zijn kun je in Minecraft op `F3` drukken
> om meer info te krijgen.

Er is ook een uitzondering voor de module "diagonal" (en alles wat met een diagonaal te maken heeft) waarbij een extra stap nodig is dat de breedte aangeeft (stap 7). **Dat is een verplichte variabele!**

```terraform
 width_expansion = 2
```

### Minecraft informatie over Speed Building

Je hebt 7 verschillende modules die te vinden zijn in de map modules/speed_building dat jouw bouw makkelijker maken:

<img class="img-fluid" src="/images/modules1.png" width="25%" height="auto"/>

Op het moment dat je bouwt en de begin-coördinaten aangeeft, dan wordt vervolgens een module gebouwd met de coördinaten zoals in onderstaand voorbeeld bij het plus-teken (+):

<img class="img-fluid" src="/images/beginpunt1.png" width="40%" height="auto"/>

