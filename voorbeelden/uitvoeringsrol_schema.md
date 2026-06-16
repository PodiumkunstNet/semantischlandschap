# Voorbeeld: Uitvoeringsrol

## Context
Het vastleggen van de rol van een uitvoerende in schema.org.

Er is een keuze gemaakt om alle rollen - waar specificatie nodig is - vast te leggen via de schema:Role of PerformanceRole class. 
Zowel bij de Productie als de uitvoering; dus van een PerformingArtsEvent wordt niet rechtstreeks de property "director" gebruikt, omdat je dat vaak voor een productie-seizoen (PerformanceWork/CreativeWork) wilt vastleggen, wat die director property niet heeft.  
Dus zie onderstaand voorbeeld voor die modellering.

Note: de additionalTypes en de rollen hieronder zijn uitgeschreven maar dat moeten termen uit een (theater)thesaurus worden.

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
    class BackstageRole2["director"] {
        <<Role>>
        - roleName director
    }

	PerformanceWork --> PerformanceRole: performer
    PerformanceWork --> BackstageRole: contributor
    PerformanceWork --> BackstageRole2: contributor
	PerformanceWork --> Producent: creator
	PerformanceRole --> Persoon: performer
	PerformanceRole2 --> Persoon2: performer
    PerformingArtsEvent --> PerformanceWork: workPerformed
	PerformingArtsEvent --> PerformanceRole2: performer
	BackstageRole --> Persoon4: contributor
	BackstageRole2 --> Persoon3: contributor

	

```

## Gerelateerde patronen
Bezoeker