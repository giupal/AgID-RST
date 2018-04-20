+-----------------------------------------------------------------------+
| |AGID_logo_carta_intestata-02.png|                                    |
+-----------------------------------------------------------------------+

+---------------------------------------+
| **Capitolo 6. GIORNALE DEGLI EVENTI** |
+---------------------------------------+

Giornale degli Eventi
=====================

La funzione di Giornale degli Eventi è quella di consentire la
tracciabilità di ogni operazione di pagamento attivata per il tramite
del Nodo dei Pagamenti-SPC.

L'operazione di pagamento si sviluppa mediante la cooperazione
applicativa tra sistemi diversi delle amministrazioni pubbliche, del
Nodo dei Pagamenti-SPC e dei prestatori dei servizi di pagamento. è
quindi necessario, per ricostruire il processo complessivo, che ognuno
dei sistemi interessati dal pagamento telematico, si doti di funzioni
specifiche per registrare i passaggi principali del trattamento
dell'operazione di pagamento. Gli eventi di ingresso e di uscita dal
sistema, ovvero le operazioni di interfaccia, sono punti cardine da
tracciare obbligatoriamente, ai quali si aggiungono cambi di stato
intermedi significativi per il singolo sistema.

Le tracce registrate dai singoli sistemi, in caso di richiesta di
verifica, devono essere estratte e confrontate con le analoghe
informazioni prodotte da tutti i sistemi di collaborazione coinvolti
nelle operazioni interessate.

Ai fini del confronto sono state individuate due aree di identificazione
dell'operazione di pagamento: l'identificazione del pagamento
telematico, basata sui campi chiave che rendono univoco il riferimento
al pagamento, e l'identificazione dello scambio dei messaggi di
interfaccia basata sui parametri dei messaggi stessi che collegano in
modo inequivocabile tali messaggi con il pagamento specifico.

Nella Tabella 29 sono indicate le informazioni e le specifiche di
rappresentazione dei dati che i soggetti appartenenti al Dominio sono
tenuti a fornire per le verifiche di cui sopra. Questi dati sono altresì
le informazioni "minime" da archiviare nel Giornale degli Eventi (`cfr. §
3.2.10 <../08-Capitolo_3/Capitolo3.rst#giornale-degli-eventi>`__). Tali informazioni devono essere memorizzate presso le strutture
che scambiano le informazioni (Enti Creditori, PSP, Intermediari
tecnologici, Nodo dei Pagamenti-SPC) e devono essere accessibili a
richiesta, nei formati che saranno concordati.

