---
title: Бюджет производительности
slug: Web/Performance/Performance_budgets
translation_of: Web/Performance/Performance_budgets
---
<p>Бюджет производительности - это лимит для предотвращения регрессий. Этот бюджет может быть применён к файлам, типам файлов, всем ресурсам приложения, определённым общим показателям (например, <a href="/en-US/docs/Glossary/Time_to_interactive">Время до интерактивности</a>) пользовательским показателям (например, Время до главного элемента) или к пороговым значениям к определённым точкам во времени. </p>

<h2 id="Зачем_нужен_бюджет">Зачем нужен бюджет?</h2>

<p>Бюджет существует для отражения желаемых вами целей. С бюджетом вы сможете осознанно выстраивать компромиссы между пользовательским опытом и объективным индикаторами эффективности приложения (например, конверсией)</p>

<p>Эти цели можно разбить на категории:</p>

<ul>
 <li>Временные (например, <a href="/en-US/docs/Glossary/Time_to_interactive">Время до интерактивности,</a> <a href="/en-US/docs/Glossary/First_contentful_paint">Первая отрисовка контента</a>).</li>
 <li>Количественный (например, размер загруженных JS файлов, количество изображений).</li>
 <li>Определённые правилами (например. индекс <a href="https://developers.google.com/speed/pagespeed/insights/">Pagespeed</a>, баллы Lighthouse).</li>
</ul>

<p>Главная цель такого подхода - сокращение регрессии. Но этот подход может помочь предсказать поведение приложения в будущем. Например, в Сентябре 50% месячного бюджета было использовано за неделю - значит, нужно ждать увеличения потребления контента, нагрузки на сервера и т.д.</p>

<p>Кроме того, подход может раскрыть некоторые нужды разработчиков (например, может оказаться, что в финальном коде вашего приложения половину объёма занимает огромная библиотека, из которой вы используете только мизерную часть функциональности).</p>

<h2 id="Как_определить_бюджет">Как определить бюджет?</h2>

<p>Бюджет должен включать 2 уровня:</p>

<ul dir="ltr">
 <li>Предупреждение</li>
 <li>Ошибка</li>
</ul>

<p>Уровень предупреждения позволяет вам быть проактивным и заниматься техническим долгом, не блокируя разработку нового функциональности</p>

<p>Уровень ошибки - это граница, по достижении которой приложение воспринимается негативно.</p>

<p>Для начала, вам нужно выяснить, какими технологиями пользуются ваши пользователи. Например, большая часть пользователей приходят с Anroid-телефонов бюджетного уровня и подсоединяются через 3G). Для подобного исследования существует множество <a href="/en-US/docs/Learn/Performance/Web_Performance_Basics">инструментов</a>. Эти метрики должны стать базой для бюджета размера файлов.</p>

<p>Базовая цель - достигнуть показателя <a href="https://infrequently.org/2017/10/can-you-afford-it-real-world-web-performance-budgets/">"Время до интерактивности" до 5 секунд при 3G/4G, и до 2 секунд для последующих загрузок</a>. Однако, вы можете придумать свои цели, основанные на контенте приложения, географии пользователей и технологиях.</p>

<p>Например, для приложения с большим количеством текста (блоги, новостные сайты), показатель <a href="/en-US/docs/Glossary/First_contentful_paint">Первая отрисовка контента (First Contentful Paint)</a> будет гораздо лучше показывать, с чем сталкивается пользователь. Иными словами, этот показатель покажет, как быстро пользователь начинает читать. И этот показатель должен быть включён в специфичные бюджеты, например, бюджет шрифтов, где вы можете применять разные техники для оптимизации. Например, <a href="/en-US/docs/Web/CSS/@font-face/font-display">font-display</a>, чтобы улучшить <a href="/en-US/docs/Learn/Performance/perceived_performance">Субъективно Ощущаемую производительность</a>).</p>

<p>Но самая главная цель таких бюджетов - это возможность корреляции Производительности и Бизнес-целей. Когда вы определяете какие-то показатели, вы должны сфокусироваться на пользовательском опыте. Только он может диктовать, как мы должны изменять приложение таким образом, чтобы не просто улучшить конверсию, но и предсказать вероятность того, что пользователь вернётся.</p>

<h2 id="Как_создать_бюджет">Как создать бюджет?</h2>

<p>Во время разработки вы можете использовать несколько инструментов, чтобы проверять некоторые показатели:</p>

<ul>
 <li>Сборщики (например, <a href="https://webpack.js.org/">webpack</a>), из коробки содержат<a href="https://webpack.js.org/configuration/performance/"> инструменты оценки производительности</a>, которые сообщат вам, если какой-то из файлов превысил допустимые размеры.</li>
 <li><a href="https://github.com/siddharthkp/bundlesize">Bundlesize</a>, позволяет вам определить и проверять размеры файлов каждый раз при интеграции вашего кода с помощью <a href="/en-US/docs/Mozilla/Continuous_integration">CI</a>.</li>
</ul>

<p>Проверка размеров файлов - это лишь первый рубеж защиты от регрессий. Преобразование этих показателей во временные может быть сложным, потому что во время разработки окружение разработчика может не включать в себя сторонние библиотеки или оптимизации, которые обычно присутствуют в Production сборках.</p>

<p>Поэтому, рекомендуется определить базовые линии для каждой метрики бюджета с учётом разницы между окружением разработчика и боевым окружением.</p>

<p>С этим может помочь, например, <a href="https://github.com/GoogleChromeLabs/lighthousebot">Lighthouse Bot</a>, который можно встроить в <a href="https://travis-ci.org/">Travis CI</a> и использовать для получения аналитики <a href="https://developers.google.com/web/tools/lighthouse/">Lighthouse</a> и <a href="https://webpagetest.org">Webpage Test</a>. Этот бот будет сообщать об ошибке или успешном прохождении тестов на основе определённых минимальных оценок.</p>

<h2 id="Как_я_могу_усилить_влияние_бюджета">Как я могу усилить влияние бюджета?</h2>

<p>Чем раньше вы сможете определить новую трату к бюджету, тем лучше вы сможете оценить текущее состояние приложения и указать на необходимые оптимизации.</p>

<p>Кроме того, лучше иметь несколько бюджетов и быть проактивным. Бюджеты должны отражать ваши текущие цели, но не должны мешать экспериментам. Например, вы можете привнести функциональность, которая увеличит общее время загрузки приложения, но попытается увеличить пользовательскую вовлечённость (например, как долго пользователь остаётся на странице).</p>

<p>Бюджет помогает вам сохранить оптимальное поведение ваших текущих пользователей, когда вы пытаетесь выйти на новые рынки или привнести что-то новое в ваше приложение.</p>

<h2 id="Смотрите_также">Смотрите также</h2>

<ul>
 <li><a href="https://addyosmani.com/blog/performance-budgets/">Start Performance Budgeting</a> by Addy Osmani</li>
 <li><a href="https://web.dev/fast/performance-budgets-101">Performance Budgets 101</a> by Milica Mihajlija</li>
 <li><a href="https://timkadlec.com/remembers/2019-03-07-performance-budgets-that-stick/">Performance Budgets That Stick</a> by Tim Kadlec</li>
</ul>