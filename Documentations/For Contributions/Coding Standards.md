### **Coding Standards**

# Стандарты кода

## Именование
- **Classes:** PascalCase (`SessionLoggerService`)
- **Methods:** PascalCase (`LogEventAsync`)
- **Private fields:** _camelCase (`_databaseService`)
- **Parameters:** camelCase (`sessionId`)

## Архитектура
- MVVM паттерн обязателен
- Dependency Injection через MAUI built-in DI
- Асинхронные методы с суффиксом `Async`


## Code Review Checklist
- Покрыто тестами
- Нет hard-coded строк
- Обработка ошибок
- Комментарии для сложной логики