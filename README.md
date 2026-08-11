# Pladser

**Pladser** er et værktøj til at lave, tilpasse, gemme og udskrive bordplaner for elever i en spisesal.

Appen tager udgangspunkt i skolens stamdata og grupperinger – fx **teams, gange/Studenthouse, linjefag, rejsehold og valgfag** – og omsætter dem til en fysisk bordplan.

Den automatiske fordeling er kun et udgangspunkt. Bordplanen kan bagefter redigeres manuelt, borde og elever kan låses, tidligere planer kan bruges som reference, og den færdige plan kan publiceres til companion-appen **Tjek Pladser** og udskrives som en farvet A3-PDF med QR-kode.

> **Kort fortalt:** Stamdata → fordel elever → tilpas → gem bordplan → aktivér Tjek Pladser → åbn PDF / print.

---

## Indhold

- [Sådan bruges Pladser](#sådan-bruges-pladser)
- [Stamdata](#stamdata)
- [Automatisk fordeling](#automatisk-fordeling)
- [Bordopstilling og fysisk placering](#bordopstilling-og-fysisk-placering)
- [Manuel redigering](#manuel-redigering)
- [Gemte bordplaner](#gemte-bordplaner)
- [Tjek Pladser](#tjek-pladser)
- [Print og PDF](#print-og-pdf)
- [Hvad gemmes hvor?](#hvad-gemmes-hvor)
- [Plan 2.0](#plan-20)
- [Status og næste skridt](#status-og-næste-skridt)

---

## Sådan bruges Pladser

Den normale arbejdsgang er:

1. **Indlæs stamdata** fra Excel eller Plan 2.0.
2. **Vælg fordelingsgrundlag**, fx Teams eller Gange / Studenthouse.
3. **Tilpas bordopstillingen** og hvor mange borde hver gruppe råder over.
4. **Vælg fordelingsregler**, fx køn, Team, gang og rotation fra en tidligere plan.
5. Klik **Fordel elever**.
6. **Tilpas manuelt** ved behov – flyt elever, byt borde og lås placeringer.
7. **Gem bordplanen** i det lokale bordplansbibliotek.
8. Klik **Aktivér Tjek Pladser**, hvis planen skal bruges til fremmødekontrol.
9. Klik **Åbn PDF / Print** for at åbne den færdige farvede A3-PDF.

---

## Stamdata

Pladser kan i dag modtage stamdata på to måder:

### Excel-regneark

Når Pladser bruges selvstændigt, kan et Excel-regneark indlæses direkte i browseren.

Pladser leder bl.a. efter oplysninger som:

- `Fornavn`
- `Efternavn`
- `Grupper`
- `Studenthouse`
- `Køn`

Elevens navn dannes af `Fornavn` + `Efternavn`.

Det er ikke nødvendigt, at alle felter findes. Flere oplysninger giver blot flere muligheder for fordelingsregler.

### Plan 2.0

Når Pladser kører integreret i **Plan 2.0**, kan stamdata sendes direkte ind i appen uden manuel filimport.

### Grupper

En elev kan tilhøre flere grupper på samme tid. Eksempler:

```text
Team 1 MM/TK
Badminton
Madkunst
Drenge 26
```

Pladser klassificerer grupperne, så brugeren kan vælge et relevant fordelingsgrundlag, fx:

- Teams
- Linjefag
- Rejsehold
- Valgfag
- andre relevante gruppeformer

`Studenthouse` behandles særskilt og svarer til elevens gang.

Køn kan i de nuværende Viggo-stamdata aflæses både fra kolonnen `Køn` og fra grupper som `Drenge 26` og `Piger 26`.

---

## Automatisk fordeling

Pladser forsøger at skabe en **brugbar social placering**, ikke bare at fylde ledige stole.

Et centralt princip er:

> Elever skal så vidt muligt have en anden elev siddende direkte overfor sig.

Hvis en gruppe fx råder over tre borde, kan en fordeling derfor blive:

- 24 elever → **8 / 8 / 8**
- 25 elever → **9 / 8 / 8**
- 26 elever → **10 / 8 / 8**

Ved 26 elever er `10 / 8 / 8` bedre end `9 / 9 / 8`, fordi alle elever dermed kan få en elev siddende overfor.

### Fordelingsregler

Ud over den grundlæggende placering kan Pladser tage hensyn til:

- **Køn** – fordel drenge og piger så ligeligt som muligt.
- **Team** – spred, saml eller ignorér elever fra samme Team.
- **Gang / Studenthouse** – spred, saml eller ignorér elever fra samme gang.
- **Team + gang** – tag højde for kombinationen af de to.

Reglerne er ønsker til den bedst mulige fordeling. De kan ikke altid opfyldes fuldstændigt, hvis elevtal, låste placeringer eller andre hensyn står i vejen.

### Rotation fra en tidligere bordplan

En gemt bordplan kan bruges som **reference** for en ny fordeling.

Pladser kan forsøge at give eleverne:

- et andet bord
- en anden side af bordet
- nye bordfæller
- en ny sidemakker
- en ny elev overfor

Formålet er reel variation fra tidligere planer – ikke bare tilfældig omrokering.

---

## Bordopstilling og fysisk placering

Spisesalen vises som tre vandrette rækker med op til otte fysiske bordpositioner i hver række.

Standardopstillingen er **8 / 3 / 8**. Nederste rækkes sidste bord bruges som standard til **Wwoofer-bordet** og indgår ikke i den almindelige elevfordeling.

Den samlede elevkapacitet er **180 pladser**.

Brugeren kan ændre antallet af aktive borde i hver række efter behov.

### Gruppeområder

Når der fx fordeles efter gange, kan flere borde høre til `Gimle`, mens andre hører til `Hjemstavn`.

Hver gruppe får sin egen farve. Farven følger gruppen, også når bordene flyttes fysisk.

### Flyt hele borde

Borde kan byttes fysisk efter fordelingen. Når et bord flyttes, følger følgende med:

- elever
- gruppetilknytning
- gruppefarve

Det betyder, at bordets sociale/gruppemæssige betydning bevares, selv om det flyttes til en anden position i salen.

---

## Manuel redigering

Den automatiske fordeling er altid kun et udgangspunkt.

### Flyt og byt elever

Elever kan markeres og flyttes eller byttes mellem pladser.

### Lås elever

En enkelt elevplacering kan låses, så den bevares ved en ny fordeling.

### Lås hele borde

Når et helt bord låses:

- bliver eleverne ved bordet stående
- kan tomme pladser ved bordet ikke bruges til andre elever
- respekteres bordet ved nye fordelinger

**Lås alle** låser alle borde og deres pladser.  
**Lås alle op** frigiver dem igen.

---

## Gemte bordplaner

Pladser har et lokalt **Bordplansbibliotek**.

En gemt bordplan indeholder den redigerbare tilstand – ikke kun et PDF-billede.

Planer kan bl.a.:

- åbnes
- opdateres
- omdøbes
- duplikeres
- slettes
- bruges som reference for rotation
- bruges som kilde til en tidligere bordopstilling

Der kan også eksporteres og importeres en **ZIP-backup** af bordplansbiblioteket.

> **Vigtigt:** Bordplansbiblioteket er i den nuværende version lokalt i den browser, hvor Pladser bruges. Central lagring på Google Drev er planlagt, men ikke implementeret endnu.

---

## Tjek Pladser

**Tjek Pladser** er en mobil companion-app til fremmødekontrol ved de fysiske borde.

Når en færdig bordplan aktiveres med **Aktivér Tjek Pladser**, publicerer Pladser et snapshot af den aktuelle plan til skolens Google Apps Script / Google Sheet-løsning.

Den publicerede version får et permanent link og en QR-kode.

### QR-kode

QR-koden indsættes i den genererede A3-PDF ved området omkring anretterbordet.

En lærer kan scanne QR-koden med telefonens kamera og åbne præcis den publicerede bordplan i Tjek Pladser.

En gammel udskrift peger fortsat på den version, der faktisk blev printet. Ændringer i Pladser ændrer ikke automatisk en allerede publiceret QR-version.

### Mobil arbejdsgang

I Tjek Pladser kan læreren:

- se bordene i deres **fysiske rækkefølge**
- se samme **gruppefarver** som i Pladser
- swipe mellem borde på hele hovedområdet
- markere enkelte elever som fraværende
- bruge **Alle er til stede** som hurtig handling
- automatisk gemme ændringer, når der swipes videre
- se, hvilke borde andre lærere allerede har kontrolleret
- se hvem der er markeret fraværende

Navigationsrækken bevarer sin position, også når appen synkroniserer i baggrunden.

### Delte kontroller

Flere lærere kan kontrollere forskellige borde samtidigt. Tjek Pladser synkroniserer den aktuelle status via Google Sheet.

En kontrolsession genbruges, så længe der har været aktivitet inden for **90 minutter**. Efter mere end 90 minutters inaktivitet oprettes en ny session.

### Statistik

Google Sheet-løsningen indeholder læsevenlige faner til bl.a.:

- **Tjek**
- **Registreringer**
- **Seneste tjek**
- **Statistik**

Statistikken viser bl.a.:

- elev
- antal tjek
- antal fravær
- fraværsprocent
- seneste fravær

Tekniske faner og ID-kolonner holdes skjult fra den almindelige visning.

---

## Print og PDF

Pladser genererer en farvet **A3-PDF** direkte.

Knappen **Åbn PDF / Print**:

1. genererer den færdige PDF
2. åbner PDF'en i browserens PDF-fremviser
3. gør det muligt at printe eller gemme præcis den version, der vises

PDF'en indeholder:

- den fysiske bordopstilling
- elevnavne
- gruppefarver
- tydelige bordplaceringer
- QR-kode til Tjek Pladser, når planen er publiceret

Den tidligere HTML/browser-printvisning er ikke den primære printvej; den genererede PDF er det endelige printprodukt.

Når Pladser kører inde i Plan 2.0, kan PDF'en desuden sendes direkte videre til Plan 2.0.

---

## Hvad gemmes hvor?

Det er vigtigt at skelne mellem de forskellige typer data.

| Data | Nuværende placering |
|---|---|
| Indlæste stamdata | Browserens aktuelle arbejdsstate |
| Redigerbar bordplan under arbejdet | Browserens arbejdsstate |
| Gemte bordplaner | Lokalt Bordplansbibliotek i browseren |
| Backup af bordplaner | ZIP-fil, som brugeren eksporterer |
| Publiceret Tjek Pladser-plan | Google Apps Script / Google Sheet |
| Fremmøderegistreringer | Google Sheet |
| Statistik fra Tjek Pladser | Google Sheet |
| A3-bordplan | Genereret PDF |

### Lokal behandling og data

Selve elevfordelingen udføres lokalt i browseren. Der bruges ikke en AI-model eller en ekstern beregningstjeneste til at lave bordplanen.

Stamdata, som indlæses fra et regneark, uploades ikke automatisk nogen steder.

**Kun når brugeren aktivt vælger `Aktivér Tjek Pladser`, sendes det nødvendige snapshot af den aktuelle bordplan til skolens Tjek Pladser-løsning.**

---

## Plan 2.0

Pladser kan bruges både selvstændigt og integreret i **Plan 2.0**.

### Plan 2.0 → Pladser

Plan 2.0 kan sende stamdata direkte til Pladser.

### Pladser → Plan 2.0

Pladser kan generere en PDF af den færdige bordplan og sende den tilbage til Plan 2.0.

Hvis Pladser ikke modtager stamdata fra Plan 2.0, kan Excel-import fortsat bruges som fallback.

---

## Status og næste skridt

Den centrale arbejdsgang fungerer nu:

**stamdata → grupper → fordelingsregler → automatisk fordeling → manuel tilpasning → lokal gemning → Aktivér Tjek Pladser → QR → mobil kontrol → A3-PDF / print**

### Næste udviklingsetape

Den næste større etape er central lagring og versionsstyring via Google Workspace:

1. **Stamdata på Google Drev**
   - en fast mappe med flere stamdataversioner
   - Pladser kan opdage, at en nyere version findes
   - brugeren vælger selv, hvornår den nye version bliver aktiv

2. **Adgangskontrol**
   - kun godkendte medarbejderkonti kan hente skolens stamdata
   - tydelig visning af hvilken Google-konto Pladser er forbundet som

3. **Bordplaner på Google Drev**
   - `Gem` kan på sigt betyde central lagring
   - planer kan åbnes fra en anden computer/browser
   - hver plan kan knyttes til den stamdataversion, den blev lavet med

4. **Webapp / Chrome-udvidelse**
   - Pladser kan hostes centralt som en intern webapp
   - en lille Chrome-udvidelse kan fungere som launcher
   - skolens IT kan evt. udrulle den til medarbejdere via Google Workspace

Den lokale lagring kan fortsat fungere som cache/sikkerhedsnet, mens Google Drev bliver det centrale arkiv.

---

## Teknisk

Pladser er i øjeblikket samlet som en browserbaseret HTML-app.

Vigtige klientbiblioteker bruges bl.a. til:

- læsning af Excel-regneark
- ZIP-backup
- PDF-generering
- QR-generering

Appen kan køre selvstændigt i browseren eller integreres i Plan 2.0.

Tjek Pladser benytter Google Apps Script og Google Sheets som backend for publicerede planer, kontroller og statistik.
