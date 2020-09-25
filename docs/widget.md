# Widget (konfigurace)

Konfigurační objekt ``_msgokConfig`` se vkládá vždy na začátek skriptu a slouží k přizpůsobení chování nebo vzhledu. Je stejný pro všechny typy použití.

## Konfigurace

| Název | Hodnota | Popis                                                    |
|-------|---------|----------------------------------------------------------|
| **recipient**  |   string  | Povinné. Identifikace účtu |
| **payload**  |   string  | Povinné. Identifikace scénáře |
| **src**   |   string  | Povinné. Identifikace designu |
| **type**  |   string  | Typ widgetu. Může být ``inline``, ``popup``, ``sidebar``. Výchozí ``inline``  |
| **title**  |  string  | Nadpis widgetu (jen pokud type=popup) |
| **open**  | bool / int  | Zpoždění, za jak dlouho se má widget sám otevřít (jen pokud type=popup). Výchozí ``false`` |
| **style**  | bool  | Pokud styly nemají být vkládány do stránky při vyrenderování (lze nahradit vlastním css).  Výchozí ``true`` |
| **classes**  | list of strings  | Připravené třídy, které ovlivňují vzhled. Použijte ``msgokWidget--fix-to-left`` pro zarovnání na levý okaj |


```js
_msgokConfig = {
  type: "popup",
  classes: ["msgokWidget--fix-to-left"],
  title: "Centrum Pomoci",   
  open: 3,   
  style: false,   
  recipient: "xxx",
  payload: "xxx", 
  src: "xxx"
};
```
