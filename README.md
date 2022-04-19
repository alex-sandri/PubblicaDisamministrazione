# PubblicaDisamministrazione

Vulnerabilità e altre scoperte fatte sui portali di vari enti pubblici.

---

## Indice

- [ClicLavoroVeneto](#cliclavoroveneto)

---

## [ClicLavoroVeneto](https://www.cliclavoroveneto.it)

| Data | Stato |
| :-: | :-: |
| 2022-04-19 | :white_check_mark: |

XSS nella pagina di visualizzazione di un offerta di lavoro.

L'attacco avviene quando l'utente clicca sul pulsante **INDIETRO** in fondo alla pagina.

### Esempio

```
https://www.cliclavoroveneto.it/appcpi#/offerte/show/{{ ID }}?ret=javascript:alert(1)
```

- `ID` è l'identificativo dell'offerta di lavoro visualizzata
- Il parametro `ret` viene inserito nell'attributo `href` del pulsante **INDIETRO**
