# Kod dit eget 'Flappy Bird' spil med KAPLAY

Dette repo gennemgår, hvordan man koder sit eget 'Flappy Bird' spil i VS Code fra start til slut med Node.js og spilbiblioteket [KAPLAY](https://kaplayjs.com/).

Ved at følge denne 'how-to' guide vil du således ende ud med at have kodet dit helt eget Flappy Bird spil ligesom det der her vises i nedenstående demo.

https://github.com/user-attachments/assets/dee5c868-99a6-48c6-a6bf-eb6859dbd354

## Nødvendigt software

For at kunne kode spillet, skal du først og fremmest have følgende software installeret:

1. [VS Code](https://code.visualstudio.com/)
2. [Node.js](https://nodejs.org/en)

### VS Code

VS Code er det program, hvori vi vil skrive koden til vores Flappy Bird spil.

VS Code er det man kalder et 'Integrated Development Environment' (hvilket ofte blot forkortes og kaldes et '<code>IDE</code>'), som nemt kan hentes og installeres via dette link:

- https://code.visualstudio.com/

> _Lav evt. en Google eller YouTube søgning på "Mac install VS Code", hvis du har en Apple computer, eller på "Windows install VS Code", hvis du har en Windows computer, for hjælp til at installere VS Code._

### Node.js

Node.js er noget man teknisk set kalder et 'JavaScript runtime environment', hvilket i sin enkelhed egentlig blot betyder, at vi kan skrive og køre koden til vores spil lokalt på vores computer i programmeringssproget kaldet <code>JavaScript</code>.

Node.js kan ligeledes nemt hentes og installeres via dette link:

- https://nodejs.org/en

> _Lav evt. en Google eller YouTube søgning på "Mac install Node.js", hvis du har en Apple computer, eller på "Windows install Node.jd", hvis du har en Windows computer, for hjælp til at installere Node.js._

## Setup af VS Code og tjek af Node.js

Før vi går i gang med at kode vores Flappy Bird spil, skal vi lige gøre 2 ting:

1. Sætte VS Code op til vores spil
2. Tjekke vores Node.js installation

### VS Code setup

Det første du selvfølgelig skal gøre er at åbne VS Code.

Når du gør det, så vil du sikkert se en form for velkomstskærm a la det her:

<img width="1024" alt="Screenshot 2025-03-18 at 20 38 19" src="https://github.com/user-attachments/assets/00e8b66f-c51a-41d5-9185-6d380be611be" />

<br>
Fra denne (måske lidt overvældende) velkomstskærm er det eneste du behøver at gøre, at trykke på den blå knap med teksten "Open Folder" ude i venstre side af skærmen, hvorved dit operativsystems stifinder åbnes.

<img width="1092" alt="Screenshot 2025-03-18 at 20 49 20" src="https://github.com/user-attachments/assets/77a4d57e-faf1-4182-83ff-6851379a575f" />

Naviger herfra først til din "Desktop".

<img width="977" alt="Screenshot 2025-03-18 at 20 54 22" src="https://github.com/user-attachments/assets/f384c2f1-1a7d-4de0-954e-fd3e4e549da0" />

Lav her en ny mappe på dit Desktop ved at trykke på knappen 'New Folder' og kald denne nye mappe for "kaplay".

<img width="977" alt="Screenshot 2025-03-18 at 21 01 36" src="https://github.com/user-attachments/assets/54c326af-8e1b-4e0f-9f07-98d3b9cccaf3" />

Tryk herefter på din nye "kaplay" mappe, så denne er markeret, og tryk dernæst på knappen "Open".

<img width="977" alt="Screenshot 2025-03-18 at 21 06 13" src="https://github.com/user-attachments/assets/4306d7c3-7e73-467b-bd7a-e274c927e2fa" />

Dette åbner "kaplay" mappen i VS Code, og alt hvad angår VS Code burde nu være på plads (hvis en "velkomstfane" endnu en gang vises efter du har åbnet mappen, så bare luk denne fane ved at trykke på det lille "x" til højre for teksten "_Welcome_" på fanen i midten af skærmen).

<img width="977" alt="Screenshot 2025-03-18 at 21 19 52" src="https://github.com/user-attachments/assets/56f89e97-2fdf-46cc-903d-50f08450bfd4" />

### Tjek Node.js installation

Nu hvor VS Code er på plads, skal vi som det næste lige have tjekket, at din Node.js installation (og den "package manager", kaldet <code>npm</code>, som kommer med Node.js) er installeret ordentligt, hvilket gøres som følger.

Tryk først på menuen "Terminal" i VS Codes menubjælke, og tryk derefter på "New Terminal" i dropdown listen.

<img width="871" alt="Screenshot 2025-03-18 at 21 58 37" src="https://github.com/user-attachments/assets/af68f67d-b830-47a5-9585-0adcfce1a7c0" />

<br>Når dette gøres, så åbnes der en terminal i bunden af VS Code (hvilken måske ser lidt anderledes ud for dig end i dette eksempel - men det gør ingen forskel for det videre).

<img width="977" alt="Screenshot 2025-03-18 at 22 14 08" src="https://github.com/user-attachments/assets/89866104-ddea-4a76-bac3-a83c2efe570f" />

Skriv i terminalen følgende kommando (og tryk 'enter'):

```bash
node -v
```

Dette skulle gerne give dig et versionsnummer i terminalen på den udgave af Node.js du har installeret, og får du et output som følgende, så er alt godt ifht. din Node.js installation.

<img width="401" alt="Screenshot 2025-03-18 at 22 26 36" src="https://github.com/user-attachments/assets/11954df4-e3c9-404d-8b03-8c04e9373696" />

På samme måde skal vi også lige tjekke, at den "package manager" som kommer med Node.js, og som hedder "npm", også er installeret korrekt.

Skriv derfor følgende kommando i din terminal (og tryk 'enter'):

```bash
npm -v
```

Får du også her et versionsnummer outputtet i din terminal, så er alt ifht. npm også godt.

<img width="416" alt="Screenshot 2025-03-18 at 22 34 09" src="https://github.com/user-attachments/assets/25b54e91-44d5-49d9-b07f-a451d9bc6ead" />

## Kodning af Flappy Bird spil

Nu hvor alt med VS Code og Node.js er på plads, så er det overordnet set følgende steps vi skal følge for at kode vores Flappy Bird spil med KAPLAY:

1. Skabe en skabelon til vores spil
2. Downloade billeder til spillet
3. Kode vores spil

### Skabelon til vores Flappy Bird spil

Via vores installation af Node.js kan vi gøre brug af noget som hedder en "package runner", der kaldes '<code>npx</code>', til nemt at skabe en form for skabelon til vores Flappy Bird spil.

Skriv derfor følgende kommando i din terminal (og tryk 'enter'), hvilket vil skabe en mappe kaldet '<code>flappybird</code>' under din '<code>kaplay</code>' mappe:

```bash
npx create-kaplay flappybird
```

Når dette gøres, så skulle du gerne kunne se et output i din terminal lignende nedenstående, og at der ude til venstre i VS Code nu findes en mappe kaldet 'flappybird'.

<img width="977" alt="Screenshot 2025-03-19 at 08 02 38" src="https://github.com/user-attachments/assets/d80e574c-5686-4799-8070-990bcd7cf6f8" />

Eneste vi så i dette step mangler at gøre, er blot at navigere ned i denne nye 'flappybird' mappe, hvilket vi fra terminalen gør ved at køre denne kommando:

```bash
cd flappybird
```

Ved at have trykket 'enter', efter at have skrevet denne kommando, står vi nu nede i vores 'flappybird' mappe, hvorfor din terminal gerne skulle se (nogenlunde) ud som følger.

<img width="977" alt="Screenshot 2025-03-19 at 08 26 58" src="https://github.com/user-attachments/assets/e902716d-6a20-4dde-bd7a-ed10eb82d691" />

> _**Note**: Hvis du vil fjerne alt det "mærkelige" output i din terminal - så denne måske ser lidt mere overskuelig ud - så skriv "clear" i din terminal og tryk 'enter', hvis du er på en Apple computer, eller "cls" og tryk 'enter', hvis du er på en Windows computer._

### Download billeder til spillet

Inden vi downloader de billeder vi skal bruge til vores Flappy Bird spil, så skal vi lige gøre nedenstående ting, så alt er klart til den efterfølgende kodning af vores spil.

#### Folde 'flappybird' mappen ud i VS Code

I venstre side af VS Code kan vi som sagt nu se den 'flappybird' mappe, hvori vi senere vil skrive vores kode til Flappy Bird spillet.

Og her er det første du skal gøre blot at trykke på den lille pil (<code>></code>) til venstre for 'flappybird' mappen, hvorved du folder denne mappe ud, så du kan se dens indhold.

<img width="977" alt="Screenshot 2025-03-19 at 08 57 41" src="https://github.com/user-attachments/assets/a17ac9ef-c634-47c4-8477-638bf03e3fd6" />

#### Folde 'public' mappen ud

På samme måde skal du nu også folde mappen 'public' ud, således at din VS Code burde se sådan her ud:

<img width="838" alt="Screenshot 2025-03-19 at 09 03 34" src="https://github.com/user-attachments/assets/f30e8821-f597-44a3-8b09-2725b5af72f2" />

#### Slet 'examples' mappen

Nu hvor du har foldet din 'public' mappe ud, så vil du kunne se en mappe herunder kaldet 'examples', hvilken vi nu vil slette, da denne mappe ikke skal bruges til noget.

Måden du gør det på i VS Code er ved først at højreklikke på 'examples' mappen, og fra den menu som fremkommer trykke på "Delete".

<img width="838" alt="Screenshot 2025-03-19 at 09 07 13" src="https://github.com/user-attachments/assets/86725b45-2ac5-4d1d-a8ef-96a8ba232db3" />

#### Slet 'bean.png' i 'sprites' mappen

På samme skal du nu slette det 'bean.png' billede, som ligger under 'sprites' mappen.

Fold derfor evt. 'sprites' mappen ud, højreklik på 'bean.png' filen, og tryk på "Delete" i den fremkomne menu.

<img width="838" alt="Screenshot 2025-03-19 at 09 26 15" src="https://github.com/user-attachments/assets/98401388-c282-4680-ae89-2e7e82f0ae3a" />

#### Download billeder til spillet

Nu hvor vi har slettet de unødvendige mapper og filer, så mangler vi blot at downloade de 4 billeder som ligger under "img" mappen i dette repo.

Måden du gør det på er først at trykke på "img" mappen i browseren til dette repo.

<img width="1004" alt="Screenshot 2025-03-19 at 09 55 49" src="https://github.com/user-attachments/assets/a2d954d1-8b01-4bfe-a456-e58340694896" />

Ved at gøre det vil du blive ført til siden for "img" mappen, hvorfra vi kan downloade spillets 4 billeder.

<img width="902" alt="Screenshot 2025-03-19 at 10 00 28" src="https://github.com/user-attachments/assets/d1e6eb7b-c6b8-4949-82ff-40203432c3d1" />

Fra denne side skal du downloade hvert af de 4 billeder, hvilket her kun vises for billedet kaldet "background.png", da processen er den samme for alle billederne.

Tryk derfor først på billedet med filnavnet "background.png", hvorved du vil få vist dette billede i din browser.

<img width="1624" alt="Screenshot 2025-03-19 at 10 07 45" src="https://github.com/user-attachments/assets/cd2990e5-7b00-4d26-848a-aa6cb3b50dbc" />

Lige over selve billedet vil du kunne se en form for bjælke, hvor man ude til højre kan finde en knap til at downloade billedet - når man fører sin mus over knappen vil den vise teksten "Download raw file" - hvilken du nu blot skal trykke på for at downloade billedet.

<img width="902" alt="Screenshot 2025-03-19 at 10 13 11" src="https://github.com/user-attachments/assets/d4d2c29e-a201-4b17-8ffb-f8fce701b019" />

Når du trykker på denne knap, så vil din browser downloade billedet, hvilket du kan se ved at trykke på "Downloads" ikonet i din browser (her er det vist for Chrome browseren, men dette burde næsten være ens for alle browsere).

<img width="460" alt="Screenshot 2025-03-19 at 10 18 04" src="https://github.com/user-attachments/assets/d03aaadb-63c9-456f-ac34-a35644f973f1" />

Efter du har downloadet "background.png" billedet, så gentag denne proces for de 3 andre billeder.

#### Flyt billeder fra 'Downloads' til 'sprites' mappe

Når du har downloadet alle 4 billeder, så skal vi lige have flyttet dem fra din computers "Downloads" mappe til dit spils "sprites" mappe (som findes under "public" mappen).

Måden du nemmest gør dette på, er først at trykke på "Downloads" ikonet i din browser, og så føre din mus over et af de downloadede billeder, således at et mappeikon vises til højre for billedet.

<img width="444" alt="Screenshot 2025-03-19 at 10 43 24" src="https://github.com/user-attachments/assets/341a4213-8531-4a24-b133-e6b14b47c724" />

Tryk nu på dette mappeikon til højre for downloaden af ét af billeder, hvorved din computers "Downloads" mappe åbnes.

<img width="1032" alt="Screenshot 2025-03-19 at 10 48 21" src="https://github.com/user-attachments/assets/9cf4864c-1271-4f07-b291-5c026e539025" />

Gå nu tilbage til VS Code og højreklik først på "sprites" mappen under "public" mappen, og tryk dernæst på "Reveal in finder" fra dropdown listen, hvis du er på en Apple computer, eller på "Reveal in Explorer", hvis du er på en Windows computer.

<img width="467" alt="Screenshot 2025-03-19 at 10 51 46" src="https://github.com/user-attachments/assets/91e128d3-2dc1-424b-a252-2bac88ef66db" />

Med dette skulle du nu gerne have 2 stifindervinduer åbne - ét for din "Downloads" mappe, og ét for din "sprites" mappe.

<img width="1315" alt="Screenshot 2025-03-19 at 10 59 25" src="https://github.com/user-attachments/assets/ff890baa-160f-4d19-811f-02695fce2088" />

Marker nu alle 4 billeder i din "Downloads" mappe - tryk evt. først på "background.png" billedet, hold "shift" tasten på dit keyboard inde, og tryk så 3 gange på piltasten der peger nedad på dit keyboard for at markere alle billeder.

<img width="668" alt="Screenshot 2025-03-19 at 11 03 03" src="https://github.com/user-attachments/assets/c07b42b6-5c99-436a-9eb9-bb5bf16b569a" />

Copy/paste eller træk nu alle 4 billeder fra din "Downloads" mappe over til din "sprites" mappe.

<img width="1298" alt="Screenshot 2025-03-19 at 11 06 55" src="https://github.com/user-attachments/assets/74fbc641-1c44-47e6-ab49-79f420d925f6" />

Og med det er alt nu på plads til at vi kan gå i gang med at kode vores helt eget Flappy Bird spil - Wuuhuuuu!!

### Kod dit spil

Overordnet set vil kodningen af dit Flappy Bird spil strække sig over følgende steps, som gennemgås i nedenstående:

1. Start udviklingsserveren
2. Setup af kode til spil
3. Setup af spillets 'scener'
4. Kodning af "Main Menu" scene
5. Kodning af "Game" scene
6. Kodning af "Game Over" scene

#### Start udviklingsserveren

For overhovedet at få vist et spil i sin browser, så er det første man gør, at starte den udviklingsserver som kommer med skabelonen, da vi tidligere kørte kommandoen "npx create-kaplay flappybird" i vores terminal.

Og heldigvis er det super nemt at starte denne udviklingsserver, da vi blot fra vores terminal skal køre følgende kommando fra <code>flappybird</code> mappen:

```bash
npm run dev
```

Når vi skriver denne kommando i vores terminal - og husker at trykke 'enter' bagefter - så vil terminalen umiddelbart vise os dette output.

<img width="781" alt="Screenshot 2025-03-19 at 13 04 49" src="https://github.com/user-attachments/assets/8bd7b76d-0996-44ea-966a-71a8b4219897" />

Og i dette output bliver vi via den blå tekst givet et link til <code>http://localhost:3001</code>, som når vi fører vores mus over linket vil vise os, hvordan vi åbner linket (på en Mac skal man holde "command" tasten inde og trykke på linket, mens man på en Windows maskine skal holde "Ctrl" tasten inde og trykke på linket).

Trykker vi således på dette link, så åbnes følgende side i vores browser - der vil opdatere sig hver gang vi gemmer den kode vi skriver - og alt er nu godt ifht. at starte udviklingsserveren.

<img width="928" alt="Screenshot 2025-03-19 at 13 17 19" src="https://github.com/user-attachments/assets/16dcb174-8857-4e7d-b04c-1401bafbaf2f" />

#### Setup af kode til spil

Nu hvor vores udviklingsserver kører, og vores umiddelbare spil vises i browseren, så skal vi nu til at starte med at sætte vort spil kode op.

Og den fil hvori vi gør det, er den "main.js" fil som ligger under mappen "src".

<img width="781" alt="Screenshot 2025-03-19 at 14 06 09" src="https://github.com/user-attachments/assets/ac246669-e4da-40ef-8113-a4170fcda601" />

Folder vi således "src" mappen ud, og dobbeltklikker på denne "main.js" fil, så åbnes den i VS Code.

<img width="1159" alt="Screenshot 2025-03-19 at 14 10 22" src="https://github.com/user-attachments/assets/ef52d2cb-9f5e-4c95-8270-e423631203f0" />

Og som det kan ses, så vil 'main.js' filen umiddelbart indeholde følgende kode, som er det der pt. vises i browseren:

```javascript
import kaplay from "kaplay";
// import "kaplay/global"; // uncomment if you want to use without the k. prefix

const k = kaplay();

k.loadRoot("./"); // A good idea for Itch.io publishing later
k.loadSprite("bean", "sprites/bean.png");

k.add([k.pos(120, 80), k.sprite("bean")]);

k.onClick(() => k.addKaboom(k.mousePos()));
```

Vi skal imidlertid ikke bruge det meste af denne kode, hvorfor du blot kan slette al koden i "main.js" filen, og erstatte den med følgende kode:

```javascript
import kaplay from "kaplay";
import "kaplay/global";
```

Med dette har vi nu det udgangspunkt vi skal bruge til at sætte vores spils kode op med KAPLAY, hvilket vi i "main.js" filen i følgende steps:

1. Initialisere kaplay
2. Loade sprites

##### Initialisere kaplay

Efter vores import af kaplay i "main.js" filen, så skal man i ethvert KAPLAY spil initialisere kaplay.

Dette gøres umiddelbart ved at kalde metoden <code>kaplay()</code> lige under ens imports, således at koden nu er:

```javascript
import kaplay from "kaplay";
import "kaplay/global";

kaplay();
```

Ifht. vores Flappy Bird spil vil vi dog give <code>kaplay()</code> metoden nogle specifikke instilliger, således at alt vil passe til det spil vi gerne vil lave.

Og den måde vi gør det på er at give et JavaScript objekt (<code>{}</code>) med nogle <code>properties</code> og <code>values</code> inde mellem <code>kaplay()</code> metodens paranteser (de properties man kan bruge og sætte kan ses af KAPLAY dokumentationen [her](https://kaplayjs.com/doc/kaplay/)).

I vores kode vil indstillingerne være følgende, hvilke kort forklares i nedenstående:

```javascript
import kaplay from "kaplay";
import "kaplay/global";

kaplay({
  background: [0, 0, 0],
  width: 500,
  height: 580,
  letterbox: true,
});
```

###### background

<code>background</code> propertien definerer, hvilken baggrundsfarve ens spil vil have. Til denne angiver vi her et JavaScript array (<code>[]</code>), hvori vi giver det 3 elementer af værdien nul (0). Disse 3 elementer repræsenterer hver en "RGB" farve/værdi (intervallet for hvert elements værdi er derfor mellem 0 og 255), og ved at sætte hvert element til nul, så vil dette give os en sort baggrundsfarve.

###### width

<code>width</code> propertien definerer bredden af vores spil, og grunden til at vi her sætter denne til 500 er, at det billede vi vil bruge til selve spillets baggrund ('background.png' i 'public/sprites/' mappen) netop også er 500 pixels bredt.

###### height

<code>height</code> propertien definerer højden på vores spil, og da vores spils baggrundsbillede også er 580 pixels højt, så sættes denne property også til 580.

###### letterbox

<code>letterbox</code> propertien bruges til at bevare billedformatet, hvis man ændrer størrelsen på ens browservindue, og vil således efterlade sorte bjælker stå på de resterende mellemrum. Her sætter vi denne property til en JavaScript boolean af værdien <code>true</code>, hvorved spillets billedformat bevares.

##### Loade sprites

Nu hvor vi har initialiseret kaplay, så mangler vi blot at loade vores billeder (hvilket man i KAPLAY kalder 'sprites') af spillets baggrund og selve 'flappy bird' fuglen, samt både top og bund af spillets rør.

Generelt loader man disse sprites (dvs. billederne) ved at kalde <code>loadSprite()</code> metoden, og mellem metodens parenteser angive:

1. Et navn til sin sprite
2. Filstien under 'public' mappen til ens sprite/billede

For vores 4 billeder vil dette være følgende i "main.js" filen:

```javascript
import kaplay from "kaplay";
import "kaplay/global";

kaplay({
  background: [0, 0, 0],
  width: 500,
  height: 580,
  letterbox: true,
});

loadSprite("bg", "sprites/background.png");
loadSprite("bird", "sprites/bird.png");
loadSprite("toppipe", "sprites/toppipe.png");
loadSprite("bottompipe", "sprites/bottompipe.png");
```

Og med det er du nu færdige med at sætte spillets startkode op, og kan nu fortsætte til næste step.

#### Setup af spillets 'scener'

Som det måske kunne ses i demoen af det færdige spil i starten af dette repo, så vil vores Flappy Bird spil indeholde følgende 3 forskellige "scener":

1. En "Main Menu" scene
2. En "Game" scene
3. En "Game Over" scene

I det følgende vil vi derfor umiddelbart sætte disse 3 scener til spillet op, så at vi bagefter kan skrive koden i hver af dem for at få spillet til at virke.

Inden vi gør det, så vil vi dog lige lave en mappe til vores scener - som vi vil kalde "scenes" og ligger under "src" mappen - således at vores kode er bedre struktureret og dermed nemmere at forstå (også for os selv 😅).

##### "scenes" mappe til vores scener

For at lave en "scenes" mappe skal vi blot gøre følgende i VS code.

Højreklik først på "src" mappen, og tryk derefter på "New Folder" i popup-menuen.

<img width="851" alt="Screenshot 2025-03-20 at 07 49 38" src="https://github.com/user-attachments/assets/668da908-b78b-47df-9b62-35e7630f2545" />

Med det vil der under "src" mappen dukker en ny mappe op under denne, i hvilken vi skriver "scenes" (og trykker 'enter' for navngive mappen dette navn).

<img width="851" alt="Screenshot 2025-03-20 at 07 52 16" src="https://github.com/user-attachments/assets/33a54327-a165-4fdd-9051-5c4b32036568" />

Alt er nu klart til at vi kan gå i gang med skabe de 3 scener i denne nye "scenes" mappe.

##### Main Menu scenen

Måden vi vil skabe vores umiddelbare scener til spillet er ret simple (og processen den samme for alle 3 scener).

For at skabe vores "Main Menu" scene - som senere bliver en scene hvor en spiller kan trykke på <code>space</code> på sit keyboard og dermed starte selve spillet - gør vi følgende.

Højreklik først på "scenes" mappen, og tryk på "New File" i den fremkomne menu.

<img width="851" alt="Screenshot 2025-03-20 at 08 40 29" src="https://github.com/user-attachments/assets/da7e3b4c-e89d-46a5-afcd-901a5364655f" />

Når vi trykker på "New File", så vil der i venstre side af VS Code, under vores "scenes" mappe, nu skabes en ny fil med tomt filnavn, hvilket vi erstatter med filnavnet "mainMenuScene.js" og trykker 'enter', hvormed denne fil automatisk åbnes i VS Codes editor.

<img width="851" alt="Screenshot 2025-03-20 at 09 35 47" src="https://github.com/user-attachments/assets/c6148167-7dc0-4132-800f-50e10699ec3e" />

Nu hvor vi har filen til vores "Main Menu" scene (som i øvrigt også er en <code>JavaScript</code> fil), og denne jo automatisk er åbnet i vores editor, så kan vi begynde at skrive en form for generel kode til denne scene.

Og måden vi her vil skabe denne scene er overordnet set at skrive en generel JavaScript <code>funktion</code>, som vi derefter kan importere i vores "main.js" fil og bruge i en KAPLAY metode kaldet <code>scene()</code>.

Helt konkret er koden følgende (hvis elementer kort forklares herunder):

```javascript
export default function mainMenuScene() {}
```

###### export default

<code>export default</code> i koden er det man i JavaScript kalder nogle <code>keywords</code> som gør, at vi her vil eksportere vores funktion, således at vi om lidt kan importere hele filens kode i vores "main.js" fil.

###### function

<code>function</code> er ligeledes et JavaScript <code>keyword</code> som man bruger til at definere en funktion - en funktion er overordnet set noget kode, som man kan bruge igen og igen i sin kode.

###### mainMenuScene() {}

<code>mainMenuScene</code> er som sådan blot det navn vi giver vores funktion (vi kunne i princippet have kaldt vores funktion hvad som helst), mens parenteserne (<code>()</code>) kan bruges til at give ens funktion nogle parametre (hvilket vi **ikke** gør her), og "tuborgklammerne" (<code>{}</code>) bruges til at skrive sin funktions kode mellem disse.

Med dette skrevet, kan nu importere koden i "mainMenuScene.js" i vores "main.js".

Åbn derfor din "main.js" fil, og start med at importer din "mainMenuScene" funktion på denne måde under dine 2 imports af kaplay i toppen af filen (enkeltdelene denne import forklares kort under koden).

```javascript
import kaplay from "kaplay";
import "kaplay/global";

import mainMenuScene from "./scenes/mainMenuScene";

kaplay({
  background: [0, 0, 0],
  width: 500,
  height: 580,
  letterbox: true,
});

loadSprite("bg", "sprites/background.png");
loadSprite("bird", "sprites/bird.png");
loadSprite("toppipe", "sprites/toppipe.png");
loadSprite("bottompipe", "sprites/bottompipe.png");
```

###### import

<code>import</code> er også et JavaScript keyword som angiver, at man vil importere noget kode fra en anden fil.

###### mainMenuScene

<code>mainMenuScene</code> er det vi vil importere fra en anden fil. Og her er det jo helt konkret den <code>mainMenuScene</code> funktion vi definerede i vores "mainMenuScene.js" fil for lidt siden.

###### from

<code>from</code> er også et JavaScript keyword som blot skal bruge til at fortælle, fra hvilken fil vi vil importere kode ind i vores "main.js" fil.

###### "./scenes/mainMenuScene"

<code>"./scenes/mainMenuScene"</code> er blot den filsti, hvorfra koden til vores import findes.

Med alt dette kan vi nu bruge KAPLAY's <code>scene()</code> metode til at sætte vores spil op til at bruge importen af vores "mainMenuScene" som startskuddet for vores spil.

Og måden man gør det på er sådan set bare, at angive 2 parametre mellem <code>scene()</code> metodens parenteser, som er:

1. Det navn man vil bruge til sin scene
2. Den funktion der skal eksekeveres, når scenen bruges

Til vores kodes vil <code>scene()</code> metodens navn være <code>"main-menu"</code>, og funktionen være den <code>mainMenuScene</code> import vi lavede for lidt siden.

Til slut i vores "main.js" fil skriver vi derfor følgende for at sætte vores "Main Menu" scene op:

```javascript
import kaplay from "kaplay";
import "kaplay/global";

import mainMenuScene from "./scenes/mainMenuScene";

kaplay({
  background: [0, 0, 0],
  width: 500,
  height: 580,
  letterbox: true,
});

loadSprite("bg", "sprites/background.png");
loadSprite("bird", "sprites/bird.png");
loadSprite("toppipe", "sprites/toppipe.png");
loadSprite("bottompipe", "sprites/bottompipe.png");

scene("main-menu", mainMenuScene);
```

Og med det er vi nu klar til at sætte de 2 andre scener (dvs. "Game" og "Game Over" scenerne) op på samme måde som vi lige har gjort her med "Main Menu" scenen.

##### Game scenen

Som sagt vil vores næste scene, dvs. "Game" scenen hvori selve Flappy Bird spillet vil spilles, skabes på samme måde som i foregående. Gør derfor følgende:

Lav en ny fil kaldet "gameScene.js" under din "scenes" mappe.

<img width="973" alt="Screenshot 2025-03-20 at 11 17 38" src="https://github.com/user-attachments/assets/144c46e5-9205-49ca-9cf7-6b3c1b077a66" />

Eksport i din "gameScene.js" fil en funktion kaldet "gameScene". Koden skal være følgende:

```javascript
export default function gameScene() {}
```

Importer dernæst denne funktion i din "main.js" fil, lige under den import du lavede for din "mainMenuScene". Koden i toppen af "main.js" filen skal derfor nu se ud som følger:

```javascript
import kaplay from "kaplay";
import "kaplay/global";

import mainMenuScene from "./scenes/mainMenuScene";
import gameScene from "./scenes/gameScene";
```

Brug til allersidst i "main.js" endnu en <code>scene()</code> metode og giv den navnet "game", samt en reference til din netop importerede <code>gameScene</code> funktion. Koden i bunden af "main.js" skal altså nu være:

```javascript
scene("main-menu", mainMenuScene);
scene("game", gameScene);
```

##### Game Over scenen

For "Game Over" scenen er processen den samme. Altså:

Skab en ny fil kaldet "gameOverScene.js" i din "scenes" mappe.

<img width="973" alt="Screenshot 2025-03-20 at 11 29 29" src="https://github.com/user-attachments/assets/6147d126-9350-4273-ad3f-c155166c4ac0" />

Eksporter en funktion kaldet "gameOverScene" i din nye "gameOverScene.js" fil. Koden er:

```javascript
export default function gameOverScene() {}
```

Importer denne funktion i "main.js" lige under de 2 foregående imports, dvs.:

```javascript
import kaplay from "kaplay";
import "kaplay/global";

import mainMenuScene from "./scenes/mainMenuScene";
import gameScene from "./scenes/gameScene";
import gameOverScene from "./scenes/gameOverScene";
```

Lav til allersidt i "main.js" en ny <code>scene()</code>, giv den navnet "game-over" og en reference til importen af din "gameOverScene" funktion.

```javascript
scene("main-menu", mainMenuScene);
scene("game", gameScene);
scene("game-over", gameOverScene);
```

Med alt dette mangler vi nu kun at kode en enkelt lille bitte ting for at få vores spil til at starte med at vise vores "Main Menu" scene som det første i spillet.

Måden vi får vores til at starte med at vise "Main Menu" scenen er ved at gøre brug af KAPLAY metoden <code>go()</code>, hvori vi blot skal skrive navnet på den scene vi vil have vist.

Så da vi først gerne vil have vores "main-menu" scene vist, så skriver vi blot <code>go("main-menu")</code> til allersidst i vores "main.js" fil, hvorved hele dennes kode gerne skulle være følgende:

```javascript
import kaplay from "kaplay";
import "kaplay/global";

import mainMenuScene from "./scenes/mainMenuScene";
import gameScene from "./scenes/gameScene";
import gameOverScene from "./scenes/gameOverScene";

kaplay({
  background: [0, 0, 0],
  width: 500,
  height: 580,
  letterbox: true,
});

loadSprite("bg", "sprites/background.png");
loadSprite("bird", "sprites/bird.png");
loadSprite("toppipe", "sprites/toppipe.png");
loadSprite("bottompipe", "sprites/bottompipe.png");

scene("main-menu", mainMenuScene);
scene("game", gameScene);
scene("game-over", gameOverScene);

go("main-menu");
```

Og .. "HELL YEAH!" vi har nu sat alle vores scener op, og kan derfor (endelig..) gå i gang med at kode vores "Main Menu" scene!

#### Kodning af "Main Menu" scene

Hvis du tjekker dit nuværende spil i din browser, så vil du for nu blot se en kedelig sort skærm ..

<img width="753" alt="Screenshot 2025-03-20 at 11 53 04" src="https://github.com/user-attachments/assets/569f8a60-a235-4e5b-b25d-82bf2f6ee66b" />

Men heldigvis skal vores "Main Menu" scene gerne ende ud med at være lig følgende billede, hvor en spiller skal kunne trykke på sit keyboards <code>space</code> tast for dermed at gå i gang med at spille selve spillet.

<img width="753" alt="Screenshot 2025-03-20 at 11 59 49" src="https://github.com/user-attachments/assets/08747c48-7b01-42c4-9b5a-bdc23e9479b7" />

Og for at nå dertil, vil processen for den kode vi vil skrive i vores "mainMenuScene.js" fil være følgende, som for hvert punkt gennemgås under nedenstående overskrifter:

1. Tilføje et baggrundsbillede
2. Tilføje en titel
3. Tilføje en undertitel
4. Tjekke for tryk på "space", og gå til næste scene

##### Tilføje et baggrundsbillede

Måden man som oftest tilføjer det man kalder "Game Objects" i KAPLAY - hvilket her vil være vores spils baggrundsbillede - er at bruge KAPLAY's <code>add()</code> metode inde mellem "tuborgklammerne" (<code>{}</code>) i en scenes funktion.

Så for at vi kan tilføje vores baggrundsbillede til vores "Main Menu" scene, så åbn først din "mainMenuScene.js" fil ved dobbeltklikke på den i VS Code.

Når den åbnes i din editor skulle den kode vi tidligere skrev gerne være følgende:

```javascript
export default function mainMenuScene() {}
```

Og for nu at tilføje vores baggrundsbillede, så definerer vi først en JavaScript variabel kaldet "bg" inde mellem <code>mainMenuScene</code> funktionens "tuborgklammer", og sætter den lig med <code>add()</code> metoden. Altå sådan her:

```javascript
export default function mainMenuScene() {
  const bg = add();
}
```

Dette vil i sig selv dog ikke få vores baggrundsbilledet vist på skærmen, da man inde mellem <code>add()</code> metodens parenteser (<code>()</code>) skal give hvert "Game Obejct" nogle "Components" inde i et Javascript array (<code>[]</code>), som er det der vil definerer en specifik adfærd for et "Game Object".

Så inde mellem <code>add()</code> metodens parenteser giver vi altså først blot metoden et tomt JavaScript array sådan her:

```javascript
export default function mainMenuScene() {
  const bg = add([]);
}
```

For vores baggrundsbillede er den eneste "Component" vi heldigvis blot skal give inde mellem "klammerne" (dvs. inde mellem <code>[]</code>) for at få billedet vist, et kald til KAPLAY metoden <code>sprite()</code>, hvortil vi bare skal give navnet på den sprite vi tidligere loaded i vores "main.js" fil.

Og tidligere gav vi jo vores loaded baggrundsbillede navnet "bg", hvorfor vi så blot kan skrive dette navn inde mellem <code>sprite()</code> metodens parenteser for at få baggrundsbilledet vist på skærmen.

Koden i "mainMenuScene.js" filen vil altså derfor blive:

```javascript
export default function mainMenuScene() {
  const bg = add([sprite("bg")]);
}
```

Ved at have tilføjet vores baggrundsbillede, så skulle skærmen til din nuværende "Main Menu" scene gerne se sådan her ud:

<img width="753" alt="Screenshot 2025-03-20 at 12 41 47" src="https://github.com/user-attachments/assets/94dca8b9-3d6a-42aa-a13c-59f1973f603a" />

##### Tilføje en titel

Måden vi vi tilføje titlen "Flappy Bird" til vores "Main Menu" scene, er stort set den samme som for det netop tilføjede baggrundsbillede.

Under variablen for vores baggrundsbillede (dvs. under linjen starten med <code>const bg = ..</code>) vil vi således også definere en konstant variabel kaldet "title", som vi ligeledes først sætter lig med <code>add()</code> metoden, og inde mellem denne metodes parenteser giver det et tomt array (<code>[]</code>).

```javascript
export default function mainMenuScene() {
  const bg = add([sprite("bg")]);
  const title = add([]);
}
```

For vores "title" variabel og "Game Object" vil vi imidlertid give følgende "Components" inde mellem "klammerne" (<code>[]</code>) i <code>add([])</code> metoden:

- text()
- pos()
- anchor()

###### text()

Komponenten <code>text()</code> bruges helt generelt til at vise tekst på skærmen.

Så for at vise titlen "Flappy Bird" skal vi derfor først blot skrive dette inde mellem <code>text()</code> komponentens parenteser.

```javascript
export default function mainMenuScene() {
  const bg = add([sprite("bg")]);
  const title = add([text("Flappy Bird")]);
}
```

###### pos()

<code>pos()</code> komponenten bruges til at placere "Game Objects" på skærmen via <code>x</code> og <code>y</code> koordinater - ligesom du kender det fra et almindeligt koordinatsystem.

For spil der vises på en skærm gælder der imidlertid følgende:

- <code>Origi</code> (dvs. positon (0, 0), hvor både x og y er nul) starter helt oppe i venstre hjørne af din skærm

- <code>x-aksen</code> går fra din skærms øverste venstre hjørne helt indtil sammes øverste højre hjørne (så jo større x er, jo længere til højre på skærmen vil et "Game Obejct" placeres)

- <code>y-aksen</code> går fra din skærms øverste venstre hjørne og helt ned til sammes nederste venstre hjørne (så jo større y er, jo længere ned på skærmen vil et "Game Obejct" placeres)

For vores "Flappy Bird" titel vil vi gerne have, at denne vises centret på x-eksen, og lidt oppe over y-aksens centrum, hvilket vi dog heldigvis nemt kan bruge KAPLAY's <code>center()</code> metode til at hjælpe os med.

Derfor vil vi som første parameter til <code>pos()</code> komponenten give dene et kald til <code>center().x</code>, hvilket vil centrere titlen i midten af skærmen på x-aksen.

Som anden parameter til <code>pos()</code> komponenten vil vi den et kald på <code>center()</code> metoden y-akse, og herfra fratrække 100 pixels, således at titlen ender med at stå lidt højere oppe på skærmen.

Helt konkret vil koden til <code>pos()</code> komponenten altså være:

```javascript
export default function mainMenuScene() {
  const bg = add([sprite("bg")]);
  const title = add([text("Flappy Bird"), pos(center().x, center().y - 100)]);
}
```

> _Læg i øvrigt mærke til, at der mellem hver komponent **SKAL** være et komma efter slutparentesen!!!_

###### anchor()

Hvis du lige nu og her kigger på vores "Main Menu" i din browser, så vil du se, at vores netop tilføjede titel lader til at stå lidt forkert ..

<img width="753" alt="Screenshot 2025-03-20 at 14 00 06" src="https://github.com/user-attachments/assets/88190202-dd1c-47c8-ac8c-d031d73a5e43" />

Men som ovenstående billede forhåbentlig viser, så skyldes denne "fejl", at vores title placeres fra dets øverste venstre hjørne med den <code>pos()</code> vi netop har defineret.

Dette kan vi imidlertid nemt ændre ved at tilføje en <code>anchor()</code> komponent til vores titel "Game Object", og mellem dets parenteser give den teksten <code>"center</code>.

Med det er vores kode i "mainMenuScene.js" filen nu:

```javascript
export default function mainMenuScene() {
  const bg = add([sprite("bg")]);
  const title = add([
    text("Flappy Bird"),
    pos(center().x, center().y - 100),
    anchor("center"),
  ]);
}
```

Og kigger på nu igen i din browser, så vil vi vores spils titel heldigvis står pænt centreret på x-aksen.

<img width="753" alt="Screenshot 2025-03-20 at 14 15 13" src="https://github.com/user-attachments/assets/a1a7665b-5763-4e0f-a01a-95f92cc60659" />

> _"Ps.": De røde prikker du ser på de to foregående billeder skyldes blot, at der her er brugt KAPLAY's 'debug' feature til at vise, hvordan spillets titel bedre og pænere centreres på x-aksen_

##### Tilføje en undertitel

Nu hvor vi har vores titel, så vi vil på stort set samme måde tilføje en "undertitel" som fortæller brugeren/spilleren af spillet, hvad de skal trykke for at starte spillet.

Til dette laver vi derfor først en konstant variabel kaldet "subtitle" under vores "title" variabel i koden, hvor vi bruger de 3 samme komponenter som før, med kun disse ændringer for hhv. <code>text()</code> og <code>pos()</code> komponenterne:

- text("Press space to play", {size: 18})
- pos(center())

Dette gør blot teksten for vores "undertitel" lidt mindre end titlen, og placerer denne midt på skærmen uden at fratrække de 100 pixels på y-aksen.

Med tilføjelsen af vores undertitel, bliver vores kode i "mainMenuScene.js" derfor følgende:

```javascript
export default function mainMenuScene() {
  const bg = add([sprite("bg")]);
  const title = add([
    text("Flappy Bird"),
    pos(center().x, center().y - 100),
    anchor("center"),
  ]);
  const subTitle = add([
    text("Press space to play..", { size: 18 }),
    pos(center()),
    anchor("center"),
  ]);
}
```

Og vores "Main Menu" scene vil nu så ud som følger i din browser:

<img width="753" alt="Screenshot 2025-03-20 at 15 33 26" src="https://github.com/user-attachments/assets/0a0416e2-89c8-4549-9ac5-a1ed3ca3bba4" />

##### Tjekke for tryk på "space", og gå til næste scene

Eneste vi nu mangler at implementere i koden i vores "mainMenuScene.js" fil er at tjekke for, når spilleren trykker på sit keyboards <code>space</code> tast, hvorved spilleren skal føres videre til næste scene (her "game" scenen) og spillet dermed starte.

Heldigvis er dette meget nemt at kode vhja. KAPLAY's <code>onKeyPress()</code> metode, da denne blot tager følgende parametre:

1. Keyboardtasten vi vil tjekke for tryk på
2. En (anonym) funktion til at handle på dette tryk

Så under al vores nuværende kode kan vi derfor blot bruge denne funktion til at tjekke for tast på "<code>space</code>", og med en anonym funktion bruge KAPLAY's <code>go()</code> metode til at gå til vores "game" scene. Med det ville koden være:

```javascript
export default function mainMenuScene() {
  const bg = add([sprite("bg")]);
  const title = add([
    text("Flappy Bird"),
    pos(center().x, center().y - 100),
    anchor("center"),
  ]);
  const subTitle = add([
    text("Press space to play..", { size: 18 }),
    pos(center()),
    anchor("center"),
  ]);

  onKeyPress("space", () => {
    go("game");
  });
}
```

Så hvis man nu først står i vores "Main Menu" scene i ens browser, deri trykker på ens "space" tast, så føres man altså nu videre til "Game" scene, hvor vi som det næste skal kode selve Flappy Bird spillet.

<img width="1496" alt="Screenshot 2025-03-20 at 19 45 54" src="https://github.com/user-attachments/assets/1d905a30-65c7-41b7-bbdf-a21ff23d0d02" />

#### Kodning af "Game" scene

Huuurraahhh .. endelig er vi nået til at skulle kode selve vores Flappy Bird spil!

Og i den forbindelse vil processen for vores kodning af selv spillet overordnet set være følgende:

1. Definere en 'tyngdekraft' for spillet
2. Tilføje vores baggrundsbillede
3. Tilføje vores Flappy bird
4. Tilføje spillets ('top' og 'bottom') rør

##### Definere en 'tyngdekraft' for spillet

Da et Flappy Bird spil jo primært handler om at en fugl konstant bliver trukket nedad af tyngdekraften, og kun ved tryk på en tast flyver opad indtil tyngdekraften igen gør sit indtog, så skal vi selvfølgelig også kode denne funktionalitet i vores spil.

At kode denne tyngdekraftsfunktionalitet er dog heldigvis super nemt vhja. KAPLAY's <code>setGravity()</code> metode.

Åbn derfor først din "gameScene.js" fil, og kald som det første inde mellem din "gameScene" funktions "tuborgklammer" denne funktion med en værdi i dens parameter sat til 400.

Koden skal altså være:

```javascript
export default function gameScene() {
  setGravity(400);
}
```

Mere skal der ikke til for at vores spil nu også vil blive påvirket af en tyngdekraft!

##### Tilføje vores baggrundsbillede

Heldigvis har vi jo tidligere prøvet at tilføje vores baggrundsbillede til en scene.

Så gentag derfor blot denne proces, således at vores "gameScene.js" kode nu vil være:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);
}
```

##### Tilføje vores Flappy bird

At tilføje vores Flappy Bird og håndtere et normalt 'Flappy Bird' spils funktionalitet er imidlertid lidt mere omfattende.

Derfor vil vi bryde processen for tilføjelse af vores Flappy Bird ned i følgende steps:

1. Tilføje en 'Flappy Bird'
2. Håndtere "jump" funktionalitet ved tast på 'space'
3. Håndtere kollision af Flappy Bird og rør
4. Håndtere når Flappy Bird er "faldet ud af" skærmen

###### Tilføje en 'Flappy Bird'

At tilføje en 'Flappy Bird' vil næsten være det sværeste af de 4 steps, da vi i denne proces skal anvende en masse "Components", når vi tilføjer vores Flappy Bird "Game Object" til skærmen via <code>add()</code> funktionen vi tidligere har brugt flere gange.

De "Components" vi vil tilføje vores "Flappy Bird" i en konstant variabel kaldet "bird" er følgende, hvilke kort forklares nedenunder med de parametre som hver skal gives:

- sprite()
- pos()
- anchor()
- scale()
- area()
- body()
- offscreen()

###### sprite()

<code>sprite()</code> komponenten har vi allerede brugt tidligere, og med den angiver vi blot, hvilket billede vi vil bruge til vores "Game Obejct". Til at vise vores tidligere loaded Flappy Bird billede giver vi derfor blot funktionen teksten <code>"bird"</code>.

###### pos()

<code>pos()</code> placerer vores Game Object et sted på skærmen efter den x og y koordinat man giver som parametre. Her sætter vi blot x koordinaten til <code>30</code>, og y koordinaten til <code>center().y</code>, så vores Flappy Bird vil placere midt på skærmen, lidt til højre fra dets venstre side.

###### anchor()

<code>anchor()</code> sætter vi blot ligesom tidligere til <code>"center"</code>.

###### scale()

<code>scale()</code> komponenten bruges til at gøre ens billeder enten større eller mindre på skærmen.

Her sætter vi denne til en værdi af <code>0.8</code>, således at vores Flappy Bird vil fylde lidt mindre på skærmen end billedets normale størrelse (en værdi under 1 gør ens billede mindre, mens en værdi større end 1 gør det større).

###### area()

Med <code>area()</code> komponenten muliggør man, at ens Game Object - her vores Flappy Bird - vil kunne detektere kollision med andre Game Obejcts.

Til denne angiver vi her ingen parametre.

###### body()

<code>body()</code> komponenten vil medvirke, at vores Flappy Bird vil blive påvirket af den tyngdekraft vi tidligere satte.

Til denne komponent vil vi give den et JavaScript objekt (<code>{}</code>) med en <code>jumpForce</code> property sat til en value af <code>140</code> i dens parameter, således at vores Flappy Bird vil "hoppe opad", når man senere kalder dens <code>jump()</code> metode.

###### offscreen()

<code>offscreen()</code> komponenten vil medføre, at vi kan detekterer, når vores Flappy Bird på den ene eller anden måde flyver ud af skærmen, hvorved man så er "game over", og vi derfor vil føre spilleren videre til vores "Game Over" scene.

Med alle disse komponenter sat ved tilføjelse af vores Flappy Bird, så bliver den fulde kode for dette følgende:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);
}
```

##### Håndtere "jump" funktionalitet ved tast på 'space'

Hvis du kigger på dit spil i din browser lige nu, så vil du se, at din Flappy Bird bare falder ud af skærmen, når din "Game" scene startes.

Vi mangler altså at kunne få vores Flappy Bird til at hoppe, når en spiller trykker på sin <code>space</code> tast.

Men dette er heldigvis nemt at implementere for vores Flappy Bird Game Object, da vi ligesom tidligere bare kan gøre brug af en <code>onKeyPress()</code> metode på vores fugl.

I den forbindelse skal vi således bare sætte denne metodes første parameter til <code>"space"</code>, og dens anden parameter til en anonym funktion. Den umiddelbare kode vil altså være:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {});
}
```

Og inde mellem den anynome funktions "tuborgklammer" skal vi bare kalde <code>jump()</code> metoden på vores <code>bird</code> variabel for at vores Flappy Bird til at hoppe lidt opad, når spilleren trykker på sin <code>space</code> tast.

Den færdige kode bliver altså:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });
}
```

##### Håndtere kollision af Flappy Bird og rør

Godt nok har vi ikke tilføjet nogle af de klassiske Flappy Bird rør til vores spil endnu. Men heldigvis er det ret så nemt at sætte at sætte vores Flappy Bird op til at registrerer kollision med sådanne rør via en <code>onCollide()</code> metode.

Denne skal vi bare kalde på vores <code>bird</code> variabel, og bruge teksten <code>"pipe"</code> som første parameter, og en anonym funktion som anden parameter. Dvs. umiddelbart sådan her:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {});
}
```

Og når vores Flappy Bird rammer et rør, så skal vi bare kalde <code>go()</code> funktionen inde mellem den anonyme funktions "tuborgklammer" med teksten <code>"game-over"</code>, således at vi går til vores "Game Over" scene.

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });
}
```

