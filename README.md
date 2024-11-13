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
Je zal zien dat er momenteel 1 layout gebruikt wordt. Er zit echter nog niet heel veel in. De navigatie zit bijvoorbeeld nog elke pagina apart. Verplaats de juiste dingen naar de layout zodat je de navigatie op 1 plaats hebt zitten.

## Oefening 3 - De navigatie uitbreiden
We willen bovenop de `home` en de `about` pagina nog een extra pagina hebben: de evenementen pagina. Op de evenementen pagina moet je ook kunnen navigeren. Deze zal dus ook de MainLayout nodig hebben. Voor onze evenementen pagina hebben we ruwweg volgende bouwblokken nodig:
- Een extra path in de router om naar deze pagina te navigeren
- Een view voor deze pagina (die dan gerefereerd wordt in de router)
- Een knop in de navigatie om naar deze pagina te navigeren

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

Toon deze lijst van evenement op de `evenementen` pagina. Je gaat waarschijnlijk de volgende stappen moeten volgen:
- Een script tag toevoegen aan de evenementen pagina (opgelet, typescript en setup!)
- Een variabele definiëren waar je de lijst in opslaat
- Deze variabele in een reference wrappen zodat er een binding is met de html in de template. Opgelet met typescript types en references. Als je de variable in een `ref` wrapt moet je de type in een `Ref` wrappen.
- Een typescript interface definiëren voor een evenement (waarschijnlijk niet strikt nodig maar wel proper). Je mag hiervoor in `components` een file aanmaken `models.ts` waar je deze interface kan exporteren. Op die manier kan je hem importeren in je `EventsView` met `import type {Evenement} from '@/components/models`
- Een `v-for` loop schrijven om over de lijst van evenementen te gaan en deze weer te geven in je template. Voor de styling mag je je fantasie een beetje gebruiken :-).

## Oefening 5 - Toekomstige evenementen tonen in de Home view
In de HomeView willen we de evenementen tonen die nog niet gepasseerd zijn (`evenement.passed = false`). Je zou hiervoor de lijst van evenementen kunnen kopiëren naar de home pagina. Vervolgens kan die daar gefilterd worden en kan je een lijst van evenementen weergeven.
Een betere manier is echter om deze lijst van evenementen en het filteren daarvan te verhuizen naar een service.
- Maak een evenement.service.ts aan
- Verplaats de evenementen array naar de service en exporteer die op de juiste manier (`useEvenement`)
- Importeer deze lijst nu in de evenementen pagina en kijk of alles nog werkt

Je kan deze lijst nu ook importeren in de Home view en daar filteren en in de template weergeven **of** je maakt een `getFutureEvents` functie aan in de service (beter) die je kan gebruiken om alleen de toekomstige evenementen in de service weer te geven.