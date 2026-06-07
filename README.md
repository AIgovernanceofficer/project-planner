# Projectplanning — Kanban & Tijdlijn

Een lichtgewicht planningstool. Je beheert
taken als gekleurde kaarten op een **Kanban-bord**, sleept ze tussen statussen, en bekijkt
ze als een **tijdlijn (Gantt)**. Voor het management maak je met één klik een nette
**PowerPoint-samenvatting** op hoofdlijnen.

De hele app is één bestand (`index.html`). Er is geen installatie, geen account en geen
server nodig: alles draait lokaal in je browser.

---

## Aan de slag

**Lokaal openen.** Dubbelklik op `index.html`. De app opent in je standaardbrowser.

**Op GitHub Pages publiceren.**
1. Maak een repository aan en zet `index.html` in de hoofdmap.
2. Ga naar **Settings → Pages**.
3. Kies bij *Source* de branch `main` en map `/ (root)`, en sla op.
4. Na een minuut staat de app live op `https://<gebruikersnaam>.github.io/<repo>/`.

> Tip: bewaar `README.md` ook in de repo, zodat collega's weten hoe het werkt.

---

## De app gebruiken

- **Kaart toevoegen** — knop **Kaart** rechtsboven, of **+ Kaart toevoegen** onder een lane.
  Een kaart heeft een titel, beschrijving, verantwoordelijke, start- en einddatum,
  prioriteit, categorie/tag en een kleur uit het UU-palet.
- **Slepen** — versleep kaarten tussen lanes (statussen) en herorden ze binnen een lane.
- **Bewerken / verwijderen** — klik op een kaart.
- **Lanes** — hernoem een lane door op de titel te klikken; via het menu (de drie puntjes)
  voeg je een lane toe, en met het kruisje verwijder je er een.
- **Tijdlijn** — wissel bovenin tussen **Bord** en **Tijdlijn**. De tijdlijn bouwt zich
  automatisch op uit de datums en toont een "vandaag"-lijn. Taken met dezelfde start- en
  einddatum verschijnen als mijlpaal (ruitje).
- **Zoeken** — filter kaarten op tekst, naam of tag.

---

## Back-ups maken en terugzetten

> **Belangrijk:** je planning wordt bewaard in de browser op het apparaat dat je gebruikt.
> Maak regelmatig een back-up, want browseropslag kan verloren gaan (zie *Veilig gebruik*).

- **Menu → 💾 Back-up opslaan** — downloadt een bestandje (bijv.
  `projectplanning-2026-06-07.json`) met je hele planning. Bewaar dit ergens veilig.
- **Menu → ↩️ Back-up terugzetten** — kies zo'n bestand om je planning weer in te laden.

Een back-up is ook handig om je planning naar een ander apparaat of een collega over te zetten:
exporteren, het bestand delen, en de ander zet het terug.

---

## Managementexport naar PowerPoint

Via **Menu → 📊 Managementexport (PowerPoint)** maak je een deck van vier slides, bewust
op hoofdlijnen gehouden zodat het presenteerbaar blijft:

1. **Titelslide** in UU-huisstijl.
2. **Voortgang in één oogopslag** — afgeronde taken, percentage en verdeling over de statussen.
3. **Tijdlijn op hoofdlijnen** — één balk per werkstroom (gegroepeerd op categorie/tag),
   met mijlpalen en een "vandaag"-lijn.
4. **Mijlpalen & komende deadlines** — gesorteerd op datum; te-late taken worden gemarkeerd.

De slides bestaan uit echte, bewerkbare PowerPoint-vormen, dus je kunt na export nog tekst
aanpassen of het officiële UU-logo plaatsen.

---

## Veilig gebruik & privacy (AVG)

Deze tool is ontworpen om eenvoudig en lokaal te werken. Lees onderstaande punten voordat
je hem voor werk met persoonsgegevens inzet.

