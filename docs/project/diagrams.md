# Диаграммы

## Диаграмма последовательности

```mermaid
sequenceDiagram
    autonumber
    actor User as Пользователь
    participant System as Система
    participant Model as ML-модель

    User->>System: Отправить текст отзыва
    System->>System: Проверить текст
    System->>Model: Передать текст
    Model-->>System: Вернуть тональность
    System-->>User: Показать результат

    Note over System: При ошибке модели —<br/>сообщение пользователю
```

## Диаграмма классов

```mermaid
classDiagram
    class User {
        +id : int
        +name : string
        +email : string
    }

    class Review {
        +id : int
        +text : string
        +createdAt : DateTime
    }

    class SentimentResult {
        +sentiment : string
        +confidence : float
    }

    User "1" o-- "*" Review 
    Review "1" *-- "1" SentimentResult 
```