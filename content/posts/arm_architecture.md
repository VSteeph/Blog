---
title: "Arm_architecture_Part1_Intro"
date: 2022-03-17T22:55:35+01:00
draft: false
ShowToc: true
TocOpen: true
tags: ["GameDev", "Architecture", "Yuzu"]
categories: ["Architecture", "GameDev"]
series: ["Switch Architecture (Arm)"]
---

# Intro

C'est le premier article sur ma découverte de l'émulateur [Yuzu](https://github.com/yuzu-emu/yuzu) qui est un émulateur pour Switch. Avant de pouvoir commencer à contribuer à cet émulateur, il y a pas mal de recherches pour comprendre l'environnement et l'architecture global du projet.

C'est donc la première Série qui va concerner l'architecture de la Switch (arm). J'ai encore une idée de ce que tout cela signifie donc on va commencer à définir le vocabulaire avec quelques articles Wikipedia pour pouvoir attaquer ce petit [PDF](https://developer.arm.com/documentation/ddi0487/ha/) de 11.000 pages, bonne chance à moi.

# Définition

Arm signifie Advanced Risc Machines, on va donc commencer à définir ce qu'est une RISC Machine.

##  [RISC](https://en.wikipedia.org/wiki/Reduced_instruction_set_computer)

Risc veut dire Reduced Instruction Set Computer. C'est à dire un ordinateur fait pour simplifié  les instructions individuelles dans le but de réaliser une tache. Il s'oppose au CISC ([Complex Instruction Set computer](https://en.wikipedia.org/wiki/Complex_instruction_set_computer), qu'on ne verra pas ici pour l'instant).
Cela a pour conséquences d'avoir des instructions plus simples, en contrepartie, une tâche nécessite souvent plus d'instructions. L'idée est de compenser le fait d'avoir plus d'instructions grâce à des instructions plus rapide.

### Avantages
Cela a permis d'avoir des programmes de plus petites tailles et moins d'accès à la mémoire principale (slow) qui a permis de faire des grosses économies de mémoire, de stockage mais aussi un gain de temps. De plus, la simplicité des instructions ont permis un gain de la productivité des développeurs même dans des langages plus bas niveau comme l'assembleur, ce qui est un très intéressant même en 2022.

Cela permet aussi de simplifier les design car l'instruction "unitaire" est plus simple, plus légère et donc, cela permet plus de liberté.

De manière générale, les RISC sont beaucoup plus utilisés à notre époque que les CISC.

## [ARM](https://en.wikipedia.org/wiki/ARM_architecture_family)

Cette architecture a été développe et est licencié par [Arm Ltd](https://en.wikipedia.org/wiki/Arm_Ltd.). La force de leur processor vient du fait qu'ils consomment moins d'énergie, génèrent moins de chaleur que la plupart de leur concurrent. Ils sont faits pour les éléments légers et portables comme les téléphones, tablettes ou les consoles.

# ARM architecture

l'arm définit le comportement d'une machine abstraite qu'on réfère à un "processing element" (PE). Les implémentations de cette architecture doivent être conforment au comportement décri de cet élément.
