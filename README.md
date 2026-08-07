# Pladser

**Pladser** er en lokal app til at fordele elever på siddepladser i en spisesal.

Appen tager udgangspunkt i skolens eksisterende elevdata og grupperinger – fx teams, gange, linjefag, rejsehold eller valgfag – og omsætter dem til en fysisk bordplan.

Den automatiske fordeling er et udgangspunkt. Bordplanen kan bagefter tilpasses manuelt, låses, gemmes, genbruges og udskrives som A3/PDF.

Pladser kan bruges som selvstændig webapp eller integreret som HTML-app i **Plan 2.0**.

## Funktioner

- Import af elevdata fra Excel-regneark
- Modtagelse af stamdata direkte fra Plan 2.0
- Automatisk sammensætning af elevnavne fra fornavn og efternavn
- Genkendelse og klassificering af grupper
- Valgfrit fordelingsgrundlag
- Fordeling af elevgrupper over et passende antal borde
- 10 siddepladser pr. bord
- Mulighed for manuelt at justere, hvor mange borde en gruppe råder over
- Fordeling med hensyn til elever siddende overfor hinanden
- Regler for bl.a. køn, teams og gange
- Mulighed for at sprede eller samle bestemte elevgrupper
- Rotation med udgangspunkt i en tidligere bordplan
- Manuel flytning og bytning af elever
- Bytning af hele borde med elever og gruppetilknytning
- Låsning af enkelte elevplaceringer
- Låsning af hele borde, inklusive eventuelle tomme pladser
- Gemte bordplaner, som kan åbnes, omdøbes og duplikeres
- Backup og gendannelse af gemte bordplaner
- Skjulbart sidepanel, så hele spisesalen kan ses under redigering
- Separat A3-printpreview
- PDF-generering og native deling
- PDF-overførsel til Plan 2.0

## Stamdata

Pladser kan få sine stamdata på to måder:

1. **Fra Plan 2.0**, når Pladser åbnes som en integreret HTML-app.
2. **Fra et Excel-regneark**, når Pladser bruges selvstændigt eller som fallback.

Det betyder, at den samme Pladser-app kan fungere både inde i Plan 2.0 og som selvstændigt værktøj.

## Regnearksformat

Ved manuel import kan Pladser læse elevdata fra et regneark med bl.a. følgende oplysninger:

- `Fornavn`
- `Efternavn`
- `Grupper`
- `Studenthouse`
- `Køn`

Elevens navn dannes af `Fornavn` + `Efternavn`.

Det er ikke nødvendigt, at alle oplysninger findes, for at Pladser kan bruges. Flere oplysninger giver blot mulighed for flere fordelingsregler.

### Grupper

Kolonnen `Grupper` kan indeholde flere gruppetilhørsforhold for samme elev.

Eksempel:

    Team 1 MM/TK
    Badminton
    Madkunst
    Drenge 26

De forskellige gruppenavne kan klassificeres efter type, så brugeren kan vælge, hvilket princip bordfordelingen skal tage udgangspunkt i.

Det kan fx være:

- Teams
- Linjefag
- Rejsehold
- Valgfag
- Andre relevante gruppeformer

`Studenthouse` behandles særskilt og svarer til elevens gang.

Køn kan i de nuværende Viggo-stamdata aflæses både fra kolonnen `Køn` og fra grupper som `Drenge 26` og `Piger 26`.

## Bord- og gruppestruktur

Spisesalen har 18 almindelige elevborde med 10 pladser ved hvert bord – i alt 180 elevpladser. Derudover indgår movebordet i den fysiske oversigt, men bruges ikke som almindeligt elevbord.

Et valgt fordelingsgrundlag opdeler eleverne i grupper. Hver gruppe tildeles et antal borde, der passer til gruppens størrelse. En mindre gruppe kan derfor have ét bord, mens en større gruppe kan have to, tre eller flere borde.

Antallet af borde kan justeres manuelt. Det er også muligt at samle flere grupper i samme bordområde.

Fordelingen foregår altid **inden for de borde, som gruppen er tildelt** – ikke på tværs af hele spisesalen.

Hvis der fx fordeles efter gange, kan et antal borde være knyttet til `Gimle`, mens andre borde er knyttet til `Hjemstavn`.

Bordene kan bagefter flyttes fysisk uden at miste deres gruppetilknytning.

## Automatisk fordeling

Pladser forsøger at skabe en brugbar social placering frem for blot at fylde ledige stole.

Et grundprincip er:

> Elever skal så vidt muligt have en anden elev siddende direkte overfor sig.

Fordeleren forsøger samtidig at holde de borde, som gruppen råder over, hensigtsmæssigt fyldt.

Hvis en gruppe fx råder over tre borde, kan en fordeling se sådan ud:

- 24 elever → 8 / 8 / 8
- 25 elever → 9 / 8 / 8
- 26 elever → 10 / 8 / 8

Ved 26 elever er 10 / 8 / 8 bedre end 9 / 9 / 8, fordi alle elever dermed kan få en elev siddende overfor.

## Fordelingsregler

Ud over den grundlæggende bordfordeling kan brugeren vælge regler for, hvordan eleverne skal blandes.

### Køn

Drenge og piger kan fordeles så ligeligt som muligt mellem gruppens borde.

### Team

Elever fra samme Team kan enten:

- spredes mellem bordene
- samles
- ignoreres som fordelingsregel

### Gang / Studenthouse

Elever fra samme gang kan tilsvarende spredes eller samles.

### Team og gang sammen

