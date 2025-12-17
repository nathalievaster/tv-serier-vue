# TV-serier – Vue SPA

Detta är en Single Page Application byggd i Vue 3 där användaren kan visa och lägga till TV-serier via ett eget REST-API. Applikationen är skapad som en del av en skoluppgift.

## Funktioner

* Visa lista med TV-serier

* Lägga till nya TV-serier

* Visa antal säsonger

* Visa om serien är pågående eller avslutad

* Enkel formulärvalidering med felmeddelanden

* Responsiv design med Tailwind CSS

## Viktigt att veta (Render)

Backend-API:t är hostat på Render (free tier).
Det innebär att tjänsten kan gå ner i viloläge om den inte används, första anropet kan därför ta upp till 1–2 minuter innan API:t svarar.


## API-endpoint
GET https://tv-serier-45iu.onrender.com/series
POST https://tv-serier-45iu.onrender.com/series

Exempel på data
{
  "title": "The Last of Us",
  "seasons": 2,
  "completed": true
}