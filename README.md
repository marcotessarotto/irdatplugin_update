# IRDAT Explorer 3 - aggiornamento per QGIS 3.44

**Nota importante**: questa e' una modifica NON UFFICIALE del plugin IRDAT Explorer 3,
originalmente prodotto da Insiel SpA. La modifica ha lo scopo di far funzionare il
plugin su QGIS 3.44.7. Non sono lo sviluppatore originale del plugin.

Motivo dell'update non ufficiale: con QGIS 3.44.7, il plugin originale non si avvia
perche' dipende da `PyQt5.QtWebKitWidgets`, modulo rimosso. L'errore tipico e':

```
Couldn't load plugin 'IRDATExplorer' due to an error when calling its classFactory() method
ModuleNotFoundError: No module named 'PyQt5.QtWebKitWidgets'
```

Plugin QGIS per la consultazione del Catalogo IRDAT FVG. Permette la ricerca nel catalogo,
la visualizzazione dei metadati e il caricamento dei layer WFS nel progetto QGIS.

## Funzionalita
- Ricerca per soggetto e/o testo libero.
- Elenco risultati con titolo, abstract, id e URL WFS.
- Visualizzazione metadati integrata (QtWebEngine) e apertura nel browser.
- Caricamento diretto dei layer WFS in QGIS.

## Requisiti
- QGIS 3.0+ (metadata: `qgisMinimumVersion=3.0`).
- Python fornito da QGIS.
- Dipendenze Python: `requests` (vedi `requirements.txt`).
- QtWebEngine (su Debian/Ubuntu: `sudo apt install python3-pyqt5.qtwebengine`).

## Installazione (manuale)
1. Installa il plugin originale "IRDAT Explorer 3" da QGIS.
2. Chiudi QGIS.
3. Copia i file di questa repository nella cartella del plugin:
   `~/.local/share/QGIS/QGIS3/profiles/default/python/plugins/irdatplugin_update`
4. Avvia di nuovo QGIS.

## Uso rapido
1. Apri il plugin "IRDAT Explorer 3".
2. Clicca "Inizia consultazione", scegli il soggetto e/o inserisci il testo.
3. Avvia la ricerca e seleziona un elemento in tabella.
4. Visualizza i metadati o carica il layer WFS.

## Sviluppo/IDE (PyCharm)
Le librerie `qgis.*` non sono installabili via pip. Per evitare errori di import:
- usa l'interprete di sistema QGIS (o un venv con "Inherit global site-packages");
- aggiungi ai path dell'interprete:
  - `/usr/share/qgis/python`
  - `/usr/share/qgis/python/plugins`

