# Patroon: Gerelateerd werk

## Context
Je wilt vastleggen dat een werk aan een ander werk is gerelateerd, waarbij het gerelateerde werk aan een persoon verbonden is. 

## Structuur

```mermaid
---
title: Patroon 'Gerelateerd werk expliciet geïdentificeerd'
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction LR
	Werk1 --> Werk2: has (some) work
	Werk2 --> Role: has (some) agent
	Role --> Persoon: has (some) agent

class Werk1["Werk"]

class Werk2["Werk"]

class Role{
 -roleName
}

```

```mermaid
---
title: Patroon 'Gerelateerd werk impliciet'
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction LR	
	Werk1 --> Role: has (some) agent
	Role --> Persoon: has (some) agent

class Werk1["Werk"]

class Role{
 -roleName
}

```

## Voorbeeld

```mermaid
---
title: Voorbeeld van het patroon 'Gerelateerd werk expliciet geïdentificeerd'
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction LR
	Werk1 --> Werk2: has libretto work
	Werk2 --> Role1: has author agent
	Werk2 --> Role2: has author agent
	Role1 --> Persoon1: has author agent
	Role2 --> Persoon2: has author agent

class Werk1["Animal farm"] {
	<<Muziektheaterstuk>>
	- has type: Work
	- has category of work: Opera
	- has title of work: Animal Farm
}

class Werk2["Animal farm"] {
	<<Libretto>>
	- has type: Work
	- has category of work: Libretto
	- has title of work: Animal Farm
}


class Role1 ["Role"]{
 -roleName: auteur van tekst
}

class Role2 ["Role"]{
 -roleName: auteur van concept
}

class Persoon1 ["Ian Burton"]
class Persoon2 ["Alexander Raskatov"]

```

```mermaid
---
title: Voorbeeld van het patroon 'Gerelateerd werk impliciet'
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction LR	
	Werk1 --> Role1: has librettist agent
	Werk1 --> Role2: has librettist agent
	Role1 --> Persoon1: has librettist agent
	Role2 --> Persoon2: has librettist agent

class Werk1["Animal farm"] {
	<<Muziektheaterstuk>>
	- has type: Work
	- has category of work: Opera
	- has title of work: Animal Farm
}

class Role1 ["Role"]{
 -roleName: auteur van tekst
}

class Role2 ["Role"]{
 -roleName: auteur van concept
}

class Persoon1 ["Ian Burton"]
class Persoon2 ["Alexander Raskatov"]

note "De 'has librettist agent'-relaties zijn 'shortcut-properties'<br />die - als alternatief - gebruikt kunnen worden indien<br />het libretto niet als eigenstandig werk is geïdentificeerd / geregistreerd."

```

## Gerelateerde patronen
-
