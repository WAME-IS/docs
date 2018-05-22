# Začíname {docsify-ignore-all}

## Priečinková štruktúra

```
sandbox/
|—— app/                                # priečinok pre preťažovanie balíkov
|    |—— config.local.dist.neon         # konfigurácia pre lokálne prostredie
|    |—— config.site.neon               # konfigurácia špecifická pre projekt
|
|—— bin/
|   |—— bootstrap.php                   # bootovací súbor aplikácie
|
|—— log/                                # záznami o chybách
|—— migrations/                         # migrácie projektu
|—— private/                            # privátny priečinok s assetmi projektu
|    |—— components/                    # front-end pluginy, knižnice, ... (bower)
|    |—— javascripts/                   # js súbory
|    |   |—— admin/                     # skripty AdminModulu
|    |   |—— init.js
|    |   |—— live-form-validation.js
|    |   |—— main.js
|    |   |—— nette.ajax.js
|    |
|    |—— stylesheets/                   # súbory so štýlmi
|        |—— admin/                     # štýly AdminModulu
|        |—— less/
|        |—— wame/
|        |—— layout.less                # hlavný súbor css štýlov projektu
|
|—— temp/                               # dočasné súbory aplikácie
|—— templates/                          # priečinok pre témy
|—— vendror/                            # PHP balíky (composer)
|—— web/                                # verejný prečinok, koreňový priečinok
    |—— css/                            # prečinok s css generovane pomocou gulp úloh
    |   |—— admin.css
    |   |—— layout.css
    |
    |—— fonts/                          # balíky s písmom
    |—— images/
    |   |—— admin/
    |
    |—— img/
    |—— webtemp/                        # webloaderom kompilované css a js súbory
```