Pladser kan også tage højde for kombinationen af Team og gang.

Det gør det fx muligt at sprede elever, der både er på samme Team og bor på samme gang, selv om de enkelte Team- og gangregler er sat anderledes.

Reglerne er ønsker til den bedst mulige fordeling. De kan derfor ikke altid opfyldes fuldstændigt, hvis elevtal, låste placeringer eller andre hensyn står i vejen.

## Rotation fra en tidligere bordplan

En gemt bordplan kan markeres som **reference** for en ny fordeling.

Pladser kan derefter forsøge at give eleverne nye relationer og nye placeringer i forhold til den tidligere plan.

Der kan bl.a. tages hensyn til:

- andet bord
- anden side af bordet
- nye bordfæller
- ny sidemakker
- ny elev overfor

De enkelte rotationshensyn kan ignoreres, forsøges opfyldt eller prioriteres.

Formålet er ikke blot at flytte eleverne tilfældigt, men at skabe reel variation fra den tidligere bordplan.

En elev, der fx sad ved siden af og overfor bestemte elever sidst, vil så vidt muligt få andre elever omkring sig næste gang.

Pladser kan efter fordelingen vise, hvor meget den nye plan faktisk adskiller sig fra referenceplanen.

## Manuel redigering

Den automatiske fordeling er altid kun et udgangspunkt.

### Flyt elever

Elever kan markeres og flyttes eller byttes mellem pladser.

### Flyt borde

Hele borde kan markeres og byttes.

Når et bord flyttes, følger følgende med:

- eleverne
- gruppetilknytningen
- områdets farve

Bordet er dermed stadig en del af sin oprindelige gruppe, selv om det fysisk flyttes til en anden position i spisesalen.

### Lås elever og borde

Enkelte elevplaceringer kan låses.

Et helt bord kan også låses. Når et bord er låst:

- bliver eleverne ved bordet stående
- kan de tomme pladser ved bordet ikke bruges til andre elever
- respekteres bordet ved nye fordelinger

**Lås alle** låser alle borde, deres elevplaceringer og deres eventuelle tomme pladser.

**Lås alle op** frigiver dem igen.

## Gemte bordplaner

Bordplaner kan gemmes i Pladser og åbnes igen senere.

En gemt plan indeholder den redigerbare bordfordeling og er derfor ikke kun et færdigt PDF-billede af resultatet.

I oversigten over bordplaner kan planer bl.a.:

- åbnes
- omdøbes
- duplikeres
- slettes
- vælges som reference for en ny fordeling

Der kan desuden eksporteres og importeres backup af de gemte bordplaner.

Det gør det muligt både at bevare tidligere placeringer og bruge dem aktivt, når en ny bordplan skal laves.

## Brugerflade

Pladser består af to hovedområder:

- et sidepanel til fordeling, regler og indstillinger
- selve spisesalen, hvor bordplanen redigeres visuelt

Sidepanelet kan skjules, så hele spisesalen kan udnytte vinduets bredde.

De mest almindelige funktioner ligger fremme i den normale arbejdsgang, mens mere sjældne valg og opsætning er samlet under indstillinger.

Knappen **Om Pladser** viser denne beskrivelse direkte i appen, når der er internetforbindelse.

## Print og PDF

Pladser har et separat printlayout beregnet til **A3**.

Printvisningen er bevidst enklere end redigeringsvisningen:

- ingen redigeringskontroller
- intet sidepanel
- ingen låse- eller markeringssymboler
- tydelige elevnavne
- maksimal udnyttelse af A3-formatet
- elevens side af bordet kan fortsat aflæses

Elevnavnene placeres, så også lange navne kan udnytte pladsen hen over selve bordet uden unødigt at gå ind over nabobordene.

PDF'en kan deles via systemets normale delingsfunktion.

Når Pladser kører inde i Plan 2.0, kan PDF'en desuden sendes videre til Plan 2.0.

## Lokal behandling

Elevdata og selve fordelingsberegningen behandles lokalt. Der kræves ikke en AI-model eller en ekstern beregningstjeneste for at lave en bordplan.

Det gør Pladser velegnet både som selvstændigt værktøj og som en del af Plan 2.0.

## Integration med Plan 2.0

Pladser kan indgå som HTML-app i **Plan 2.0**.

Integrationen går begge veje:

**Plan 2.0 → Pladser**

Pladser kan modtage skolens stamdata direkte fra Plan 2.0 og bruge dem som grundlag for bordfordelingen.

**Pladser → Plan 2.0**

Pladser kan generere en PDF af den færdige bordplan og sende den videre til Plan 2.0.

Hvis Pladser ikke modtager stamdata fra Plan 2.0, kan brugeren fortsat importere et regneark manuelt.

Pladser er derfor ikke afhængig af Plan 2.0 for at fungere.

## Status

Pladser er under aktiv udvikling, men den samlede arbejdsgang fungerer nu:

**stamdata → valg af grupper → fordelingsregler → automatisk fordeling → manuel tilpasning → gem bordplan → A3/PDF**

Tidligere bordplaner kan samtidig bruges som grundlag for nye fordelinger, så Pladser kan skabe variation fra gang til gang i stedet for blot at lave en ny tilfældig placering.

Den videre udvikling fokuserer især på:

- endnu bedre social variation mellem bordplaner
- bedre hjælp til at vurdere kvaliteten af en fordeling
- flere relevante fordelingshensyn uden at gøre appen kompliceret
- fortsat forbedring af A3/PDF-læseligheden
- tættere integration med Plan 2.0
