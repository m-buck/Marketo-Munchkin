# Marketo-Munchkin
Munchkin.js code allows for tracking of end-user page visits and clicks to your Marketo landing pages and external web pages

## Getting started
Login to Marketo --> Admin --> Munchkin

Update ```Munchkin.init('000-xxx-000');``` with your Marketo instance ID

Insert updated code and save

```
(function() {
  var didInit = false;
  function initMunchkin() {
    if(didInit === false) {
      didInit = true;
      Munchkin.init('000-xxx-000');
    }
  }
  var s = document.createElement('script');
  s.type = 'text/javascript';
  s.async = true;
  s.src = '//munchkin.marketo.net/munchkin.js';
  s.onreadystatechange = function() {
    if (this.readyState == 'complete' || this.readyState == 'loaded') {
      initMunchkin();
    }
  };
  s.onload = initMunchkin;
  document.getElementsByTagName('head')[0].appendChild(s);
})();
```
