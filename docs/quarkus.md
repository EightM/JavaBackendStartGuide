### Почему Quarkus ?

[Quarkus](https://quarkus.io/) - Framework от [RedHat](https://ru.wikipedia.org/wiki/Red_Hat), взгляд на экосистему которого заставляет рассмотреть его в качестве альтернативы таким Framework'ам как Helidon (Oracle), Spring Boot (VMware), Micronaut.
В отличии от остальных Framework'ов, перечисленных выше, Quarkus не пошел по пути создания чего-то абсолютно уникального. 
Вместо этого, он предлагает использовать уже давно существующую в рамках мира backend web-разработки реализацию спецификации [Jakarta REST (ранее известный как JAX-RS](https://jakarta.ee/specifications/restful-ws/3.1/jakarta-restful-ws-spec-3.1.html), известной как [Resteasy](https://resteasy.dev/).
 В сущности, это означает, что разработчикам не пришлось особенно много усилий прилагать, чтобы уйти от устаревшего формата разработки.
Конечно же, это можно было сделать и с помощью Spring Boot, но количество усилий несоизмеримо.
По опыту могу сказать, что типовой микросервис можно перенести c сервлетного JAX-RS на Quarkus даже за 5 минут (конечно же, это средняя температура по больнице).

#### Quarkus реактивный, даже не сомневайся

Изначально, как было выше сказано, Quarkus использовал популярную реализацию Jakarta REST. Однако команда разработчиков пошла дальше. Вместе с разработчиками Resteasy был разработан [Resteasy Reactive](https://quarkus.io/guides/resteasy-reactive).
В нем Quarkus использует [Vert.x](https://vertx.io/) - набор библиотек для реализации [реактивных](https://www.reactivemanifesto.org/) приложений. При этом, поддержка всех механизмов и аннотаций спецификации Jakarta REST сохранилась.
Думаю, лучше всего реактивность Quarkus описывают слова из статьи [Quarkus Reactive Architecture](https://quarkus.io/guides/quarkus-reactive-architecture):

!!! note "Quarkus is reactive"

    Quarkus is reactive. It’s even more than this: Quarkus unifies reactive and imperative programming. You don’t even have to choose: you can implement reactive components and imperative components then combine them inside the very same application. No need to use different stacks, tooling or APIs; Quarkus bridges both worlds.

Для более четкого представления о том, что я написал, предлагаю к прочтению [Quarkus Reactive Architecture](https://quarkus.io/guides/quarkus-reactive-architecture), [Using Eclipse Vert.x API from a Quarkus Application](https://quarkus.io/guides/vertx#executing-asynchronous-code-from-a-blocking-thread), и, для более глубокого погружения [Vert.x Reference Guide](https://quarkus.io/guides/vertx-reference).


#### Экосистема
##### Документация

При изучении таких Framework'ов как Spring и Quarkus в первую очередь встает вопрос о документации и ее качестве.
В случае Quarkus она не должна оставить изучающего равнодушным. Стоит просто зайти на [страницу](https://quarkus.io/guides/) и наслаждаться. 
Там ты найдешь как короткие вводные статьи для новичков о том, как использовать тот или иной Framework в рамках Quarkus, так и концепты внутреннего устройства проекта.
Наконец, там присутствуют Referenc'ные статьи для продолжающих разработчиков.

#### Утилиты

Spring имеет такую замечательную утилиту [Spring Initializr](https://start.spring.io/) для генерации и первичной настройки проекта. 
В свою очередь, Quarkus предоставляет Web-страницу со схожим функционалом [code.quarkus.io](https://code.quarkus.io/).
Там ты сможешь выбрать: язык разработки, систему сборки, и, также все необходимые для разработки зависимости.
 В итоге ты получаешь готовый проект, осталось лишь внедрить свою бизнес-логику.
Также, Quarkus тесно интегрируется с самыми популярными [IDE](https://quarkus.io/guides/ide-tooling), системами сборки [Gradle](https://quarkus.io/guides/gradle-tooling)/[Maven](https://quarkus.io/guides/maven-tooling). Наконец, стоит отметить наличие прекрасного и самодостаточного [CLI](https://quarkus.io/guides/cli-tooling).


##### Поддержка технологий
Quarkus старается поддерживать множество популярных технологий. 
Для сериализации [используется](https://quarkus.io/guides/rest-json) [Jackson](https://github.com/FasterXML/jackson). 
Для логгирования поддерживаются следующие API:

  * [JBoss Logging](https://github.com/jboss-logging/jboss-logging)
  * JDK java.util.logging (JUL)
  * [SLF4J](https://www.slf4j.org/)
  * [Apache Commons Logging](https://commons.apache.org/proper/commons-logging/)
  * [Apache Log4j 2](https://logging.apache.org/log4j/2.x/)
  * [Apache Log4j 1](https://logging.apache.org/log4j/1.2/)

Не могу не упомянуть про способ логгирования, которого мне не достает в любом другом Framework'e:

```java title="Упрощенное логгирование"
package com.example;

import io.quarkus.logging.Log; 

class MyService { 
    public void doSomething() {
        Log.info("Simple!"); 
    }
}
```

Подробнее о том, как работает такой способ читай [тут](https://quarkus.io/guides/logging).

Для подключения к БД адаптированы привычные JDBC драйверы к множеству СУБД, но также предлагается и вариант подключения с помощью [реактивных клиентов](https://quarkus.io/guides/reactive-sql-clients). 
Подробнее можно почитать [здесь](https://quarkus.io/guides/datasource).
Если, вдруг, ты соскучился по Hibernate, то [вот](https://quarkus.io/guides/hibernate-orm) и [вот](https://quarkus.io/guides/hibernate-orm-panache). ПоДучи и распишись.

Выше я осветил наиболее важные технологии, которые ты так или иначе встретишь на месте работы. Но, конечно же Quarkus поддерживает множество других, я бы даже усомнился, что ты сможешь не найти поддержку чего-либо. 
Достигается это не только за счет поддержки Core-команды от RedHat, но и существования Quarkiverse.


##### Quarkiverse

[Quarkiverse Github](http://github.com/quarkiverse) - это место в Github, куда любой разработчик/группа разработчиков может выложить расширение для Quarkus.
Расширения Quarkus, размещенные в организации Quarkiverse, могут быть легко включены в каталог расширений Quarkus, доступный на code.quarkus.io, и в инструменты командной строки Quarkus (такие как mvn quarkus:list-extensions, gradle listExtensions). Но это не только лишь набор репозиториев. Множество расширений пишется по определенному [набору правил](https://hub.quarkiverse.io/) и имеют собственную [документацию](https://docs.quarkiverse.io/index/explore/index.html). Актуальный список расширений ты найдешь [тут](https://quarkus.io/extensions/). Перед использованием расширений можно прочитать [краткое руководство](https://quarkus.io/faq).


##### Сообщество
Также, по собственному опыту, могу сказать что сообщество глубоко заинтересовано и открыто к решению проблем. При желании можно задать любой вопрос в [чате](https://quarkusio.zulipchat.com/), в котором сидят разработчики Quarkus и с охотой отвечают на любые вопросы, в том числе вопросы совсем новичков.


##### Developer Joy
Отдельно хотелось бы отметить тот факт, что команда разработчиков Quarkus делает акцент на комфорте разработки, используя Quarkus:

!!! note "Beyond simply working, we’re aiming for Joy."
  
    Quarkus is not just about being great for writing Web Applications or Micro-Services. 
    We’re focusing on more than the feature set: we make sure that every feature works well, simply, with little to no configuration, in the most intuitive way possible.
    It should be trivial to develop simple things, and easy to develop the more complex ones.

Прочитай [это](https://quarkus.io/developer-joy/), надеюсь тебе понравится.

#### Блоги, Книги, Подкасты

Сообщество Quarkus старается так или иначе популяризировать свой продукт. На главной странице [сайта](https://quarkus.io/) можно найти все необходимые ресурсы для слежения за развитием проекта. [Блог](https://quarkus.io/blog/), [Подкасты](https://quarkus.io/insights/), [Книги](https://quarkus.io/books/) и многое другое.

#### Личный опыт
В блоге Quarkus можно найти [истории миграции на Quarkus](https://quarkus.io/blog/tag/user-story/). Почитай как-нибудь на досуге.
Хотел бы рассказать о своем опыте немного. В нашей компании разработка велась на сервлетах, сервисы собирались в WAR-архивы и запускались с помощью Wildfly.
В какой-то момент мы начали испытывать проблемы разного рода, связанные с разделением ресурсов, логгированием, метриками, и даже OOM - где из-за одного сервиса умирали все сразу. Экспертизы Spring с его Spring Boot почти ни у кого в команде не было. Появление Quarkus в нашем случае стал спасительным кругом.
Quarkus, и тесно интегрированные с ним Vert.x, [Smallrye](https://smallrye.io/), спустя нескольких лет использования вызывают у меня лишь приятные воспоминания.

#### How-to старт
Для того, чтобы начать писать код, достаточно зайти на страницу [Get Started](https://quarkus.io/get-started/) и следовать инструкциям.
Здесь тебя научат как написать и запустить простейший микросервис, используя Quarkus. Обязательно обрати внимание на раздел `Next Steps`, там будут ссылки на статьи,
которые подробнее расскажут как писать [REST сервисы](https://quarkus.io/guides/rest-json), в том числе [реактивно](https://quarkus.io/guides/getting-started-reactive). 
Также, покажут как упростить разработку в твоей любимой [IDE](https://quarkus.io/guides/ide-tooling) и многое другое.


<figure markdown>
  ![developerjoy](images/icon-developerjoy.svg){ width="300" }
  <figcaption>Приятного путешествия :)</figcaption>
</figure>