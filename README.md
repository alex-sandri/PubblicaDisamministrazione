# PubblicaDisamministrazione

Vulnerabilità e altre scoperte fatte sui portali di vari enti pubblici.

---

## Indice

- [ClicLavoroVeneto](#cliclavoroveneto)
- [PagoInRete](#pagoinrete)

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

## [PagoInRete](https://pagoinrete.pubblica.istruzione.it/)

| Data | Stato |
| :-: | :-: |
| 2022-02-07 | :white_check_mark: |

Chiunque abbia effettuato l'accesso al portale può, conoscendone l'identificativo, accedere ai dettagli di qualsiasi pagamento.

### Esempio

```
https://pagoinrete.pubblica.istruzione.it/parsWeb/ricevuta_telematica.html?codiceAvviso={{ CODICE_AVVISO }}&codiceIuv={{ CODICE_AVVISO }}
https://pagoinrete.pubblica.istruzione.it/parsWeb/dettaglioAvviso/{{ CODICE_UTENTE }}/{{ CODICE_AVVISO }}
https://pagoinrete.pubblica.istruzione.it/parsWeb/stampa_ricevuta.pdf?avvisoId={{ CODICE_AVVISO }}&codiceScuola=
```

- `CODICE_AVVISO` è il codice dell'avviso di pagamento
- `CODICE_UTENTE` è l'identificativo dell'utente
