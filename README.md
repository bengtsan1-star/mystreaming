# 📺 mystreaming

App to keep track of streaming and give suggestions about new streaming.

**mystreaming** är en enkel webbapp för att hålla koll på vad du ser på olika streamingtjänster,
hitta nya serier och filmer att titta på och få veta när det kommer nya avsnitt.
Appen är en enda HTML-fil och behöver ingen server, inget konto och ingen installation.

## 🌐 Öppna appen: [bengtsan1-star.github.io/mystreaming](https://bengtsan1-star.github.io/mystreaming/)

---

## Innehåll
- [Funktioner](#funktioner)
- [Kom igång](#kom-igång)
- [Koppla till TMDB (för Upptäck och Bevakning)](#koppla-till-tmdb)
- [Så använder du appen](#så-använder-du-appen)
  - [Min lista](#min-lista)
  - [Upptäck](#upptäck)
  - [Bevakning av nya avsnitt](#bevakning-av-nya-avsnitt)
  - [Spara och flytta listan](#spara-och-flytta-listan)
- [Inloggning](#inloggning)
- [Var sparas min data?](#var-sparas-min-data)
- [Utveckla vidare med GitHub](#utveckla-vidare-med-github)
- [Vanliga frågor](#vanliga-frågor)
- [Teknik](#teknik)
- [Data och tack](#data-och-tack)

---

## Funktioner

| Del | Vad den gör |
|---|---|
| **Min lista** | Titlar med tjänst, typ (serie/film), kategori och status: *Tittar nu*, *Vill se* eller *Sett klart*. Avsnittsräknare för serier och betyg 1–5 stjärnor. |
| **Sök och filter** | Sök på titel och filtrera på status, tjänst och kategori. Statistik överst. |
| **Upptäck** | Bläddra bland serier och filmer som finns på svenska streamingtjänster, per tjänst och kategori. Sortera på populärast, bäst betyg eller nyast. |
| **Fritextsökning** | Sök på valfri titel och se direkt vilka tjänster i Sverige som har den. |
| **Bevakning** | Visar nya och kommande avsnitt för serier du följer och markerar dem med 🆕. |
| **Spara till fil** | Säkerhetskopia (JSON), export till Excel (CSV) och inläsning från fil. |

Över 15 tjänster finns förvalda: Netflix, HBO Max, Disney+, Viaplay, Prime Video, Apple TV+, SVT Play,
TV4 Play, SkyShowtime, Paramount+, Discovery+, UR Play, Mubi, Cineasterna, Crunchyroll, YouTube m.fl.
Under Upptäck hämtas den aktuella listan över tjänster direkt från TMDB.

---

## Kom igång

### Använd appen på nätet (enklast)
Öppna **[bengtsan1-star.github.io/mystreaming](https://bengtsan1-star.github.io/mystreaming/)** i valfri
webbläsare – på datorn eller i mobilen. Inget att installera.

**Lägg till på hemskärmen i mobilen**
- **iPhone (Safari):** tryck **Dela** → **Lägg till på hemskärmen**.
- **Android (Chrome):** tryck **⋮** → **Lägg till på startskärmen**.

Då öppnas appen med en egen ikon, nästan som en vanlig app.

### Kör appen lokalt
1. Ladda ner eller klona repot:
   ```bash
   git clone https://github.com/bengtsan1-star/mystreaming.git
   ```
2. Öppna `index.html` i din webbläsare (dubbelklicka på filen).
3. Klart! Börja lägga till det du tittar på under **Min lista**.

### Bra att veta
- **Varje enhet och webbadress har sin egen lista och nyckel.** Webbversionen och en lokalt öppnad
  `index.html` räknas som olika platser – lägg in TMDB-nyckeln en gång per enhet och flytta listan med
  **💾 Spara lista till fil** och **📂 Läs in fil**.
- **Webbversionen uppdateras automatiskt.** Sidan publiceras med GitHub Pages från grenen `main`;
  varje push dit syns på webbadressen efter någon minut.

---

## Koppla till TMDB

*Min lista* fungerar direkt. För **Upptäck** och **Bevakning** behöver appen hämta data från
filmdatabasen [TMDB](https://www.themoviedb.org/), vilket kräver en gratis API-nyckel:

1. Skapa ett gratis konto på [themoviedb.org](https://www.themoviedb.org/signup).
2. Gå till [Inställningar → API](https://www.themoviedb.org/settings/api) och begär en nyckel
   för **personligt bruk**.
3. Kopiera din **API Key** (eller *API Read Access Token* – båda fungerar).
4. Öppna fliken **Upptäck** i appen, klistra in nyckeln och klicka **Spara**.

Nyckeln sparas bara i din webbläsare och finns aldrig i koden. Använder du appen på flera enheter
lägger du in nyckeln en gång per enhet. Vill du byta nyckel finns knappen **Byt API-nyckel**
längst ner under Upptäck.

---

## Så använder du appen

### Min lista

**Lägga till en titel**
1. Skriv titeln i fältet **Titel**.
2. Välj **Tjänst**, **Typ** (serie eller film), **Kategori** och **Status**.
3. Klicka **Lägg till** (eller tryck Enter).

**Status**
- **Tittar nu** – det du håller på med. Serier får en avsnittsräknare och bevakas automatiskt.
- **Vill se** – din att-se-lista.
- **Sett klart** – här kan du sätta betyg med stjärnorna (klicka på samma stjärna igen för att ta bort betyget).

Byt status med knapparna **→ Tittar nu**, **→ Vill se** och **→ Sett klart** till höger på varje titel.

**Hålla koll på avsnitt**
För serier med status *Tittar nu* visas **S** (säsong) och **A** (avsnitt). Klicka **+1 avsnitt**
när du sett ett avsnitt, eller skriv in siffrorna direkt.

**Hitta i listan**
- Flikarna **Alla / Tittar nu / Vill se / Sett klart** filtrerar på status.
- Sökfältet filtrerar på titel.
- Rullistorna filtrerar på tjänst och kategori (de visar bara det som finns i din lista).

**Ta bort** – knappen *Ta bort* frågar alltid först.

### Upptäck

Här hittar du nytt att titta på – även sådant du inte lagt till själv.

**Bläddra**
1. Välj **Serier** eller **Filmer**.
2. Välj **Tjänst** (t.ex. Netflix) och/eller **Kategori** (t.ex. Komedi).
3. Välj sortering: **Populärast**, **Bäst betyg** eller **Nyast**.
4. Klicka **Visa fler** längst ner för fler träffar.

**Söka på titel**
Skriv i sökfältet överst, t.ex. *Bonusfamiljen*. Appen söker automatiskt efter en kort paus
(eller när du trycker Enter) och visar både serier och filmer. Varje kort visar vilka tjänster
i Sverige som har titeln, t.ex. *📺 Netflix, SVT Play*. Töm sökfältet för att komma tillbaka
till bläddringsläget. (Filtren för typ, tjänst och kategori gäller inte vid fritextsökning.)

**Lägga till**
Klicka **+ Vill se** på ett kort. Titeln hamnar i *Min lista* med tjänst, kategori och år ifyllt,
och knappen ändras till **✓ I din lista**.

### Bevakning av nya avsnitt

Rutan **🔔 Bevakning** överst i *Min lista* visar:
- **Nya avsnitt** – avsnitt som släppts sedan förra kollen, eller under de senaste 14 dagarna
  och som du inte sett enligt din avsnittsräknare.
- **Kommande** – nästa avsnitt med datum, t.ex. *om 4 dagar*.

**Vilka serier bevakas?**
- Serier med status *Tittar nu* bevakas automatiskt.
- Andra serier (t.ex. på *Vill se* när du väntar på en ny säsong) slår du på med **🔔 Bevaka**.
- Stäng av med **🔕 Sluta bevaka**.

**När kollar appen?**
Automatiskt när du öppnar appen (högst var 6:e timme), eller direkt när du klickar **Kolla nu**.

**Märket 🆕 Nytt avsnitt**
Visas på serier med något nytt. Klicka på märket för att kvittera – för serier du tittar på hoppar
avsnittsräknaren då fram till senaste avsnittet.

Serier du lagt till själv kopplas till TMDB via titeln. Om appen hittar en serie med ett annat namn
står det *kopplad till ”…”* så att du kan se att den valt rätt.

### Spara och flytta listan

Knapparna under statistiken i *Min lista*:

| Knapp | Vad den gör |
|---|---|
| **💾 Spara lista till fil** | Sparar hela listan som `mystreaming-ÅÅÅÅ-MM-DD.json` i *Hämtade filer*. Bra som säkerhetskopia. |
| **📊 Exportera till Excel (CSV)** | Sparar listan som en tabell som går att öppna i Excel eller Numbers. |
| **📂 Läs in fil** | Läser in en sparad JSON-fil. Titlarna slås ihop med din lista – samma titel blir aldrig dubbel, och den senast ändrade versionen behålls. |

**Flytta listan till en annan dator eller mobil:** spara till fil på den ena enheten och läs in
filen på den andra – eller använd GitHub-synk nedan.

### Spara listan i GitHub

Listan kan sparas som en fil (`lista.json`) i ett **privat** GitHub-repo, så att du har samma lista
på alla enheter. Appens kod är publik, men listan ligger i ett separat privat repo
(t.ex. `bengtsan1-star/mystreaming-data`) som bara du kommer åt.

**Ställ in (en gång per enhet)**
1. Skapa en token på [GitHub → Fine-grained token](https://github.com/settings/personal-access-tokens/new).
2. **Repository access:** *Only select repositories* → **mystreaming-data**.
3. **Permissions → Repository permissions → Contents:** *Read and write*.
4. Klicka **Generate token** och kopiera den.
5. I appen under *Min lista*: klicka **⚙️**, klistra in token och klicka **Spara och synka**.

**Så fungerar synken**
- Appen synkar automatiskt när den öppnas och några sekunder efter varje ändring.
  **☁️ Synka med GitHub** synkar direkt.
- Ändringar från flera enheter slås ihop: den senast ändrade versionen av en titel vinner,
  och borttagna titlar förblir borttagna.
- Varje synk blir en commit i repot, så du kan se historiken och återställa äldre versioner.
- **Koppla från** (under ⚙️) stänger av synken på enheten.

Token sparas bara i din webbläsare. Ge den åtkomst till *endast* datarepot.

---

## Inloggning

Appen öppnas med en enkel inloggningsskärm:

| | |
|---|---|
| **Användarnamn** | `stream` |
| **Lösenord** | `stream` |

- Med **Kom ihåg mig på den här enheten** ibockad loggar du bara in en gång per enhet.
  Utan bocken gäller inloggningen tills du stänger fliken.
- **Logga ut** finns uppe till höger.

> ⚠️ Inloggningen är bara ett lås mot förbipasserande, inte riktigt skydd. Allt körs i webbläsaren
> och källkoden är publik, så användarnamn och lösenord går att läsa i `index.html`.
> Din lista syns ändå aldrig för andra – den ligger bara i din egen webbläsare.
> Vill du byta användarnamn eller lösenord ändrar du `LOGIN_USER` och `LOGIN_PASS` i `index.html`.

---

## Var sparas min data?

Allt sparas lokalt i din webbläsare (`localStorage`) – inget skickas till någon server förutom
sökningar mot TMDB. Det betyder att:

- listan finns kvar när du stänger och öppnar appen igen i **samma** webbläsare,
- olika webbläsare och enheter har **var sin** lista,
- listan försvinner om du rensar webbplatsdata i webbläsaren – spara därför till fil ibland.

---

## Utveckla vidare med GitHub

Koden finns i repot [bengtsan1-star/mystreaming](https://github.com/bengtsan1-star/mystreaming)
och webbversionen publiceras automatiskt med **GitHub Pages**.

### Så hänger det ihop

```
Din dator                    GitHub                         Webben
index.html  ── git push ──▶  repot mystreaming (main)  ──▶  bengtsan1-star.github.io/mystreaming
                             GitHub Pages bygger sidan       (uppdateras efter ca 1 minut)
```

### Första gången på en ny dator

1. Installera GitHubs verktyg (kräver [Homebrew](https://brew.sh/) på Mac):
   ```bash
   brew install gh
   ```
2. Logga in – webbläsaren öppnas och du godkänner med en engångskod:
   ```bash
   gh auth login --web --git-protocol https
   ```
3. Hämta koden:
   ```bash
   git clone https://github.com/bengtsan1-star/mystreaming.git
   cd mystreaming
   ```

### Göra en ändring och publicera den

1. Ändra i `index.html` (eller `README.md`) och testa genom att öppna filen i webbläsaren.
2. Se vad som ändrats:
   ```bash
   git status
   git diff
   ```
3. Spara ändringen som en *commit* med en kort beskrivning:
   ```bash
   git add index.html
   git commit -m "Beskriv vad du ändrade"
   ```
4. Skicka upp till GitHub:
   ```bash
   git push
   ```
5. Vänta ungefär en minut och ladda om
   [webbadressen](https://bengtsan1-star.github.io/mystreaming/) (⌘R).

### Användbara kommandon

| Kommando | Vad det gör |
|---|---|
| `git status` | Visar vilka filer som ändrats |
| `git diff` | Visar exakt vad som ändrats |
| `git log --oneline` | Visar historiken |
| `git pull` | Hämtar senaste versionen från GitHub (om du ändrat på en annan dator) |
| `git restore index.html` | Ångrar ändringar i en fil som inte är committade |
| `gh auth status` | Visar om du är inloggad på GitHub |

### GitHub Pages-inställningar

Pages är inställt under **Settings → Pages** i repot: källa är grenen `main` och mappen `/` (rot).
Där ser du också status för senaste publiceringen. Under fliken **Actions** syns varje bygge –
blir något fel visas det där.

---

## Vanliga frågor

**Upptäck säger att API-nyckeln inte godkändes.**
Kontrollera att du kopierat hela nyckeln utan mellanslag. Du hittar den på
[themoviedb.org/settings/api](https://www.themoviedb.org/settings/api).

**En serie visar fel avsnitt eller är kopplad till fel serie.**
Ta bort titeln och lägg till den igen via *Upptäck* – då kopplas den till exakt rätt serie.

**Kan jag få notiser om nya avsnitt?**
Inte än. Appen kollar bara när den är öppen. Notiser kräver en server som kollar regelbundet.

**Varför saknas en tjänst?**
I *Min lista* kan du välja *Annan*. Under *Upptäck* visas alla tjänster som TMDB känner till i Sverige.

---

## Teknik

- En enda fil: `index.html` med HTML, CSS och JavaScript – inga ramverk eller beroenden.
- Data sparas i webbläsarens `localStorage`.
- Film- och seriedata hämtas från [TMDB API v3](https://developer.themoviedb.org/) (region `SE`, språk `sv-SE`).
- Följer webbläsarens ljusa/mörka läge och fungerar i mobilen.
- Publiceras med **GitHub Pages** från grenen `main` (rotmappen) till
  [bengtsan1-star.github.io/mystreaming](https://bengtsan1-star.github.io/mystreaming/).

---

## Data och tack

Film- och seriedata samt information om tjänster kommer från [TMDB](https://www.themoviedb.org/),
och uppgifter om var titlar kan streamas kommer från JustWatch via TMDB.
Den här appen använder TMDB:s API men är inte godkänd eller certifierad av TMDB.
