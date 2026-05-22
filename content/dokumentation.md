---
Draft: "false"
Title: dokumentation
Author: Jonathan Friis
Description: En overfladisk guide til kommende webmastere
Weight:
---
### DISCLAIMER
Denne artikel lærer dig ikke at bruge de nødvendige værktøjer for at kunne hoste siden, den lærer dig kun de absolut basale nødvendigheder for at kunne opdatere artiklerne, hvis du ikke kan bruge basal commandline på din computer, så er der lang vej. Ikke desto mindre er det muligt at lære det og komme godt videre.

Det er meningen at man skal kunne ændre i artiklen til kommende generationer af webmastere. Den kan faktisk også findes på selve hjemmesiden under https://aporia-fagblad.dk/dokumentation/

Dog er den "skjult" da der ikke er nogen links til den.

### Hvordan fungerer hjemmesiden
Vi bruger et program kaldet hugo til at sætte hjemmesiden op, hjemmesiden bliver hostet af gtihub. Git bruges til at sende filerne til github. Det hjælper at have kendskab til commandline og markdown, men det er ikke nødvendigt, alt derudover kan læres. Commandline vil herfra blive refereret til som CLI.

**Github:** Github hoster vores hjemmeside gratis, jeg har indsat et workflow, på github, som der ikke må ændres i, medmindre hugo eller github kommer med en opdatering som gør workflowet ubrugeligt. Det fungerer sådan at man uploader aporia mappen til github, hvor github så kører et hugo program som aflæser filerne, giver hjemmesiden til github som så hoster siden.

**CLI:** Bruges til at opdaterer hjemmesiden i sig selv, du skal kunne navigere i forskellige mapper og ændrer i filer med din favorit text editor, jeg bruger selv lazyvim gennem neovim fordi det fungerer rigtigt godt sammen med CLI. Neovim er en svær text editor at lære, men man kan ikke rigtigt komme fra det igen når man først er startet med det.

**Obsidian:** Er et program du kan bruge til nemt at navigere i for at finde artiklerne i selve aporia mappen, den aflæser md filtyper og viser dem pænt struktureret. Det er generelt også fantastisk til at tage noter i.

**Markdown:** Er et format som obsidian og hugo bruger. Alle artikler skal have formatet md for at kunne aflæses af hugo.


### Hvordan formaterer man en artikel?
Hvis du har en smule erfaring med markdown burde det ikke være så svært. Jeg foreslår at kigge i en af de nuværende artikler (i aporia mappen). De ligger under `aporia-fagblad\content\udgivelser`. De har en masse egenskaber i toppen som man skal udfylde, de skal være tilstede øverst i md filen, hugo aflæser filerne og tager dem i brug. Det er sådan den skelner mellem metadata som "forfatter", beskrivelse osv.

Du kopierer selve artiklerne du får tilsendt ind i en ny markdown fil. Det er nemmest at kopiere fra word. Hvis de sender dig en pdf, så bed om at få de originale filer tilsendt, for det tager 10 timer ekstra at kopiere fra pdf.

Hvis du bruger obsidian kan du bruge en template til både \_Index og til artiklerne, så udfylder du bare felterne.

#### Metadata:
Data som indgår under alle artiklerne 

**Draft** Afgør om artiklen skal være med på siden eller ej, altså om den skal vises på hjemmesiden. Hvis der står false vil hjemmesiden komme med, derfor skal der generelt stå false ved dem alle sammen.

**title** afgør hvad titlen er, det skal self bare være titlen på artiklen, og være det samme som titlen på md dokumentet.

**author** er forfatteren, husk at den muligvis skal stå tomt, hvis forfatteren vil anonymiseres, alternativt kan de jo vælge et pseudonym.

**weight** er artiklens placering i forhold til de andre på index siden, den mindste vægt står øverst, derfor skal der stå "1" ved den første artikel, "2" ved den næste, osv..



### Hvordan opdaterer man hjemmesiden når der kommer en ny udgivelse?
Man skal først lave en ny mappe i udgivelsesmappen fundet under `aporia-fagblad\content\udgivelser`.

De nuværende mapper hedder ting som F2025, E2025 (For forår og efterår). Alle udgivelser skal lægges inde i mappen i et markdown (md) format. Så kald den nye mappe det samme.

Derefter laver du en ny .md fil inde i mappen der hedder \_index, det er der "Leder" afsnittet skal være.

Derefter laver du bare en ny fil i mappen til hver artikel, formaterer artiklerne og lægger dem i mappen.

