# Kod dit eget 'Flappy Bird' spil med KAPLAY

Dette repo gennemgår, hvordan man koder sit eget 'Flappy Bird' spil i VS Code fra start til slut med Node.js og spilbiblioteket [KAPLAY](https://kaplayjs.com/).

Ved at følge denne 'how-to' guide vil du således ende ud med at have kodet dit helt eget Flappy Bird spil.

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

Inden vi gør det, så vil vi dog lige lave en mappe til vores scener - som vi vil kalde "scenes" og ligger den under "src" mappen - således at vores kode er bedre struktureret og dermed nemmere at forstå (også for os selv 😅).

##### "scenes" mappe
For at lave en "scenes" skal vi blot gøre følgende i VS code.

Højreklik først på "src" mappen, og tryk derefter på "New Folder" i popup-menuen.

<img width="851" alt="Screenshot 2025-03-20 at 07 49 38" src="https://github.com/user-attachments/assets/668da908-b78b-47df-9b62-35e7630f2545" />

Med det vil der under "src" mappen dukker en ny mappe op under denne, i hvilken vi skriver "scenes" (og trykker 'enter' for navngive mappen dette navn).



##### Main Menu scenen
