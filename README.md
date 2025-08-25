# Data portefølje - Fra Exel til PowerBI

##Billede skal være her 

## Litteraturliste

- [Formål](#Formål)
- [Data Kilder](#Data-kilder)
- [Design](#Design)
  - [Mock up](#Mock-up)
  - [Værktøjer](#Værktøjer)
- [Arbejdsproces](#Arbejdsproces)
  - [Kode](#Kode) 
  - [Data udtrækning](#Data-udtrækning)
  - [Data rensning](#Data-rensning)
  - [Data transformation](#Data-transformation)
  - [Opstillingen af MYSQL](#Opstillingen-af-MYSQL)
- [Visualisering](#Visualisering)
- [Power BI og DAX måling](#Power-BI-og-DAX-måling)
- [Analyse](#Analyse)
  - [Fund](#Fund)
  - [Validering](#Vildering)
  - [Udforskning](#Udforskning)
- [Anbefalinger](#Anbefalinger)
- [Konklusion](#Konklusion)


# Formål 
Formanden for Mærsks marketingsafdeling er interreseret i finde de 10 mest populære danske Youtubers i 2025. Med grundlag på at vide hvem, som egner sig bedst til at køre en succesful kampagne med.

## User Story 

Som formand for Mærsks marketingsafdeling står Shannon med opgaven til at finde den bedste YouTube-kanal, som vil være bedst at køre kampagner. For at frembringe en god ROI. Du er blevet hyret som en freelancer til at indsamle, og identificere Danmarks største Youtubere, baseret på antal visningerne, antal abonnenter, og video opladede.<img width="499" height="73" alt="image" src="https://github.com/user-attachments/assets/5e5501a2-2c95-4f3d-bfb4-9047be600473" />
### Hvordan realisereres dette?

Ved at opstille en dashboard som giver indsigt til i de 10 mest populære Youtubers i Danmark - Dashboaded burde bestå af følgende:

-	En liste af de største Youtuberes baseret på antal visninger, antal abonnenter, og video opladede.
-	Illustrere nøgle metrics (kanal-navn, abonnenter, videoer, seer tal, engagement ratioer)
-	Være brugervenlig, og let at kunne filtrere
-	Bestå af de nyeste data



# Data Kilder
Som nævnt tideligere skal følgende data indsamles:

- Kanal navn
- Abonnenenter
- Videoer
- Antal visninger

- Dataerne bliver hentet fra hjemmesiden Kaggel. Her et et extrakt af exel-filen : indsæt en fil


# Design 

## Krav for Dashboard

For at dashboaded succesfuldt kan bedst kan besvare formålet, skal følgende definere:

1. Hvem er de 10 mest populære Youtubers i DK?
2. Hvilke 3 youtubers har oplaoded flest videoer? 
3. Hvilke 3 har flest antal visninger?
4. Hvilke 3 har højst gennemsnitlige antal visninger pr. video?
5. Hvilke 3 har det bedste forhold mellem visninger og abonnenter?
6. Hvilke 3 har den højeste engegementrate pr. video?


## Dashboard mockup og visualieringer

Dashboaded bør være visuelt overksueligt, og kunne illustrere informationerne anstændigt. Følgende visuliserings redskaber kan anvendes:

1. Table
2. Treemap
3. Scorecards
4. Horizontal bar chart

![alt text](Assets/images/Dashboard-Mockup.png)

## Værktøjer

Colons can be used to align columns.

| Værktøj       | Formål     |
| ------------- |:-------------:|
|  Mockup     | Design af dashboardets wireframes|
| Excel    | Indledende dataudforskning |
| SQL | Datatransformation, rensning og test   |
| Power BI |  Visualisering via interaktive dashboards |
| GitHub | Dokumentation og versionsstyring |


# Arbejdsproces

Tilgangen til at immødekomme formålet er som følgende:

1. Indsamling af data
2. Udforskning og første analyse i Excel
3. Indlæsning i SQL Server
4. Datatransformation og rensning med SQL
5. Datatest og validering (datatyper, og dubletter)
6. Visualisering i Power BI
7. Opstille fund og generingen af indsigter
8. Udarbejdelse af dokumentation
9. Udgive resultater på GitHub

## Dataudforskning 

- Vi har mindst fire centrale kolonner, der giver de nødvendige informationer (abonnenter, visninger, videoer, kanalnavn).
- Kanalnavne skal udtrækkes fra et ID-felt, hvor data er adskilt af “@”.
- Datasættet indeholder flere kolonner end nødvendigt, og unødvendige data bør fjernes.

## Datarensning 

Formålet er at sikre et klart og konsistent datasæt. Krav til rensede data, er som følgende:

1. Kun relevante kolonner beholdes
2. Konsistente og korrekte datatyper
3. Overskuelig struktur

Med følgende MYSQL syntakster kan vi realisere det:

![alt text](Assets/images/Række-tæller.png)


![alt text](Assets/images/Kollone-tjekker.png)


![alt text](Assets/images/Data-type-tester.png)



![alt text](Assets/images/Duplet-tjekker.png)


#### Trin til datarensning
- Fjern irrelevante kolonner
- Udtræk kanalnavne fra første kolonne
- Omdøb kolonner med aliaser
- Transformér data

### Transformering af data 
![alt text](Assets/images/transformering-sql.png)

### Opstilling af MYSQL View

![alt text](Assets/images/sql-view.png)

# Visualisering 

Power BI dashboardet viser DK's top 10 YouTubers i 2025:
![alt text](Assets/images/Dashboard.png)

# Power BI og DAX måling

DAX-metrics defineret i Power BI inkluderer:

Totale abonnenter (i mio.)
![alt text](Assets/images/Total-abonnenter.png)
Totale visninger (i mio.)
![alt text](Assets/images/Total-views.png)
Totale videoer
![alt text](Assets/images/Total-videoer.png)
Gennemsnitlige visninger pr. video (i mio.)
![alt text](Assets/images/Total-videoer.png)
Engagementrate pr. abonnent
![alt text](Assets/images/Sub-engage-rate.png)

### få oversat målingerne korrek, dt er ikke sammenhængende!!!!

# Analyse

For at imødekomme chefen for marketingsafdelingens behov, skal følgende spørgesmål besvares:

Nøglespørgsmål:
Hvem er de 10 YouTubere med flest abonnenter?

| Nr.  | Kanal navne       | Antal abonnenter     |
| ----  | ------------- |:-------------:|
| 1.  |  Subway Surfers    | 9720000
| 2.  | Unisport    | 5290000 |
| 3.  | MagmaMusen | MagmaMusen |
| 4.  | Kiloo Games |  3130000 |
| 5.  | AlumiTube| 2100000|
| 6.  | Slikhaar TV - Mens hair | 2080000   |
| 7.  | Jacob's Piano |  1920000 |
| 8.  | กินไปไทยหรั่ง | กินไปไทยหรั่ง |
| 9.  | Glitch King|  1730000 |
| 10.  | SsethTzeentach | 1570000|

Hvilke 3 kanaler har uploadet flest videoer?

| Nr.  | Kanal navne       | Antal videoer     |
| ----  | ------------- |:-------------:|
| 1.  |  Hyper Verse • MMD    | 12648  |
| 2.  | HLTVorg | 5089 |
| 3.  | Unisport | 3951 |


Hvilke 3 kanaler har flest visninger?

| Nr.  | Kanal navne       | Antal videoer     |
| ----  | ------------- |:-------------:|
| 1.  |  Subway Surfers  | 1670487976  |
| 2.  | Unisport | 1557580702 |
| 3.  | MagmaMusen | 1259217870 |


Hvilke 3 kanaler har højest gennemsnitlige visninger pr. video?

| Nr.  | Kanal navne       |  gennemsnitlige visninger (Millioner)    |
| ----  | ------------- |:-------------:|
| 1.  |  Peter Asschenfeldt and the Colonels  | 4,5  |
| 2.  | SsethTzeentach | 3,5 |
| 3.  | Jacob's Piano | 2,3 |


Hvilke 3 kanaler har højest abonnent-engagement pr. uploadet video?


| Nr.  | Kanal navne       |  gennemsnitlige visninger (tusinde)    |
| ----  | ------------- |:-------------:|
| 1.  |  Peter Asschenfeldt and the Colonels  | 16.447 |
| 2.  | SsethTzeentach | 15.544|
| 3.  | Bertram - Craft and Wilderness | 11.650|


  



