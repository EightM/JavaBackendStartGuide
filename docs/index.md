
??? warning "Дисклеймер"

    - *в руководстве рассматривается развитие Java backend-разработчика*
    - *руководство написано исходя из того, что читатель не полный новичок в CS, и у него есть базовые знания*
    - *руководство намеренно написано в неформальном стиле, в формате монолога. Все предлагаемые изменения должны соответствовать данному стилю*
    - *целью руководства не является составление полного списка всех возможных курсов, книг или обучающих материалов. Состав должен представлять собой краткий, но не кратчайший список из максимально полезных обучающих материалов, советов и рекомендаций*
    - *Использование изображений в руководстве разрешено только в крайних случаях. Оставьте картинки профильным статьям*.

## Благодарности

Отдельное спасибо Вите за все запятые, дефисы и тире.
Особая признательность всем тем замечательным людям, которые помогали советами, критикой и собственными дополнениями материала. Вы лучшие.

## Почему Java?

Первый вопрос который приходит в голову, когда выбираешь язык. На то, чтобы выбрать Java есть целый ряд причин:

1. **Огромная база кода.** Если ты хочешь что-то сделать, с большой вероятностью для этого уже есть библиотека;
2. **Отличная документация.** Подробнейшее описание API языка (Javadoc), дотошно описанная спецификация самого языка (JLS) и спецификация модели памяти (JMM) добавляют уверенности, что если у тебя появился вопрос: «Как это работает?» или «Почему это работает именно так?» — на него получится найти ответ;
3. **Гибкость.** Java — это не только язык, но и JVM платформа. С использованием этой платформы написаны, например, Kotlin (привет, Android), Scala (привет, ФинТех) и Clojure. Всё это позволяет нам, оседлав Java и потратив некоторое время, дрейфовать в сторону той предметной области, которая наиболее интересна;
4. **Сообщество.** Если у тебя появился вопрос, на него, скорее всего, ответили ещё в 2010. Если у тебя появилась гениальная идея проекта, на гитхабе, вероятно, уже есть десяток различных реализаций. Новичкам всегда радостно помогут советами прочитать, наконец, Javadoc;
5. **Карьерные возможности.** Java повсюду: backend, mobile, desktop (нет, он не умер). Без работы точно не останешься.

Есть и ворох недостатков:

1. **Многословность**. Java многословна. То, что сейчас в Python занимает одну строку, в Java займёт 10. Не такой большой минус в современном мире, где есть Intellij и автодополнение, плюс в язык добавляются модные фичи вроде `var`. К тому же в языках вроде Kotlin или Scala можно писать достаточно компактный код;
2. **Обилие устаревшего кода.** Java появилась в 1995 году, и с тех пор было написано много кода. Чертовски много. Всё это нужно поддерживать, развивать и лелеять, так как бизнес очень не любит тратить деньги. Например, Java 8 вышла в 2014 году, а согласно [опросу](https://www.jetbrains.com/ru-ru/lp/devecosystem-2020/java/) JetBrains в 2020 году, её доля составляет 75%! Так что, залетев на работу, с высокой долей вероятности ты будешь писать на старой версии, в которой нет современного сахара, увы;
3. **Ограниченная сфера применения.** В современном мире Java по настоящему блистает в качестве backend-языка. Да, ты можешь писать mobile, но там развивается Kotlin. Да, ты можешь писать desktop, но люди выбирают Electron. Локомотив хайпа находится в вебе, поэтому мы садимся именно в него.

## Подготовка

Перед обучением тебе понадобится:

- **Установка Java**. Всегда бери самую свежую версию. Даже если на работе будешь писать на восьмерке, стоит держать руку на пульсе и быть в курсе всех современных Java фишек. 

- **Среда разработки.** Используй intellij IDEA Community, скажешь спасибо потом. Из альтернатив есть: 
  - Eclipse. Старый, неудобный, но ещё относительно популярный в некоторых местах;
  - VS Code. Это не IDE, но хороший редактор кода, который обвешивают кучей плагинов.
- **Знакомство с Git**. Гит — система контроля версий. Если ты когда-нибудь слышал слова "коммиты", "ветки" и "PR" — это оно. Для начала хватит простого [гайда](https://rogerdudler.github.io/git-guide/index.ru.html), чтобы понимать базовые термины. Потом стоит почитать документацию к своей IDE. IDEA, например, поддерживает работу с гит из коробки.
- **Профиль на GitHub**. Гитхаб — это такая социальная сеть для разработчиков. Ставь лайки библиотекам, которые используешь, и изучай тренды. Не стесняйся выкладывать туда все свои мелкие проекты, только не забывай про Readme. Потом будешь рад, когда понадобится найти проект, в котором ты уже делал работающие аспекты или работу с авторизацией.
- **Ведение заметок.** Очень важный пункт. Тебе предстоит поглощать огромное количество информации, большую часть которой ты забудешь уже на следующий день. Чтобы помочь своему мозгу, начни вести заметки по методике ZettelKasten, например, в notion.io https://habr.com/ru/post/509756/.
- **Будь в курсе**. Java активно развивается. Чтобы не остаться в стороне от важных новостей, ты должен их читать. Начни с подписки на ежемесячную подборку [Java Annotated](https://blog.jetbrains.com/idea/tag/java-annotated/) и подписывайся на интересных авторов.
  

## Обучение

Если хорошенько поискать, можно найти десятки статей о том, какие книги лучше читать и какие курсы лучше проходить. Заботливые люди рисуют дорожные карты и, казалось бы, просто бери и следуй гайдам. Но проблема в том, что их слишком много! Современный мир backend-разработки требует от тебя разбираться в куче вещей, и простой человек Василий, попробовав во всём этом разобраться, очень скоро почувствует беспомощность, грусть и отчаяние. 

Однако, всё не так страшно. Учиться придется очень много, к счастью, мы отобрали только самые лучшие материалы.