# site-dynamic-data-snippet


После тегов `<body></body>` вставить код.
Если `Jquery` уже импортирован то вставлять его повторно не нужно, можно убрать первую строчку `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>`
```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.27.0/moment.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.29.1/locale/ru.min.js"></script>
<script>
    var D = new Date();
    var hour = moment().utc(3).format('H');
    var day_now = (moment().utc(3).format('D'));
    var day_tom = (moment().utc(3).add(1, 'day').format('D'));
    var month_now = (moment().utc(3).format('LL')).replace(/[0-9]/g, '').slice(0,-3).toUpperCase();
    var month_tom = (moment().utc(3).add(1, 'day').format('LL')).replace(/[0-9]/g, '').slice(0,-3).toUpperCase();

    if(Number(hour) <= 17 ) {
        $("#day").text(day_now);
        $("#month").text(month_now);
    } else {
        $("#day").text(day_tom);
        $("#month").text(month_tom);
    }
</script>
```
 
Скрипт автоматически вставляет дату и месяц в те блоки индентификаторы которых обьявлены как `day` и `month`

В таком примере в тег `<span id="day">` будет вставлена дата и в тег `<span id="month"></span>` будет вставлен текущий месяц
```
<span id="day"></span> <span id="month"></span>
```

Любое содержимое внутри блока будет измененно, не вставляйте ничего более.
Можно применять любые стили.
