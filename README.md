# .docx Tekstmanipulasjonsverktøy

Dette repositoriet inneholder to Python-skript for å manipulere tekst i `.docx`-filer. Det første skriptet fjer_tekst er designet for å fjerne tekst som befinner seg mellom "med" og "konsulenter", inkludert disse ordene, fra både paragrafer og tabeller i et `.docx`-dokument. Det andre fjern_eller_erstatt tilbyr en mer fleksibel løsning for å søke og erstatte basert på regulære uttrykk.

## 1. Fjern Spesifikk Tekst

### Beskrivelse

`fjern_tekst.py` er et skript designet for å fjerne tekst mellom "med" og "konsulenter", inkludert disse ordene, fra både paragrafer og tabeller i et `.docx`-dokument.

### Bruk

For å bruke skriptet, sørg for at du har `python-docx` installert:

```bash
pip install python-docx
```

Kjør skriptet ved å oppgi stien til input- og output-filen som argumenter:

```bash
python3 fjern_tekst.py <input_file.docx> <output_file.docx>
```

## 2. Fleksibelt Søk og Erstatt

### Beskrivelse

`fleksibelt_sok_og_erstatt.py` er et mer avansert verktøy som lar brukeren spesifisere et søkemønster (som et regulært uttrykk) og en valgfri erstatningstekst. Dette skriptet kan manipulere tekst i både paragrafer og tabeller i et `.docx`-dokument.

### Bruk

Før du kjører dette skriptet, installer `python-docx` hvis du ikke allerede har gjort det:

```bash
pip install python-docx
```

Bruk skriptet ved å følge denne syntaksen:

```bash
python3 fleksibelt_sok_og_erstatt.py <input_file.docx> <output_file.docx> <soke_pattern> [--erstatt_med <erstatningstekst>]
```

Hvis --erstatt_med ikke er spesifisert, vil teksten som matcher mønsteret bli fjernet fra dokumentet.

Eksempler

For å fjerne tekst mellom "med" og "konsulenter":

```bash
python3 fleksibelt_sok_og_erstatt.py dinfil.docx nyfil.docx "med \w{1,4} konsulenter"
```

For å erstatte tekst mellom "med" og "konsulenter" med "XYZ":

```bash
python3 fleksibelt_sok_og_erstatt.py dinfil.docx nyfil.docx "med \w{1,4} konsulenter" --erstatt_med "XYZ"
```