##### Håndtere når Flappy Bird er "faldet ud af" skærmen

At håndtere at ens Flappy Bird "falder ud af skærmen" er heldigvis også nemt, da vi også her bare skal gå til "Game Over" scenen, når det sker.

I den forbindelse kan vi nemlig bare bruge <code>onExitScreen()</code> metoden på vores <code>bird</code> variabel, og via en anonym funktion som parameter bruge <code>go()</code> funktionen til at gå til "Game Over" scenen, når vores Flappy Bird falder ud af skærmen.

Med det bliver vores kode altså:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });
}
```

##### Tilføje spillets ('top' og 'bottom') rør

For at tilføje de klassiske rør i et Flappy Bird vil skrive en funktion til at hjælpe os med det, som vi så vil først kalder én gang uden for funktionen, og med et vist tidsinterval kalde samme kontinuerligt inden i funktionen (hvilket man kalder "rekursive" kald til en funktion).

Overordnet set vil tlføjelsen af rør således følgde disse steps:

1. Definer funktion
2. Kald funktion
3. implementer konstant tilføjelse af rør i funktionen

###### Definer funktion

At definere den funktion, som kontinuerligt vil skabe spillets rør, er let nok.

For her vil vi bare lave en konstant variabel, kaldet "spawnPipes", og umiddelbart sætte den lig med en tom <code>arrow function</code>.

Definitionen af denne funktion bliver derfor bare:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });

  const spawnPipes = () => {};
}
```

