# Pladser

**Pladser** er en enkel lokal HTML-app til at fordele elever på siddepladser i en spisesal.

Appen tager udgangspunkt i skolens eksisterende grupperinger – fx teams, profilfag, rejsehold eller valgfag – og omsætter dem til en fysisk bordplan, som efterfølgende kan justeres manuelt.

## Funktioner

- Import af elevdata fra Excel-regneark
- Automatisk sammensætning af elevnavne fra fornavn og efternavn
- Genkendelse og klassificering af grupper
- Valgfrit fordelingsgrundlag
- Fordeling af hver gruppe over tre borde
- 10 siddepladser pr. bord
- Manuel flytning og bytning af elever
- Bytning af hele borde med elever og gruppetilknytning
- Låsning af enkelte elevplaceringer
- Låsning af alle elevplaceringer ved et bord
- Skjulbart sidepanel, så hele spisesalen kan ses under redigering
- Rent A3-printlayout
- PDF-generering og native deling
- Forberedt til integration med Plan 2.0

## Regnearksformat

Pladser kan importere elevdata fra et regneark med bl.a. følgende kolonner:

- `Fornavn`
- `Efternavn`
- `Grupper`
- `Studenthouse`

Elevens navn dannes af `Fornavn` + `Efternavn`.

### Grupper

Kolonnen `Grupper` kan indeholde flere linjeseparerede gruppetilhørsforhold for samme elev.

Eksempel:

    Team 1 MM/TK
    Badminton
    Madkunst

De forskellige gruppenavne kan klassificeres efter type, så brugeren kan vælge, hvilket princip bordfordelingen skal tage udgangspunkt i.

Det kan fx være:

- Teams
- Profilfag
- Rejsehold
- Valgfag
- Andre relevante gruppeformer

`Studenthouse` behandles særskilt og svarer til elevens gang.

## Bord- og gruppestruktur

Spisesalen består af 18 borde med 10 pladser ved hvert bord.

En valgt gruppe knyttes til et område bestående af tre borde. Det giver op til 30 pladser til gruppen.

Fordelingen foregår altid **inden for gruppens tre borde** – ikke på tværs af hele spisesalen.

## Fordelingsprincip

Pladser forsøger at skabe en brugbar social placering frem for blot at fylde ledige stole.

En central regel er:

> Elever skal så vidt muligt have en anden elev siddende direkte overfor sig.

Fordeleren prioriterer derfor:

1. At udfylde en tom plads overfor en elev, der allerede sidder alene.
2. At placere nye elever som modstående par.
3. At fordele disse par hensigtsmæssigt mellem gruppens tre borde.
4. Kun at efterlade elever uden en elev overfor, når elevtal, låste placeringer eller andre begrænsninger gør det nødvendigt.

Eksempel:

- 24 elever → 8 / 8 / 8
- 25 elever → 9 / 8 / 8
- 26 elever → 10 / 8 / 8 frem for 9 / 9 / 8

Ved 26 elever betyder 10 / 8 / 8, at alle elever kan få en elev overfor.

## Manuel redigering

Den automatiske fordeling er et udgangspunkt.

Efter fordelingen kan brugeren justere bordplanen manuelt.

### Flyt elever

Elever kan markeres og byttes mellem pladser.

### Flyt borde

Hele bordområder kan markeres og byttes.

Når et bord flyttes, følger følgende med:

- eleverne
- gruppetilknytningen
- områdets farve

Bordet er dermed stadig en del af sin oprindelige gruppe, selv om det fysisk flyttes til en anden position i spisesalen.

### Lås placeringer

Elevplaceringer kan låses, så den automatiske fordeling ikke ændrer dem.

Det er også muligt at låse elevplaceringerne ved et helt bord via gruppetitlen.

Låste placeringer respekteres ved efterfølgende fordelinger.

## Print og PDF

Pladser har et separat printlayout beregnet til **A3**.

Printvisningen er bevidst enklere end redigeringsinterfacet:

- ingen kontroller
- ingen sidepaneler
- ingen redigeringsmarkeringer
- større og tydeligere elevnavne
- bordplanen udnytter A3-formatet
- elevens side af bordet skal fortsat kunne aflæses

PDF kan genereres og deles via systemets native delingsfunktion.

## Lokal behandling

Pladser er bygget som en enkel HTML-app.

Elevdata behandles lokalt i browseren. Appen kræver ikke en AI-model for at foretage fordelingen.

Det gør Pladser velegnet både som selvstændigt værktøj og som en mindre app inde i et større skolesystem.

## Plan 2.0

Pladser er udviklet med henblik på også at kunne indgå i **Plan 2.0**.

Målet er, at Pladser både skal kunne:

- importere sine egne stamdata
- modtage relevante stamdata fra Plan 2.0
- sende genererede dokumenter/PDF'er videre gennem Plan 2.0's bridge

Integrationen udvikles løbende.

## Status

Pladser er under aktiv udvikling.

Den nuværende prototype fokuserer især på:

- robust gruppebaseret elevfordeling
- socialt fornuftige placeringer
- manuel efterredigering
- låsning og bytning
- læsevenligt A3-output
- integration med Plan 2.0
