# API Dokumentácia pre Ubytovanie

API poskytuje informácie o ubytovacích zariadeniach, recenziách, používateľoch a rezerváciách.

## Endpoints

### Ubytovanie

- **GET /properties**  
  Vráti zoznam všetkých ubytovacích zariadení.

- **GET /properties/{id}**  
  Vráti detaily konkrétneho ubytovacieho zariadenia na základe jeho ID.

### Recenzie

- **GET /reviews**  
  Vráti zoznam všetkých recenzií.

- **GET /reviews/{id}**  
  Vráti detaily konkrétnej recenzie na základe jej ID.

### Používatelia

- **GET /users**  
  Vráti zoznam všetkých používateľov.

- **GET /users/{id}**  
  Vráti detaily konkrétneho používateľa na základe jeho ID.

### Rezervácie

- **GET /bookings**  
  Vráti zoznam všetkých rezervácií.

- **GET /bookings/{id}**  
  Vráti detaily konkrétnej rezervácie na základe jej ID.

## Odpovede

Odpovede z API sú vo formáte JSON a obsahujú všetky potrebné informácie o danom objekte (napr. ubytovanie, recenzia, používateľ alebo rezervácia).

### Properties

```json
{
      "id": "unikátne ID ubytovania",
      "title": "názov ubytovania",
      "description":" krátky popis ubytovania",
      "images": "array obrázkov",
      "location": "miesto kde sa ubytovanie nachádza",
      "price": "cena v €",
      "rooms": "počet izieb",
      "guests": "počet hostí ktorí sa zmestia do ubytovacieho zariadenia",
      "rating": "hodnotenie od 0 do 5",
      "amenities": "array dodatočných služieb, ktoré ubytovanie poskytuje",
      "host": {
        "id": "ID hostiteľa",
        "name": "meno hostiteľa"
      }
    }
```

### Reviews

```json
{
  "id": "unikátne ID recenzie",
  "propertyId": "ID ubytovania, na ktoré sa recenzia vzťahuje",
  "user": "Meno používateľa",
  "rating": "hodnotenie od 0 do 5",
  "text": "Text recenzie, ktorý popisuje skúsenosť s ubytovaním."
}

```

### Users

```json
{
  "id": "unikátne ID používateľa",
  "name": "Meno používateľa",
  "email": "Email používateľa"
}

```

### Bookings

```json
{
  "id": "unikátne ID rezervácie",
  "propertyId": "ID ubytovania, ktoré je rezervované",
  "userId": "ID používateľa, ktorý rezerváciu vytvoril",
  "startDate": "Dátum začiatku rezervácie vo formáte YYYY-MM-DD",
  "endDate": "Dátum konca rezervácie vo formáte YYYY-MM-DD"
}

```
