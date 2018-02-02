# Come usare il form e la mappa

Questa semplice applicazione è stata realizzata con il contributo di [Lorenzo Perone](https://github.com/lorenzoperone) per [Wikimedia Italia](https://www.wikimedia.it/), [Andrea Borruso](https://github.com/aborruso) per [onData](http://ondata.it) e [Paolo Frizzera](https://github.com/geofrizz). Il metodo adottato per realizzarla è descritto in questo documento mentre il codice necessario è presente nel repository [rastrellierebologna](https://github.com/ondata/rastrellierebologna). Per il codice, i documenti ed i dati sono state scelte **licenze aperte**: [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.it), [OdBL](https://it.wikipedia.org/wiki/Open_Database_License), [GPL 3](https://it.wikipedia.org/wiki/GNU_General_Public_License).

Le rastrelliere per biciclette in [Openstreetmap](https://www.openstreetmap.org/#map=5/42.147/12.568) sono definite attreverso gli elementi presenti in [questa pagina wiki](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dbicycle_parking):

* [**bicycle_parking**](https://wiki.openstreetmap.org/wiki/IT:Key:bicycle_parking) - i valori dei tag che secondo noi si adattano alla situazione di Bologna sono: **stands**, **wall_loops**, **rack**, **bollard**, **wide_stands**, nella tabella sotto sono descritti gli specifici casi

|**Key**|**Valore**|**Commento**|**Immagine**| 
|--------------------|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| 
|bicycle_parking|stands|Un pezzo di metallo ripiegato contro cui si può appoggiare una bicicletta nella sua interezza. Rende possibile legarci il telaio e una ruota. Sicurezza moderata. Questo tag va utilizzato anche per i sostegni non rettangolari (ad esempio a forma tonda, a strana forma artistica , a forma di w).|[![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/dc/Bike_racks_at_north-west_of_Westfield_-_geograph.org.uk_-_1041057.jpg/100px-Bike_racks_at_north-west_of_Westfield_-_geograph.org.uk_-_1041057.jpg)](https://wiki.openstreetmap.org/wiki/File:Bike_racks_at_north-west_of_Westfield_-_geograph.org.uk_-_1041057.jpg)| 
|bicycle_parking|wall_loops|Spesso considerati sarcasticamente dei "piega ruote" dai ciclisti. Spesso attaccati ad un muro o ad un terreno. Permette di legare solo la ruota anteriore (o la ruota posteriore) e solo la parte più anteriore o la parte bassa. Se viene applicata della forza, le ruote della bici possono venire danneggiate.|[![](https://wiki.openstreetmap.org/w/images/thumb/c/c2/Bike-parking-wheelbender.jpg/100px-Bike-parking-wheelbender.jpg)](https://wiki.openstreetmap.org/wiki/File:Bike-parking-wheelbender.jpg)|
|bicycle_parking|rack|Una rastrelliera è simile all'ancoraggio sopra, ma tipicamente più grande e contiene molte più biciclette. Una tipologia è una rastrelliera appendiabiti (foto a destra). In una tipologia inferiore manca il supporto laterale del tutto.|[![](https://wiki.openstreetmap.org/w/images/thumb/4/41/Triton_Bike_Rack.png/100px-Triton_Bike_Rack.png)](https://wiki.openstreetmap.org/wiki/File:Triton_Bike_Rack.png)|
|bicycle_parking|anchors|Semplicemente un ancoraggio fissato in un muro, per terra o su un masso.|| 
|bicycle_parking|bollard|Un tipo speciale di dissuasore progettato per il bloccaggio della bici. Generalmente, la bici è bloccata sul palo centrale e "braccia" di qualche tipo impediscono ai ladri di sollevare semplicemente la bici sopra il palo.|[![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/Bike_path_on_College_in_Toronto.jpeg/100px-Bike_path_on_College_in_Toronto.jpeg)](https://wiki.openstreetmap.org/wiki/File:Bike_path_on_College_in_Toronto.jpeg)|
|bicycle_parking|wide_stands|Un tipo di sostegno migliore con un pezzo di metallo largo e ripiegato contro cui si può appoggiare una bicicletta nella sua interezza. È più largo di quello descritto con il valore precedente **stand**. Si possono parcheggiare due biciclette sui due lati del sostegno senza che i manubri siano nel mezzo. Di solito sono più lunghi di un normale sostegno. Dal momento che ci sono due pezzi di metallo, c'è più spazio per legare la bicicletta.|[![](https://wiki.openstreetmap.org/w/images/thumb/2/28/Wide_stands_1.jpeg/100px-Wide_stands_1.jpeg)](https://wiki.openstreetmap.org/wiki/File:Wide_stands_1.jpeg)|

* **capacity** - numero di stalli (posti) disponibili, inserire solo un numero
* **covered** - se coperta usare **yes** altrimenti **no**
* [**access**](https://wiki.openstreetmap.org/wiki/IT:Key:access): valore tag: **yes**, **private**, **customer**, **unknown**

Il tipo di accesso è definito in questa tabella

|**Valore**|**Descrizione**|
|--------------------|-----------------|
|customer|Solo per i clienti|
|private|Solo su permesso del proprietario su base individuale. Da usare ad esempio per le rastrelliere presenti in spazi privati di condomini.|
|yes|Il pubblico ha un diritto di accesso ufficiale, legalmente riconosciuto, ad esempio una rastrelliera installata una strada pubblica.|

* **name**: eventuale nome della struttura, ad esempio **Velostazione Dynamo**,

più i seguenti tag, non obbligatori

* **addr:city** - nome della città, Bologna in questo caso
* **addr:street** - nome della via comprensivo del prefisso, ad esempio **Via Zamboni**
* **addr:housenumber** - numero civico in prossimità del quale la rastrelliera si trova, ad esempio **6/B**, è utile utilizzare il **numero civico** se la rastrelliera è nelle sue immediate vicinanze, ad esempio a meno di 10 metri. Inserire **al massimo un numero civico**.

* **note** - può essere utilizzato per inserire, ad esempio, le seguenti informazioni:

  * **stato manutentivo** - ci sono parti rotte, ha bisogno di manutenzione
  * **note relative alla posizione** - ad esempio la rastrelliera presente in OSM non c'è o è in una posizione diversa. Per praticità assumeremo che se c'è una rastrelliera con caratteristiche comparabili (copertura, tipo, numero stalli) ad una distanza inferiore a 10 metri si assume che sia spostata e si inserisce la nota attraverso il **form** nella nuova posizione segnalando l'**id osm** visualizzabile in mappa interrogando i marker rossi, ad esempi nel caso di *id: node/5234639534* riportare solo le ultime quattro cifre del numero **9534** di quella da spostare, se la distanza è maggiore si fanno due inserimenti procedendo così:

    * si compila un form mettendosi nella posizione in cui in OSM è segnata la rasprelliera e si inserisce nelle **note** l'**id** e il commento **mancante**
    * si compila un nuovo form in corrispondenza della rastrelliera distante più di 10 metri e non presente in OSM con tutte le caratteristiche.

Per ogni dubbio puoi scrivere un messaggio in [questo](https://groups.google.com/forum/#!forum/mappiamobo) gruppo Google.
