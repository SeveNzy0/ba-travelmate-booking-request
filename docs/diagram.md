# Feature: [Filter of price]
## Use Case: [Фільтрація готелів за ціною]

Основним учасником є користувач, який повинен обрати фільтрацію ціни готелю (обрати мінімальну ціну АБО максимальну ціну АБО мінімальну та максимальну ціну), після цього система перевіряє чи мінімальна ціна не менше нуля, якщо мінімальна ціна менше 0 тоді показує помилку та повертає мінімальну ціну як 0, якщо мінімальна ціна більше нуля продовжується процес. Юзер клікає на пошук готелей за обраною ціною, система відділяє готелі та показує їх на сторінці; якщо жодний готель не підпадає під критерії користувача система перенаправлює нас на сторінку з помилкою де вказано що готелей не знайдено, після цього перенаправлює на пошук готелей; якщо віднайшовся хоча б один готель за критеріями юзера, система показує це


```mermaid
graph TD
    Start([User navigates to 'Filter by Price']) --> InputPrice[User inputs price criteria:<br>min, max, or range]

    InputPrice --> CheckMin{Min price < 0?}
    
    %% Alternate Flow A2 (Negative price)
    CheckMin -- Yes --> A2_Error[Display pop-up error:<br>'Invalid price entered']
    A2_Error --> A2_Reset[System replaces entered number with 0]
    A2_Reset --> InputPrice

    %% Range Validation (Max < Min)
    CheckMin -- No --> CheckRange{Max price < Min price?}
    
    CheckRange -- Yes --> RangeError[Display error message:<br>'Maximum price cannot be less than minimum price']
    RangeError --> InputPrice

    %% Main Flow
    CheckRange -- No --> ClickSearch[User clicks 'Search for Hotels']
    ClickSearch --> ExecuteSearch[System searches for matching hotels]

    ExecuteSearch --> CheckResults{Matching hotels found?}

    %% Main Flow Outcome
    CheckResults -- Yes --> DisplayHotels[System refreshes page and displays<br>only the filtered hotels]
    DisplayHotels --> End([End Process])

    %% Alternate Flow A1 (No hotels found)
    CheckResults -- No --> A1_RedirectError[System redirects to error page:<br>'No hotels were found within this price range...']
    A1_RedirectError --> A1_ReturnSearch[System redirects user back<br>to hotel search page]
    A1_ReturnSearch --> End
```