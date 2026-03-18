```markdown
# Test Task Project — API автотесты

Проект для автоматизации тестирования API с использованием Kotlin и современного стека инструментов. 
Реализована слоистая архитектура, поддержка мокирования через Wiremock, интеграция с Allure для отчетности 
и CI/CD через GitLab CI.

## Содержание

- [Структура проекта](#структура-проекта)
- [Запуск тестов](#запуск-тестов)
- [Контакты](#контакты)

---

## Структура проекта

```
testTaskProject/
docs/
CHECKLIST.md                   # Чек-лист ручного тестирования
TESTCASES.md                   # Детальные тест-кейсы

src/
main/kotlin/com/testtaskproject/
models/                       # DTO/POJO классы для запросов/ответов
clients/                       # HTTP клиенты (RestAssured) и клиенты БД
config/                         # Конфигурации (URL, credentials)
utils/                           # Утилиты (хелперы, работа с файлами)
mocks/                           # Wiremock моки
WireMockServerManager.kt       # Управление Wiremock сервером
stubs/                         # Конкретные стабы
UserStubs.kt                  # Стабы для user endpoints
PaymentStubs.kt               # Стабы для payment endpoints

    test/kotlin/com/testtaskproject/
      api/                             # Тестовые классы
      steps/                           # Шаги с @Step для Allure
      providers/                        # Генерация тестовых данных (Faker)
      extensions/                        # JUnit extensions
      assertions/                         # Кастомные проверки
      specs/                              # Rest Assured спецификации
      annotation/                          # Кастомные аннотации

resources/
logback.xml                        # Конфигурация логирования
application.properties              # Настройки приложения
mocks/
__files/                           # Тела ответов (JSON)
mappings/                           # Маппинги запросов
schemas/                             # JSON схемы для валидации

gradle/wrapper/
build.gradle.kts
gradle.properties
settings.gradle.kts
README.md
```

---

## Запуск тестов

```bash
./gradlew clean              # Очистка проекта
./gradlew build              # Сборка проекта
./gradlew test               # Запуск всех тестов
./gradlew test --tests *ClassName   # Запуск конкретного класса
./gradlew test -DincludeTags=smoke  # Запуск тестов с тегом
./gradlew allureReport       # Генерация Allure отчета
./gradlew allureServe        # Запуск Allure сервера
```

---

## Контакты

**Автор:** Dmitrii Kuzmi4ev  
**GitHub:** [@DmitriiKuzmi4ev](https://github.com/DmitriiKuzmi4ev)  
**Репозиторий:** [testTaskProject](https://github.com/DmitriiKuzmi4ev/testTaskProject)
```