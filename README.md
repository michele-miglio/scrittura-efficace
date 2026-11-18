# Scrittura efficace

Skill italiana per Codex, versione **1.0.0**. Dà una mano quando bisogna scrivere qualcosa per un lettore preciso, che si tratti di comunicare un ritardo, spiegare un’idea, aprire un racconto o presentare un’offerta. Si può usare anche per rivedere solo una frase lasciando intatto il resto.

## Come lavora

Parte dal compito e dalle informazioni disponibili. In una mail di servizio mette in evidenza ciò che cambia per chi legge. In un articolo sviluppa il passaggio fra una prova e la conclusione. Nel copy commerciale collega la promessa a una funzione o a un risultato documentato e rende chiaro il passo successivo.

Quando il testo suona artificiale, cerca il problema concreto. Due paragrafi possono dire la stessa cosa, un aggettivo può prendere il posto di una prova, una formula di cortesia può essere fuori tono. Una metafora riuscita o una ripetizione voluta possono invece meritare di restare. Per lavorare sulla voce di un autore o di un brand, si possono allegare esempi approvati.

## Installazione personale in Codex

Clona il repository e copia la cartella della skill nella directory personale di Codex. I comandi seguenti funzionano con una shell compatibile con POSIX e rispettano un eventuale `CODEX_HOME` personalizzato.

```sh
git clone https://github.com/michele-miglio/scrittura-efficace.git
cd scrittura-efficace
destinazione="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$destinazione"
if [ -e "$destinazione/scrittura-efficace" ] || [ -L "$destinazione/scrittura-efficace" ]; then
  echo "La skill è già presente in $destinazione/scrittura-efficace"
else
  cp -R scrittura-efficace "$destinazione/"
fi
```

Apri una nuova conversazione Codex in un progetto e descrivi il lavoro editoriale. Puoi anche richiamare direttamente la skill con `$scrittura-efficace`. Se vuoi limitarla a un solo progetto, la cartella della skill può stare in `.agents/skills/` alla radice di quel progetto. Non ci sono dipendenze da installare.

## Tre richieste da provare

- **Revisione puntuale.** «La cliente conosce già il progetto. Accorcia solo il primo paragrafo di questa mail. Conserva la mia battuta finale e lascia identici costo e scadenza.»
- **Contenuto editoriale.** «Trasforma questi appunti in una newsletter per i clienti di una libreria. Scrivi oggetto, anteprima e corpo con la voce di chi lavora al banco. La prenotazione avviene rispondendo alla mail.»
- **Conversione.** «Questi sono i fatti verificati sul corso e le condizioni di rimborso. Scrivi titolo, testo e pulsante della pagina di iscrizione. Il dubbio principale dei lettori è se riusciranno a seguire le lezioni dal vivo.»

## Cosa contiene

| File | Funzione |
|---|---|
| [SKILL.md](scrittura-efficace/SKILL.md) | Interpreta la richiesta, distingue stesura da revisione e sceglie gli approfondimenti pertinenti. |
| [Scrittura e revisione](scrittura-efficace/references/scrittura-e-revisione.md) | Organizzazione del pensiero, eccezioni nelle istruzioni, argomentazione, ritmo e profondità dell’intervento. |
| [Voce e naturalezza](scrittura-efficace/references/voce-e-naturalezza.md) | Voce dell’autore o del brand, tono della situazione e diagnosi delle formule generiche. |
| [Conversione](scrittura-efficace/references/conversione.md) | Proposta di valore, prove, obiezioni, invito all’azione e formule persuasive con esempi italiani. |
| [Contenuti e canali](scrittura-efficace/references/contenuti-e-canali.md) | Adattamento a newsletter, articoli, social, microtesti e script, con attenzione a ciò che cambia fra lettura e ascolto. |
| [Metadati Codex](scrittura-efficace/agents/openai.yaml) | Nome visibile ed esempio di invocazione nel client. |

I riferimenti riportano le fonti editoriali e contengono esempi illustrativi. Si possono consultare singolarmente.

## Verifiche

Il pacchetto 1.0.0 ha superato il validatore di Codex. In un ciclo editoriale con subagenti Terra sono state raccolte 39 risposte a 20 brief distinti, durante successive revisioni. Le prove riguardano la scrittura in italiano. L’effetto sulle conversioni commerciali richiede dati sul comportamento dei lettori.

Dopo l’installazione personale, in una sessione nuova di Codex Desktop, una richiesta di newsletter per una libreria ha attivato spontaneamente la skill. La traccia mostra la lettura di `SKILL.md` dalla directory personale prima della consegna di oggetto, anteprima e corpo. Questo riscontro riguarda quella richiesta e il modello Terra usato nella prova.
