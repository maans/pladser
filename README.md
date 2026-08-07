# Pladser

**Pladser** er en lokal HTML-app til at fordele elever på siddepladser i en spisesal.

Appen tager udgangspunkt i skolens eksisterende elevdata og grupperinger – fx teams, gange, linjefag, rejsehold eller valgfag – og omsætter dem til en fysisk bordplan, som efterfølgende kan justeres manuelt.

Pladser kan bruges som selvstændig webapp eller integreret som HTML-app i **Plan 2.0**.

## Funktioner

- Import af elevdata fra Excel-regneark
- Modtagelse af stamdata direkte fra Plan 2.0
- Automatisk sammensætning af elevnavne fra fornavn og efternavn
- Genkendelse og klassificering af grupper
- Valgfrit fordelingsgrundlag
- Fordeling af hver gruppe over tre borde
- 10 siddepladser pr. bord
- Fordeling med hensyn til, at elever så vidt muligt har nogen siddende overfor
- Manuel flytning og bytning af elever
- Bytning af hele borde med elever og gruppetilknytning
- Låsning af enkelte elevplaceringer
- Låsning af alle elevplaceringer ved et bord
- Skjulbart sidepanel, så hele spisesalen kan ses under redigering
- Separat og læsevenligt A3-printlayout
- PDF-generering og native deling
- PDF-overførsel til Plan 2.0

## Stamdata

Pladser kan få sine stamdata på to måder:

1. **Fra Plan 2.0**, når Pladser åbnes som en integreret HTML-app.
2. **Fra et Excel-regneark**, når Pladser bruges selvstændigt eller som fallback.

Det betyder, at den samme Pladser-app kan fungere både inde i Plan 2.0 og som selvstændigt værktøj.

## Regnearksformat

Ved manuel import kan Pladser læse elevdata fra et regneark med bl.a. følgende kolonner:

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
- Linjefag
- Rejsehold
- Valgfag
- Andre relevante gruppeformer

`Studenthouse` behandles særskilt og svarer til elevens gang.

## Bord- og gruppestruktur

Spisesalen består af 18 borde med 10 pladser ved hvert bord – i alt 180 pladser.

Et valgt fordelingsgrundlag opdeler eleverne i grupper. Hver gruppe knyttes til et område bestående af tre borde og har dermed op til 30 pladser.

Fordelingen foregår altid **inden for gruppens tre borde** – ikke på tværs af hele spisesalen.

Bordområdernes titler følger den valgte gruppe. Hvis der fx fordeles efter gange, kan tre borde derfor alle være mærket `Gimle`, mens en anden gruppe på tre borde fx hedder `Hjemstavn`.

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

Den automatiske fordeling er et udgangspunkt. Efter fordelingen kan bordplanen justeres manuelt.

### Flyt elever

Elever kan markeres og byttes mellem pladser.

### Flyt borde

Hele borde kan markeres og byttes.

Når et bord flyttes, følger følgende med:

- eleverne
- gruppetilknytningen
- områdets farve

Bordet er dermed stadig en del af sin oprindelige gruppe, selv om det fysisk flyttes til en anden position i spisesalen.

### Lås placeringer

Elevplaceringer kan låses, så den automatiske fordeling ikke ændrer dem.

Det er også muligt at låse elevplaceringerne ved et helt bord via bordets gruppetitel.

Låste placeringer respekteres ved efterfølgende fordelinger.

## Brugerflade

Pladser er opdelt i to hovedområder:

- et sidepanel til fordeling, indstillinger og kontrol
- selve spisesalen, hvor bordplanen redigeres visuelt

Sidepanelet kan skjules, så hele spisesalen kan udnytte vinduets bredde.

De funktioner, der bruges til den normale arbejdsgang, er placeret mest fremtrædende, mens klassificering af grupper, kobling mellem grupper og bordområder samt andre opsætningsfunktioner kan holdes samlet som indstillinger.

## Print og PDF

Pladser har et separat printlayout beregnet til **A3**.

Printvisningen er bevidst enklere end redigeringsinterfacet:

- ingen redigeringskontroller
- intet sidepanel
- ingen redigeringsmarkeringer
- tydelige elevnavne
- maksimal udnyttelse af A3-formatet
- elevens side af bordet kan fortsat aflæses

PDF'en genereres fra Pladsers egen bordplan og kan deles via systemets native delingsfunktion.

Når Pladser kører inde i Plan 2.0, kan den genererede PDF desuden overføres til Plan 2.0 gennem integrationen mellem de to apps.

## Lokal behandling

Pladser er bygget som en selvstændig HTML-app.

Elevdata og selve fordelingsberegningen behandles lokalt. Appen kræver ikke en AI-model eller en ekstern beregningstjeneste for at foretage bordfordelingen.

Det gør Pladser velegnet både som selvstændigt værktøj og som et modul i et større skolesystem.

## Integration med Plan 2.0

Pladser kan indgå som HTML-app i **Plan 2.0**.

Integrationen understøtter i dag to centrale dataretninger:

**Plan 2.0 → Pladser**

Pladser kan modtage skolens stamdata direkte fra Plan 2.0 og bruge dem som grundlag for bordfordelingen.

**Pladser → Plan 2.0**

Pladser kan generere en PDF af den færdige bordplan og sende den videre til Plan 2.0 via den native bridge/dataoverførsel.

Hvis Pladser ikke modtager stamdata fra Plan 2.0, kan brugeren fortsat importere et regneark manuelt.

Dermed er Pladser ikke afhængig af Plan 2.0 for at fungere.

## Arkitektur

Pladser er bevidst udviklet som en relativt selvstændig HTML-app.

Det giver en enkel integrationsmodel:

- appen kan udvikles og testes selvstændigt
- den kan hostes og bruges direkte i en browser
- den kan indlejres som HTML-app i Plan 2.0
- stamdata kan leveres af værtsprogrammet
- resultater kan sendes tilbage gennem en bridge
- den grundlæggende funktionalitet er ikke afhængig af værtsprogrammet

Denne model gør det muligt at udvikle mindre specialiserede værktøjer som selvstændige HTML-apps og efterfølgende integrere dem i Plan 2.0.

## Status

Pladser er under aktiv udvikling, men den centrale arbejdsgang fungerer:

**stamdata → valg af grupper → automatisk fordeling → manuel tilpasning → A3/PDF**

Den nuværende udvikling fokuserer især på:

- forbedring og forenkling af brugerfladen
- robust gruppebaseret elevfordeling
- socialt hensigtsmæssige placeringer
- manuel efterredigering
- låsning og bytning
- læsevenligt A3-output
- tættere integration med Plan 2.0

Et naturligt næste trin er at kunne gemme selve den redigerbare bordplan som et **Pladser-datasæt**, så en placering senere kan åbnes og redigeres videre i stedet for kun at eksistere som PDF.