##### Ændre seneste udgivelse knappen
Derefter går du ind i \config\_default\hugo.yaml og ændrer linje 36 til den udgivelse du er nået til. Så fx. hedder den lige nu F2026. Så der står på linjen:
url: "https://exukia.github.io/aporia-fagblad/udgivelser/f2026/"

Så hvis din nye udgivelse hedder E2026 skal den ændre til:
url: "https://exukia.github.io/aporia-fagblad/udgivelser/e2026/"

Derefter vil knappen på forsiden som hedder "seneste udgivelser", sende brugeren til den seneste udgivelse.

Prøv nu at skriv "hugo server" i terminalen (med aporia-fagblad som working directory). Der vil komme et link, oftest http://localhost:1313/. Siden vil nu have alle de nye artikler, og man ville kunne se og rette i dem.


### Hvad er \_index?
\_index er teksten der bliver vist på siden, jeg har brugt den til at vise forordet for alle udgivelserne. Den har en anden template end artiklerne, da indstillingerne er anderledes.


### Hvordan bruger man git?
Du behøves ikke vide en skid om git, når det først er sat op skal du kun kende disse tre kommandoer:

**git add:** Tilføjer filen eller mappen til den næste version. Hvis man skriver `git add .` mens man er i sit working directory(Aporia-fagblad.dk mappen), så vil alle ændringer man har foretaget sig komme med i næste opdatering. Det er den nemmeste måde at gøre det på.

**git commit -m:** Man skriver hvilke ændringer der har været, som en kommentar. Så hvis man har ændret i fonten siden sidste opdatering, så vil man skrive `git commit -m "Ændret i font"`. Så vil den kommentar stå ved alle filer der er blevet ændret siden sidst, det er også muligt at skrive noget specifikt til hver fil. Men det kommer vi ikke ind på her.

**git push:** skubber ændringerne til github og opdaterer den rigtige hjemmeside "aporia-fagblad.dk".

Hvis man har behov for at vide mere om git, er det en fordel at spørge sin yndlings LLM eller kigge på youtube. Derudover vil den ansvarlige før dig hjælpe dig med opsætningen, ellers så skriv til aporia@jonathanfriis.dk.


### Hvordan ændrer man billederne af bestyrelsen
Man går simpelthen bare ind i mappen `static\images`og fjerner de gamle billeder og tilføjer nye med det samme navn, fx fjerner man billedet `webmaster.jpg`og indsætter et billede af den nye webmaster kaldet `webmaster.jpg`. HUSK FILTYPEN.


### Hvad nu hvis vi vil ændre i formatet?
Lær at bruge hugo, der findes utallige overfladiske youtubevideoer, se de lange i stedet for de korte. Det kommer man længst med. 

Man kan ændre font, farver, logoer osv. men sæt dig godt ind i det først. Det tog mig 30 timer at lære det med middelmådig erfaring, så kan du også.


### Opdater "seneste udgivelse" knappen på forsiden
For at opdatere knappen skal du gå ind under \config\_default\hugo.yaml og opdaterer feltet "seneste" under feltet "button". Det eneste du skal opdatere er at ændre linket, så hvis du vil opdatere fra E2067 til F2068 skal du ændre det fra:

url: "https://exukia.github.io/aporia-fagblad/udgivelser/E2067/"

Til:

url: "https://exukia.github.io/aporia-fagblad/udgivelser/F2028/"

Husk på, at linket refererer til en bestemt mappe, derfor skal den nye mappe også hedde F2068 for at linket kan henvise til et bestemt sted.


### Vil du gøre noget fancy?
Hvis du vil ændre i noget CSS kode skal du navigere til `\assets\css\common\`der findes alle mine ændringer, som fx. font, opsætning af bibliografi, opsætning af fodnoter osv. Der står under al kode hvad det gør. Lad vær med at skrive noget i dem hvis du ikke ved hvad du har gang i.

HTML ændres under `\layouts\partials\`der findes nogen forskellige ændringer, noget af det er standard indstillinger, andet er font osv. Lad vær med at skrive noget i dem hvis du ikke ved hvad du har gang i.

Hugo konfigurationen findes under `\config\_default\`der er konfiguration som brødkrummer, antal sider på en side, startside, logoer osv. Hvis man vil ændre aporias logo på forsiden skal man lægge et billede ind i mappen `\static\images\` kaldet aporia.jpg, og fjerne den gamle.


#### Sæt dit præg:
Skriv dit navn herunder og udødeliggør dig selv:
Jonathan Friis

