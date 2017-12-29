# Inštalácia

Teraz, keď už máme všetko pripravené, povieme si, ako si nainštalovať WAME IS, aby ste mohli vidieť v praxi jeho plný potenciál.

1. Stiahnime si projekt cez Composer:
```
composer create-project wameis/sandbox:dev-master <project-name>
```

2. Nainštalujeme si všetky závislosti, ktoré sú potrebné pre chod WAME IS:
```
composer install
```

## Príprava databazy

### Úprava konfiguračného súboru
Konfiguračný súbor **config.local.neon** obsahuje všetky potrebné konfiguračné nastavenia pre dané prostredie. Na lokálnom serveri bude súbor obsahovať iné údaje ako na produkčnom serveri.

**Postup:**
- zduplikuje sa súbor **config.local.dist.neon**, ktorý slúži ako predloha.
- upraví sa názov zduplikovaného súboru na **config.local.neon**
- vyplnia sa potrebné prístupové a konfiguračné údaje

### Generovanie databazy 
1. Vygenerujeme si schému databázy:
    ```
    php web/index.php orm:schema-tool:create
    ```
2. Vygenerujeme si štandardné routy:
    ```
    php web/index.php router:update-default-routes
    ```
3. Následne spustíme migrácie:
    ```
    php web/index.php migrations:continue
    ```
4. Vytvoríme si štandardné pozície a komponenty:
    ```
    composer wame:component:update
    ```