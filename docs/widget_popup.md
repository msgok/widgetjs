# Widget Popup

## Automatické otevření

Pokud se má widget sám otevírat, můžeme volat metodu ``show()`` bezprostředně po ``create()``. Dokud není zavolána metoda ``show()`` není widget vůbec vykreslen.

```js
var e = document.createElement("script");
e.src = "https://cdn.msgok.net/client/v5.js";
e.async = true;
e.defer = true;
e.addEventListener("load",function(){
  window.msgokWidget.create(null, _msgokConfig).show();
});
document.getElementsByTagName("head")[0].appendChild(e);
```

## Otevření kliknutím na odkaz

Pokud se má widget otevírat až po kliknutí na odkaz (v příkladu na všechny s třídou ``openChat``), použijte metodu ``hide()`` (Pokud je popup otevřený, schová se. Pokud zavřený, otevře se). 

```js
var e = document.createElement("script");
e.src = "https://cdn.msgok.net/client/v5.js";
e.async = true;
e.defer = true;
e.addEventListener("load",function(){
  var w = window.msgokWidget.create(null, _msgokConfig).show();
  document.querySelector(".openChat").addEventListener("click", function (e) {
    w.hide(); //metoda hide(); ma stejnou funkci jako toggle.
  });
});
document.getElementsByTagName("head")[0].appendChild(e);
```
                      
