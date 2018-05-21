# Balíčky a závislosti

Modulárny systém WAME IS je prispôsobený na využívanie balíčkov (packages), ktoré sa vyvíjaju interne/komunitou alebo sú to balíčky tretích stán.

Rozdeliť ich môžme do 2 skupín:
- **back-end** balíčky
- **front-end** balíčky

## Back-end Balíčky

Na správu back-end balíčkov sa využíva [**composer**](https://getcomposer.org) a konfiguruje sa pomocou *composer.json* súboru.
Základné použitie je veľmi jednoduché. Stačí spustiť v **terminály** nasledujúci príkaz:

```
composer require NazovBalicka
```
 
> Ak chceš vedieť viac informácií o **composer** skús si prečítať tento [PHP tutoriál](https://www.codementor.io/jadjoubran/php-tutorial-getting-started-with-composer-8sbn6fb6t).

### Composer.json

**Ukážka zápisu require balíčkov**

```
...
"require": {
		"php": ">= 7.0",
		"nette/application": "^2.4",
		"nette/bootstrap": "^2.4",
		"nette/caching": "^2.4",
		"nette/di": "^2.4",
		"nette/finder": "^2.4",
		"nette/forms": "^2.4",
		"nette/http": "^2.4",
		"nette/mail": "^2.4",
		"nette/robot-loader": "^2.4",
		"nette/safe-stream": "^2.3",
		"nette/security": "^2.4",
		"nette/utils": "^2.4",
		"latte/latte": "^2.4",
		"tracy/tracy": "^2.4",
		"wame/HomepageModule": ">=0.0.1",
		"wame/MenuModule": ">=0.0.1"
        }
...
```

### Composer install/update

Inštaláciu balíčkov spustíme príkazom `composer install`. Príkaz `composer update` spúšťame len ak chcem aktualizovať balíčky a ich závislosti.

!> Pravidlom je, že príkaz `composer update` spúštame výhradne len na **localhoste** (lokálnom počítači).

## Front-end Balíčky

Balíčky súvisiace s front-end spravujú pomocou nástroja [**bower**](https://bower.io).
Konfiguráciu robíme cez súbor *bower.json*


### Bower.json

Konfiguračný súbor

#### Pridanie balíčka

Spustenie príkazu `bower install NazovBalika --save`

> Vyššie spomenuty príkaz s parametrom `--save` vykoná okrem inštalácie balíka aj jeho zapísania do súboru *bower.json*

#### Sekcia Preen

Konfigurácia, cez ktorú je možné ovlyvniť suborový obsah balíčka. Do tejto sekcie je možné zapísať súbory, ktoré chceme zachovať. Všetky ostatné súbory budú odstránené.

**Ukážka pre balík bootstrap**

```
...
"preen": {
    "bootstrap": [
      "fonts/*.*",
      "js/*.js",
      "less/*.less",
      "less/mixins/*.less"
    ]
}
...
```

> Ďalšie infomácie o npm balíku [preen](https://www.npmjs.com/package/preen)

#### Sekcia Overrides
Konfigurácia, ktorou je možné normalizovať štruktúru/názvy súborov.

```
...
"overrides": {
    "jquery": {
      "main": "dist/*.js",
      "normalize": {
        "js": "*.js"
      }
    }
}
...
```

!> Vyžadované je mať zapísané v tejto sekcii aspoň názov balíka napr: `"bootbox.js": {}`


> Ďalšie infomácie o npm balíku [gulp-bower-normalize](https://www.npmjs.com/package/gulp-bower-normalize)


### Gulpfile.js

Nasadenie nástroja [gulp](https://gulpjs.com) prináša automatizáciu úloh, ktoré je potrebné vykonať k správnemu fungovaniu projektu.

**Užitočné gulp príkazy**:

- `gulp` - spustenie default úlohy
- `gulp preen` - "čistenie" nainštalovaných balíkov
- `gulp bower-normalize` - normalizácia balíkov
- `gulp compileLess` - kompilácia less súborov
- `gulp compileSass` - kompilácia sass súborov (administrácia)