###### Kald funktion

At kalde denne ny "spawnPipes()" funktion er også let.

For under selve funktionen laver vi således bare et kald til denne på denne måde:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });

  const spawnPipes = () => {};

  spawnPipes();
}
```

##### implementer konstant tilføjelse af rør i funktionen

At implementere den konstante tilføjelse af spillet rør, inden mellem "tuborgklammerne" af vores "spawnPipes" funktion, er imdilertid lidt mere omfattende.

Men for at gøre processen lidt mere overskuelig, så vil vi gribe dette an via disse steps:

1. Få tilfældig y-koordinat for rør
2. Tilføj 'toppipe'
3. Tilføj 'bottompipe'
4. Flyt rør ved update af spillet
5. Tilføj nye rør hvert 5 sekund

###### Få tilfældig y-koordinat for rør

Grunden til at vi først vil skabe en tilfældig y-koordinat er, at vores rør jo gerne skal komme ind på skærmen i forskellige højder, ligesom de i et klassisk Flappy Bird spil.

At få en tilfældig y-koordinat er dog heldigvis nemt vhja. KAPLAY's <code>rand()</code> funktion, for hvilken vi blot vil give dennes parametre værdierne <code>-300</code> og <code>-200</code>, således at højden på et rørs placering skiftes tilfældigt.

Så derfor laver vi blot en variabel kaldet "randomY", og sætter denne lig med et kald som ovenfor beskrevet. Dvs.:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });

  const spawnPipes = () => {
    const randomY = rand(-300, -200);
  };

  spawnPipes();
}
```

