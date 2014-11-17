<h1 id="руководство-по-интеграции-sdk-adcamp-для-мобильных-web-страниц">Руководство по интеграции SDK AdCamp для мобильных WEB-страниц</h1>

<p><div class="toc"><div class="toc">

<ul>
<li><a href="#подготовка-к-работe">Подготовка к работe</a></li>
<li><a href="#требования">Требования</a></li>
<li><a href="#получение-рекламного-кода">Получение рекламного кода</a></li>
<li><a href="#вставка-рекламного-кода-на-страницу">Вставка рекламного кода на страницу</a></li>
</ul>




</div>
</div>
</p>






<h3 id="подготовка-к-работe">Подготовка к работe</h3>

<p>SDK AdCamp для мобильных WEB-страниц позволяет разработчикам размещать статичные и интерактивные рекламные объявления на своем сайте.</p>

<p>SDK AdCamp для мобильных WEB-страниц поддерживает следующие типы рекламных мест:</p>

<ul>
<li>стандартный баннер, который встраивается в верстку страницы (размеры <br>
320х50, 640х100, 728х90 )</li>
<li><p>полноэкранный баннер; появляется при загрузке страницы. (размер <br>
баннера подбирается с учетом определенного размера экрана и его <br>
ориентации)</p></li>
<li><p>плавающий баннер – отличается от стандартного баннера тем, что <br>
“прокручивается” вместе со страницей, то есть занимает фиксированное <br>
положение не на СТРАНИЦЕ, а на ЭКРАНЕ.</p></li>
</ul>

<p>Большой выбор действий при клике на рекламу позволяет направлять пользователей в App Store, Google Play, iTunes, браузер, а также производить переход к картам, видео и набору номера и смс. Опционально для объявлений можно настраивать географический (по GPS) и демографический таргетинг, передавая данные в запросе на рекламу.</p>

<h3 id="требования">Требования</h3>

<p>Поддерживаемые браузеры:</p>

<ul>
<li>Safari (iOS 5.0+) </li>
<li>Google Chrome </li>
<li>Opera Coast </li>
<li>Firefox </li>
<li>Яндекс.Браузер</li>
<li>Android browser (Android 2.3+) </li>
<li>Internet Explorer (Windows Phone 7.0+)</li>
<li>Nokia browser (Symbian 60S) </li>
<li>OSS Browser (Symbian 60S)</li>
</ul>



<h3 id="получение-рекламного-кода">Получение рекламного кода</h3>

<p>Чтобы разместить на сайте рекламный блок, необходимо сначала получить рекламный код.  <br>
Вы можете получить рекламный код написав запрос на электронную почту account@adcamp.ru, в письме необходимо указать название площадки и тип плейсмента.</p>



<h3 id="вставка-рекламного-кода-на-страницу">Вставка рекламного кода на страницу</h3>

<p>Для того, чтобы начать ротацию объявлений, в коде страницы необходимо создать рекламный блок с параметрами:</p>

<ul>
<li>data-pid – уникальный идентификатор вашего рекламного блока (генерируется <br>
нашей системой);</li>
<li>data-width – ширина рекламного блока;</li>
<li>data-height – высота рекламного блока.</li>
</ul>

<p>Размеры рекламного блока необходимы только для стандартных и плавающих блоков, в случае с полноэкранными объявлениями они не нужны.</p>

<p>Вставьте рекламный код между тегами <code>&lt;BODY&gt;</code> и <code>&lt;/BODY&gt;</code> в место на странице, где должно отображаться рекламное объявление.</p>

<p><strong>Пример:</strong></p>

<pre class="prettyprint"><code class=" hljs xml"><span class="hljs-doctype">&lt;!DOCTYPE html&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-title">html</span>&gt;</span>
 <span class="hljs-tag">&lt;<span class="hljs-title">head</span>&gt;</span>
   <span class="hljs-tag">&lt;<span class="hljs-title">title</span>&gt;</span>Комментарии<span class="hljs-tag">&lt;/<span class="hljs-title">title</span>&gt;</span>
   <span class="hljs-tag">&lt;<span class="hljs-title">meta</span> <span class="hljs-attribute">http-equiv</span>=<span class="hljs-value">"Content-Type"</span> <span class="hljs-attribute">content</span>=<span class="hljs-value">"text/html; charset=utf-8"</span>&gt;</span>
 <span class="hljs-tag">&lt;/<span class="hljs-title">head</span>&gt;</span>
 <span class="hljs-tag">&lt;<span class="hljs-title">body</span>&gt;</span> 

  <span class="hljs-comment">&lt;!-- Меню --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-title">div</span>&gt;</span>Меню<span class="hljs-tag">&lt;/<span class="hljs-title">div</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- Контент --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-title">div</span>&gt;</span>Содержимое документа<span class="hljs-tag">&lt;/<span class="hljs-title">div</span>&gt;</span>


<span class="hljs-comment">&lt;!-- Начало вставки рекламного кода AdCamp --&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-title">script</span> <span class="hljs-attribute">src</span>=<span class="hljs-value">"http://ssp.adcamp.ru/static/loader.js"</span> <span class="hljs-attribute">type</span>=<span class="hljs-value">"text/javascript"</span>&gt;</span><span class="javascript"></span><span class="hljs-tag">&lt;/<span class="hljs-title">script</span>&gt;</span>
<span class="hljs-comment">&lt;!-- Подключаем рекламный блок --&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-title">div</span> <span class="hljs-attribute">class</span>=<span class="hljs-value">"adc_block"</span> 
    <span class="hljs-attribute">data-pid</span>=<span class="hljs-value">"5"</span>
    <span class="hljs-attribute">data-width</span>=<span class="hljs-value">"320"</span> 
    <span class="hljs-attribute">data-height</span>=<span class="hljs-value">"50"</span> 
&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-title">div</span>&gt;</span>
<span class="hljs-comment">&lt;!-- Конец вставки рекламного кода AdCamp --&gt;</span>


 <span class="hljs-tag">&lt;/<span class="hljs-title">body</span>&gt;</span> 
<span class="hljs-tag">&lt;/<span class="hljs-title">html</span>&gt;</span></code></pre>
