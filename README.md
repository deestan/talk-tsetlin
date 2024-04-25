Format: A3 tusj

# Why interesting! - fokus begrensinger
- TANKE: ML på en Commodore 64?
- lite minne
- pluss/minus/xor/and i16: 6 sykler OPCODES: ADC, SBC, EOR, AND
- Multiply i8: 149 sykler
- Multiply f40: 1400 sykler

# Løsning: sushi med nerder - kort
- Meg [alt det der]
- Johannes: Åja! Tsetlinmaskiner.

# Sneak peek! - fokus operasjoner
- Stor Tsetlinmaskin som finner kreft x 100000
- lærer! bruker 54 bytes (108 4-bits heltall)! REM 18 (9x2) inputs, 4-bits (8x2) minne, 6 clauses

# What historical!
- Michael Lvovitch Tsetlin (1924-1966), Sovjetisk matematiker og fysiker
  oppfant algoritme som lærte "online", minne på ett heltall, og kunne ombestemme seg
  kombinerte algoritmene for å løse komplekse problemer
- Ole-Christoffer Granmo of Agder
  Tok opp tråden for å få "moderne ML" ut av dette, videreutviklet "Tsetlin Machine"
  klassifisering, mønster, bildegjenkjenning, convolution, deep, recurrent...

# Metaforane

# Butt up explanation

## Automaton
- TEGN 1
- input literal "has 4 wheels"
- output "det er relevant for å vite om det er en bil"

## Automaton
- [TEGN 3 - sikker relevant, usikker, sikker irrelevant]
- Holds opinion on literal relevancy for a clause
- low values are certainly irrelevant
- high values are certainly relevant
- middle is uncertain
- ONLY MOVABLE PART - i.e. can be trained

## Clause
- [STOR TEGNING]
- gets all literals
- considers only those used by automata
- AND-SUM, 0 or 1

## Machine
- [STOR TEGNING] har symboler på PLUSS og AND
- Boolean inputs mapped to literals
- classify A / NOT A
- confidence metric
- majority vote via integer sum of clauses

# Example of a Tsetlin machine in action - car classifier?
- pre-trained? næ
- si explainable

## strukturer input av månelander
- [ill: månelander, terreng]
- vis ren inputdata, strukturer det til bools
- input fart-opp[0-1,1-5,>5], fart-ned[0-1,1-5,>5], over-flatt-terreng, avstand-bakke[<5,5-50,>50]
- literaler! inn i boks! ut igjen er yesno for bremserakett!

## Maskinene kan forklare seg!
- [ill: månelander]
- MASKIN SOM KLASSIFISERER "LANDEREN SKAL GI FART OPPOVER"
- Regler:
- PÅ: lander er ikke over flatt terreng
- PÅ: hastighet oppover er under 1m/s OG avstand til bakken er under 5 meter
- AV: hastighet nedover er under 10m/s OG avstand til bakken er over 50 meter
- AV: hastighet nedover er under 1m/s OG avstand til bakken er under 5 meter
- Hvorfor aktiverte du ikke bremseraketten HER?
- fordi: AV: hastighet nedover er under 10m/s OG avstand til bakken er over 50 meter
         PÅ: lander er ikke over flatt terreng
- Hvorfor aktiverte du bremseraketten HER?
- fordi: AV: hastighet nedover er under 1m/s OG avstand til bakken er under 5 meter
         PÅ: hastighet oppover er under 1m/s OG avstand til bakken er under 5 meter
         PÅ: lander er ikke over flatt terreng

# How to train yes?
- [ill: Tsetlinmaskin med noen clauses]
## NOTES TO SELF
- Komplekst å gå gjennom
- interessante paralleller til Game Theory og Markov Chains!
- but do a a live example
- GRÅÅÅVT SÆTT: oppsummer fra kilde: True negative clause output is ignored to increase the freedom of the automata. By
  progressively suppressing false negative and false positive clause output, and reinforcing true
  positive clause output, we intend to guide the Tsetlin Automata towards maximizing pattern
  recognition accuracy. This guiding is based on what we will refer to as Type I and Type II
  Feedback.

# other cool shit
- convolution, deep machines, recurrent machines
- teams of macheeans / composites and confidences

# kilder og mer info:
- kode https://github.com/cair/tmu
- introduksjonsbok WIP http://tsetlinmachine.org
- pågåenge forskningsprosjekt https://prosjektbanken.forskningsradet.no/en/project/FORISS/312434
