### Quarkus

[Quarkus](https://quarkus.io/) - наиболее популярный "FullStack Framework" после [Spring](https://spring.io/). Детище **RedHat**, вышедшее в Opensource. Проект насчитывает уже третий мажорный релиз и даже обзавелся LTS-версией. В отличии от того же Spring, Quarkus построен на реализации [JAX-RS](https://en.wikipedia.org/wiki/Jakarta_RESTful_Web_Services) от [Resteasy](https://resteasy.dev/), из которой позже, специально для Quarkus, выросла реализация [Resteasy reactive](https://quarkus.io/guides/resteasy-reactive), построенная на [Vert.x](https://vertx.io/).  Тот факт, что Quarkus основан уже на давно существующей реализации JAX-RS, стал подспорьем для перехода множества компаний в миграции своих сервисов с [Wildfly](https://www.wildfly.org/) без каких-либо тяжелых усилий.
Как и Spring Framework, Quarkus из коробки поддерживает большинство технологий, в таком виде, чтобы с ними было комфортно работать в рамках экосистемы Quarkus.
Если вы вдруг испугались, что придется заново учить новые ORM, JDBC, Logging-Framework'и, то спещу огорчить тут вы увидите тот же [Hibernate](https://quarkus.io/guides/hibernate-orm-panache), [SLF4J](https://quarkus.io/guides/logging), [Datasource](https://quarkus.io/guides/datasource) и многое другое. Причем, работать с ними, возможно, будет даже [удобнее](https://quarkus.io/guides/logging#simplified-logging) чем в Spring. 

#### Документация

При изучении таких Framework'ов как Spring, Quarkus, Helidon, Micronaut...и тд. В первую очередь встает вопрос о документации.
Документация Quarkus не должна оставить равнодушным. Стоит просто зайти на [страницу](https://quarkus.io/guides/) и наслаждаться. Там вы найдете как короткие вводные статьи для новичков о том, как использовать тот или иной Framework в рамках Quarkus, так и концепты внутреннего устройства проекта, и, наконец Reference'ые подробнейшие статьи для продолжающих разработчиков.

#### Утилиты

Spring имеет такую замечательную утилиту [Spring Initializr](https://start.spring.io/) для генерации и первичной настройки проекта. 
В Свою очередь, Quarkus предоставляет Web-интерфейс со схожим функционалом [code.quarkus.io](https://code.quarkus.io/).
Также, Quarkus тесно интегрируется с самыми популярными [IDE](https://quarkus.io/guides/ide-tooling), системами сборки [Gradle](https://quarkus.io/guides/gradle-tooling)/[Maven](https://quarkus.io/guides/maven-tooling). Наконец, стоит отметить наличие прекрасного и самодостаточного [CLI](https://quarkus.io/guides/cli-tooling).

#### Сообщество

Стоит отметить, что у сообщества [Quarkus](https://quarkus.io/) есть такой феномен как [Quarkiverse](https://quarkiverse.io/), куда множество компаний по всему миру выкладывают собственные расширения над [Quarkus](https://quarkus.io/).
Уже сейчас, при желании, там можно обнаружить поддержку большинства актуальных технологий "из коробки".
Например, если вам необходимо настроить в проекте взаимодействие по протоколу [SOAP](https://ru.wikipedia.org/wiki/SOAP), то достаточно обратиться сюда [quarkus-cxf extension](https://docs.quarkiverse.io/quarkus-cxf/dev/index.html). Там вы найдете все необходимое.
Также, по собственному опыту, могу сказать что сообщество глубоко заинтересовано и открыто к решению проблем. При желании можно задать любой вопрос в [чате](https://quarkusio.zulipchat.com/), в котором сидят разработчики [Quarkus](https://quarkus.io/) и с охотой отвечают на любой вопрос.

#### Блоги, Книги, Подкасты

Сообщество Quarkus старается так или иначе популяризировать свой продукт. На главной странице [сайта](https://quarkus.io/) можно найти все необходимые ресурсы для слежения за развитием проекта. [Блог](https://quarkus.io/blog/), [Подкасты](https://quarkus.io/insights/), [Книги](https://quarkus.io/books/) и многое другое.

#### How-to 

Выше были описаны ключевые моменты, которые необходимо знать при вступлении в экосистему Quarkus. От себя могу сказать, что писать на данном Framework'е одно удовольствие.
Конечно же, чтобы написать типичный CRUD, достаточно зайти в раздел [get started](https://quarkus.io/get-started/) и следовать шагам, который данный раздел предлагает. От себя, советую прочитать концептуальные статьи об устройстве Quarkus, в особенности [Quarkus Reactive Architecture](https://quarkus.io/guides/quarkus-reactive-architecture), [Vert.x Reference](https://quarkus.io/guides/vertx-reference), [CDI Reference](https://quarkus.io/guides/cdi-reference).