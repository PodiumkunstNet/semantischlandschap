```mermaid
---
title: Voorbeeld van het patroon 'Uitvoeringsrol'
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction TD
	class Productieprogrammauitvoering["Animal Farm 2022-2023"] {
		<<Productieprogrammauitvoering>>		
		- has type: Expression
		- has category of expression: Productieseizoen
		- has title of expression: Animal Farm 2022-2023
		- timespan: 2022-2023
	}
	class Uitvoering["Animal Farm"] {
		<<Uitvoering>>		
		- has type: Expression
		- has category of expression: Operauitvoering
		- has category of expression: Première
		- has title of expression: Animal Farm
		- datum: 3 maart 2023
		- locatie: Nationale Opera & Ballet, Amsterdam
	}
	class PerformanceRole["Mrs. Jones"] {
		<<PerformanceRole>>
		- characterName: Mrs. Jones
		- zangstem: sopraan  
	}
	class PerformanceRole2["Mrs. Jones"] {
		<<PerformanceRole>>
		- characterName: Mrs. Jones
		- zangstem: sopraan  
	}
	class PerformanceRole3["2e Mrs. Jones"] {
		<<PerformanceRole>>
		- characterName: 2e Mrs. Jones
		- zangstem: sopraan  
	}
	class MrsJones["Mrs. Jones"] {
		<<Schema:Person>>
		- name: Mrs. Jones
		- description: "The wife of the negligent 
		  Manor Farm owner, Mr. Jones."		
	}
	class MrJones["Mr. Jones"] {
		- name: Mr. Jones
		- jobTitle: farmer
		- description: "The alcoholic master of Manor Farm 
		  who mistreats his animals, prompting them to rebel
		  and take control of the farm."
	}
	class Book["Animal Farm"] {
		<<Schema:Book>>
		- name: Animal Farm
		- datePublished: 1945
		- description: "A satirical allegorical novel by  
		  George Orwell about a group of farm animals who 
		  overthrow their human farmer, hoping to
		  create a society where the animals can be 
		  equal, free, and happy."
	}
	class Persoon["Francis van Broekhuizen"] {
		<<Persoon>>
	}
	class Persoon2["Iemand anders"] {
		<<Persoon>>
	}
		
	Productieprogrammauitvoering --> PerformanceRole: has actor
	Productieprogrammauitvoering --> Uitvoering: omvat
	Persoon <-- PerformanceRole: has actor
	Uitvoering --> PerformanceRole2: has actor
	Persoon2 <-- PerformanceRole2: has actor
	Productieprogrammauitvoering --> PerformanceRole3: has actor
	Persoon2 <-- PerformanceRole3: has actor
	PerformanceRole --> MrsJones: character
	PerformanceRole2 --> MrsJones: character
	PerformanceRole3 --> MrsJones: character
	MrsJones --> MrJones: spouse
	MrsJones <-- MrJones: spouse
	MrJones <-- Book: character	
	MrsJones <-- Book: character	
	
	note for Persoon "Persoon betrokken in een 
					bepaalde rol bij (in principe) 
					alle uitvoeringen in het kader 
					van de programmauitvoering."
	
	note for Persoon2 "Persoon betrokken in een 
						bepaalde rol bij een specifieke
						uitvoering. 
						(Dezelfde persoon kan - in een 
						andere rol - betrokken zijn bij 
						de gehele productie- 
						programmauitvoering.)" 


```
