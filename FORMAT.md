# FORMAT.md
This file describes the specifications of possible file formats for the Diorite project. THIS IS A WORK IN PROGRESS

# TODO
- [ ] Decide whether to use scientific notation for note pitches or a more intuitive system based on the A notes

# Extensions
Possible custom file extensions
- .dt

# Formatting (actively changing)
All items can and should be seperated by a certain symbol (probably the pipe "|" or a comma) but should also be optional whenever possible such as in this example: "2{CDE}" which would be a walkup of half notes C, D, and E.

Sets of brackets and braces should always be seperated from each other. For example: "[{}|{}]|[{}]"
## Comments
Comments should use two slashes "//"
## Measures
Measures should be designated by brackets.
## Clefs
Clefs should be described inside measures using the following:

- A three-letter name of the clef (if none is specified then notes should automatically default to the closest one):
    - Tre: Treble
    - Bas: Bass
    - Alt: Alto
    - Ten: Tenor
    - Neu: Neutral
    - Tab: Guitar Tab

If a clef is specified in a piece but is empty in a certain measure, it should be automatically populated by a single rest of the measure length (usually a whole rest)

### Possible bass clef viewed in a terminal
(I know I'm bad at ASCII please don't hurt my feelings >_<)
```
				_____
          -=-.* _____
         '*  |* _____
           .'   _____
          ~'    _____
```
## Rests
Rests should be described using the following:

- A number for duration (default to 1)
- The letter 'R'
## Notes
Notes should be described using the following :

- A number for duration (default to 1)
- A letter for pitch (not caps sensitive)
- A sign to denote whether a note should be sharp or flat (optional)
- A number to denote the octave (default to 4)

Any modifiers for a note can be put outside a set of curly braces.
### Chords
*TODO*
### Examples
- A whole middle C sharp note would be "1C+4" or just "C+".
- A half middle D flat note would be "2D-4" or just "2D-".
- Two quarter middle C notes would be "4C4|4C4", "4C|4C", or just "4{C|C}".

## Für Elise in Current Format
*Based on the first five measures of [this](https://upload.wikimedia.org/wikipedia/commons/2/27/Beethoven_WoO_59_Erstausgabe.png) sheet music*
(This should be updated whenever a change is made to the Diorite format)

```
[16{ED+}5] | [16{ {ED+E}5 | B4D+5C5 }] | [{8A 16{RCEA}}4] | [{8B 16{REG+B}}4] | [8C5 | 16{RE4E5D+5}]
```

```
// Expanded //
[ // Measure 1 //
    16{
    E
    D+
    }5
]|
[ // Measure 2 //
    16{
        {
        E
        D+
        E
        }5|
        B4
        D+5
        C5
    }
]|
[ // Measure 3 //
    {
        8A
        16{
            R
            C
            E
            A
        }
    }4
]|
[ // Measure 4 //
    {
        8B
        16{
            R
            E
            G+
            B
        }
    }4
]|
[ // Measure 5 //
    8C5|
    16{
        R
        E4
        E5
        D+5
    }
]
```
