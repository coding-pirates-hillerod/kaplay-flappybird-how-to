# Kod dit eget 'Flappy Bird' spil med KAPLAY

Dette repo gennemgår, hvordan man koder sit eget 'Flappy Bird' spil i VS Code fra start til slut med Node.js og spilbiblioteket KAPLAY.

Ved at følge denne 'how-to' guide vil du således ende ud med at have kodet dit helt eget Flappy Bird spil.

## Nødvendigt software

For at kunne kode spillet, skal du dog først og fremmest have følgende software installeret:

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

Lav herfra en ny mappe på dit Desktop ved at trykke på knappen 'new folder' og kald denne nye mappe for "kaplay".

<img width="977" alt="Screenshot 2025-03-18 at 21 01 36" src="https://github.com/user-attachments/assets/54c326af-8e1b-4e0f-9f07-98d3b9cccaf3" />

Tryk herefter på din nye "kaplay" mappe, så denne er markeret, og tryk dernæst på knappen "Open".

<img width="977" alt="Screenshot 2025-03-18 at 21 06 13" src="https://github.com/user-attachments/assets/4306d7c3-7e73-467b-bd7a-e274c927e2fa" />

Dette åbner "kaplay" mappen i VS Code, og alt hvad angår VS Code burde nu være på plads (hvis en "velkomstfane" endnu en gang vises efter du har åbnet mappen, så bare luk denne fane ved at trykke på det lille "x" til højre for teksten "_Welcome_" på fanen i midten af skærmen).

<img width="977" alt="Screenshot 2025-03-18 at 21 19 52" src="https://github.com/user-attachments/assets/56f89e97-2fdf-46cc-903d-50f08450bfd4" />

### Tjek Node.js installation

Nu hvor VS Code er på plads, skal vi som det næste lige have tjekket, at din Node.js installation (og den "package manager", kaldet <code>npm</code>, som kommer med Node.js) er installeret ordentligt, hvilket gøres som følger.

Tryk først på menuen "Terminal" i VS Codes menubjælke, og tryk derefter på "New Terminal" i dropdown listen.

<img width="871" alt="Screenshot 2025-03-18 at 21 58 37" src="https://github.com/user-attachments/assets/af68f67d-b830-47a5-9585-0adcfce1a7c0" />

Når dette gøres, så åbnes der en terminal i bunden af VS Code (hvilken måske ser lidt anderledes ud for dig end i dette eksempel - men gør ingen forskel for det videre).

<img width="977" alt="Screenshot 2025-03-18 at 22 14 08" src="https://github.com/user-attachments/assets/89866104-ddea-4a76-bac3-a83c2efe570f" />

