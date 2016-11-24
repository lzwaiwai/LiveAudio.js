# VoiceLive.js

> Voice Live function library with Howler.js.

## Installation

In a browser:

```html
  <script src="voiceLive.js"></script>
```

Using npm:

```
  $ npm i -g npm
  $ npm i --save howler
  $ npm i --save voiceLive
```

## Examples

![img](http://o3pvuu23u.qnssl.com/image/voiceLive.png)

``` javascript
  var datas = [{
    id: 4,
    src: 'xxxxx',
    time: 16,
    currentTime: 0
  }, {
    id: 4,
    src: 'xxxxx',
    time: 25,
    currentTime: 0
  }];

  var vl = new LiveAudio({
    datas: this.datas, 
    step: (itemId, currentTime, progress) => { // for live process, and like a timer 
      $('#currentTime-' + itemId).text(Math.floor(currentTime) + 's');
      $('#progress-' + itemId).text((progress * 100).toFixed(1) + '%')
    },
    events: { // for cur voice
      onload: function () {
        console.log('onload');
      },
      onloaderror: function () {
        console.log('onloaderror');
      },
      onplay: function () {
        console.log('onplay');
      },
      onpause: function () {
        console.log('onpause');
      },
      onstop: function () {
        console.log('onstop');
      },
      onend: function () {
        this.playNext(); // for auto play next item
        console.log('onend');
      }
    }
  });
```

## Methods
1. vl.play(id)

2. vl.pause(id)

3. vl.stop(id)

4. vl.playNext()

5. vl.playPre()

6. vl.addVoice(data)
