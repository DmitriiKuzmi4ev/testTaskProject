
# Test Task Project — API автотесты

Проект для автоматизации тестирования API с использованием Kotlin и современного стека инструментов. 
Реализована слоистая архитектура, поддержка мокирования через Wiremock, интеграция с Allure для отчетности 
и CI/CD через GitLab CI.

## Содержание

- [Структура проекта](#полная-структура-проекта)
- [Запуск тестов](#команды-для-запуска)
- [Контакты](#контакты)

## Полная структура проекта:

testTaskProject/
│
├── 📁 docs/                                     # Тестовая документация
│   ├── 📄 CHECKLIST.md                           
│   └── 📄 TESTCASES.md                           
│
├── 📁 src/
│   ├── 📁 main/kotlin/com/testtaskproject/        
│   │   ├── 📁 models/                           # DTO/POJO классы (Request/Response модели)        
│   │   ├── 📁 clients/                          # HTTP клиенты (RestAssured) и DB клиенты (Spring JDBC)  
│   │   ├── 📁 config/                           # Конфигурации (URL, credentials, properties)  
│   │   ├── 📁 utils/                            # Утилиты (хелперы, экстеншны, работа с файлами)   
│   │   └── 📁 mocks/                            # Wiremock моки для внешних сервисов   
│   │       ├── 📄 WireMockServerManager.kt      # Управление запуском/остановкой Wiremock сервера    
│   │       └── 📁 stubs/                        # Пакет с конкретными стабами     
│   │           ├── 📄 UserStubs.kt              # Стабы для user endpoints
│   │           └── 📄 PaymentStubs.kt           # Стабы для payment endpoints
│   │
│   └── 📁 test/kotlin/com/testtaskproject/          
│       ├── 📁 api/                              # Тестовые классы (UserApiTest, PaymentApiTest)     
│       ├── 📁 steps/                            # Шаги с @Step для Allure (UserSteps, PaymentSteps)     
│       ├── 📁 providers/                        # Генерация тестовых данных (Faker)     
│       ├── 📁 extensions/                       # JUnit extensions   
│       ├── 📁 assertions/                       # Кастомные проверки (ResponseAssertions)      
│       ├── 📁 specs/                            # Rest Assured спецификации (RequestSpecs, ResponseSpecs)      
│       └── 📁 annotation/                       # Кастомные аннотации (@ApiLogin, @WithMocks)      
│
├── 📁 resources/                                      
│   ├── 📄 logback.xml                           # Конфигурация логирования      
│   ├── 📄 application.properties                # Настройки приложения (URL, БД)      
│   ├── 📁 mocks/                                      
│   │   ├── 📁 __files/                          # Тела ответов      
│   │   └── 📁 mappings/                         # Маппинги запросов      
│   └── 📁 schemas/                                     
│
├── 📁 gradle/wrapper/
├── 📄 build.gradle.kts                                 
├── 📄 gradle.properties                                
├── 📄 settings.gradle.kts                              
└── 📄 README.md           

## Команды для запуска:

./gradlew clean	- Очистка проекта
./gradlew build	- Сборка проекта
./gradlew test	- Запуск всех тестов
./gradlew test --tests *ClassName	- Запуск конкретного класса
./gradlew test -DincludeTags=smoke	- Запуск тестов с тегом
./gradlew allureReport	- Генерация Allure отчета
./gradlew allureServe	- Запуск Allure сервера


## Контакты:

Автор: Dmitrii Kuzmi4ev
GitHub: @DmitriiKuzmi4ev
Репозиторий: testTaskProject