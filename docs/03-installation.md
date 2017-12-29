# Inštalácia

Teraz, keď už máme všetko pripravené, povieme si, ako si nainštalovať WAME-IS, aby ste mohli vidieť v praxi jeho plný potenciál.

1. Stiahnime si projekt cez Composer:
```
composer create-project wameis/sandbox:dev-master <project-name>
```

2. Nainštalujeme si všetky závislosti, ktoré sú potrebné pre chod WAME-IS:
```
composer install
```

3. Pre pokoj duše si vymažeme dáta v temp priečinku:
```
composer clear
```

4. Následne si vygenerujeme štruktúru databázy:
```
php web/index.php orm:schema-tool:create
```

5. Nastavíme si routovanie
```
php web/index.php router:update-default-routes
```

6. Teraz si prenesieme migrácie zo všetkých modulov do hlavného priečinka.
```
php web/index.php migrations:collect
```

7. Spustíme si tieto migrácie:
```
php web/index.php migrations:continue
```

8. Vytvoríme štandardné pozície a komponenty
```
composer wame:component:update
```