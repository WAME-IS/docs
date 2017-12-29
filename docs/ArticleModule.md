## ArticleModule

ArticleModule je jeden zo základných modulov obsiahnutý v štandardnom WAMEx balíčku. Jeho cieľom je, ako napovedá názov, správa článkov. Je aplikovateľný napríklad na osobný blog.

### Komponenty

Komponenty reprezentujú základné celky, z ktorých pozostáva celý modul. Je to akoby modul bola skladačka a komponenty boli jej dieliky. V tomto module nájdete obsiahnuté nasledujúce balíky:

- Article (tento komponent vypisuje jeden článok z databázy buď na základe daných kritérií alebo sa podieľa na tvorení väčších dátových štruktúr, viď ArticleList nižšie)
- ArticleList (tento komponent vypisuje zoznam článkov na základe daných kritérií, pričom na výpis článkov využíva Article modul)
- ArticleEmptyList (ak máme nejaké iné elementy, ktoré sme pri článkoch chceli aplikovat, napríklad tlačídlo na pridanie nového článku, použijeme na tento účel tento modul)