###### Tilføj 'toppipe'

Tilføjelse af spillets øverste rør foregår på normal vis ved at tilføje dette med <code>add()</code>, hvori vil definere følgende komponenter:

- sprite()
- pos()
- area()
- et tag (som bare er en tekststreng)

###### sprite()

I <code>sprite()</code> komponenten angiver vi bare denne til vores tidligere loaded "toppipe".

###### pos()

For <code>pos()</code> komponenten angiver vi bare x-koordinaten til at være lig med skærmens bredde vhja. KAPLAY's <code>width()</code> funktion, og y-koordinaten til vores "randomY" variabel.

###### area()

<code>aread()</code> tilføjer vi bare uden parametre.

###### et tag

Som 'tag' til vores rør - dvs. både 'top' og 'bottom' - tildeler vi bare tekststrengen <code>"pipe"</code>

Koden til vores 'toppipe' bliver altså:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });

  const spawnPipes = () => {
    const randomY = rand(-300, -200);
    const topPipe = add([
      sprite("toppipe"),
      pos(width(), randomY),
      area(),
      "pipe",
    ]);
  };

  spawnPipes();
}
```

###### Tilføj 'bottompipe'

Tilføjelsen af 'bottompipe' er stort set den samme som ovenstående.

Eneste ændringer af <code>sprite()</code> og <code>pos()</code> komponenterne er følgende.

###### sprite()

<code>sprite()</code> gives teksten <code>"bottompipe"</code> som reference til vores tidligere loaded sprite.

###### pos()

<code>pos()</code> komponentens x-koordinat sættes igen til <code>width()</code>, mens y-koordination sættes til y-koordinaten af 'toppipe' plus dennes højde plus 100 pixels for at skabe mellemrummet mellem rørerne.

Koden for 'bottompipe' er derfor:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });

  const spawnPipes = () => {
    const randomY = rand(-300, -200);
    const topPipe = add([
      sprite("toppipe"),
      pos(width(), randomY),
      area(),
      "pipe",
    ]);
    const bottomPipe = add([
      sprite("bottompipe"),
      pos(width(), topPipe.pos.y + topPipe.height + 100),
      area(),
      "pipe",
    ]);
  };

  spawnPipes();
}
```

