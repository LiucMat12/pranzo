# A tavola! — app ordini

## Pubblicazione gratuita su GitHub Pages
1. Crea un repository **pubblico** su GitHub, ad esempio `pranzo`.
2. Carica `index.html` e `config.js` nella radice del repository.
3. In Settings → Pages scegli **Deploy from a branch**, branch `main`, cartella `/ (root)` e salva.
4. Il sito sarà su `https://TUO-UTENTE.github.io/pranzo/`.

## Ordini condivisi (Firebase Spark, piano gratuito senza carta)
1. Crea un progetto su Firebase Console con piano **Spark** (non Blaze).
2. Aggiungi una **Web App** e copia i valori di configurazione in `config.js`.
3. Attiva Firestore Database e crea un database.
4. Per una **prova temporanea** usa queste regole Firestore:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /ordini/{id} {
      allow read, create, update, delete: if true;
    }
  }
}
```

5. Pubblica le regole e aggiorna `config.js` su GitHub.

**ATTENZIONE:** queste regole sono aperte a chiunque abbia l'indirizzo del database: sono adatte solo a una prova non sensibile e di breve durata. Anche il riepilogo è pubblico. Non inserire dati personali sensibili o informazioni mediche nelle note. Per un uso continuativo occorrono autenticazione e regole più restrittive.

## Costi e limiti
GitHub Pages per repository pubblici e Firebase Spark offrono quote gratuite, non una garanzia contrattuale di gratuità per sempre. Non passare al piano Blaze. Verifica le condizioni aggiornate dei servizi prima dell'utilizzo.

## Nota
Senza configurazione Firebase l'app funziona in modalità demo nel browser, ma gli ordini non si sincronizzano.
