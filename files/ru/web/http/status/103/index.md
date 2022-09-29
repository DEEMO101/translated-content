---
title: 103 Early Hints
slug: Web/HTTP/Status/103
tags:
  - HTTP
  - Информация
  - Код состояния
  - ТаблицаСоответствия
  - Требуется Содержание
  - Черновик
translation_of: Web/HTTP/Status/103
---
<p>{{HTTPSidebar}}</p>

<p>HTTP код <strong><code>103 Early Hints</code></strong> в первую очередь предназначен для использования с заголовком {{HTTPHeader("Link")}}, чтобы клиент мог начать предварительную загрузку пока сервер готовит ответ.</p>

<h2 id="Синтаксис">Синтаксис</h2>

<pre class="syntaxbox">103 Early Hints</pre>

<h2 id="Характеристики">Характеристики</h2>

<table class="standard-table">
 <thead>
  <tr>
   <th scope="col">Характеристики</th>
   <th scope="col">Статус</th>
   <th scope="col">Комментарий</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>{{RFC(8297, "103 Early Hints")}}</td>
   <td>IETF RFC</td>
   <td>Начальное определение (Initial Definition)</td>
  </tr>
 </tbody>
</table>

<h2 id="Совместимость_с_браузерами">Совместимость с браузерами</h2>

<p>{{Compat}}</p>

<h2 id="Смотрите_также">Смотрите также</h2>

<ul>
 <li>{{HTTPHeader("Link")}}</li>
</ul>