## Oefening 1 - Runnen van de applicatie
Zorg ervoor dat je de applicatie kan runnen. Je gaat eerst alle package moet installeren:
```bash
npm install
```

En vervolgens kan je de applicatie runnen met

```bash
npm run dev
```

## Oefening 2 - De layout
Je zal zien dat er momenteel 1 layout gebruikt wordt. Er zit echter nog niet heel veel in. De navigatie zit bijvoorbeeld nog op elke pagina apart. Verplaats de juiste elementen naar de layout zodat je de navigatie op 1 plaats kan beheren. Kijk ook nog even na of er misschien andere elementen gedeeld kunnen worden door de verschillende pagina's.

## Oefening 3 - De navigatie uitbreiden
We willen bovenop de `home` en de `about` pagina nog een extra pagina toevoegen: een evenementen pagina. Op de evenementen pagina moet je ook kunnen navigeren naar de andere pagina's. Deze zal dus ook de MainLayout, met de recent toegevoegde navigatie, nodig hebben. Om onze evenementen pagina toe te voegen moeten we ruwweg de volgende stappen volgen:

- Een extra path object in de router toevoegen om naar deze pagina te navigeren
- Een view voor deze pagina (die dan gerefereerd wordt in de router)
- Een knop in de navigatie om naar deze pagina te navigeren

Voorlopig mag de evenementen pagina nog een vrij lege pagina zijn. We gaan in het volgende oefening er wat content aan toevoegen.

## Oefening 4 - Evenementen tonen
Gegeven de volgende lijst van evenementen:

```ts
const evenementen = [
    {name: "super duper party", date: "tomorrow", passed: false},
    {name: "fantastic event", date: "yesterday", passed: true},
    {name: "super duper party2", date: "15/12/24", passed: false},
    {name: "super festival ", date: "11/11/24", passed: true},
]
```

Toon deze lijst van evenementen op de `evenementen` pagina. Je gaat waarschijnlijk de volgende stappen moeten volgen:

- Een script tag toevoegen aan de evenementen pagina (opgelet, de language is typescript en het is een setup script!)
- Een variabele definiëren waar je de lijst in opslaat
- Deze variabele in een reference wrappen zodat er een binding is met de html in de template. Opgelet met typescript types en references. Als je de variable in een `ref` wrapt moet je de type in een `Ref` wrappen.
- Een typescript interface definiëren voor een evenement. Het is niet strikt nodig om deze in een aparte file te steken maar het zorgt wel voor properdere code als je je types in een aparte file beheert. Je mag hiervoor in `components` een file aanmaken `models.ts` waar je deze interface kan aanmaken en exporteren. Op die manier kan je hem importeren in je `EventsView` met `import type {Evenement} from '@/components/models`
- Een `v-for` loop schrijven om over de lijst van evenementen te gaan en deze weer te geven in je template. Voor de styling mag je je fantasie een beetje gebruiken :-).

## Oefening 5 - Toekomstige evenementen tonen in de Home view
In de HomeView willen we de evenementen tonen die nog niet gepasseerd zijn (`evenement.passed = false`). Je zou hiervoor de lijst van evenementen kunnen kopiëren naar de home pagina. Vervolgens kan die daar gefilterd worden en kan je een lijst van evenementen weergeven.
Een betere manier is echter om deze lijst van evenementen (en het filteren daarvan) te verhuizen naar een service.
- Maak een evenement.service.ts aan
- Verplaats de evenementen array naar de service en exporteer die op de juiste manier (`useEvenement`)
- Importeer deze lijst nu in de evenementen pagina en kijk of alles nog werkt

Je kan deze lijst nu ook importeren in de Home view en daar filteren om in de template weer te geven. **Een betere manier zou zijn** dat je een `getFutureEvents` functie maakt in de service die je kan gebruiken om alleen de toekomstige evenementen in de service weer te geven.

- Maak een `getFutureEvents` functie in de service
- Zorg ervoor dat je in deze functie alleen de evenementen returned die nog niet geweest zijn (passed = false)
- Expose deze functie / variabele
- Gebruik de functie / variabele in de HomeView

## Oefening 6 - Custom component
Elke Pagina heeft zijn eigen titel. Geef deze titel wat styling zodat het er mooier uitziet (bv een andere kleur, een andere font, ...).
Om te voorkomen dat je dit voor elke pagina / view apart moet doen kan je de titel in een custom component zetten en de styling daar doen.
