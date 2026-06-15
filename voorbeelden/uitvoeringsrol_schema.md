# Voorbeeld: Uitvoeringsrol

## Context
Het vastleggen van de rol van een uitvoerende in schema.org.
Dit voorbeeld bevat twee verschillende methodieken:
- bij sommige classes zoals PerformingartsEvent bestaat de "director" property en kan die "rol" zonder schema:Role class gemodelleerd worden.
- bij andere classes zoals PerformanceWork bestaan die niet en moet het via de meer generieke contributor property en wel met de Role class. 

Note: de additionalTypes hieronder zijn uitgeschreven maar dat moeten termen uit een (theater)thesaurus worden.

## Voorbeeld
```mermaid
---
title: Uitvoeringsrol in schema.org
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction TD
	class PerformanceWork["Animal Farm 2022-2023"] {
		<<PerformanceWork>>
		- additionalType: Operauitvoering
		- startDate : 3 december 2022
		- endDate : 30 maart 2023
		- isBasedOn : link naar werk Orwell
	}
	class PerformingArtsEvent["Animal Farm"] {
		<<PerformingArtsEvent>>
        - additionalType: Première
		- startDate: 3 maart 2023
		- duration: "128m"
		- location: Nationale Opera & Ballet, Amsterdam
	}
	class PerformanceRole["Mrs. Jones"] {
		<<PerformanceRole>>
		- characterName: Mrs. Jones
        - roleName sopraan
	}
	class PerformanceRole2["Mrs. Jones"] {
		<<PerformanceRole>>
		- characterName: Mrs. Jones
		- roleName sopraan  
	}
	class Persoon["Francis van Broekhuizen"] {
		<<Persoon>>
	}
    class Persoon2["understudy"] {
        <<Persoon>>
    }
    class Persoon3["Damiano Michieletto"] {
        <<Persoon>>
    }
    class Persoon4["Wout van Tongeren"] {
        <<Persoon>>
    }
	class Producent["Nationale Opera & Ballet"] {
		<<Organization>>
		- additionalType: Opera, ballet
		- location: Amsterdam
	}
    class BackstageRole["dramaturg"] {
        <<Role>>
        - roleName dramaturg
    }

	PerformanceWork --> PerformanceRole: performer
	PerformanceRole --> Persoon: performer
    PerformanceWork --> BackstageRole: contributor
	PerformanceWork --> Producent: creator
    PerformingArtsEvent --> PerformanceWork: workPerformed
	PerformingArtsEvent --> PerformanceRole2: performer
	PerformingArtsEvent --> Persoon3: director
	PerformanceRole2 --> Persoon2: performer
	BackstageRole --> Persoon4: contributor

	

```

## Gerelateerde patronen
Bezoeker