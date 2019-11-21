---
description: 'Что такое МИС Медкей, как работать с документацией'
---

# Введение

## Пара слов о системе

Медицинская информационная система Медкей — современное программное решение для автоматизации работы медицинских учреждений. МИС Медкей позволяет обрабатывать электронные медицинские карты, автоматизировать осуществление врачебной практики, финансовый учёт, внедрить клиентоориентированный подход \(CRM\), предоставлять статистику и отчётность по работе учреждения. 

Функционально МИС Медкей позволяет решить следующие задачи:

* Автоматизировать обработку ЭМК в соответствии со стандартами HL7 FHIR, OpenEHR и ГОСТ Р ИСО 27789-2016;
* Организовать работу врачей \(планирование работы врачей, графика работы, обработка направлений, записей на приём\);
* Централизовать обработку финансовых документов \(закрытие выполнения услуг по информации от кассового ПО, осуществление операций через кассу, работа со страховыми организациями, учёт расходных материалов и затрат на их закупку\);
* Обеспечить сотрудников CRM-инструментами без дополнительного ПО \(обработка лидов, преобразование, журналирование всех взаимодействий \(звонков, E-mail и т.д.\), обработка программ лояльности\);
* Предоставить инструменты статистики и отчётности.

Более подробно с функциями можно ознакомиться на странице [Обзор функций](funkcii/obzor-funkcii.md), и в разделе документации «_Функции_».

Хотелось бы отметить следующие факты про МИС Медкей:

* **Это** [**полностью свободное ПО**](dlya-razrabotchikov/politika-licenzirovaniya.md) с открытым исходным кодом \(лицензия GPLv3.0\);
* **Имеет современную** [**технологичную платформу**](dlya-razrabotchikov/stek-tekhnologii.md) \(PHP7.3, ReactJS, Docker\), является централизованным веб-приложением, для работы сотрудников подойдёт любой браузер;
* **Может работать с минимальными** [**системными требованиями**](administrirovanie/sistemnye-trebovaniya.md) \(даже на самом простом хостинге с 1 vCore, 500 MB RAM и 1 GB свободного места\).

## О документации

Эта документация разработана для тех, кто хочет:

1. **Установить МИС Медкей и начать работу в системе.** Страницы [Установка](administrirovanie/untitled/) и [Быстрый старт](funkcii/bystry-start.md) — верный выбор для тех, кто хочет как можно скорее перейти от слов к делу. Мы постарались осветить все технически важные вопросы в разделе «_Администрирование_».
2. **Принять решение об использовании МИС Медкей и ознакомиться с принципами её работы.** Начните со статьи «[Обзор функций](funkcii/obzor-funkcii.md)». В разделе «_Функции_» приведён перечень основных функций, которые мы уже успели задокументировать. Также данный раздел может быть полезен при ознакомлении с демо-версией системы.
3. **Доработать МИС Медкей под потребности медицинской организации.** В разделе «_Для разработчиков_» мы постарались осветить вопросы доработки системы, расширения её функциональности, и многие другие нюансы. Там описано, как [собрать МИС их исходного кода](dlya-razrabotchikov/sborka-iz-iskhodnogo-koda.md), как можно [использовать МИС Медкей в своих разработках](dlya-razrabotchikov/politika-licenzirovaniya.md) и многое другое.

## Немного истории

МИС Медкей создан командой энтузиастов. Изначально, в 2012 году, МИС Медкей создавалась в качестве облачного сервиса. Но постепенно, по мере формирования интереса к идеям ПО с открытым исходным кодом, было принято решение сменить концепцию. В 2017 году мы начали разрабатывать новую версию системы, и уже в 2018 году выпустили первый релиз медицинской информационной системы с открытым исходным кодом. Сегодня МИС Медкей имеет современную программную платформу, которая обеспечивает устойчивое развитие функциональности. МИС Медкей находится в активной фазе развития. С планами разработки и релизов можно ознакомиться с разделом «Карта развития».



