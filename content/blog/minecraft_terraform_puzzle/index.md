---
title: minecraft-terraform-puzzle
description: Opdracht om puzzel op te lossen binnen een vlak in Minecraft met Terraform.
content_blocks: []
mainContentInfo: ''
tags:
  - opdracht
  - terrameister-2024
categories: []
author: Mark
date: 2024-2-21
image: il_1140xN.3004388421_f94w.jpg

---

### Beoordeling

Bij deze opdracht wordt je beoordeeld op:

- Snelheid
- Fouten

### Opdrachtomschrijving

Je hebt 19 stukjes van de puzzel en die moeten binnen een vlak passen zonder dat ze elkaar, of een vlak, overlappen. Je krijgt een map waarin alle vormen van de puzzelstukjes staan. Het witte vlak is een beginpunt waar vandaan gebouwd moet worden, en een vak waar die in moet passen.

### Hoe pak je het aan?

> Hoe maak je muziek in Minecraft en hoe programmeer je dat in Terraform

#### Terraform-instructies

Check allereerst in je Terraform broncode of het provider address klopt in het bestand provider.tf

Om een module voor de puzzel aan te maken zijn er een paar dingen nodig:

1. Voor modules moet je in `main.tf` werken.
2. Geef aan dat het om een `module` gaat, welke module het is (`puzzleP1 t/m puzzleP19`) en geef een unieke naam aan van jouw `module`.
3. Het pad naar de file waar de module aangeroepen wordt (`source`)
4. Geef aan van welk materiaal het blok moet zijn (`material`)
5. Geef het beginpunt aan van het puzzelstukje dat je wilt maken met de coördinaten `x`, `y`, `z`.

```terraform
 module "puzzel_peace1" {
 source = "./modules/puzzles/puzzleP1"
 material = "crimson_hyphae"


 position = {
   x = 0,
   y = 0,
   z = 0
  }
 }

```

> Tip: In het geval dat de coördinaten niet duidelijk zijn kun je in Minecraft op `F3` drukken
> om meer info te krijgen.

Hieronder staat een uitgewerkt voorbeeld deze opdracht:

<img class="img-fluid" src="/images/code.png" width="28%" height="auto"/>

<img class="img-fluid" src="/images/beginpunt.png" width="40%" height="auto"/>

Vervolgens moet je `terraform init` in de console uitvoeren en `terraform apply`

Vergeet niet dat je alle veranderingen moet bevestigen door "yes" te typen na
`terraform apply`.

<img class="img-fluid" src="/images/apply.png" width="40%" height="auto"/>

### Minecraft informatie over puzzels

Je hebt 19 puzzelstukjes die te vinden zijn in de map modules/puzzles:

<img class="img-fluid" src="/images/modules.png" width="25%" height="auto"/>

Voor een beter overzicht kun je hier een map vinden met alle puzzelstukjes in de volgorde 1 t/m 19:

<img class="img-fluid" src="/images/puzzle.png" width="40%" height="auto"/>

