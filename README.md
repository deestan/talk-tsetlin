Format: A3 tusj

# Why interesting!
- TANKE: ML på en Commodore 64?
- lite minne
- pluss/minus/xor/and i16: 6 sykler OPCODES: ADC, SBC, EOR, AND
- Multiply i8: 149 sykler
- Multiply f40: 1400 sykler

# Løsning: sushi med nerder
- Meg [alt det der]
- Johannes: Åja! Tsetlinmaskiner.

# What historical!
- Michael Lvovitch Tsetlin (1924-1966), Sovjetisk matematiker og fysiker
  oppfant algoritme som lærte "online", minne på ett heltall, og kunne ombestemme seg
  kombinerte algoritmene for å løse komplekse problemer
- Ole-Christoffer Granmo of Agder
  Tok opp tråden for å få "moderne ML" ut av dette, videreutviklet "Tsetlin Machine"
  klassifisering, mønster, bildegjenkjenning, convolution, deep, recurrent...

# Metaforane

## Maskinene kan forklare seg!
- [ill: månelander]
- MASKIN SOM KLASSIFISERER "LANDEREN SKAL GI FART OPPOVER"
- Hvorfor aktiverte du ikke landingsmotoren HER?
- fordi: AV: hastighet nedover er under 10m/s OG avstand til bakken er over 50 meter
         PÅ: lander er ikke over flatt terreng
- Hvorfor aktiverte du landingsmotoren HER?
- fordi: AV: hastighet nedover er under 1m/s OG avstand til bakken er under 5 meter
         PÅ: hastighet oppover er under 1m/s OG avstand til bakken er under 5 meter
         PÅ: lander er ikke over flatt terreng

# Top down explanation

## Machine
- [STOR TEGNING] har symboler på PLUSS og AND
- Boolean inputs mapped to literals
- classify A / NOT A
- confidence metric
- majority vote via integer sum of clauses

## Clause
- [STOR TEGNING]
- gets all literals
- considers only those used by automata
- AND-SUM, 0 or 1

## Automaton
- [TEGN 3 - sikker relevant, usikker, sikker irrelevant]
- Holds opinion on literal relevancy for a clause
- low values are certainly irrelevant
- high values are certainly relevant
- middle is uncertain
- ONLY MOVABLE PART - i.e. can be trained

# Example of a Tsetlin machine in action - car classifier?
- pre-trained!

# How to train yes?
- Komplekst å gå gjennom
- interessante paralleller til Game Theory og Markov Chains!
- but do a a live example
- GRÅÅÅVT SÆTT: oppsummer fra kilde: True negative clause output is ignored to increase the freedom of the automata. By
  progressively suppressing false negative and false positive clause output, and reinforcing true
  positive clause output, we intend to guide the Tsetlin Automata towards maximizing pattern
  recognition accuracy. This guiding is based on what we will refer to as Type I and Type II
  Feedback.

# Explainable yes!
- Rewrite trained car identifier logic to English

# other cool shit
- convolution, deep machines, recurrent machines
- teams of macheeans / composites and confidences

# kilder og mer info:
- kode https://github.com/cair/tmu
- introduksjonsbok WIP http://tsetlinmachine.org
- pågåenge forskningsprosjekt https://prosjektbanken.forskningsradet.no/en/project/FORISS/312434
