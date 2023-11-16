# Widget Popup

## Automatické otevření

Pokud se má widget sám otevírat, můžeme volat metodu ``show()`` bezprostředně po ``create()``. Dokud není zavolána metoda ``show()`` není widget vůbec vykreslen.

```js
var e = document.createElement("script");
e.src = "https://cdn.msgok.net/client/[version].js";
e.async = true;
e.defer = true;
e.addEventListener("load",function(){
  window.msgokWidget.create(null, _msgokConfig).show();
});
document.getElementsByTagName("head")[0].appendChild(e);
```

## Automatické otevření po X sekundách

Pokud se má widget sám otevřít po určitém počtu sekund, stačí v konfiguračním objektu přidat atribut ``open`` s hodnotou odpovídající počtu sekund, po které se má před otevřením čekat.

## Automatické otevření jen na specifické adrese

Stejně jak v předchozím případě je nutné upravit konfigurační objekt, zároveň je nutné tuto úpravu oddělit od ostatních parametrů a aplikovat ji jen v případě, že se návštěvník nachází na konkrétní webové adrese. Můžete to provést například následující podmínkou, kterou vložíte za úvodní definici objektu ``_msgokConfig``:

```js
if(window.location.href.indexOf("kontakty") !== -1){
	_msgokConfig.open = 3; //na stránce s kontakty se popup automaticky otevře po 3 sekundách od načtení stránky
}
```

## Otevření kliknutím na odkaz

Pokud se má widget otevírat až po kliknutí na odkaz (v příkladu na všechny s třídou ``openChat``), použijte metodu ``hide()`` (Pokud je popup otevřený, schová se. Pokud zavřený, otevře se). 

```js
var e = document.createElement("script");
e.src = "https://cdn.msgok.net/client/[version].js";
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
                      
