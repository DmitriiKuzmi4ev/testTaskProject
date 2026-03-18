# Test Task Project — API автотесты

Проект для автоматизации тестирования API с использованием Kotlin и современного стека инструментов. 
Реализована слоистая архитектура, поддержка мокирования через Wiremock, интеграция с Allure для отчетности 
и CI/CD через GitLab CI.

## Содержание

- [Стэк технологий](#стэк-технологий)
- [Структура проекта](#полная-структура-проекта)
- [Команды](#команды)
- [Контакты](#контакты)

## Стэк технологий

**Язык** - Kotlin  
**Сборка** - Gradle (Kotlin DSL)  
**Тестирование** - JUnit 5, Rest Assured  
**Отчетность** - Allure  
**Мокирование** - Wiremock  
**Работа с данными** - Faker, Spring JDBC  
**Логирование** - Logback, SLF4J, p6spy  
**UI тесты (опционально)** - Selenide  
**Брокеры сообщений** - Apache Kafka  
**CI/CD** - GitLab CI

## Полная структура проекта

    testTaskProject/
        docs/
            CHECKLIST.md                   # Чек-лист ручного тестирования  
            TESTCASES.md                   # Тест-кейсы  
  
        src/
            main/kotlin/com/testtaskproject/  
                models/                    # Data классы  
                clients/                   # API клиенты  
                config/                    # Конфигурации  
                utils/                     # Утилиты  

            test/kotlin/com/testtaskproject/  
                api/                       # API тесты  
                providers/                 # Провайдеры данных  
                extensions/                # JUnit extensions  
                assertions/                # Кастомные проверки  

    resources/  
    logback.xml                            # Конфигурация логирования  
    application.properties                 # Свойства приложения  
  
    gradle/wrapper/  
    build.gradle.kts  
    gradle.properties  
    settings.gradle.kts  
    README.md  

## Команды

`./gradlew clean` | Очистка проекта |  
`./gradlew build` | Сборка проекта |  
`./gradlew test` | Запуск всех тестов |  
`./gradlew allureReport` | Генерация Allure отчета |  
`./gradlew allureServe` | Запуск Allure сервера |  

## Контакты

**Автор:** Dmitrii Kuzmi4ev  
**GitHub:** [@DmitriiKuzmi4ev](https://github.com/DmitriiKuzmi4ev)  
**Репозиторий:** [testTaskProject](https://github.com/DmitriiKuzmi4ev/testTaskProject)
```