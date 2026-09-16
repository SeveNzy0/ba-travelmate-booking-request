# Feature: [Filter of price]
## Use Case: [Фільтрація готелів за ціною]

Основним учасником є користувач, який повинен обрати фільтрацію ціни готелю (обрати мінімальну ціну АБО максимальну ціну АБО мінімальну та максимальну ціну), після цього система перевіряє чи мінімальна ціна не менше нуля, якщо мінімальна ціна менше 0 тоді показує помилку та повертає мінімальну ціну як 0, якщо мінімальна ціна більше нуля продовжується процес. Юзер клікає на пошук готелей за обраною ціною, система відділяє готелі та показує їх на сторінці; якщо жодний готель не підпадає під критерії користувача система перенаправлює нас на сторінку з помилкою де вказано що готелей не знайдено, після цього перенаправлює на пошук готелей; якщо віднайшовся хоча б один готель за критеріями юзера, система показує це


```mermaid
flowchart TD
    Start([User navigates to 'Filter by Price']) --> PriceInput[User inputs Minimum, Maximum, or Price Range]
    
    PriceInput --> CheckMin{Is Minimum Price < 0?}
    
    %% Alternative Flow A2: Negative Price Input
    CheckMin -- Yes (A2) --> ErrMin[Show Pop-up: 'Invalid price entered']
    ErrMin --> FixMin[Replace entered value with 0]
    FixMin --> SearchBtn
    
    CheckMin -- No --> SearchBtn[User clicks 'Search for Hotels' button]
    
    SearchBtn --> QuerySystem[System applies filter and searches hotels]
    
    QuerySystem --> CheckResults{Do any hotels meet criteria?}
    
    %% Main Success Flow
    CheckResults -- Yes --> DisplayHotels[System refreshes page and displays filtered hotels]
    DisplayHotels --> EndSuccess([End])
    
    %% Alternative Flow A1: No Hotels Found
    CheckResults -- No (A1) --> ErrNoResults[Redirect to error page: 'No hotels were found within this price range...']
    ErrNoResults --> RedirectSearch[System redirects back to hotel search page]
    RedirectSearch --> EndFail([End])

```