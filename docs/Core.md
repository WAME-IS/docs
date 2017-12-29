## Core

Core modul obsahuje základné triedy, na ktorých je postavený celý systém. VŠETKY typy objektov, ktoré sa budú nachádzať v projekte, by mali dediť od týchto tried.

### Register

Registre predstavujú jednotný spôsob na registrovanie typov do pluginov. Register má daný práve jeden parameter, ktorým je názov triedy, ktorý musia pridávané typy implementovať. Ak chceme vytvoriť register, robíme to podľa vzoru:

```
class FilterHandlersRegister extends \Wame\Core\Registers\BaseRegister
{
    public function __construct() {
        parent::__construct(\Nazov\Triedy\Ktore\Register\Berie::class);
    }
}
```

### Control "Status"

Tento stav je daný všetkým presenterom a komponentom. Ich úlohou je predávať stav medzi komponentami a presenterom.

Čítanie hodnoty tohoto stavu môžeme vykonať jednoducho:

```
$this->status->get("def", function($value) {
    //callback volany pri zmene hodnoty
});
```

Poprípadne môžeme tento efekt docieliť aj bez eventu, ale hodnota nemusí byť vyplnená. Vždy vráti len aktuálnu hodnotu:

```
$this->status->get("def"), "return");
```