###### Flyt rør ved update af spillet

På nuværende tispunkt tilføjer vi altså kun ét 'top' og 'bottom' helt ude til højre i skærmen, således at disse ikke kan ses.

Imidlertid vil vi jo gerne have disse til kontinuerligt at flytte sig til venstre hen over skærmen, således at vores Flappy Bird kan prøve at 'flyve' igennem disse.

Måden vi får det til at ske, er heldigvis ganske simpel ved at bruge vhja. <code>onUpdate()</code> metoden på begge rør, og så inde i denne funktion flytte hvert rør med <code>-50</code> på x-aksen for begge rør vhja. <code>move()</code> metoden.

Koden for at flytte rørerne er derfor:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });

  const spawnPipes = () => {
    const randomY = rand(-300, -200);
    const topPipe = add([
      sprite("toppipe"),
      pos(width(), randomY),
      area(),
      "pipe",
    ]);
    const bottomPipe = add([
      sprite("bottompipe"),
      pos(width(), topPipe.pos.y + topPipe.height + 100),
      area(),
      "pipe",
    ]);

    topPipe.onUpdate(() => {
      topPipe.move(-50, 0);
    });
    bottomPipe.onUpdate(() => {
      bottomPipe.move(-50, 0);
    });
  };

  spawnPipes();
}
```

###### Tilføj nye rør hvert 5 sekund

Med den konstante bevægelse af hvert rør, så mangler faktisk nu kun at kalde vores "spawnPipes" funktion hvert 5 sekund, således at nye rør skabes, der ligeledes vil bevæge sig hen over skærmen.

Heldigvis kan vi også nemt kode dette vhja. KAPLAY's <code>wait()</code> funktion, da man skal give denne en første parameter for hvor ofte en funktion skal eksekeveres, og som anden parameter den funktion som skal eksekveres.

I vores tilfældes giver vi således blot denne funktion tallet <code>5</code> som første parameter, og dernæst en reference til vores <code>spawnPipes</code> som anden parameter.

Vores kode bliver altså følgende:

```javascript
export default function gameScene() {
  setGravity(400);

  const bg = add([sprite("bg")]);

  const bird = add([
    sprite("bird"),
    pos(30, center().y),
    scale(0.8),
    area(),
    anchor("center"),
    body({ jumpForce: 140 }),
    offscreen(),
  ]);

  bird.onKeyPress("space", () => {
    bird.jump();
  });

  bird.onCollide("pipe", () => {
    go("game-over");
  });

  bird.onExitScreen(() => {
    go("game-over");
  });

  const spawnPipes = () => {
    const randomY = rand(-300, -200);
    const topPipe = add([
      sprite("toppipe"),
      pos(width(), randomY),
      area(),
      "pipe",
    ]);
    const bottomPipe = add([
      sprite("bottompipe"),
      pos(width(), topPipe.pos.y + topPipe.height + 100),
      area(),
      "pipe",
    ]);

    topPipe.onUpdate(() => {
      topPipe.move(-50, 0);
    });
    bottomPipe.onUpdate(() => {
      bottomPipe.move(-50, 0);
    });

    wait(5, spawnPipes);
  };

  spawnPipes();
}
```

Og med dét er vores kodning af spillets "Game" scene nu færdigt, og denne scene skulle gerne se (nogenlunde) ud som følger:

<img width="861" alt="Screenshot 2025-03-21 at 11 21 20" src="https://github.com/user-attachments/assets/9e6e6523-bb9f-484c-8f49-a531c9194924" />

#### Kodning af "Game Over" scene

Yaaiii .. Nu mangler vi kun at kode vores "Game Over scene, og så er alt færdigt!!

Så åbn din "gameOverScene.js" fil, hvori vi vil kode denne scene efter disse steps:

1. Tilføj baggrundsbillede
2. Tilføj "Game Over" titel
3. Tilføj "Press space to play again .." undertitel
4. Håndtere tast på "space" for igen at spille spillet

##### Tilføj baggrundsbillede

Tilføjelsen af baggrundsbilledet har vi allerede gjort flere gange .. så koden er blot:

```javascript
export default function gameOverScene() {
  const bg = add([sprite("bg")]);
}
```

##### Tilføj "Game Over" titel

I vores "mainMenuScene.js" fil tilføjede vi her tidligere en titel til denne scene.

Og her vil vi blot bruge samme kode - med lidt få ændringer som er:

```javascript
export default function gameOverScene() {
  const bg = add([sprite("bg")]);
  const title = add([
    text("Game Over"),
    pos(center().x, center().y - 100),
    anchor("center"),
  ]);
}
```

##### Tilføj "Press space to play again .." undertitel

At tilføje en undertitel med teksten "Press space to play again .." gøres også på samme måde som tidligere - her, igen, med nogle få ændringer:

```javascript
export default function gameOverScene() {
  const bg = add([sprite("bg")]);
  const title = add([
    text("Game Over"),
    pos(center().x, center().y - 100),
    anchor("center"),
  ]);
  const subTitle = add([
    text("Press space to play again ..", { size: 18 }),
    pos(center()),
    anchor("center"),
  ]);
}
```

#### Håndtere tast på "space" for igen at spille spillet

Håndtering af tast på "space" for igen at spille spillet er totalt lig den fra vores "mainMenuScene.js" scene, hvorfor vi bare kan kopiere <code>onKeyPress()</code> funktionen og dens kode ind i vores "gameOverScene.js":

```javascript
export default function gameOverScene() {
  const bg = add([sprite("bg")]);
  const title = add([
    text("Game Over"),
    pos(center().x, center().y - 100),
    anchor("center"),
  ]);
  const subTitle = add([
    text("Press space to play again ..", { size: 18 }),
    pos(center()),
    anchor("center"),
  ]);

  onKeyPress("space", () => {
    go("game");
  });
}
```

## The End .. !
Med alt dette skulle du nu have dit eget  fuldt ud virkende 'Flappy Bird' spil .. godt gået, hvis du er nået her til!

## Bidrag
Denne guide er skabt med bidrag af:
- [Jonas Bak Phillipson](https://github.com/jbakchr) (_Formand og Kaptajn for Coding Pirates Hillerød_)
