# Widget (konfigurace)

Konfigurační objekt ``_msgokConfig`` se vkládá vždy na začátek skriptu a slouží k přizpůsobení chování nebo vzhledu. Je stejný pro všechny typy použití.

## Verze knihovny

Aktuálně je poslední verze knihovny `v7.js`.

## Konfigurace

| Název | Hodnota | Popis                                                    |
|-------|---------|----------------------------------------------------------|
| **recipient**  |   string  | Povinné. Identifikace účtu |
| **payload**  |   string  | Povinné. Identifikace scénáře |
| **src**   |   string  | Povinné. Identifikace designu |
| **type**  |   string  | Typ widgetu. Může být ``inline``, ``popup``, ``sidebar``. Výchozí ``inline``  |
| **title**  |  string  | Nadpis widgetu (jen pokud type=popup) |
| **width**  |  int  | Šířka widgetu |
| **maxHeight**  |  int  | Maximální výška widgetu v ``%`` (tzn. hodnota 90 odpovídá maximální výšce 90% velikosti okna prohlížeče) |
| **margin**  |  int  | Odsazení ze stran (margin-left a margin-right) v ``px`` |
| **marginBottom**  |  int  | Odsazení od spodní strany v ``px`` |
| **zindex**  |  int  | Hodnota CSS vlastnosti ``z-index``, která určuje pořadí první na stránce, které se překrývají. Doporučujeme využít v kombinaci s hodnotou ``margin``, ``marginBottom`` a ``maxHeight`` a najít vhodné místo, které na stránce nebude s ničím kolidovat |
| **open**  | bool / int  | Zpoždění, za jak dlouho se má widget sám otevřít (jen pokud type=popup). Výchozí ``false`` |
| **style**  | bool  | Pokud styly nemají být vkládány do stránky při vyrenderování (lze nahradit vlastním css).  Výchozí ``true`` |
| **classes**  | list of strings  | Připravené třídy, které ovlivňují vzhled nebo chování. Použijte názvy tříd z tabulky Seznam podporovaných tříd |
| **color**  | string  | Barva textu (nebo ikonky) pro type=popup. Formát rgb (příklad ``rgb(255,255,255)``) |
| **background**  | string  | Barva pozadí plovoucího okna (nebo pozadí ikonky) pro type=popup. Formát rgb (příklad ``rgb(0,0,0)``) |
| **variables**  | object  | Objekt obsahující key - value hodnoty, které jsou předány do scénáře. Doporučení: používejte proměnných ``varX`` (kde X je číslo 1-9) ty jsou předány do scénáře automaticky. Vlastní názvy musí podporovat vygenerovaná šablona.  |
| **beforeStep**  | fnc(step, callback)  | Funkce kde v prvním parametru je objekt s odpověďmi uživatele a v druhém parametru je callback funkce, kterou lze předat zpět nové proměnné, které se vloží do objektu `variables` před tím, než jsou odeslány po akci uživatele (kliknutí na tlačítko)  |
| **onStep**  | fnc(step)  | Funkce kde v prvním parametru je objekt s aktuálním krokem v rámci scénáře  |
| **mobile**  | bool  | Pokud je `false` nerobrazuje se na mobilu  |




```js
_msgokConfig = {
  type: "popup",
  classes: ["msgokWidget--fix-to-left"],
  title: "Centrum Pomoci",   
  open: 3,   
  recipient: "xxx",
  payload: "xxx", 
  src: "xxx",
  variables: {var1: "ahoj@seznam.cz"}
};
```


## Seznam podporovaných tříd

| Název | Hodnota | Popis                                                    |
|-------|---------|----------------------------------------------------------|
| ``msgokWidget--fix-to-right``  | Zarovnání doprava  | Výchozí |
| ``msgokWidget--fix-to-left``  | Zarovnání doleva  | Výchozí |
| ``msgokWidget--size-icon``  | Zobrazení ve formátu ikonky  |  |
| ``msgokWidget--size-small``  | Zobrazení ve formátu plovoucího okna (zabolené rohy po stranách)  | Doporučujeme kombinovat s vhodným odsazením od kraje parametrem ``margin`` v konfiguračním objektu |
| ``msgokWidget--icon-info``  | Ikonka "i" v kroužku  | Jen pokud zároveň použijete třídu ``msgokWidget--size-icon`` |
| ``msgokWidget--icon-help``  | Ikonka "otazník" v kroužku  | Jen pokud zároveň použijete třídu ``msgokWidget--size-icon`` |
| ``msgokWidget--icon-chat``  | Ikonka chatu  | Jen pokud zároveň použijete třídu ``msgokWidget--size-icon`` |
