# Registro delle modifiche — S-IT-3Copia

Tutte le modifiche degne di nota di S-IT-3Copia, dalla più recente.

## v3.3.2.10 — settembre 2026 · Neerlandese e italiano

- **Novità:** due lingue in più – **neerlandese** e **italiano**. Il programma parla così sei lingue. Il nome del programma cambia con esse: 3Kopieer e 3Copia.
- Sono tradotti, come di consueto, le finestre, le finestre di dialogo, i messaggi, il pianificatore e i registri; a ciascuna delle due lingue corrisponde una pagina di aiuto propria.
- La barra delle lingue in tutte le pagine di aiuto propone ora sei lingue.
- Il programma in sé non è cambiato: profili, filtri e impostazioni esistenti restano invariati.

## v3.3.2.9 — agosto 2026 · Edizione internazionale

- **Novità:** il programma parla quattro lingue – tedesco, inglese, francese e spagnolo. La lingua viene scelta durante l'installazione e si può cambiare in qualsiasi momento in ⚙; la scelta mostra per ogni lingua la bandiera corrispondente. Il nome del programma cambia con essa: 3Kopier, 3Copy, 3Copier, 3Copiar.
- Sono tradotti le finestre, tutte le finestre di dialogo, i messaggi durante la copia, il pianificatore e i registri. Ogni lingua ha la sua pagina di aiuto; le pagine rimandano l'una all'altra.
- Nomi dei file e impostazioni restano uguali in tutte le lingue (`3Kopier.ini`, profili con estensione `.3ko`, cartella `Logs`): un cambio di lingua non modifica profili, filtri e impostazioni esistenti.
- **Migliorato:** le impostazioni (⚙) sono ora su due colonne – a sinistra lingua e ingrandimento, a destra conservazione e dettaglio dei registri. La finestra è così molto più bassa e sta per intero sullo schermo anche con un ingrandimento elevato.
- **Migliorato:** i pulsanti della barra dei profili si adattano alla lunghezza della loro scritta, così il testo mantiene un margine sufficiente in ogni lingua.

## v3.3.2.8 — agosto 2026

- **Novità:** tolleranza sulle date contro gli scarti su unità NAS e di rete – nella modalità «solo se più recente» i file immutati non vengono più scambiati per più recenti a causa di differenze di pochi secondi né ricopiati a ogni esecuzione (tolleranza di 2 secondi, come Robocopy /FFT).
- **Novità:** simbolo 🛡 per profilo (accanto a 🚫) – regola quella tolleranza (Automatico / Sempre / Disattivato); «Automatico» agisce solo sui percorsi di rete `\\` ed è l'impostazione predefinita, «Sempre» aiuta con le unità di rete con lettera assegnata (`X:`, `Y:` …).
- **Migliorato:** i percorsi nel riepilogo delle attività non vengono più tagliati al bordo ma accorciati in modo pulito (inizio…fine); il percorso completo compare nel suggerimento.
- **Corretto:** la finestra di esecuzione non poteva essere ridotta a icona quando veniva avviata dalla finestra del pianificatore aperta; la crocetta di chiusura (X) agisce ora come ⏹ Stop e interrompe in modo pulito solo quella esecuzione.

## v3.3.2 — luglio 2026

- **Novità:** indicazione della velocità – durante la copia la riga di stato mostra la velocità di trasferimento del momento (per esempio `157.4 MB/s`), anche nella finestra di avanzamento del pianificatore.
- **Novità:** filtro per attività (🔰) – esclusioni aggiuntive solo per quell'attività oppure una regola SOLO («copiare unicamente determinati tipi di file»), per esempio l'attività 1 solo con `*.pdf`. Il simbolo 🔰 diventa verde non appena è stata definita una regola; le esclusioni dell'intero profilo continuano ad applicarsi in aggiunta.
- **Novità:** dettaglio del registro a scelta (⚙) – Compatto (predefinito) con una riga riepilogativa per attività, Dettagliato con una riga per cartella; gli errori figurano sempre per intero nel registro.
- **Novità:** coda per il pianificatore – le esecuzioni che si sovrappongono non vanno più perdute ma si susseguono; le finestre dei risultati non bloccano l'esecuzione successiva, ⏹ Stop interrompe soltanto quella in corso. La finestra di esecuzione compare anche con il programma nell'area di notifica e può essere ridotta a icona; le interruzioni figurano nel registro come «FAZIT (ABGEBROCHEN)».

## v3.3.1 — luglio 2026 · Passaggio a Python

- Passaggio completo da AutoIt a Python – uso e svolgimento invariati, i file `3Kopier.ini` e i profili `.3ko` esistenti continuano a funzionare senza alcun adattamento.
- Le copie avvengono in secondo piano – la finestra resta reattiva anche con moltissimi file o con unità di rete lente; copia a blocchi, «Stop» ha effetto immediato.
- **Novità:** pianificatore automatico – eseguire profili secondo una pianificazione in secondo piano, con modalità silenziosa e funzionamento nell'area di notifica con avvio automatico.
- **Novità:** elenco delle esclusioni – tenere fuori dalla copia file e cartelle intere (cache dei browser, file temporanei, grandi formati di immagine); con valori iniziali sensati, adattabili per profilo.
- **Novità:** sospensione dopo la copia in alternativa all'arresto (le due possibilità si escludono a vicenda).
- Nuove impostazioni (⚙): ingrandimento dal 90 al 200 %, conservazione dei registri (da 1 giorno a illimitato) con pulizia immediata; i registri sono ora un file proprio per ogni esecuzione nella cartella `Logs`.
- Finestra dei risultati rivista (una colonna per attività); l'elenco a discesa dei profili carica subito, senza pulsante «Carica»; i percorsi molto lunghi sono mostrati accorciati (inizio…fine), con il percorso completo nel suggerimento.
- Percorsi di rete e NAS (UNC) migliorati, calcolo della quantità di dati senza blocchi; il bilancio si trova ora in alto; piccole correzioni di impaginazione; è accluso `Lizenz.txt`.

## v3.2.1 — versione AutoIt

- Trattamento automatico dei percorsi lunghi (MAX_PATH): i percorsi di destinazione a partire da 260 caratteri vengono accorciati automaticamente – prima il nome del file, se serve anche l'ultima sottocartella. I nomi accorciati ricevono il contrassegno `-3k`.
- La quantità di dati viene conteggiata correttamente anche con percorsi lunghi, sia nell'indicazione sia nella barra di avanzamento.
- Dimensione del registro limitata automaticamente a 512 KB – le voci più vecchie vengono rimosse, le esecuzioni recenti restano.

## v3.2.0 — versione AutoIt

- Le opzioni sovrascrivi/sposta per attività vengono ora salvate sia nel file INI sia nei profili `.3ko`.
- Le cartelle di destinazione vengono create prima del controllo; i percorsi di rete vengono saltati nel calcolo della quantità di dati, senza blocchi.
- Correzioni visive: spaziature dell'intestazione, larghezza delle scritte e posizione delle caselle di spunta riviste.

---

© 2026 Sattler IT-Service, Greifenstein · Autore: Hans Udo Sattler
