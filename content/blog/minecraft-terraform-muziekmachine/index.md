---
title: Bouw een muziekmachine
draft: false
description: >-
  Opdracht om een muziekmachine te programmeren in Minecraft met Terraform die
  een bestaand melodietje kan afspelen.
content_blocks: []
mainContentInfo: ''
tags:
  - opdracht
  - terrameister-2024
categories: []
author: Mark
date: 2024-2-13
image: il_1140xN.3004388421_f94w.jpg

---

### Beoordeling

Bij deze opdracht wordt je beoordeeld op:

- Manier van programmeren
- Creativiteit
- Herkenbaarheid
- Nauwkeurigheid
- Instrumentkeuze

### Opdrachtomschrijving

Voor deze opdracht moet je een melodie maken. Dat doe je aan de hand van een
`note_block` en een `repeater`. Eerst maak je één van de eerste drie melodieën (1
t/m 3), en voor extra punten kies je een melodie uit 4 t/m 9.

1. Twinkle, Twinkle, Little Star
2. Happy Birthday
3. Jingle Bells
4. The Pink Panther Theme
5. Pirates of the Caribbean Theme
6. Star Wars Theme
7. Harry Potter Theme
8. "Let It Go" uit "Frozen"
9. "Shape of You" by Ed Sheeran (simplified version)

### Hoe pak je het aan?

> Hoe maak je muziek in Minecraft en hoe programmeer je dat in Terraform

#### Terraform-instructies

Check allereerst in je Terraform broncode of het provider address klopt in het bestand provider.tf

Om met de muziekopdracht bezig te zijn heb je geen module nodig, maar een
resource. Voordeel hiervan is dat je geen `terraform init` hoeft uit te voeren
bij de keren dat je iets maakt.

Op het moment dat je een resource aanmaakt moet je het volgende weten:

1. Voor resource moet je in `main.tf` werken.
2. Geef aan dat het om een `resource` gaat, welke resource het is (`minecraft_block`) en geef een unieke naam aan van jouw `resource`.
3. Geef aan van welk materiaal het blok moet zijn (`material`)
4. Geef het beginpunt aan van het puzzelstukje dat je wilt maken met de coördinaten `x`, `y`, `z`.

```terraform
resource "minecraft_block" "noteblock" {

  material = "note_block[note=7]"

  position = {
    x = 0,
    y = -60,
    z = 0
 }
}
```

> Tip: In het geval dat de coördinaten niet duidelijk zijn kun je in Minecraft op `F3` drukken
> om meer info te krijgen.

Hieronder staat een uitgewerkt voorbeeld deze opdracht:

```terraform
resource "minecraft_block" "noteblock_1" {

  material = "note_block[note=6]"

  position = {
    x = 100,
    y = -59,
    z = -100
 }
}

resource "minecraft_block" "node_edit_1" {
  material = "gold_block"

  position = {
    x = 100,
    y = -60,
    z = -100
 }
}

resource "minecraft_block" "repeater_1" {
  material = "repeater[delay=4,facing=west]"

  position = {
    x = 101,
    y = -60,
    z = -100
 }
}
```

Vervolgens moet je `terraform apply` in de console uitvoeren.

<img class="img-fluid" src="/images/muziekmachine1.png" />




Vergeet niet dat je alle veranderingen moet bevestigen door "yes" te typen na
`terraform apply`.


<img class="img-fluid" src="/images/muziekmachine2.png" />

#### Minecraft informatie hoe je muziek maakt

##### note block

Om een redstone mechanisme te starten moet je een actievatie middel hebben, zo als:
- Button
- Lever
- Pressure Plate

Een `note_block` bepaald de toonhoogte van een noot.

In onderstaand voorbeeld laten we zien hoe je de ingestelde noot, het geluid en
de delay kunt zien en aanpassen.

Om een goed geluid te krijgen, moet je de noot instellen als volgt:

<img class="img-fluid" src="/images/muziekmachine3.png" />

##### Mob heads

Om ervoor te zorgen dat jouw note_block als geluid een bepaald instrument
gebruikt, moet je het juiste block eronder plaatsen. Voor meer informatie over
de note_block, kun je de volgende link raadplegen:

https://minecraft.fandom.com/wiki/Note_Block#Mob_heads

Hieronder een paar voorbeelden in terraform taal.

```terraform

locals {
  fluit = "clay"
  bel = "gold_block"
  guitar = "white_wool"
  piano = "glowstone"
}

resource "minecraft_block" "node_edit_bells" {
  material = local.fluit

  position = {
    x = 100,
    y = -60,
    z = -100
 }
}

```

##### Repeater

Een `repeater` koppelt noten aan elkaar en bepaald de tijd tussen twee noten.

Delays zijn nodig om noten apart van elkaar te houden. In het volgende schema
kun je zien hoe lang de vertraging moet zijn voor elk type noot:

<img class="img-fluid" src="/images/muziekmachine4.png" />

Elke repeater kan voor 1 tot max. 4 ticks vertraging zorgen. Heb je meer
repeaters nodig? Gebruik dan meer repeaters. Dus 2 repeaters met delay 4 zou
voor een vertraging van 8 ticks zorgen.

Een repeater moet naar de juiste richting gaan (bijv. `north`, `south`, `east`,
`west`).

Voor een beter begrip hoe een delay werkt kan je de volgende video bekijken:

{{< youtube zTCfTtg5res >}}

https://www.youtube.com/watch?v=zTCfTtg5res

Meer informatie over de positie van repeaters kun je vinden op de volgende website:

https://minecraft.fandom.com/wiki/Redstone_Repeater#Block_states

Veel succes!
