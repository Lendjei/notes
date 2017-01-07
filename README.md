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

![alt text](https://github.com/Lendjei/notes/blob/master/img/1.png "img 1")