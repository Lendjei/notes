# soundcloud

**Добавить виджет с ресурса soundcloud**

1. Следует выбрать песню, н-р, https://soundcloud.com/abstrasensionrec/woodju-ft-coma-this-is-our-night?in=lena-protasova/sets/track
2. Изучить [документацию](https://developers.soundcloud.com/blog/html5-widget-api)
3. Использовать код из документации:

html
```html
<iframe id="sc-widget" width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F1848538&show_artwork=true"></iframe>
```

js
```javascript
<script src="https://w.soundcloud.com/player/api.js" type="text/javascript"></script>
<script type="text/javascript">
  (function(){
    var widgetIframe = document.getElementById('sc-widget'),
        widget       = SC.Widget(widgetIframe),
        newSoundUrl = 'http://api.soundcloud.com/tracks/13692671';

    widget.bind(SC.Widget.Events.READY, function() {
      // load new widget
      widget.bind(SC.Widget.Events.FINISH, function() {
        widget.load(newSoundUrl, {
          show_artwork: false
        });
      });
    });

  }());
</script>
```

4. Нужные данные трека

Нажимать share<br />
![alt text](https://github.com/Lendjei/notes/blob/master/img/1.png "img 1")

Перейти на вкладку Embed<br />
![alt text](https://github.com/Lendjei/notes/blob/master/img/2.png "img 2")

выбираем нужный вид виджета(2)<br />
копируем код для вставки(3)

В данном примере код будет такой:<br />
```html
<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/215879554&amp;color=ff5500&amp;auto_play=false&amp;hide_related=false&amp;show_comments=true&amp;show_user=true&amp;show_reposts=false"></iframe>
```

Можно скорректировать вид виджета, изменив стандартные настройки. <br />
Для этого удобно буде воспользоваться [ресурсом](https://w.soundcloud.com/player/api_playground.html)

![alt text](https://github.com/Lendjei/notes/blob/master/img/3.png "img 3")

Далее можно просто вставлять наименование свойства с нужным значением в скопированный ранее код.

Итого получим следующий код:

html:
```html
<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/215879554&amp;color=ff5500&amp;auto_play=false&amp;hide_related=false&amp;show_comments=true&amp;show_user=true&amp;show_reposts=false"></iframe>
```

js
```javascript
<script src="https://w.soundcloud.com/player/api.js" type="text/javascript"></script>
<script type="text/javascript">
  (function(){
    var widgetIframe = document.getElementById('sc-widget'),
        widget       = SC.Widget(widgetIframe),
        newSoundUrl = 'http://api.soundcloud.com/tracks/215879554';

    widget.bind(SC.Widget.Events.READY, function() {
      // load new widget
      widget.bind(SC.Widget.Events.FINISH, function() {
        widget.load(newSoundUrl, {
          show_artwork: false
        });
      });
    });

  }());
</script>
```