**Tabella** **29 - Informazioni "minime" da archiviare nel "Giornale degli Eventi "**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| dataOra   | 1         | an        | 1..1      | 19        | Indica la |
| Evento    |           |           |           |           | data e    |
|           |           |           |           |           | l’ora     |
|           |           |           |           |           | dell’even |
|           |           |           |           |           | to        |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601, |
|           |           |           |           |           | alla      |
|           |           |           |           |           | risoluzio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | del       |
|           |           |           |           |           | milliseco |
|           |           |           |           |           | ndo       |
|           |           |           |           |           | e sempre  |
|           |           |           |           |           | riferito  |
|           |           |           |           |           | al GMT.   |
|           |           |           |           |           | Formato   |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss.sss |
|           |           |           |           |           | ]         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 1         | an        | 1..1      | 1..35     | Campo     |
| ificativo |           |           |           |           | alfanumer |
| Dominio   |           |           |           |           | ico       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che invia |
|           |           |           |           |           | la        |
|           |           |           |           |           | richiesta |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| identific | 1         | an        | 1..1      | 1..35     | Riferimen |
| ativoUniv |           |           |           |           | to        |
| ocoVersam |           |           |           |           | univoco   |
| ento      |           |           |           |           | assegnato |
|           |           |           |           |           | al        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | dall’ente |
|           |           |           |           |           | beneficia |
|           |           |           |           |           | rio       |
|           |           |           |           |           | e         |
|           |           |           |           |           | presente  |
|           |           |           |           |           | nel       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | che ha    |
|           |           |           |           |           | originato |
|           |           |           |           |           | l’evento. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| codiceCon | 1         | an        | 1..1      | 1..35     | Codice    |
| testoPaga |           |           |           |           | univoco   |
| mento     |           |           |           |           | necessari |
|           |           |           |           |           | o         |
|           |           |           |           |           | a         |
|           |           |           |           |           | definire  |
|           |           |           |           |           | il        |
|           |           |           |           |           | contesto  |
|           |           |           |           |           | nel quale |
|           |           |           |           |           | viene     |
|           |           |           |           |           | effettuat |
|           |           |           |           |           | o         |
|           |           |           |           |           | il        |
|           |           |           |           |           | versament |
|           |           |           |           |           | o         |
|           |           |           |           |           | presente  |
|           |           |           |           |           | nel       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | che ha    |
|           |           |           |           |           | originato |
|           |           |           |           |           | l’evento. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 1         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| Prestator |           |           |           |           | del       |
| eServiziP |           |           |           |           | Prestator |
| agamento  |           |           |           |           | e         |
|           |           |           |           |           | servizi   |
|           |           |           |           |           | di        |
|           |           |           |           |           | Pagamento |
|           |           |           |           |           | univoco   |
|           |           |           |           |           | nel       |
|           |           |           |           |           | Dominio   |
|           |           |           |           |           | scelto    |
|           |           |           |           |           | dall’util |
|           |           |           |           |           | izzatore  |
|           |           |           |           |           | finale    |
|           |           |           |           |           | e/o       |
|           |           |           |           |           | dall’Ente |
|           |           |           |           |           | Creditore |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoVersa | 1         | an        | 0..1      | 1..35     | Forma     |
| mento     |           |           |           |           | tecnica   |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | presente  |
|           |           |           |           |           | nel       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | che ha    |
|           |           |           |           |           | originato |
|           |           |           |           |           | l’evento. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| compo     | 1         | an        | 1..1      | 1..35     | Sistema o |
| nente     |           |           |           |           | sottosist |
|           |           |           |           |           | ema       |
|           |           |           |           |           | che ha    |
|           |           |           |           |           | generato  |
|           |           |           |           |           | l’evento  |
|           |           |           |           |           | (es.      |
|           |           |           |           |           | FESP,     |
|           |           |           |           |           | WFESP)    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| categ     | 1         | an        | 1..1      | 1..35     | INTERNO/I |
| oriaEvent |           |           |           |           | NTERFACCI |
| o         |           |           |           |           | A,        |
|           |           |           |           |           | indica se |
|           |           |           |           |           | l'evento  |
|           |           |           |           |           | tracciato |
|           |           |           |           |           | è         |
|           |           |           |           |           | relativo  |
|           |           |           |           |           | un'operaz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | di        |
|           |           |           |           |           | interfacc |
|           |           |           |           |           | ia        |
|           |           |           |           |           | con altri |
|           |           |           |           |           | sistemi   |
|           |           |           |           |           | oppure se |
|           |           |           |           |           | rappresen |
|           |           |           |           |           | ta        |
|           |           |           |           |           | un'operaz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | interna   |
|           |           |           |           |           | (es.      |
|           |           |           |           |           | cambio di |
|           |           |           |           |           | stato) al |
|           |           |           |           |           | proprio   |
|           |           |           |           |           | sistema   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoE     | 1         | an        | 1..1      | 1..35     | Identific |
| vento     |           |           |           |           | ativo     |
|           |           |           |           |           | del tipo  |
|           |           |           |           |           | di        |
|           |           |           |           |           | evento.   |
|           |           |           |           |           | Nel caso  |
|           |           |           |           |           | di        |
|           |           |           |           |           | interazio |
|           |           |           |           |           | ni        |
|           |           |           |           |           | SOAP è il |
|           |           |           |           |           | nome del  |
|           |           |           |           |           | metodo    |
|           |           |           |           |           | SOAP.     |
+-----------+-----------+-----------+-----------+-----------+-----------+
| sotto     | 1         | an        | 1..1      | 1..35     | Nel caso  |
| TipoEvent |           |           |           |           | di        |
| o         |           |           |           |           | interazio |
|           |           |           |           |           | ni        |
|           |           |           |           |           | SOAP      |
|           |           |           |           |           | sincrone  |
|           |           |           |           |           | assume i  |
|           |           |           |           |           | valori    |
|           |           |           |           |           | req/rsp   |
|           |           |           |           |           | per       |
|           |           |           |           |           | indicare  |
|           |           |           |           |           | rispettiv |
|           |           |           |           |           | amente    |
|           |           |           |           |           | SOAP      |
|           |           |           |           |           | Request e |
|           |           |           |           |           | SOAP      |
|           |           |           |           |           | *Response*|
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 1         | an        | 1..1      | 1..35     | Nel caso  |
| ificativo |           |           |           |           | di eventi |
| Fruitore  |           |           |           |           | di tipo   |
|           |           |           |           |           | INTERFACC |
|           |           |           |           |           | IA        |
|           |           |           |           |           | si deve   |
|           |           |           |           |           | utilizzar |
|           |           |           |           |           | e         |
|           |           |           |           |           | l’Identif |
|           |           |           |           |           | icativo   |
|           |           |           |           |           | del       |
|           |           |           |           |           | sistema   |
|           |           |           |           |           | del       |
|           |           |           |           |           | Soggetto  |
|           |           |           |           |           | richieden |
|           |           |           |           |           | te        |
|           |           |           |           |           | nell’ambi |
|           |           |           |           |           | to        |
|           |           |           |           |           | del       |
|           |           |           |           |           | Dominio.  |
|           |           |           |           |           |           |
|           |           |           |           |           | (Es.      |
|           |           |           |           |           | identific |
|           |           |           |           |           | ativoStaz |
|           |           |           |           |           | ioneInter |
|           |           |           |           |           | mediarioP |
|           |           |           |           |           | A         |
|           |           |           |           |           | nel caso  |
|           |           |           |           |           | della     |
|           |           |           |           |           | *nodoInvi*|
|           |           |           |           |           | *aRPT*)   |
|           |           |           |           |           |           |
|           |           |           |           |           | Nel caso  |
|           |           |           |           |           | di eventi |
|           |           |           |           |           | di tipo   |
|           |           |           |           |           | INTERNO,  |
|           |           |           |           |           | si può    |
|           |           |           |           |           | utilizzar |
|           |           |           |           |           | e         |
|           |           |           |           |           | un nome   |
|           |           |           |           |           | di        |
|           |           |           |           |           | component |
|           |           |           |           |           | e         |
|           |           |           |           |           | o sotto   |
|           |           |           |           |           | component |
|           |           |           |           |           | e         |
|           |           |           |           |           | che       |
|           |           |           |           |           | genera    |
|           |           |           |           |           | l’evento. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 1         | an        | 1..1      | 1..35     | Nel caso  |
| ificativo |           |           |           |           | di eventi |
| Erogatore |           |           |           |           | di tipo   |
|           |           |           |           |           | INTERFACC |
|           |           |           |           |           | IA        |
|           |           |           |           |           | si deve   |
|           |           |           |           |           | utilizzar |
|           |           |           |           |           | e         |
|           |           |           |           |           | l’Identif |
|           |           |           |           |           | icativo   |
|           |           |           |           |           | del       |
|           |           |           |           |           | sistema   |
|           |           |           |           |           | del       |
|           |           |           |           |           | Soggetto  |
|           |           |           |           |           | risponden |
|           |           |           |           |           | te        |
|           |           |           |           |           | nell’ambi |
|           |           |           |           |           | to        |
|           |           |           |           |           | del       |
|           |           |           |           |           | Dominio.  |
|           |           |           |           |           |           |
|           |           |           |           |           | (Es.      |
|           |           |           |           |           | “NodoDeiP |
|           |           |           |           |           | agamentiS |
|           |           |           |           |           | PC”       |
|           |           |           |           |           | nel caso  |
|           |           |           |           |           | della     |
|           |           |           |           |           | *nodoInvi*|
|           |           |           |           |           | *aRPT*)   |
|           |           |           |           |           |           |
|           |           |           |           |           | Nel caso  |
|           |           |           |           |           | di eventi |
|           |           |           |           |           | di tipo   |
|           |           |           |           |           | INTERNO,  |
|           |           |           |           |           | si può    |
|           |           |           |           |           | utilizzar |
|           |           |           |           |           | e         |
|           |           |           |           |           | un nome   |
|           |           |           |           |           | di        |
|           |           |           |           |           | component |
|           |           |           |           |           | e         |
|           |           |           |           |           | o sotto   |
|           |           |           |           |           | component |
|           |           |           |           |           | e         |
|           |           |           |           |           | che       |
|           |           |           |           |           | processa  |
|           |           |           |           |           | l’evento. |
|           |           |           |           |           | Per       |
|           |           |           |           |           | quest’ult |
|           |           |           |           |           | ima       |
|           |           |           |           |           | tipologia |
|           |           |           |           |           | il valore |
|           |           |           |           |           | può       |
|           |           |           |           |           | coincider |
|           |           |           |           |           | e         |
|           |           |           |           |           | con       |
|           |           |           |           |           | l’iden    |
|           |           |           |           |           | tificativ |
|           |           |           |           |           | oFruito   |
|           |           |           |           |           | re,       |
|           |           |           |           |           | qualora   |
|           |           |           |           |           | non vi    |
|           |           |           |           |           | sia un    |
|           |           |           |           |           | component |
|           |           |           |           |           | e         |
|           |           |           |           |           | che       |
|           |           |           |           |           | risponde  |
|           |           |           |           |           | all’event |
|           |           |           |           |           | o         |
|           |           |           |           |           | stesso.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| identific | 1         | an        | 0..1      | 1..35     | identific |
| ativoStaz |           |           |           |           | ativo     |
| ioneInter |           |           |           |           | della     |
| mediarioP |           |           |           |           | Stazione  |
| A         |           |           |           |           | dell’inte |
|           |           |           |           |           | rmediario |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | nel       |
|           |           |           |           |           | sistema   |
|           |           |           |           |           | del Nodo  |
|           |           |           |           |           | dei       |
|           |           |           |           |           | Pagamenti |
|           |           |           |           |           | SPC, da   |
|           |           |           |           |           | cui è     |
|           |           |           |           |           | transitat |
|           |           |           |           |           | a         |
|           |           |           |           |           | la        |
|           |           |           |           |           | RPT/RT.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| canalePag | 1         | an        | 0..1      | 1..35     | identific |
| amento    |           |           |           |           | ativo     |
|           |           |           |           |           | del       |
|           |           |           |           |           | Canale    |
|           |           |           |           |           | del PSP   |
|           |           |           |           |           | nel       |
|           |           |           |           |           | sistema   |
|           |           |           |           |           | del Nodo  |
|           |           |           |           |           | dei       |
|           |           |           |           |           | Pagamenti |
|           |           |           |           |           | SPC da    |
|           |           |           |           |           | cui è     |
|           |           |           |           |           | transitat |
|           |           |           |           |           | a/si      |
|           |           |           |           |           | vuole far |
|           |           |           |           |           | transitar |
|           |           |           |           |           | e         |
|           |           |           |           |           | la        |
|           |           |           |           |           | RPT/RT.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| parametri | 1         | an        | 0..1      | 1..512    | parametri |
| Specifici |           |           |           |           | specifici |
| Interfacc |           |           |           |           | utilizzat |
| ia        |           |           |           |           | i         |
|           |           |           |           |           | nell’inte |
|           |           |           |           |           | rfaccia   |
|           |           |           |           |           | dal PSP o |
|           |           |           |           |           | dall’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | nel       |
|           |           |           |           |           | modello   |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | 1 o 3     |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Esito     | 1         | an        | 0..1      | 1..35     | Campo     |
|           |           |           |           |           | opzionale |
|           |           |           |           |           | in base   |
|           |           |           |           |           | allo      |
|           |           |           |           |           | stato     |
|           |           |           |           |           | dell’oper |
|           |           |           |           |           | azione    |
|           |           |           |           |           | al        |
|           |           |           |           |           | momento   |
|           |           |           |           |           | della     |
|           |           |           |           |           | registraz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | dell’even |
|           |           |           |           |           | to.       |
|           |           |           |           |           |           |
|           |           |           |           |           | Obbliga   |
|           |           |           |           |           | torio     |
|           |           |           |           |           | nel caso  |
|           |           |           |           |           | di        |
|           |           |           |           |           | richieste |
|           |           |           |           |           | SOAP.     |
+-----------+-----------+-----------+-----------+-----------+-----------+

Si precisa per i PSP che deve essere sempre registrato, all’interno del
Giornale degli Eventi, l’evento relativo alla generazione della RT
(avente sia esito positivo, sia esito negativo): in questo caso
valorizzare il dato:

-  categoriaEvento a “INTERNO”;

-  identificativoErogatore a “GENERAZIONE-RT”.

`Torna all'indice <../index.rst>`__

.. |AGID_logo_carta_intestata-02.png| image:: ../media/header.png
   :width: 5.90551in
   :height: 1.30277in