**Waar staan mijn gegevens?**
Je planning wordt opgeslagen in de lokale opslag (*localStorage*) van de browser op het
apparaat dat je gebruikt. De app stuurt jouw planninggegevens **niet** naar een server.

**Welke externe verbindingen zijn er wél?**
De app haalt twee dingen van het internet op, en alleen op het moment dat je ze gebruikt:
- de **lettertypen** (via Google Fonts) voor de juiste UU-opmaak;
- de **PowerPoint-module** (via cdnjs) wanneer je een managementexport maakt.

Daarbij worden technische verzoeken naar die externe diensten gedaan (zoals bij vrijwel elke
website). Je planninginhoud wordt daarbij niet meegestuurd — de PowerPoint wordt in je eigen
browser opgebouwd. Wil je volledig offline werken, dan kun je de lettertypen en de
PowerPoint-module lokaal meeleveren in plaats van via internet (zie *Aanpassen*).

**Aandachtspunten voor verantwoord gebruik:**
- **Gedeelde of openbare computers** — omdat de gegevens in de browser blijven staan, kan
  iemand anders op hetzelfde apparaat ze later openen. Gebruik op gedeelde apparaten een
  privé-/incognitovenster (let op: dan verdwijnt de planning na het sluiten — exporteer
  vooraf een back-up).
- **Browsergegevens wissen** — als je browsergeschiedenis/sitegegevens wist, of een andere
  browser of apparaat gebruikt, is de opslag leeg. Maak dus back-ups.
- **Back-upbestanden zijn niet versleuteld** — het geëxporteerde JSON-bestand is gewone,
  leesbare tekst. Bewaar het op een veilige, toegangsbeperkte locatie en mail het niet
  zomaar rond als het persoonsgegevens bevat.
- **Dataminimalisatie** — neem niet méér persoonsgegevens op dan nodig. Vermijd bijzondere
  categorieën persoonsgegevens (zoals gezondheid, religie, etniciteit). Voor namen van
  betrokkenen kun je overwegen om met initialen of rollen te werken.
- **Geen toegangsbeheer of logging** — de tool kent geen accounts, rechten of audit-trail.
  Gebruik hem als praktisch planningshulpmiddel, niet als bron- of registratiesysteem voor
  gevoelige informatie.
- **Publicatie via GitHub Pages** — de *app* is openbaar zichtbaar, maar jouw *planning*
  niet: die staat alleen in jouw browser, niet in de repository. Zet geen back-upbestanden
  met persoonsgegevens in een openbare repo.

> Dit is algemene informatie over hoe de tool werkt, geen juridisch advies. Toets het
> gebruik bij twijfel aan je eigen organisatierichtlijnen en, waar van toepassing, aan je
> privacy- of functionaris gegevensbescherming.

---

## Het UU-logo toevoegen

Het officiële UU-logo mag niet nagemaakt of aangepast worden en zit daarom niet ingebakken.
Wil je het toevoegen:
1. Zet het officiële logobestand (de Nederlandse variant) als `logo.png` naast `index.html`.
2. Vervang in `index.html` het blok `<div class="logo-slot">…</div>` door:
   `<img src="logo.png" alt="Universiteit Utrecht" style="height:42px">`

---

## Aanpassen

- **Kleuren en lettertypen** staan bovenin `index.html` als CSS-variabelen (`:root`) en in
  het `COLORS`-blok in het script — passend bij het UU-palet.
- **Standaard-lanes en voorbeeldkaarten** vind je in de functie `seed()`.
- **Volledig offline** maken: download de lettertypen en het bestand
  `pptxgen.bundle.js` en verwijs er lokaal naar in plaats van naar de internetlinks.

---

## Techniek

Eén `index.html` met HTML, CSS en JavaScript; geen build-stap en geen afhankelijkheden om te
installeren. De PowerPoint-export gebruikt de browserbibliotheek PptxGenJS. Opslag verloopt
via *localStorage* met een terugval op tijdelijk geheugen wanneer opslag niet beschikbaar is.
