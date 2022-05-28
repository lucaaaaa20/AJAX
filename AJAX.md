# AJAX

#### Che cos'è ajax?

**Ajax** non è un linguaggio di programmazione, è una metodologia, l'acronimo Ajax sta per **Asynchronous JavaScript and XML**, e ci permette di creare pagine dinamiche, poichè ci da la possibilità di eseguire chiamate al server senza che la pagina venga ricaricata nel momento di una chiamata Ajax, quindi l'utente non si accorge di niente. La funzionalità migliore e più utile di Ajax è quella di poter richiamare una **REST API**

------

#### Come si usa?

Inanzitutto per utilizzare Ajax abbiamo bisogno di uno script Javascript nel nostro file HTML, e anche di importare la libreria **Jquery** che ci faciliterà alcune funzioni di Ajax. Dopo di questo possiamo creare la nostra prima richiesta.

Esempio:

![GET_Ajax](C:\Users\utente\Desktop\AJAX\GET_Ajax.PNG)

- Per prima cosa abbiamo bisogno inserire il seguente testo che ci indicherà l'inizio di una chiamata ![chiamata](C:\Users\utente\Desktop\Ajax\chiamata.PNG)

- All'interno di 

  ```javascript
  $.ajax(
  	
  )
  ```

  abbiamo bisogno di inserire un oggetto javascript, che potrà contenere vari valori, i più importanti ed essenziali per il funzionamento corretto sono quelli dell'immagine di sopra, più **data:** <dati da inviare>  (nell'esempio non è presente poichè è una richiesta di tipo **GET** quindi non abbiamo bisogno di inserirlo, poichè stiamo semplicemente richiedendo dei dati al server)

  1. ```javascript
     url:"http://localhost:3000/chat"
     ```

     Stiamo dicendo che al momento di lancio della chiamata ajax deve andare all'indirizzo **/chat**, nel quale è presente una API che esegue la **GET **presente nel punto **4**
  
  2. ```javascript
     Type: "GET"
     ```
  
     Stiamo indicando il tipo di richiesta che stiamo facendo all'API
  
  3. ```javascript
     success:function (data){
     	//Funzione da eseguire
     }
     ```
  
     Il **success** indica la funzione da svolgere nel momento in cui la richiesta all'API vada a buon fine, il risultato della API finirà in **data**, perciò con i dati che otterremo potremmo eseguire delle funzioni direttamente nello script della nostra pagina HTML
     
     ------
     
     ![api_get](C:\Users\utente\Desktop\Ajax\api_get.png)
     
     ​	Per esempio questa è la nostra API, che restituirà tutte quante le righe presenti della tabella, il risultato finirà in **data**
     
     ​	perciò data avrà un oggetto **JSON** con tutti quanti questi campi
     
     ![database](C:\Users\utente\Desktop\Ajax\database.png)
     
     ​	In questo modo possiamo andare a fare quello che vogliamo una volta che riceviamo questi dati![funzione_ajax](C:\Users\utente\Desktop\Ajax\funzione_ajax.png)
     
     ​	per esempio la nostra chiamata ajax andrà ad eseguire questa funzione in caso la chiamata all'API andrà a buon fine, 	perciò la nostra funzione andrà semplicemente a loopare il nostro oggetto javascript che contiene tutte quante le 		 	righe, e il nume utente sarà uguale ad **Ugo** andrà ad applicare dello stile diverso rispetto al casao in cui la condizione   	sia falsa	
     
     ​	E in seguito allo scorrimento dell'oggetto si andranno ad inserire tutti quante queste card all'interno dell'elemento del 	nostro **DOM** con id **chat**
     
     ------
     
  5. ```javascript
     error: function(data){
     	//Funzione da eseguire
     }
     ```
  
     L'**error** indica la funzione da svolgere nel momento in cui la richiesta all'API non vada a buon fine, il risultato della API finirà in **data**, perciò proprio come per il success, potremmo andare ad eseguire una funzione in caso di errore, nell'esempio stiamo semplicemente dicendo che in caso di errore andremo a stampare in console **"non mandato"**
  
- Visto che queste chiamate ajax vengono create e richiamate nel lato client, perciò potranno essere creare all'interno di uno script esterno o direttamente in uno script creato nella pagina **HTML**, possiamo andare a richiamarle nel momento che vogliamo, ad esempio possiamo associarle al click di un pulsante, al caricamento della pagina etc...

  ![funzioni_richiamate](C:\Users\utente\Desktop\Ajax\funzioni_richiamate.png)

  Per esempio **elencoMessaggi()** è la chiamata ajax mostrata sopra, che verrà eseguita una volta che il file verrà caricato 	completamente, **login()** e **getMex() **sono altre due chiamate ajax che vengono associate al click di un pulsante.

  Possiamo andare anche a impostare un timer secondo il quale ogni volta il lasso di tempo passa andrà ad eseguire la nostra **ajax**
  
  ------
  
  

> Risorse usate:
>
> https://it.wikipedia.org/wiki/AJAX
>
> https://stackoverflow.com/questions/4674470/is-ajax-a-separate-language-from-javascript-or-is-it-a-javascript-framework
>
> https://bsscommerce.com/blog/javascript-jquery-ajax-are-they-the-same-or-different/
>
> https://www.w3schools.com/xml/ajax_intro.asp
>
> Codice dell'esempio: https://github.com/lucaaaaa20/chat
