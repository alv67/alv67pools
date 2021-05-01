
---

# alv pools

Questo progetto è semplicemente un tutorial per l'apprendimento di Svelte (https://www.svelte.dev)


## Per iniziare

Installa le dipendenze...

```bash
cd alvpools
npm install
```

...e poi avvia [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Naviga su [localhost:5000](http://localhost:5000). 
Dovresti vedere l'applicazione in esecuzione in modalità sviluppo. In questo modo ogni modifica salvata è automaticamente attivata sull'applicazione.

Il server risponde solo se raggiunto da localhost. Per attivare la connessione da altri computer edita il comando
 `sirv` nel file package.json e includi l'opzione `--host 0.0.0.0`.

Se utilizzi [Visual Studio Code](https://code.visualstudio.com/) si raccomanda di installare l'estensione ufficiale [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). 

## Compilare ed eseguire in modalità produzione

Per creare la versione ottimizzata dell'applicazione:

```bash
npm run build
```

È così possibile eseguire questa applicazione ottimizzata con il comando `npm run start`. 

È utilizzato [sirv](https://github.com/lukeed/sirv), che è incluso nelle `dependencies` di package.json' così l'applicazione funzionerà quando distribuita su piattaforme come [Heroku](https://heroku.com).

## Modalità single-page app (SPA)

Di default , sirv risponde a richieste che corrispondono a file in`public`. Questo massimizza la compatibilità con server statici, permettendo la distribuzione dell'applicazione ovunque.

Se stai compilando l'applicazione single-page (SPA) con instradamenti multipli, sirv necessita di poter rispondere a richieste provenienti da *qualsiasi* percorso. E' possibile definirlo tramite la modifica del comando `"start"` in package.json:

```js
"start": "sirv public --single"
```

## Utilizzo di TypeScript

Questa applicazione nasce con una script utile per configurare l'ambiente di sviluppo Typescript, per farlo utilizzare:

```bash
node scripts/setupTypeScript.js
```

Altrimenti rimuovere lo script:

```bash
rm scripts/setupTypeScript.js
```
