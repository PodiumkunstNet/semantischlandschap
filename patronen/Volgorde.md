# Patroon: volgorde
## Context
Volgorde uitvoeringen (bv. tracks cd)
Uitwerking in schema.org

## Structuur
```mermaid
---
title: Patroon 'Volgorde'
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction RL
    MusicRecording --> MusicAlbum: inAlbum
    MusicRecording --> MusicComposition: recordingOf
    MusicComposition --> MusicComposition: includedComposition
    MusicComposition --> Person: composer
class MusicAlbum{
    Text: name
    Integer: numTracks
    MusicRecording: track
}
class MusicRecording{
    Text: name
    Integer: position
}
class MusicComposition{
    Text: name
    Person: composer
}
class Person{
    Text: name
}
class PerformingArtsEvent{
    Text: name
    MusicComposition: workPerformed
}
```

## Voorbeeld
A CD from the Muziekweb collection has been modeled as MusicAlbum in schema.org. A MusicAlbum is derived from MusicPlaylist, which is derived from CreativeWork. A MusicPlaylist can contain several MusicRecordings, each having a 'position' property. By ordering the values of the position property (ascending) the MusicRecordings (the tracks of the CD) can be played in the right order (as they are listed on the CD). 

Each MusicRecording can be linked to a MusicComposition using the property 'recordingOf'. Each track in this example is a recording of a part of the Symphony. Therefor, the MusicComposition that is linked to the MusicRecording is modeled with the 'includedComposition' property that links the part to the whole.

The whole Symphony (the Work) being modeled as MusicComposition has a 'composer' property that links the composer Person to the Work.

Note: For simplicity, we only modeled two tracks, where the CD has four tracks (and the Symphony four parts, or movements).

Note: The recording on this CD can not be modeled as PerformingArtsEvent, because it was not registered in front of an audience. It could be modeled as being a MusicEvent, but that is not part of this example.


```mermaid
---
title: uitwerking Patroon 'Volgorde' met voorbeeld Mahler's Symfonie nr.1 in D gr.t., "Titan"
config:
 class:
  hideEmptyMembersBox: true
---
classDiagram
	direction RL
    MusicRecordingI --> MusicAlbum: inAlbum
    MusicRecordingII --> MusicAlbum: inAlbum
    MusicRecordingI --> MusicCompositionI: recordingOf
    MusicRecordingII --> MusicCompositionII: recordingOf
    MusicCompositionI --> MusicCompositionWork: includedComposition
    MusicCompositionII --> MusicCompositionWork: includedComposition
    MusicCompositionWork --> Person: composer

class MusicAlbum["Symphony no.1"]{
    <<MusicAlbum>>
    - id: AAX9232
    - name: Symphony no.1
    - numTracks: 4
}
class MusicRecordingI{
    <<MusicRecording>>
    - id: AAX9232-0001
    - name: Symfonie nr.1 in D gr.t., "Titan" deel I
    - position: 1
}
class MusicRecordingII{
    <<MusicRecording>>
    - id: AAX9232-0002
    - name: Symfonie nr.1 in D gr.t., "Titan" deel II
    - position: 2
}

class MusicCompositionI{
    <<MusicComposition>>
    - name: Symfonie nr.1 in D gr.t., "Titan" deel I
    - id: U00000582955-0001
}
class MusicCompositionII{
    <<MusicComposition>>
    - name: Symfonie nr.1 in D gr.t., "Titan" deel II
    - id: U00000582955-0002
}
class MusicCompositionWork{
    <<MusicComposition>>
    - id: U00000582955
    - name: Symfonie nr.1 in D gr.t., "Titan"
}
class Person{
    <<Person>>
    - name: Gustav Mahler
    - id:
}
```


## Gerelateerde patronen