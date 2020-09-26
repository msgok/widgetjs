# Widget Styly

Některé formy použití vyžadují, aby přímo do stránky, kde je vložen náš kód byly doplněny potřebné CSS. Tyto styly se vkládají do nového elementu ``<style>``, který si obsluhující skript sám vytvoří.

## Úprava výchozích stylů
Pro úpravu vlastních stylů a přizpůsobení designu můžete využít toho, že každá definice má vlastní pojmenovanou třídu, kterou je možné přepsat vlastní definicí (vzhledem k hiearchii bude nutné použít klíčové slovo ``!important``). 

Druhou doporučenou variantou je uložit si vygenerované CSS, vložit je do vlastních CSS definicí a následně přidat do konfiguračního objektu parametry ``style: false``. Díky tomu nebude skript styly vkládat přímo do stránky.
