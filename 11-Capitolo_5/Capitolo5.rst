+-----------------------------------------------------------------------+
| |AGID_logo_carta_intestata-02.png|                                    |
+-----------------------------------------------------------------------+

+-----------------------------------------------+
| **Capitolo 5. MESSAGGI E FLUSSI INFORMATIVI** |
+-----------------------------------------------+

Messaggi e flussi informativi
=============================

Di seguito sono descritti i documenti che costituiscono la
rappresentazione telematica delle informazioni che dovranno essere
scambiati nell’ambito di processi di pagamento di somme versate favore
di un ente pubblico.

Le tipologie di documento scambiate nel processo di pagamento telematico
sono individuate come:

-  *Richiesta Pagamento Telematico* (**RPT**)

-  *Ricevuta Telematica* (**RT**)

-  *Richiesta Revoca* (**RR**)

-  *Esito Revoca* (**ER**)

Nel presente capitolo sono inoltre riportate le informazioni relative a
"Tabella delle Controparti" (`§ 4.2.1 <../09-Capitolo_4/Capitolo4.rst#tabella-delle-controparti>`__), "Catalogo Dati Informativi" (`§
5.3.7 <../11-Capitolo_5/Capitolo5.rst#catalogo-dati-informativi>`__) e flussi inerenti i “Totali di Traffico” (`§ 4.5.1 <../09-Capitolo_4/Capitolo4.rst#totali-di-traffico>`__).

Formato dei messaggi
--------------------
.. _Formato dei messaggi:

I formati adottati devono possedere almeno i seguenti requisiti:

-  consentire, nei diversi ambiti di applicazione e per le diverse
   tipologie di trattazione, l'archiviazione, la leggibilità,
   l'interoperabilità e l’interscambio dei messaggi;

-  la non alterabilità dei messaggi durante le fasi di accesso;

-  la possibilità di effettuare operazioni di ricerca tramite indici di
   classificazione o di archiviazione;

-  l'immutabilità del contenuto e della sua struttura. A tale fine i
   messaggi non devono contenere macroistruzioni o codice eseguibile,
   tali da attivare funzionalità che possano modificarne nel tempo la
   struttura o il contenuto.

Al fine di garantire il rispetto del requisito di interoperabilità, si
prevede una rappresentazione in formato XML.

Dovranno essere definite strutture che ne consentano la validazione sia
presso l’Ente Creditore che presso il Prestatori di servizi di
pagamento, relativamente alle fasi di generazione e di verifica
formale dei messaggi.

Le strutture rappresentano lo standard minimo a cui gli Enti Creditori e
i Prestatori di servizi di pagamento devono attenersi; il rigoroso
rispetto dello standard minimo è indispensabile per garantire
l’interoperabilità.

Per la visualizzazione dei messaggi, devono essere adottate soluzioni
che presentino le informazioni in modo fedele alla struttura.

Soggetti
--------
.. _Soggetti:

Sono di seguito elencati i soggetti coinvolti nel processo di pagamento:

a. Soggetto Pagatore: rappresenta il soggetto (Persona Fisica o
   Giuridica) debitore di somme di denaro nei confronti della
   Pubblica Amministrazione. L’Ente Creditore è responsabile della
   corretta identificazione del Soggetto Pagatore;

b. Soggetto Versante: rappresenta il soggetto delegato che effettua per
   conto del soggetto pagatore il versamento delle somme dovute. Il
   Soggetto Versante è identificato dalla componente WISP del Nodo
   (per i pagamenti disposti presso l’EC) o dal PSP, se necessario,
   negli altri casi;

c. Ente Beneficiario: rappresenta la Pubblica Amministrazione
   creditrice, a qualsiasi titolo, di somme dovute dal
   *Soggetto Pagatore*;

d. Istituto Attestante: rappresenta il Prestatore di Servizi di
   Pagamento che effettua il pagamento richiesto e ne attesta la
   regolarità.

Formato dei dati
----------------
.. _Formato dei dati:

Le colonne *Liv,* *Genere,* *Occ*, *Len* e *UNIFI* assumono i seguenti
significati:

+-----------------+-----------------+-----------------+-----------------+
| **colonna**     | *Liv*           | indica il       |                 |
|                 |                 | livello di      |                 |
|                 |                 | indentazione    |                 |
|                 |                 | del dato al     |                 |
|                 |                 | fine di rendere |                 |
|                 |                 | evidenti le     |                 |
|                 |                 | strutture che   |                 |
|                 |                 | contengono      |                 |
|                 |                 | ulteriori       |                 |
|                 |                 | informazioni    |                 |
|                 |                 | (colonna Genere |                 |
|                 |                 | uguale ad s):   |                 |
|                 |                 | esempio, le     |                 |
|                 |                 | strutture di    |                 |
|                 |                 | livello 1 sono  |                 |
|                 |                 | formate da      |                 |
|                 |                 | tutti i dati di |                 |
|                 |                 | livello         |                 |
|                 |                 | superiore ad 1, |                 |
|                 |                 | quelle di       |                 |
|                 |                 | livello 2 sono  |                 |
|                 |                 | formate da      |                 |
|                 |                 | tutti i dati di |                 |
|                 |                 | livello         |                 |
|                 |                 | superiore a 2,  |                 |
|                 |                 | e così via.     |                 |
+-----------------+-----------------+-----------------+-----------------+
| **colonna**     | *Genere*        | che può         |                 |
|                 |                 | assumere i      |                 |
|                 |                 | seguenti valori |                 |
+-----------------+-----------------+-----------------+-----------------+
|                 |                 | s               | struttura che   |
|                 |                 |                 | può contenere   |
|                 |                 |                 | altre strutture |
|                 |                 |                 | o dati,         |
+-----------------+-----------------+-----------------+-----------------+
|                 |                 | an              | dato            |
|                 |                 |                 | alfanumerico,   |
+-----------------+-----------------+-----------------+-----------------+
|                 |                 | n               | dato numerico.  |
+-----------------+-----------------+-----------------+-----------------+
| **colonna**     | *Occ*           | indica le       |                 |
|                 |                 | “occorrenze”    |                 |
|                 |                 | del dato nel    |                 |
|                 |                 | formato         |                 |
|                 |                 | **min..max**.   |                 |
+-----------------+-----------------+-----------------+-----------------+
|                 |                 | L’eventuale     |                 |
|                 |                 | obbligatorietà  |                 |
|                 |                 | di tali         |                 |
|                 |                 | informazioni è  |                 |
|                 |                 | legata alla     |                 |
|                 |                 | natura          |                 |
|                 |                 | dell’ente, alle |                 |
|                 |                 | specifiche      |                 |
|                 |                 | esigenze e      |                 |
|                 |                 | caratteristiche |                 |
|                 |                 | dell’operazione |                 |
|                 |                 | ovvero ad       |                 |
|                 |                 | accordi tra     |                 |
|                 |                 | utilizzatore e  |                 |
|                 |                 | prestatore di   |                 |
|                 |                 | servizi di      |                 |
|                 |                 | pagamento.      |                 |
+-----------------+-----------------+-----------------+-----------------+
| **colonna**     | *Len*           | indica la       |                 |
|                 |                 | lunghezza       |                 |
|                 |                 | massima del     |                 |
|                 |                 | dato nel        |                 |
|                 |                 | formato         |                 |
|                 |                 | *min..max*; nel |                 |
|                 |                 | caso si tratti  |                 |
|                 |                 | di una          |                 |
|                 |                 | lunghezza fissa |                 |
|                 |                 | comparirà solo  |                 |
|                 |                 | il dato *len*,  |                 |
|                 |                 | nel caso di     |                 |
|                 |                 | lunghezze fisse |                 |
|                 |                 | in alternativa  |                 |
|                 |                 | la notazione    |                 |
|                 |                 | sarà *len1*  |  |                 |
|                 |                 | *len2*.         |                 |
+-----------------+-----------------+-----------------+-----------------+
| **colonna**     | *UNIFI*         | indica la       |                 |
|                 |                 | corrispondenza  |                 |
|                 |                 | corrispondenza  |                 |
|                 |                 | del Dato con    |                 |
|                 |                 | gli schemi ISO  |                 |
|                 |                 | 20022 -         |                 |
|                 |                 | UNIversal       |                 |
|                 |                 | Financial       |                 |
|                 |                 | Industry        |                 |
|                 |                 | message         |                 |
|                 |                 | (UNIFI).        |                 |
+-----------------+-----------------+-----------------+-----------------+

Richiesta Pagamento Telematico (RPT)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Richiesta Pagamento Telematico (RPT):

È il documento informatico predisposto da un Ente Creditore o da un suo
intermediario per consentire all'utilizzatore finale di richiedere, al
prestatore di servizi di pagamento dallo stesso prescelto, un pagamento
a favore dello stesso Ente Creditore.

**Tabella** **1 - Elementi componenti la RPT**

+---------+---------+----------+---------+---------+---------+---------+
| **Dato**| **Liv** |**Genere**| **Occ** | **Len** |**UNIFI**|**Conte**|
|         |         |          |         |         |         |**nuto** |
+=========+=========+==========+=========+=========+=========+=========+
| versione| 1       | an       | 1..1    | 1..16   | Version | Version |
| Oggetto |         |          |         |         | Number  | e       |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | identif |
|         |         |          |         |         |         | ica     |
|         |         |          |         |         |         | l’ogget |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | scambia |
|         |         |          |         |         |         | to.     |
+---------+---------+----------+---------+---------+---------+---------+
| Dominio | 1       | s        | 1..1    |         | Initiat | Aggrega |
|         |         |          |         |         | ing     | to      |
|         |         |          |         |         | Party   | “domini |
|         |         |          |         |         |         | o”      |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | riporta |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | informa |
|         |         |          |         |         |         | zioni   |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | consent |
|         |         |          |         |         |         | ono     |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | individ |
|         |         |          |         |         |         | uare    |
|         |         |          |         |         |         | univoca |
|         |         |          |         |         |         | mente   |
|         |         |          |         |         |         | l’ambit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | applica |
|         |         |          |         |         |         | zione   |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | richies |
|         |         |          |         |         |         | ta.     |
+---------+---------+----------+---------+---------+---------+---------+
| identifi| 2       | an       | 1..1    | 1..35   | Tax     | Campo   |
| cativoDo|         |          |         |         | Identif | alfanum |
| minio   |         |          |         |         | ication | erico   |
|         |         |          |         |         | Number  | contene |
|         |         |          |         |         |         | nte     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | codice  |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | struttu |
|         |         |          |         |         |         | ra      |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | invia   |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | richies |
|         |         |          |         |         |         | ta      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to.     |
+---------+---------+----------+---------+---------+---------+---------+
| identifi| 2       | an       | 0..1    | 1..35   | Name    | Identif |
| cativo  |         |          |         |         |         | ica     |
| Stazione|         |          |         |         |         | la      |
| Richie  |         |          |         |         |         | stazion |
| dente   |         |          |         |         |         | e       |
|         |         |          |         |         |         | richied |
|         |         |          |         |         |         | ente    |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | una     |
|         |         |          |         |         |         | codific |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | predefi |
|         |         |          |         |         |         | nita    |
|         |         |          |         |         |         | dal     |
|         |         |          |         |         |         | mittent |
|         |         |          |         |         |         | e,      |
|         |         |          |         |         |         | che ne  |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | dare    |
|         |         |          |         |         |         | evidenz |
|         |         |          |         |         |         | a,      |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | richies |
|         |         |          |         |         |         | ta.     |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Il Nodo |
|         |         |          |         |         |         | dei     |
|         |         |          |         |         |         | Pagamen |
|         |         |          |         |         |         | ti-SPC  |
|         |         |          |         |         |         | non     |
|         |         |          |         |         |         | effettu |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | verific |
|         |         |          |         |         |         | he      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | congrue |
|         |         |          |         |         |         | nza     |
|         |         |          |         |         |         | su tale |
|         |         |          |         |         |         | dato.   |
+---------+---------+----------+---------+---------+---------+---------+
| identifi| 1       | an       | 1..1    | 1..35   | Message | Identif |
| cativo  |         |          |         |         | Identif | icativo |
| Messag  |         |          |         |         | ication | legato  |
| gioRi   |         |          |         |         |         | alla    |
| chiesta |         |          |         |         |         | trasmis |
|         |         |          |         |         |         | sione   |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | richies |
|         |         |          |         |         |         | ta      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to.     |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | univoco |
|         |         |          |         |         |         | nell’am |
|         |         |          |         |         |         | bito    |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | stessa  |
|         |         |          |         |         |         | data    |
|         |         |          |         |         |         | riferit |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | all’ele |
|         |         |          |         |         |         | mento   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | dataOra |
|         |         |          |         |         |         | Messagg |
|         |         |          |         |         |         | ioRichi |
|         |         |          |         |         |         | esta.   |
+---------+---------+----------+---------+---------+---------+---------+
| data    | 1       | an       | 1..1    | 19      | Creatio | Indica  |
| OraMes  |         |          |         |         | n       | la data |
| saggioRi|         |          |         |         | Date    | e l’ora |
| chiesta |         |          |         |         | Time    | di      |
|         |         |          |         |         |         | generaz |
|         |         |          |         |         |         | ione    |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | messagg |
|         |         |          |         |         |         | io      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | richies |
|         |         |          |         |         |         | ta      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | formato |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 8601    |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | [YYYY   |
|         |         |          |         |         |         | ]-[MM]- |
|         |         |          |         |         |         | [DD]T[h |
|         |         |          |         |         |         | h]:[mm] |
|         |         |          |         |         |         | :[ss]   |
+---------+---------+----------+---------+---------+---------+---------+
| aut     | 1       | an       | 1..1    | 4       | Proprie |Contien  |
| enticaz |         |          |         |         | tary    |e        |
| ioneSog |         |          |         |         | Code    |la       |
| getto   |         |          |         |         |         |modalit  |
|         |         |          |         |         |         |à        |
|         |         |          |         |         |         |di       |
|         |         |          |         |         |         |identif  |
|         |         |          |         |         |         |icazion  |
|         |         |          |         |         |         |e        |
|         |         |          |         |         |         |applica  |
|         |         |          |         |         |         |ta       |
|         |         |          |         |         |         |al       |
|         |         |          |         |         |         |soggett  |
|         |         |          |         |         |         |o        |
|         |         |          |         |         |         |che      |
|         |         |          |         |         |         |deve     |
|         |         |          |         |         |         |essere   |
|         |         |          |         |         |         |addebit  |
|         |         |          |         |         |         |ato      |
|         |         |          |         |         |         |per il   |
|         |         |          |         |         |         |pagamen  |
|         |         |          |         |         |         |to       |
|         |         |          |         |         |         |- ‘CNS’= |
|         |         |          |         |         |         |CIE/CNS  |
|         |         |          |         |         |         |- ‘USR’= |
|         |         |          |         |         |         |Userid   |
|         |         |          |         |         |         |e        |
|         |         |          |         |         |         |passwor  |
|         |         |          |         |         |         |d        |
|         |         |          |         |         |         |- ‘OTH’= |
|         |         |          |         |         |         |Altro    |
|         |         |          |         |         |         |- ‘N/A’= |
|         |         |          |         |         |         |Non      |
|         |         |          |         |         |         |applica  |
|         |         |          |         |         |         |bile     |
+---------+---------+----------+---------+---------+---------+---------+
| Sog     | 1       | s        | 0..1    |         | Debtor  | Aggrega |
| gettoVe |         |          |         |         |         | zione   |
| rsante  |         |          |         |         |         | “versan |
|         |         |          |         |         |         | te”     |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | riporta |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | informa |
|         |         |          |         |         |         | zioni   |
|         |         |          |         |         |         | concern |
|         |         |          |         |         |         | enti    |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | effettu |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | per     |
|         |         |          |         |         |         | conto   |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | Pagator |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| ide     | 2       | s        | 1..1    |         |         | Aggrega |
| ntifica |         |          |         |         |         | zione   |
| tivoUni |         |          |         |         |         | che     |
| vocoVer |         |          |         |         |         | riporta |
| sante   |         |          |         |         |         | le      |
|         |         |          |         |         |         | informa |
|         |         |          |         |         |         | zioni   |
|         |         |          |         |         |         | concern |
|         |         |          |         |         |         | enti    |
|         |         |          |         |         |         | l’ident |
|         |         |          |         |         |         | ificazi |
|         |         |          |         |         |         | one     |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| tip     | 3       | an       | 1..1    | 1       | Proprie | Campo   |
| oIdenti |         |          |         |         | tary    | alfanum |
| ficativ |         |          |         |         | Code    | erico   |
| oUnivoc |         |          |         |         |         | che     |
| o       |         |          |         |         |         | indica  |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | natura  |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e;      |
|         |         |          |         |         |         | può     |
|         |         |          |         |         |         | assumer |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | seguent |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | valori: |
|         |         |          |         |         |         | -    ‘F |
|         |         |          |         |         |         | ’  \ =  |
|         |         |          |         |         |         | Persona |
|         |         |          |         |         |         | fisica  |
|         |         |          |         |         |         | -    ‘G |
|         |         |          |         |         |         | ’  \ =  |
|         |         |          |         |         |         | Persona |
|         |         |          |         |         |         | Giuridi |
|         |         |          |         |         |         | ca.     |
+---------+---------+----------+---------+---------+---------+---------+
| cod     | 3       | an       | 1..1    | 1..35   | Tax     | Campo   |
| iceIden |         |          |         |         | Identif | alfanum |
| tificat |         |          |         |         | ication | erico   |
| ivoUniv |         |          |         |         | Number  | che può |
| oco     |         |          |         |         |         | contene |
|         |         |          |         |         |         | re      |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | codice  |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | o, in   |
|         |         |          |         |         |         | alterna |
|         |         |          |         |         |         | tiva,   |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | partita |
|         |         |          |         |         |         | IVA del |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Nei     |
|         |         |          |         |         |         | casi    |
|         |         |          |         |         |         | applica |
|         |         |          |         |         |         | bili,   |
|         |         |          |         |         |         | quando  |
|         |         |          |         |         |         | non è   |
|         |         |          |         |         |         | possibi |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | identif |
|         |         |          |         |         |         | icare   |
|         |         |          |         |         |         | fiscalm |
|         |         |          |         |         |         | ente    |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o,      |
|         |         |          |         |         |         | può     |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | utilizz |
|         |         |          |         |         |         | ato     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | valore  |
|         |         |          |         |         |         | “\   AN |
|         |         |          |         |         |         | ONIMO   |
|         |         |          |         |         |         | \ ”     |
+---------+---------+----------+---------+---------+---------+---------+
| ana     | 2       | an       | 1..1    | 1..70   | Name    | Indica  |
| grafica |         |          |         |         |         | il      |
| Versant |         |          |         |         |         | nominat |
| e       |         |          |         |         |         | ivo     |
|         |         |          |         |         |         | o la    |
|         |         |          |         |         |         | ragione |
|         |         |          |         |         |         | sociale |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| ind     | 3       | an       | 0..1    | 1..70   | StreetN | Indica  |
| irizzoV |         |          |         |         | ame     | l’indir |
| ersante |         |          |         |         |         | izzo    |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| civ     | 3       | an       | 0..1    | 1..16   | Buildin | Indica  |
| icoVers |         |          |         |         | g       | il      |
| ante    |         |          |         |         | Number  | numero  |
|         |         |          |         |         |         | civico  |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| cap     | 3       | an       | 0..1    | 1..16   | Postal  | Indica  |
| Versant |         |          |         |         | Code    | il CAP  |
| e       |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| loc     | 3       | an       | 0..1    | 1..35   | Town    | Indica  |
| alitaVe |         |          |         |         | Name    | la      |
| rsante  |         |          |         |         |         | localit |
|         |         |          |         |         |         | à       |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| pro     | 3       | an       | 0..1    | 1..35   | Country | Indica  |
| vinciaV |         |          |         |         | SubDivi | la      |
| ersante |         |          |         |         | sion    | provinc |
|         |         |          |         |         |         | ia      |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| naz     | 3       | an       | 0..1    | 2       | Country | Indica  |
| ioneVer |         |          |         |         |         | il      |
| sante   |         |          |         |         |         | codice  |
|         |         |          |         |         |         | nazione |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 3166.   |
+---------+---------+----------+---------+---------+---------+---------+
| e-m     | 3       | an       | 0..1    | 1..256  | Remitta | Indiriz |
| ailVers |         |          |         |         | nce     | zo      |
| ante    |         |          |         |         | Locatio | di      |
|         |         |          |         |         | n       | posta   |
|         |         |          |         |         | Electro | elettro |
|         |         |          |         |         | nic     | nica    |
|         |         |          |         |         | Address | del     |
|         |         |          |         |         |         | versant |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| sog     | 1       | s        | 1..1    |         | Ultimat | Aggrega |
| gettoPa |         |          |         |         | e       | zione   |
| gatore  |         |          |         |         | Debtor  | “sogget |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |  |      | pagator |
|         |         |          |         |         |         | e”      |
|         |         |          |         |         | Debtor  | che     |
|         |         |          |         |         | [1]_    | rappres |
|         |         |          |         |         |         | enta    |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | (Person |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | Fisica  |
|         |         |          |         |         |         | 1..1    |
|         |         |          |         |         |         | Giuridi |
|         |         |          |         |         |         | ca)     |
|         |         |          |         |         |         | debitor |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | somme   |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | denaro  |
|         |         |          |         |         |         | nei     |
|         |         |          |         |         |         | confron |
|         |         |          |         |         |         | ti      |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | Pubblic |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | Amminis |
|         |         |          |         |         |         | trazion |
|         |         |          |         |         |         | e       |
+---------+---------+----------+---------+---------+---------+---------+
| ide     | 2       | s        | 1..1    |         |         | Aggrega |
| ntifica |         |          |         |         |         | zione   |
| tivoUni |         |          |         |         |         | che     |
| vocoPag |         |          |         |         |         | riporta |
| atore   |         |          |         |         |         | le      |
|         |         |          |         |         |         | informa |
|         |         |          |         |         |         | zioni   |
|         |         |          |         |         |         | concern |
|         |         |          |         |         |         | enti    |
|         |         |          |         |         |         | l’ident |
|         |         |          |         |         |         | ificazi |
|         |         |          |         |         |         | one     |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| tip     | 3       | an       | 1..1    | 1       | Proprie | Campo   |
| oIdenti |         |          |         |         | tary    | alfanum |
| ficativ |         |          |         |         | Code    | erico   |
| oUnivoc |         |          |         |         |         | che     |
| o       |         |          |         |         |         | indica  |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | natura  |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e,      |
|         |         |          |         |         |         | può     |
|         |         |          |         |         |         | assumer |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | seguent |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | valori: |
|         |         |          |         |         |         | -    ‘F |
|         |         |          |         |         |         | ’  \ =  |
|         |         |          |         |         |         | Persona |
|         |         |          |         |         |         | fisica  |
|         |         |          |         |         |         | -    ‘G |
|         |         |          |         |         |         | ’  \ =  |
|         |         |          |         |         |         | Persona |
|         |         |          |         |         |         | Giuridi |
|         |         |          |         |         |         | ca.     |
+---------+---------+----------+---------+---------+---------+---------+
| cod     | 3       | an       | 1..1    | 1..35   | Tax     | Campo   |
| iceIden |         |          |         |         | Identif | alfanum |
| tificat |         |          |         |         | ication | erico   |
| ivoUniv |         |          |         |         | Number  | che può |
| oco     |         |          |         |         |         | contene |
|         |         |          |         |         |         | re      |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | codice  |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | o, in   |
|         |         |          |         |         |         | alterna |
|         |         |          |         |         |         | tiva,   |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | partita |
|         |         |          |         |         |         | IVA del |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Nei     |
|         |         |          |         |         |         | casi    |
|         |         |          |         |         |         | applica |
|         |         |          |         |         |         | bili,   |
|         |         |          |         |         |         | quando  |
|         |         |          |         |         |         | non è   |
|         |         |          |         |         |         | possibi |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | identif |
|         |         |          |         |         |         | icare   |
|         |         |          |         |         |         | fiscalm |
|         |         |          |         |         |         | ente    |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | oggetto |
|         |         |          |         |         |         | ,       |
|         |         |          |         |         |         | può     |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | utilizz |
|         |         |          |         |         |         | ato     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | valore  |
|         |         |          |         |         |         | “\   AN |
|         |         |          |         |         |         | ONIMO   |
|         |         |          |         |         |         | \ ”     |
+---------+---------+----------+---------+---------+---------+---------+
| ana     | 2       | an       | 1..1    | 1..70   | Name    | Indica  |
| grafica |         |          |         |         |         | il      |
| Pagator |         |          |         |         |         | nominat |
| e       |         |          |         |         |         | ivo     |
|         |         |          |         |         |         | o la    |
|         |         |          |         |         |         | ragione |
|         |         |          |         |         |         | sociale |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e       |
+---------+---------+----------+---------+---------+---------+---------+
| ind     | 2       | an       | 0..1    | 1..70   | Street  | Indica  |
| irizzoP |         |          |         |         | Name    | l’indir |
| agatore |         |          |         |         |         | izzo    |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e       |
+---------+---------+----------+---------+---------+---------+---------+
| civ     | 2       | an       | 0..1    | 1..16   | Buildin | Indica  |
| icoPaga |         |          |         |         | g       | il      |
| tore    |         |          |         |         | Number  | numero  |
|         |         |          |         |         |         | civico  |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| cap     | 2       | an       | 0..1    | 1..16   | Postal  | Indica  |
| Pagator |         |          |         |         | Code    | il CAP  |
| e       |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e       |
+---------+---------+----------+---------+---------+---------+---------+
| loc     | 2       | an       | 0..1    | 1..35   | Town    | Indica  |
| alitaPa |         |          |         |         | Name    | la      |
| gatore  |         |          |         |         |         | localit |
|         |         |          |         |         |         | à       |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e.      |
+---------+---------+----------+---------+---------+---------+---------+
| pro     | 2       | an       | 0..1    | 1..35   | Country | Indica  |
| vinciaP |         |          |         |         | SubDivi | la      |
| agatore |         |          |         |         | sion    | provinc |
|         |         |          |         |         |         | ia      |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e       |
+---------+---------+----------+---------+---------+---------+---------+
| naz     | 2       | an       | 0..1    | 2       | Country | Indica  |
| ionePag |         |          |         |         |         | il      |
| atore   |         |          |         |         |         | codice  |
|         |         |          |         |         |         | nazione |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 3166.   |
+---------+---------+----------+---------+---------+---------+---------+
| e-m     | 2       | an       | 0..1    | 1..256  | Remitta | Indiriz |
| ailPaga |         |          |         |         | nce     | zo      |
| tore    |         |          |         |         | Locatio | di      |
|         |         |          |         |         | n       | posta   |
|         |         |          |         |         | Electro | elettro |
|         |         |          |         |         | nic     | nica    |
|         |         |          |         |         | Address | del     |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e       |
+---------+---------+----------+---------+---------+---------+---------+
| ent     | 1       | s        | 1..1    |         | Credito | Aggrega |
| eBenefi |         |          |         |         | r       | zione   |
| ciario  |         |          |         |         |         | “ente   |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario”  |
|         |         |          |         |         |         | credito |
|         |         |          |         |         |         | re      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | somme   |
|         |         |          |         |         |         | nei     |
|         |         |          |         |         |         | confron |
|         |         |          |         |         |         | ti      |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e;      |
|         |         |          |         |         |         | è       |
|         |         |          |         |         |         | costitu |
|         |         |          |         |         |         | ita     |
|         |         |          |         |         |         | dai     |
|         |         |          |         |         |         | seguent |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | element |
|         |         |          |         |         |         | i:      |
+---------+---------+----------+---------+---------+---------+---------+
| ide     | 2       | s        | 1..1    |         |         | Aggrega |
| ntifica |         |          |         |         |         | zione   |
| tivoUni |         |          |         |         |         | che     |
| vocoBen |         |          |         |         |         | riporta |
| eficiar |         |          |         |         |         | le      |
| io      |         |          |         |         |         | informa |
|         |         |          |         |         |         | zioni   |
|         |         |          |         |         |         | concern |
|         |         |          |         |         |         | enti    |
|         |         |          |         |         |         | l’ident |
|         |         |          |         |         |         | ificazi |
|         |         |          |         |         |         | one     |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario.  |
+---------+---------+----------+---------+---------+---------+---------+
| tip     | 3       | an       | 1..1    | 1       | Proprie | Campo   |
| oIdenti |         |          |         |         | tary    | alfanum |
| ficativ |         |          |         |         | Code    | erico   |
| oUnivoc |         |          |         |         |         | che     |
| o       |         |          |         |         |         | indica  |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | natura  |
|         |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario;  |
|         |         |          |         |         |         | se      |
|         |         |          |         |         |         | present |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | assumer |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | valore  |
|         |         |          |         |         |         | **G**,  |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Identif |
|         |         |          |         |         |         | icativo |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | Persona |
|         |         |          |         |         |         | Giuridi |
|         |         |          |         |         |         | ca.     |
+---------+---------+----------+---------+---------+---------+---------+
| cod     | 3       | an       | 1..1    | 1..35   | Tax     | Campo   |
| iceIden |         |          |         |         | Identif | alfanum |
| tificat |         |          |         |         | ication | erico   |
| ivoUniv |         |          |         |         | Number  | contene |
| oco     |         |          |         |         |         | nte     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | codice  |
|         |         |          |         |         |         | fiscale |
|         |         |          |         |         |         | dell’En |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | tario   |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to.     |
+---------+---------+----------+---------+---------+---------+---------+
| den     | 2       | an       | 1..1    | 1..70   | Name    | Contien |
| ominazi |         |          |         |         |         | e       |
| oneBene |         |          |         |         |         | la      |
| ficiari |         |          |         |         |         | denomin |
| o       |         |          |         |         |         | azione  |
|         |         |          |         |         |         | dell’En |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re      |
+---------+---------+----------+---------+---------+---------+---------+
| cod     | 2       | an       | 0..1    | 1..35   |         | Indica  |
| iceUnit |         |          |         |         |         | il      |
| OperBen |         |          |         |         |         | codice  |
| eficiar |         |          |         |         |         | dell’un |
| io      |         |          |         |         |         | ità     |
|         |         |          |         |         |         | operati |
|         |         |          |         |         |         | va      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | taria   |
+---------+---------+----------+---------+---------+---------+---------+
| den     | 2       | an       | 0..1    | 1..70   |         | Contien |
| omUnitO |         |          |         |         |         | e       |
| perBene |         |          |         |         |         | la      |
| ficiari |         |          |         |         |         | denomin |
| o       |         |          |         |         |         | azione  |
|         |         |          |         |         |         | dell’un |
|         |         |          |         |         |         | ità     |
|         |         |          |         |         |         | operati |
|         |         |          |         |         |         | va      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | taria.  |
+---------+---------+----------+---------+---------+---------+---------+
| ind     | 2       | an       | 0..1    | 1..70   | Street  | Indica  |
| irizzoB |         |          |         |         | Name    | l’indir |
| enefici |         |          |         |         |         | izzo    |
| ario    |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario.  |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Può     |
|         |         |          |         |         |         | coincid |
|         |         |          |         |         |         | ere     |
|         |         |          |         |         |         | con     |
|         |         |          |         |         |         | quello  |
|         |         |          |         |         |         | dell’un |
|         |         |          |         |         |         | ità     |
|         |         |          |         |         |         | operati |
|         |         |          |         |         |         | va      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | taria   |
+---------+---------+----------+---------+---------+---------+---------+
| civ     | 2       | an       | 0..1    | 1..16   | Buildin | Indica  |
| icoBene |         |          |         |         | g       | il      |
| ficiari |         |          |         |         | Number  | numero  |
| o       |         |          |         |         |         | civico  |
|         |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario.  |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Può     |
|         |         |          |         |         |         | coincid |
|         |         |          |         |         |         | ere     |
|         |         |          |         |         |         | con     |
|         |         |          |         |         |         | quello  |
|         |         |          |         |         |         | dell’un |
|         |         |          |         |         |         | ità     |
|         |         |          |         |         |         | operati |
|         |         |          |         |         |         | va      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | taria.  |
+---------+---------+----------+---------+---------+---------+---------+
| cap     | 2       | an       | 0..1    | 1..16   | Postal  | Indica  |
| Benefic |         |          |         |         | Code    | il CAP  |
| iario   |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario.  |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Può     |
|         |         |          |         |         |         | coincid |
|         |         |          |         |         |         | ere     |
|         |         |          |         |         |         | con     |
|         |         |          |         |         |         | quello  |
|         |         |          |         |         |         | dell’un |
|         |         |          |         |         |         | ità     |
|         |         |          |         |         |         | operati |
|         |         |          |         |         |         | va      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | taria   |
+---------+---------+----------+---------+---------+---------+---------+
| loc     | 2       | an       | 0..1    | 1..35   | Town    | Indica  |
| alitaBe |         |          |         |         | Name    | la      |
| neficia |         |          |         |         |         | localit |
| rio     |         |          |         |         |         | à       |
|         |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario.  |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Può     |
|         |         |          |         |         |         | coincid |
|         |         |          |         |         |         | ere     |
|         |         |          |         |         |         | con     |
|         |         |          |         |         |         | quello  |
|         |         |          |         |         |         | dell’un |
|         |         |          |         |         |         | ità     |
|         |         |          |         |         |         | operati |
|         |         |          |         |         |         | va      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | taria   |
+---------+---------+----------+---------+---------+---------+---------+
| pro     | 2       | an       | 0..1    | 1..35   | Country | Indica  |
| vinciaB |         |          |         |         | SubDivi | la      |
| enefici |         |          |         |         | sion    | provinc |
| ario    |         |          |         |         |         | ia      |
|         |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario.  |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Può     |
|         |         |          |         |         |         | coincid |
|         |         |          |         |         |         | ere     |
|         |         |          |         |         |         | con     |
|         |         |          |         |         |         | quello  |
|         |         |          |         |         |         | dell’un |
|         |         |          |         |         |         | ità     |
|         |         |          |         |         |         | operati |
|         |         |          |         |         |         | va      |
|         |         |          |         |         |         | destina |
|         |         |          |         |         |         | taria   |
+---------+---------+----------+---------+---------+---------+---------+
| naz     | 2       | an       | 0..1    | 2       | Country | Indica  |
| ioneBen |         |          |         |         |         | il      |
| eficiar |         |          |         |         |         | codice  |
| io      |         |          |         |         |         | nazione |
|         |         |          |         |         |         | dell’en |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | benefic |
|         |         |          |         |         |         | iario   |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 3166.   |
+---------+---------+----------+---------+---------+---------+---------+
| dat     | 1       | s        | 1..1    |         |         | Aggrega |
| iVersam |         |          |         |         |         | zione   |
| ento    |         |          |         |         |         | “dati   |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | Versame |
|         |         |          |         |         |         | nto”    |
|         |         |          |         |         |         | costitu |
|         |         |          |         |         |         | ita     |
|         |         |          |         |         |         | dai     |
|         |         |          |         |         |         | seguent |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | element |
|         |         |          |         |         |         | i:      |
+---------+---------+----------+---------+---------+---------+---------+
| dat     | 2       | an       | 1..1    | 10      | Request | Indica  |
| aEsecuz |         |          |         |         | ed      | la data |
| ionePag |         |          |         |         | Executi | in cui  |
| amento  |         |          |         |         | on      | si      |
|         |         |          |         |         | Date    | richied |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | venga   |
|         |         |          |         |         |         | effettu |
|         |         |          |         |         |         | ato     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | formato |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 8601    |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | [YYYY   |
|         |         |          |         |         |         | ]-[MM]- |
|         |         |          |         |         |         | [DD].   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Non     |
|         |         |          |         |         |         | può     |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | anterio |
|         |         |          |         |         |         | re      |
|         |         |          |         |         |         | alla    |
|         |         |          |         |         |         | data di |
|         |         |          |         |         |         | invio   |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | RPT e   |
|         |         |          |         |         |         | non può |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | superio |
|         |         |          |         |         |         | re      |
|         |         |          |         |         |         | di 30   |
|         |         |          |         |         |         | giorni  |
|         |         |          |         |         |         | rispett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | alla    |
|         |         |          |         |         |         | stessa  |
|         |         |          |         |         |         | data.   |
+---------+---------+----------+---------+---------+---------+---------+
| imp     | 2       | an       | 1..1    | 3..12   | Amount  | Campo   |
| ortoTot |         |          |         |         |         | numeric |
| aleDaVe |         |          |         |         |         | o       |
| rsare   |         |          |         |         |         | (due    |
|         |         |          |         |         |         | cifre   |
|         |         |          |         |         |         | per la  |
|         |         |          |         |         |         | parte   |
|         |         |          |         |         |         | decimal |
|         |         |          |         |         |         | e,      |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | separat |
|         |         |          |         |         |         | ore     |
|         |         |          |         |         |         | dei     |
|         |         |          |         |         |         | centesi |
|         |         |          |         |         |         | mi      |
|         |         |          |         |         |         | è il    |
|         |         |          |         |         |         | punto   |
|         |         |          |         |         |         | “.”),   |
|         |         |          |         |         |         | indican |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | l’impor |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | relativ |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | alla    |
|         |         |          |         |         |         | somma   |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | versare |
|         |         |          |         |         |         | .       |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | uguale  |
|         |         |          |         |         |         | alla    |
|         |         |          |         |         |         | somma   |
|         |         |          |         |         |         | delle   |
|         |         |          |         |         |         | varie   |
|         |         |          |         |         |         | occorre |
|         |         |          |         |         |         | nze     |
|         |         |          |         |         |         | (da 1 a |
|         |         |          |         |         |         | 5) del  |
|         |         |          |         |         |         | dato    |
|         |         |          |         |         |         | importo |
|         |         |          |         |         |         | Singolo |
|         |         |          |         |         |         | Versame |
|         |         |          |         |         |         | nto     |
|         |         |          |         |         |         | present |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | nella   |
|         |         |          |         |         |         | struttu |
|         |         |          |         |         |         | ra      |
|         |         |          |         |         |         | DatiSin |
|         |         |          |         |         |         | goloVer |
|         |         |          |         |         |         | samento |
|         |         |          |         |         |         | .       |
+---------+---------+----------+---------+---------+---------+---------+
| tip     | 2       | an       | 1..1    | 4       | Proprie | Forma   |
| oVersam |         |          |         |         | tary    | tecnica |
| ento    |         |          |         |         | Code    | di      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | attrave |
|         |         |          |         |         |         | rso     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | quale   |
|         |         |          |         |         |         | viene   |
|         |         |          |         |         |         | effettu |
|         |         |          |         |         |         | ata     |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | provvis |
|         |         |          |         |         |         | ta      |
|         |         |          |         |         |         | presso  |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | PSP.    |
|         |         |          |         |         |         | Può     |
|         |         |          |         |         |         | assumer |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | seguent |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | valori: |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **BBT** |
|         |         |          |         |         |         | Bonific |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | Bancari |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | Tesorer |
|         |         |          |         |         |         | ia      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **BP**  |
|         |         |          |         |         |         | Bollett |
|         |         |          |         |         |         | ino     |
|         |         |          |         |         |         | Postale |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **AD**  |
|         |         |          |         |         |         | Addebit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | diretto |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **CP**  |
|         |         |          |         |         |         | Carta   |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **PO**  |
|         |         |          |         |         |         | Pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | attivat |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | presso  |
|         |         |          |         |         |         | PSP     |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **OBEP**|
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | On-line |
|         |         |          |         |         |         | banking |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | e-payme |
|         |         |          |         |         |         | nt      |
+---------+---------+----------+---------+---------+---------+---------+
| ide     | 2       | an       | 1..1    | 1..35   | Credito | Riferim |
| ntifica |         |          |         |         | r       | ento    |
| tivoUni |         |          |         |         | Referen | univoco |
| vocoVer |         |          |         |         | ce      | assegna |
| samento |         |          |         |         |         | to      |
|         |         |          |         |         |         | al      |
|         |         |          |         |         |         | versame |
|         |         |          |         |         |         | nto     |
|         |         |          |         |         |         | dall’En |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re,     |
|         |         |          |         |         |         | utilizz |
|         |         |          |         |         |         | ato     |
|         |         |          |         |         |         | ai fini |
|         |         |          |         |         |         | specifi |
|         |         |          |         |         |         | ci      |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | rendico |
|         |         |          |         |         |         | ntazion |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | riconci |
|         |         |          |         |         |         | liazion |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | eseguit |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | sui     |
|         |         |          |         |         |         | conti   |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | tesorer |
|         |         |          |         |         |         | ia.     |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Si      |
|         |         |          |         |         |         | faccia  |
|         |         |          |         |         |         | riferim |
|         |         |          |         |         |         | ento    |
|         |         |          |         |         |         | al      |
|         |         |          |         |         |         | capitol |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | 7.1     |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | present |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | Sezione |
|         |         |          |         |         |         | .       |
+---------+---------+----------+---------+---------+---------+---------+
| Cod     | 2       | an       | 1..1    | 1..35   | Message | Codice  |
| iceCont |         |          |         |         | Identif | univoco |
| estoPag |         |          |         |         | ication | necessa |
| amento  |         |          |         |         |         | rio     |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | definir |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | contest |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | nel     |
|         |         |          |         |         |         | quale   |
|         |         |          |         |         |         | viene   |
|         |         |          |         |         |         | effettu |
|         |         |          |         |         |         | ato     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | versame |
|         |         |          |         |         |         | nto.    |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Si      |
|         |         |          |         |         |         | faccia  |
|         |         |          |         |         |         | riferim |
|         |         |          |         |         |         | ento    |
|         |         |          |         |         |         | al §    |
|         |         |          |         |         |         | 7.3     |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | present |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | Sezione |
|         |         |          |         |         |         | .       |
+---------+---------+----------+---------+---------+---------+---------+
| iba     | 2       | an       | 0..1    | 1..35   | Debtor. | Identif |
| nAddebi |         |          |         |         | Account | ica     |
| to      |         |          |         |         | IBAN    | l’Inter |
|         |         |          |         |         |         | nationa |
|         |         |          |         |         |         | l       |
|         |         |          |         |         |         | Bank    |
|         |         |          |         |         |         | Account |
|         |         |          |         |         |         | Number  |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | conto   |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | addebit |
|         |         |          |         |         |         | are,    |
|         |         |          |         |         |         | definit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 13616.  |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Il      |
|         |         |          |         |         |         | dato è  |
|         |         |          |         |         |         | obbliga |
|         |         |          |         |         |         | torio   |
|         |         |          |         |         |         | qualora |
|         |         |          |         |         |         | l’infor |
|         |         |          |         |         |         | mazione |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         |tipoP    |
|         |         |          |         |         |         | agament |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | assuma  |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | valore  |
|         |         |          |         |         |         | “AD”.   |
+---------+---------+----------+---------+---------+---------+---------+
| bic     | 2       | an       | 0..1    | 8  | 11 | Debtor  | Bank    |
| Addebit |         |          |         |         | Agent   | Identif |
| o       |         |          |         |         | .BIC    | ier     |
|         |         |          |         |         |         | Code    |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | banca   |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | addebit |
|         |         |          |         |         |         | o,      |
|         |         |          |         |         |         | definit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 9362.   |
+---------+---------+----------+---------+---------+---------+---------+
| fir     | 2       | an       | 1..1    | 1..1    | Proprie | Codice  |
| maRicev |         |          |         |         | tary    | del     |
| uta     |         |          |         |         | Code    | tipo di |
|         |         |          |         |         |         | firma   |
|         |         |          |         |         |         | digital |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | elettro |
|         |         |          |         |         |         | nica    |
|         |         |          |         |         |         | qualifi |
|         |         |          |         |         |         | cata    |
|         |         |          |         |         |         | cui     |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | sottopo |
|         |         |          |         |         |         | sto     |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | messagg |
|         |         |          |         |         |         | io      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | Ricevut |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | Telemat |
|         |         |          |         |         |         | ica,    |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | tipolog |
|         |         |          |         |         |         | ie      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | firma   |
|         |         |          |         |         |         | previst |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | dalle   |
|         |         |          |         |         |         | Regole  |
|         |         |          |         |         |         | Tecnich |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | sulla   |
|         |         |          |         |         |         | firma   |
|         |         |          |         |         |         | digital |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **0** = |
|         |         |          |         |         |         | Firma   |
|         |         |          |         |         |         | non     |
|         |         |          |         |         |         | richies |
|         |         |          |         |         |         | ta      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **1** = |
|         |         |          |         |         |         | CaDes   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **3** = |
|         |         |          |         |         |         | XaDes   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | La      |
|         |         |          |         |         |         | possibi |
|         |         |          |         |         |         | lità    |
|         |         |          |         |         |         | per     |
|         |         |          |         |         |         | l'Ente  |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | richied |
|         |         |          |         |         |         | ere     |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | firma   |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | RT è    |
|         |         |          |         |         |         | depreca |
|         |         |          |         |         |         | ta.     |
|         |         |          |         |         |         | Il dato |
|         |         |          |         |         |         | viene   |
|         |         |          |         |         |         | mantenu |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | per     |
|         |         |          |         |         |         | retro   |
|         |         |          |         |         |         | compati |
|         |         |          |         |         |         | bilità  |
|         |         |          |         |         |         |         |
+---------+---------+----------+---------+---------+---------+---------+
| dat     | 2       | S        | 1..5    |         |         | Aggrega |
| iSingol |         |          |         |         |         | zione   |
| oVersam |         |          |         |         |         | “dati   |
| ento    |         |          |         |         |         | dei     |
|         |         |          |         |         |         | singoli |
|         |         |          |         |         |         | versame |
|         |         |          |         |         |         | nti”,   |
|         |         |          |         |         |         | da un   |
|         |         |          |         |         |         | minimo  |
|         |         |          |         |         |         | di uno  |
|         |         |          |         |         |         | ad un   |
|         |         |          |         |         |         | massimo |
|         |         |          |         |         |         | di 5    |
|         |         |          |         |         |         | occorre |
|         |         |          |         |         |         | nze     |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | versame |
|         |         |          |         |         |         | nto,    |
|         |         |          |         |         |         | facenti |
|         |         |          |         |         |         | capo ad |
|         |         |          |         |         |         | un      |
|         |         |          |         |         |         | unico   |
|         |         |          |         |         |         | identif |
|         |         |          |         |         |         | icativo |
|         |         |          |         |         |         | Univoco |
|         |         |          |         |         |         | Versame |
|         |         |          |         |         |         | nto.    |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Si      |
|         |         |          |         |         |         | precisa |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | nell’ag |
|         |         |          |         |         |         | gregazi |
|         |         |          |         |         |         | one     |
|         |         |          |         |         |         | datiSin |
|         |         |          |         |         |         | goloPag |
|         |         |          |         |         |         | amento  |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | RT      |
|         |         |          |         |         |         | relativ |
|         |         |          |         |         |         | a,      |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | occorre |
|         |         |          |         |         |         | nze     |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | versame |
|         |         |          |         |         |         | nto     |
|         |         |          |         |         |         | devono  |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | riporta |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | nello   |
|         |         |          |         |         |         | stesso  |
|         |         |          |         |         |         | ordine  |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | RPT.    |
+---------+---------+----------+---------+---------+---------+---------+
| imp     | 3       | an       | 1..1    | 3..12   | Amount  | Campo   |
| ortoSin |         |          |         |         |         | numeric |
| goloVer |         |          |         |         |         | o       |
| samento |         |          |         |         |         | (due    |
|         |         |          |         |         |         | cifre   |
|         |         |          |         |         |         | per la  |
|         |         |          |         |         |         | parte   |
|         |         |          |         |         |         | decimal |
|         |         |          |         |         |         | e,      |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | separat |
|         |         |          |         |         |         | ore     |
|         |         |          |         |         |         | dei     |
|         |         |          |         |         |         | centesi |
|         |         |          |         |         |         | mi      |
|         |         |          |         |         |         | è il    |
|         |         |          |         |         |         | punto   |
|         |         |          |         |         |         | “.”),   |
|         |         |          |         |         |         | indican |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | l’impor |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | relativ |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | alla    |
|         |         |          |         |         |         | somma   |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | versare |
|         |         |          |         |         |         | relativ |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | al      |
|         |         |          |         |         |         | singolo |
|         |         |          |         |         |         | versame |
|         |         |          |         |         |         | nto.    |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | diverso |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | “0.00”  |
|         |         |          |         |         |         |         |
+---------+---------+----------+---------+---------+---------+---------+
| com     | 3       | an       | 0..1    | 3..12   | Charges | Campo   |
| mission |         |          |         |         | Fees    | numeric |
| eCarico |         |          |         |         |         | o       |
| PA      |         |          |         |         |         | (due    |
|         |         |          |         |         |         | cifre   |
|         |         |          |         |         |         | per la  |
|         |         |          |         |         |         | parte   |
|         |         |          |         |         |         | decimal |
|         |         |          |         |         |         | e,      |
|         |         |          |         |         |         | il      |
|         |         |          |         |         |         | separat |
|         |         |          |         |         |         | ore     |
|         |         |          |         |         |         | dei     |
|         |         |          |         |         |         | centesi |
|         |         |          |         |         |         | mi      |
|         |         |          |         |         |         | è il    |
|         |         |          |         |         |         | punto   |
|         |         |          |         |         |         | “.”),   |
|         |         |          |         |         |         | indican |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | l’impor |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | eventua |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | commiss |
|         |         |          |         |         |         | ione    |
|         |         |          |         |         |         | spettan |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | al PSP  |
|         |         |          |         |         |         | di cui  |
|         |         |          |         |         |         | si fa   |
|         |         |          |         |         |         | carico  |
|         |         |          |         |         |         | l’Ente  |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re.     |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Il dato |
|         |         |          |         |         |         | è       |
|         |         |          |         |         |         | riporta |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | a solo  |
|         |         |          |         |         |         | titolo  |
|         |         |          |         |         |         | indicat |
|         |         |          |         |         |         | ivo     |
|         |         |          |         |         |         | e non   |
|         |         |          |         |         |         | comport |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | attivit |
|         |         |          |         |         |         | à       |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | carico  |
|         |         |          |         |         |         | del PSP |
|         |         |          |         |         |         | che non |
|         |         |          |         |         |         | abbiano |
|         |         |          |         |         |         | attive  |
|         |         |          |         |         |         | convenz |
|         |         |          |         |         |         | ioni    |
|         |         |          |         |         |         | specifi |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | con uno |
|         |         |          |         |         |         | o più   |
|         |         |          |         |         |         | Enti    |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | ri.     |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Se      |
|         |         |          |         |         |         | present |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | diverso |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | “0.00”. |
|         |         |          |         |         |         |         |
+---------+---------+----------+---------+---------+---------+---------+
| iba     | 3       | an       | 0..1    | 1..35   | Credito | Identif |
| nAccred |         |          |         |         | r       | ica     |
| ito     |         |          |         |         | Account | l’Inter |
|         |         |          |         |         | IBAN    | nationa |
|         |         |          |         |         |         | l       |
|         |         |          |         |         |         | Bank    |
|         |         |          |         |         |         | Account |
|         |         |          |         |         |         | Number, |
|         |         |          |         |         |         | definit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 13616,  |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | conto   |
|         |         |          |         |         |         | corrent |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | bancari |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | postale |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | accredi |
|         |         |          |         |         |         | tare,   |
|         |         |          |         |         |         | indicat |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | dall’En |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re.     |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Non     |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | present |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | qualora |
|         |         |          |         |         |         | sia     |
|         |         |          |         |         |         | stata   |
|         |         |          |         |         |         | popolat |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | struttu |
|         |         |          |         |         |         | ra      |
|         |         |          |         |         |         | datiMar |
|         |         |          |         |         |         | caBollo |
|         |         |          |         |         |         | Digital |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | In      |
|         |         |          |         |         |         | tutti   |
|         |         |          |         |         |         | gli     |
|         |         |          |         |         |         | alti    |
|         |         |          |         |         |         | casi è  |
|         |         |          |         |         |         | obbliga |
|         |         |          |         |         |         | torio.  |
|         |         |          |         |         |         |         |
+---------+---------+----------+---------+---------+---------+---------+
| bic     | 3       | an       | 0..1    | 8  | 11 | Credito | Bank    |
| Accredi |         |          |         |         | r       | Identif |
| to      |         |          |         |         | Agent   | ier     |
|         |         |          |         |         | BIC     | Code    |
|         |         |          |         |         |         | definit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 9362    |
|         |         |          |         |         |         | presso  |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | quale   |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | effettu |
|         |         |          |         |         |         | ato     |
|         |         |          |         |         |         | l’accre |
|         |         |          |         |         |         | dito.   |
+---------+---------+----------+---------+---------+---------+---------+
| iba     | 3       | an       | 0..1    | 1..35   | Credito | Identif |
| nAppogg |         |          |         |         | r       | ica     |
| io      |         |          |         |         | Account | l’Inter |
|         |         |          |         |         | IBAN    | nationa |
|         |         |          |         |         |         | l       |
|         |         |          |         |         |         | Bank    |
|         |         |          |         |         |         | Account |
|         |         |          |         |         |         | Number, |
|         |         |          |         |         |         | definit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 13616,  |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | conto   |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | accredi |
|         |         |          |         |         |         | tare    |
|         |         |          |         |         |         | presso  |
|         |         |          |         |         |         | un PSP  |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | provved |
|         |         |          |         |         |         | erà     |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | trasfer |
|         |         |          |         |         |         | ire     |
|         |         |          |         |         |         | i fondi |
|         |         |          |         |         |         | incassa |
|         |         |          |         |         |         | ti      |
|         |         |          |         |         |         | sul     |
|         |         |          |         |         |         | conto   |
|         |         |          |         |         |         | indicat |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | nell’el |
|         |         |          |         |         |         | emento  |
|         |         |          |         |         |         | ibanAcc |
|         |         |          |         |         |         | redito. |
|         |         |          |         |         |         | Per     |
|         |         |          |         |         |         | indicaz |
|         |         |          |         |         |         | ioni    |
|         |         |          |         |         |         | circa   |
|         |         |          |         |         |         | l’utili |
|         |         |          |         |         |         | zzo     |
|         |         |          |         |         |         | vedi il |
|         |         |          |         |         |         | paragra |
|         |         |          |         |         |         | fo      |
|         |         |          |         |         |         | 8.1.1.5 |
|         |         |          |         |         |         | .       |
+---------+---------+----------+---------+---------+---------+---------+
| bic     | 3       | an       | 0..1    | 8 \| 11 | Credito | Bank    |
| Appoggi |         |          |         |         | r       | Identif |
| o       |         |          |         |         | Agent   | ier     |
|         |         |          |         |         | BIC     | Code    |
|         |         |          |         |         |         | definit |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | secondo |
|         |         |          |         |         |         | lo      |
|         |         |          |         |         |         | standar |
|         |         |          |         |         |         | d       |
|         |         |          |         |         |         | ISO     |
|         |         |          |         |         |         | 9362    |
|         |         |          |         |         |         | dell’el |
|         |         |          |         |         |         | emento  |
|         |         |          |         |         |         | ibanApp |
|         |         |          |         |         |         | oggio.  |
+---------+---------+----------+---------+---------+---------+---------+
| cre     | 3       | an       | 0..1    | 1..35   |         | Eventua |
| denzial |         |          |         |         |         | li      |
| iPagato |         |          |         |         |         | credenz |
| re      |         |          |         |         |         | iali    |
|         |         |          |         |         |         | richies |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | dal     |
|         |         |          |         |         |         | Prestat |
|         |         |          |         |         |         | ore     |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | servizi |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | Pagamen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | necessa |
|         |         |          |         |         |         | rie     |
|         |         |          |         |         |         | per     |
|         |         |          |         |         |         | complet |
|         |         |          |         |         |         | are     |
|         |         |          |         |         |         | l’opera |
|         |         |          |         |         |         | zione   |
|         |         |          |         |         |         | (ad     |
|         |         |          |         |         |         | esempio |
|         |         |          |         |         |         | :       |
|         |         |          |         |         |         | un      |
|         |         |          |         |         |         | codice  |
|         |         |          |         |         |         | bilater |
|         |         |          |         |         |         | ale     |
|         |         |          |         |         |         | utilizz |
|         |         |          |         |         |         | abile   |
|         |         |          |         |         |         | una     |
|         |         |          |         |         |         | sola    |
|         |         |          |         |         |         | volta). |
+---------+---------+----------+---------+---------+---------+---------+
| cau     | 3       | an       | 1..1    | 1..140  | Unstruc | Rappres |
| saleVer |         |          |         |         | tured   | enta    |
| samento |         |          |         |         |         | la      |
|         |         |          |         |         | Remitta | descriz |
|         |         |          |         |         | nce     | ione    |
|         |         |          |         |         | Informa | estesa  |
|         |         |          |         |         | tion    | della   |
|         |         |          |         |         |         | causale |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | versame |
|         |         |          |         |         |         | nto     |
|         |         |          |         |         |         | che     |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | conform |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | a       |
|         |         |          |         |         |         | quanto  |
|         |         |          |         |         |         | indicat |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | nella   |
|         |         |          |         |         |         | Sezione |
|         |         |          |         |         |         | I       |
|         |         |          |         |         |         | dell’Al |
|         |         |          |         |         |         | legato  |
|         |         |          |         |         |         | A alle  |
|         |         |          |         |         |         | Linee   |
|         |         |          |         |         |         | guida.  |
+---------+---------+----------+---------+---------+---------+---------+
| dat     | 3       | an       | 1..1    | 1..140  | Additio | Rappres |
| iSpecif |         |          |         |         | nal     | enta    |
| iciRisc |         |          |         |         | Remitta | l’indic |
| ossione |         |          |         |         | nce     | azione  |
|         |         |          |         |         | Informa | dell’im |
|         |         |          |         |         | tion    | putazio |
|         |         |          |         |         |         | ne      |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | specifi |
|         |         |          |         |         |         | ca      |
|         |         |          |         |         |         | entrata |
|         |         |          |         |         |         | ed è    |
|         |         |          |         |         |         | così    |
|         |         |          |         |         |         | articol |
|         |         |          |         |         |         | ato:    |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | <tipo   |
|         |         |          |         |         |         | contabi |
|         |         |          |         |         |         | lità>”  |
|         |         |          |         |         |         | /”      |
|         |         |          |         |         |         | <codice |
|         |         |          |         |         |         | contabi |
|         |         |          |         |         |         | lità>   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Dove    |
|         |         |          |         |         |         | <tipo   |
|         |         |          |         |         |         | contabi |
|         |         |          |         |         |         | lità>   |
|         |         |          |         |         |         | ha il   |
|         |         |          |         |         |         | seguent |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | signifi |
|         |         |          |         |         |         | cato:   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **0**   |
|         |         |          |         |         |         | Capitol |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | articol |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | Entrata |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | Bilanci |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | dello   |
|         |         |          |         |         |         | Stato   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **1**   |
|         |         |          |         |         |         | Numero  |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | contabi |
|         |         |          |         |         |         | lità    |
|         |         |          |         |         |         | special |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **2**   |
|         |         |          |         |         |         | Codice  |
|         |         |          |         |         |         | SIOPE   |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | **9**   |
|         |         |          |         |         |         | Altro   |
|         |         |          |         |         |         | codice  |
|         |         |          |         |         |         | ad uso  |
|         |         |          |         |         |         | dell’En |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re      |
+---------+---------+----------+---------+---------+---------+---------+
| dat     | 3       | s        | 0..1    |         |         | Aggrega |
| iMarcaB |         |          |         |         |         | zione   |
| olloDig |         |          |         |         |         | che     |
| itale   |         |          |         |         |         | contien |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | le      |
|         |         |          |         |         |         | informa |
|         |         |          |         |         |         | zioni   |
|         |         |          |         |         |         | necessa |
|         |         |          |         |         |         | rie     |
|         |         |          |         |         |         | al PSP  |
|         |         |          |         |         |         | per     |
|         |         |          |         |         |         | generar |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | marca   |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | bollo   |
|         |         |          |         |         |         | digital |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | La      |
|         |         |          |         |         |         | struttu |
|         |         |          |         |         |         | ra      |
|         |         |          |         |         |         | è       |
|         |         |          |         |         |         | obbliga |
|         |         |          |         |         |         | toria   |
|         |         |          |         |         |         | qualora |
|         |         |          |         |         |         | l’infor |
|         |         |          |         |         |         | mazione |
|         |         |          |         |         |         | ibanAcc |
|         |         |          |         |         |         | redito  |
|         |         |          |         |         |         | non sia |
|         |         |          |         |         |         | present |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | In      |
|         |         |          |         |         |         | tutti   |
|         |         |          |         |         |         | gli     |
|         |         |          |         |         |         | altri   |
|         |         |          |         |         |         | casi    |
|         |         |          |         |         |         | non     |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | popolat |
|         |         |          |         |         |         | a.      |
+---------+---------+----------+---------+---------+---------+---------+
| tip     | 4       | an       | 1..1    | 2       | Proprie | Contien |
| oBollo  |         |          |         |         | tary    | e       |
|         |         |          |         |         | Code    | la      |
|         |         |          |         |         |         | tipolog |
|         |         |          |         |         |         | ia      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | Bollo   |
|         |         |          |         |         |         | Digital |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         | Può     |
|         |         |          |         |         |         | assumer |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | seguent |
|         |         |          |         |         |         | i       |
|         |         |          |         |         |         | valori: |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | 01      |
|         |         |          |         |         |         | Imposta |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | bollo   |
+---------+---------+----------+---------+---------+---------+---------+
| has     | 4       | an       | 1..1    | 70      |         | Contien |
| hDocume |         |          |         |         |         | e       |
| nto     |         |          |         |         |         | l’impro |
|         |         |          |         |         |         | nta     |
|         |         |          |         |         |         | informa |
|         |         |          |         |         |         | tica    |
|         |         |          |         |         |         | (digest)|
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | documen |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | informa |
|         |         |          |         |         |         | tico    |
|         |         |          |         |         |         | cui è   |
|         |         |          |         |         |         | associa |
|         |         |          |         |         |         | ta      |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | marca   |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | bollo   |
|         |         |          |         |         |         | digital |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | L’algor |
|         |         |          |         |         |         | itmo    |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | *hash*  |
|         |         |          |         |         |         | da      |
|         |         |          |         |         |         | utilizz |
|         |         |          |         |         |         | are     |
|         |         |          |         |         |         | è       |
|         |         |          |         |         |         | SHA-256 |
|         |         |          |         |         |         | .       |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | La      |
|         |         |          |         |         |         | stringa |
|         |         |          |         |         |         | di 256  |
|         |         |          |         |         |         | bit (32 |
|         |         |          |         |         |         | ottetti |
|         |         |          |         |         |         | )       |
|         |         |          |         |         |         | risulta |
|         |         |          |         |         |         | to      |
|         |         |          |         |         |         | di tale |
|         |         |          |         |         |         | algorit |
|         |         |          |         |         |         | mo      |
|         |         |          |         |         |         | deve    |
|         |         |          |         |         |         | essere  |
|         |         |          |         |         |         | convert |
|         |         |          |         |         |         | ito     |
|         |         |          |         |         |         | in      |
|         |         |          |         |         |         | base64  |
|         |         |          |         |         |         | [2]_.   |
+---------+---------+----------+---------+---------+---------+---------+
| pro     | 4       | an       | 1..1    | 2       | Proprie | Sigla   |
| vinciaR |         |          |         |         | tary    | automob |
| esidenz |         |          |         |         | Code    | ilistic |
| a       |         |          |         |         |         | a       |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | provinc |
|         |         |          |         |         |         | ia      |
|         |         |          |         |         |         | di      |
|         |         |          |         |         |         | residen |
|         |         |          |         |         |         | za      |
|         |         |          |         |         |         | del     |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | pagator |
|         |         |          |         |         |         | e.      |
|         |         |          |         |         |         |         |
|         |         |          |         |         |         | Nel     |
|         |         |          |         |         |         | caso di |
|         |         |          |         |         |         | soggett |
|         |         |          |         |         |         | o       |
|         |         |          |         |         |         | residen |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | all’est |
|         |         |          |         |         |         | ero     |
|         |         |          |         |         |         | indicar |
|         |         |          |         |         |         | e       |
|         |         |          |         |         |         | la      |
|         |         |          |         |         |         | provinc |
|         |         |          |         |         |         | ia      |
|         |         |          |         |         |         | della   |
|         |         |          |         |         |         | sede    |
|         |         |          |         |         |         | legale  |
|         |         |          |         |         |         | dell’En |
|         |         |          |         |         |         | te      |
|         |         |          |         |         |         | Credito |
|         |         |          |         |         |         | re.     |
+---------+---------+----------+---------+---------+---------+---------+

Ricevuta Telematica (RT)
~~~~~~~~~~~~~~~~~~~~~~~~
.. _Ricevuta Telematica (RT):

È il documento informatico rilasciato a cura dell’organizzazione che
effettua l’operazione di pagamento di somme nei confronti di enti
pubblici su ordine dell'utilizzatore finale.

**Tabella** **2 - Elementi componenti la RT**

+---------+---------+---------+---------+---------+---------+---------+
| **Dato**| **Liv** |**Gener**| **Occ** | **Len** |**UNIFI**|**Conte**|
|         |         |**e**    |         |         |         |**nuto** |
+=========+=========+=========+=========+=========+=========+=========+
| ver     | 1       | an      | 1..1    | 1..16   | Version | Riporta |
| sioneOg |         |         |         |         | Number  | la      |
| getto   |         |         |         |         |         | stessa  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zione   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | “versio |
|         |         |         |         |         |         | neOgget |
|         |         |         |         |         |         | to”     |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | (**RPT**|
|         |         |         |         |         |         | )       |
+---------+---------+---------+---------+---------+---------+---------+
| Dom     | 1       | s       | 1..1    |         | Initiat | Riporta |
| inio    |         |         |         |         | ing     | le      |
|         |         |         |         |         | Party   | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “Domini |
|         |         |         |         |         |         | o”      |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | (**RPT**|
|         |         |         |         |         |         | )       |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 1       | an      | 1..1    | 1..35   | Message | Identif |
| ntifica |         |         |         |         | Identif | icativo |
| tivoMes |         |         |         |         | ication | legato  |
| saggioR |         |         |         |         |         | alla    |
| icevuta |         |         |         |         |         | trasmis |
|         |         |         |         |         |         | sione   |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | telemat |
|         |         |         |         |         |         | ica.    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | univoco |
|         |         |         |         |         |         | nell’am |
|         |         |         |         |         |         | bito    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | stessa  |
|         |         |         |         |         |         | data    |
|         |         |         |         |         |         | riferit |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | all’ele |
|         |         |         |         |         |         | mento   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | dataOra |
|         |         |         |         |         |         | Messagg |
|         |         |         |         |         |         | ioRicev |
|         |         |         |         |         |         | uta.    |
|         |         |         |         |         |         |         |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 1       | an      | 1..1    | 19      | Creatio | Indica  |
| aOraMes |         |         |         |         | n       | la data |
| saggioR |         |         |         |         | Date    | e ora   |
| icevuta |         |         |         |         | Time    | del     |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a,      |
|         |         |         |         |         |         | secondo |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | formato |
|         |         |         |         |         |         | ISO     |
|         |         |         |         |         |         | 8601    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | [YYYY   |
|         |         |         |         |         |         | ]-[MM]- |
|         |         |         |         |         |         | [DD]T[h |
|         |         |         |         |         |         | h]:[mm] |
|         |         |         |         |         |         | :[ss]   |
+---------+---------+---------+---------+---------+---------+---------+
| rif     | 1       | an      | 1..1    | 1..35   | Origina | Con     |
| eriment |         |         |         |         | l       | riferim |
| oMessag |         |         |         |         | Message | ento    |
| gioRich |         |         |         |         | Identif | al      |
| iesta   |         |         |         |         | ication | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | (**RT**)|
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | l’eleme |
|         |         |         |         |         |         | nto     |
|         |         |         |         |         |         | contien |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | il dato |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Messagg |
|         |         |         |         |         |         | ioRichi |
|         |         |         |         |         |         | esta    |
|         |         |         |         |         |         | legato  |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | trasmis |
|         |         |         |         |         |         | sione   |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | (**RPT**|
|         |         |         |         |         |         | )       |
+---------+---------+---------+---------+---------+---------+---------+
| rif     | 1       | an      | 1..1    | 10      | Origina | Indica  |
| eriment |         |         |         |         | l       | la data |
| oDataRi |         |         |         |         | Creatio | secondo |
| chiesta |         |         |         |         | n       | il      |
|         |         |         |         |         | Date    | formato |
|         |         |         |         |         | Time    | ISO     |
|         |         |         |         |         |         | 8601    |
|         |         |         |         |         |         | [YYYY   |
|         |         |         |         |         |         | ]-[MM]- |
|         |         |         |         |         |         | [DD]    |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | generaz |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | riferim |
|         |         |         |         |         |         | entoMes |
|         |         |         |         |         |         | saggioR |
|         |         |         |         |         |         | ichiest |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| ist     | 1       | s       | 1..1    |         | Debtor  | Aggrega |
| itutoAt |         |         |         |         | Agent   | zione   |
| testant |         |         |         |         |         | relativ |
| e       |         |         |         |         |         | a       |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | soggett |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | Prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | emette  |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | documen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | attesta |
|         |         |         |         |         |         | zione   |
|         |         |         |         |         |         | dell’av |
|         |         |         |         |         |         | venuto  |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to.     |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 2       | s       | 1..1    |         | Financi | Aggrega |
| ntifica |         |         |         |         | al      | zione   |
| tivoUni |         |         |         |         | Institu | che     |
| vocoAtt |         |         |         |         | tion    | riporta |
| estante |         |         |         |         | Identif | le      |
|         |         |         |         |         | ication | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | concern |
|         |         |         |         |         |         | enti    |
|         |         |         |         |         |         | l’ident |
|         |         |         |         |         |         | ificazi |
|         |         |         |         |         |         | one     |
|         |         |         |         |         |         | fiscale |
|         |         |         |         |         |         | dell’Is |
|         |         |         |         |         |         | tituto  |
|         |         |         |         |         |         | attesta |
|         |         |         |         |         |         | nte     |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to.     |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Si      |
|         |         |         |         |         |         | precisa |
|         |         |         |         |         |         | inoltre |
|         |         |         |         |         |         | che la  |
|         |         |         |         |         |         | struttu |
|         |         |         |         |         |         | ra      |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con     |
|         |         |         |         |         |         | quella  |
|         |         |         |         |         |         | dell’el |
|         |         |         |         |         |         | emento  |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Univoco |
|         |         |         |         |         |         | Mittent |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | indicat |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | Tabella |
|         |         |         |         |         |         | 1       |
|         |         |         |         |         |         | riporta |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | capitol |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | 7       |
|         |         |         |         |         |         | dell’Al |
|         |         |         |         |         |         | legato  |
|         |         |         |         |         |         | A alle  |
|         |         |         |         |         |         | Linee   |
|         |         |         |         |         |         | guida.  |
+---------+---------+---------+---------+---------+---------+---------+
| tip     | 3       | an      | 1..1    | 1       | Proprie | Campo   |
| oIdenti |         |         |         |         | taryCod | alfanum |
| ficativ |         |         |         |         | e       | erico   |
| oUnivoc |         |         |         |         |         | che     |
| o       |         |         |         |         |         | descriv |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | codific |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | utilizz |
|         |         |         |         |         |         | ata     |
|         |         |         |         |         |         | per     |
|         |         |         |         |         |         | individ |
|         |         |         |         |         |         | uare    |
|         |         |         |         |         |         | l’Istit |
|         |         |         |         |         |         | uto     |
|         |         |         |         |         |         | attesta |
|         |         |         |         |         |         | nte     |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to;     |
|         |         |         |         |         |         | se      |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | può     |
|         |         |         |         |         |         | assumer |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | seguent |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | valori: |
|         |         |         |         |         |         | - **‘G  |
|         |         |         |         |         |         | ’**\ =  |
|         |         |         |         |         |         | persona |
|         |         |         |         |         |         | giuridi |
|         |         |         |         |         |         | ca      |
|         |         |         |         |         |         | - **‘A  |
|         |         |         |         |         |         | ’**\ =  |
|         |         |         |         |         |         | Codice  |
|         |         |         |         |         |         | ABI     |
|         |         |         |         |         |         | - **‘B  |
|         |         |         |         |         |         | ’**\ =  |
|         |         |         |         |         |         | Codice  |
|         |         |         |         |         |         | BIC     |
|         |         |         |         |         |         | (standa |
|         |         |         |         |         |         | rd      |
|         |         |         |         |         |         | ISO     |
|         |         |         |         |         |         | 9362)   |
|         |         |         |         |         |         | Si      |
|         |         |         |         |         |         | precisa |
|         |         |         |         |         |         | che il  |
|         |         |         |         |         |         | valore  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | sempre  |
|         |         |         |         |         |         | lo      |
|         |         |         |         |         |         | stesso  |
|         |         |         |         |         |         | per     |
|         |         |         |         |         |         | tutte   |
|         |         |         |         |         |         | le RT   |
|         |         |         |         |         |         | generat |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | dal     |
|         |         |         |         |         |         | PSP. A  |
|         |         |         |         |         |         | tale    |
|         |         |         |         |         |         | scopo   |
|         |         |         |         |         |         | si      |
|         |         |         |         |         |         | evidenz |
|         |         |         |         |         |         | ia      |
|         |         |         |         |         |         | che il  |
|         |         |         |         |         |         | PSP è   |
|         |         |         |         |         |         | quello  |
|         |         |         |         |         |         | indicat |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | PSP     |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | Catalo  |
|         |         |         |         |         |         | go      |
|         |         |         |         |         |         | Dati    |
|         |         |         |         |         |         | Informa |
|         |         |         |         |         |         | tivi    |
|         |         |         |         |         |         | (vedi   |
|         |         |         |         |         |         | Tabella |
|         |         |         |         |         |         | 9).     |
+---------+---------+---------+---------+---------+---------+---------+
| cod     | 3       | an      | 1..1    | 1..35   | BIC |   | Campo   |
| iceIden |         |         |         |         | Proprie | alfanum |
| tificat |         |         |         |         | tary    | erico   |
| ivoUniv |         |         |         |         | |       | che può |
| oco     |         |         |         |         | Tax     | contene |
|         |         |         |         |         | Identif | re      |
|         |         |         |         |         | ication | il      |
|         |         |         |         |         | Number  | codice  |
|         |         |         |         |         |         | fiscale |
|         |         |         |         |         |         | o la    |
|         |         |         |         |         |         | partita |
|         |         |         |         |         |         | IVA, o  |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | codice  |
|         |         |         |         |         |         | ABI o   |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | codice  |
|         |         |         |         |         |         | BIC del |
|         |         |         |         |         |         | prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | attesta |
|         |         |         |         |         |         | nte.    |
+---------+---------+---------+---------+---------+---------+---------+
| den     | 2       | an      | 1..1    | 1..70   | Name    | Contien |
| ominazi |         |         |         |         |         | e       |
| oneAtte |         |         |         |         |         | la      |
| stante  |         |         |         |         |         | denomin |
|         |         |         |         |         |         | azione  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
+---------+---------+---------+---------+---------+---------+---------+
| cod     | 2       | an      | 0..1    | 1..35   |         | Indica  |
| iceUnit |         |         |         |         |         | il      |
| OperAtt |         |         |         |         |         | codice  |
| estante |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | rilasci |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| den     | 2       | an      | 0..1    | 1..70   |         | Indica  |
| omUnitO |         |         |         |         |         | la      |
| perAtte |         |         |         |         |         | denomin |
| stante  |         |         |         |         |         | azione  |
|         |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | attesta |
|         |         |         |         |         |         | nte.    |
+---------+---------+---------+---------+---------+---------+---------+
| ind     | 2       | an      | 0..1    | 1..70   | Street  | Indica  |
| irizzoA |         |         |         |         | Name    | l’indir |
| ttestan |         |         |         |         |         | izzo    |
| te      |         |         |         |         |         | dell’at |
|         |         |         |         |         |         | testant |
|         |         |         |         |         |         | e.      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con     |
|         |         |         |         |         |         | quello  |
|         |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | rilasci |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| civ     | 2       | an      | 0..1    | 1..16   | Buildin | Indica  |
| icoAtte |         |         |         |         | g       | il      |
| stante  |         |         |         |         | Number  | numero  |
|         |         |         |         |         |         | civico  |
|         |         |         |         |         |         | dell’at |
|         |         |         |         |         |         | testant |
|         |         |         |         |         |         | e.      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con     |
|         |         |         |         |         |         | quello  |
|         |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | rilasci |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| cap     | 2       | an      | 0..1    | 1..16   | Postal  | Indica  |
| Attesta |         |         |         |         | Code    | il CAP  |
| nte     |         |         |         |         |         | dell’at |
|         |         |         |         |         |         | testant |
|         |         |         |         |         |         | e.      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con     |
|         |         |         |         |         |         | quello  |
|         |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | rilasci |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| loc     | 2       | an      | 0..1    | 1..35   | Town    | Indica  |
| alitaAt |         |         |         |         | Name    | la      |
| testant |         |         |         |         |         | localit |
| e       |         |         |         |         |         | à       |
|         |         |         |         |         |         | dell’at |
|         |         |         |         |         |         | testant |
|         |         |         |         |         |         | e.      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con     |
|         |         |         |         |         |         | quello  |
|         |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | rilasci |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| pro     | 2       | an      | 0..1    | 1..35   | Country | Indica  |
| vinciaA |         |         |         |         | SubDivi | la      |
| ttestan |         |         |         |         | sion    | provinc |
| te      |         |         |         |         |         | ia      |
|         |         |         |         |         |         | dell’at |
|         |         |         |         |         |         | testant |
|         |         |         |         |         |         | e.      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con     |
|         |         |         |         |         |         | quello  |
|         |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | rilasci |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| naz     | 2       | an      | 0..1    | 2       | Country | Indica  |
| ioneAtt |         |         |         |         |         | il      |
| estante |         |         |         |         |         | codice  |
|         |         |         |         |         |         | nazione |
|         |         |         |         |         |         | dell’at |
|         |         |         |         |         |         | testant |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | secondo |
|         |         |         |         |         |         | lo      |
|         |         |         |         |         |         | standar |
|         |         |         |         |         |         | d       |
|         |         |         |         |         |         | ISO     |
|         |         |         |         |         |         | 3166.   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con     |
|         |         |         |         |         |         | quello  |
|         |         |         |         |         |         | dell’un |
|         |         |         |         |         |         | ità     |
|         |         |         |         |         |         | operati |
|         |         |         |         |         |         | va      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | rilasci |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| ent     | 1       | s       | 1..1    |         | Credito | Riporta |
| eBenefi |         |         |         |         | r       | le      |
| ciario  |         |         |         |         |         | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “enteBe |
|         |         |         |         |         |         | neficia |
|         |         |         |         |         |         | rio”    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | (**RPT**|
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica.    |
+---------+---------+---------+---------+---------+---------+---------+
| sog     | 1       | s       | 0..1    |         | Debtor  | Riporta |
| gettoVe |         |         |         |         |         | le      |
| rsante  |         |         |         |         |         | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “sogget |
|         |         |         |         |         |         | toVersa |
|         |         |         |         |         |         | nte”    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | (**RPT**|
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica.    |
+---------+---------+---------+---------+---------+---------+---------+
| sog     | 1       | s       | 1..1    |         | Ultimat | Riporta |
| gettoPa |         |         |         |         | e       | le      |
| gatore  |         |         |         |         | Debtor  | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         | |       | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         | Debtor  | i       |
|         |         |         |         |         | [3]_    | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “sogget |
|         |         |         |         |         |         | toPagat |
|         |         |         |         |         |         | ore”    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | (RPT)   |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica.    |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 1       | s       | 1..1    |         |         | Aggrega |
| iPagame |         |         |         |         |         | zione   |
| nto     |         |         |         |         |         | “dati   |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | versame |
|         |         |         |         |         |         | nto”    |
|         |         |         |         |         |         | costitu |
|         |         |         |         |         |         | ita     |
|         |         |         |         |         |         | dai     |
|         |         |         |         |         |         | seguent |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | element |
|         |         |         |         |         |         | i:      |
+---------+---------+---------+---------+---------+---------+---------+
| cod     | 2       | n       | 1..1    | 1       | Proprie | Campo   |
| iceEsit |         |         |         |         | tary    | numeric |
| oPagame |         |         |         |         | Code    | o       |
| nto     |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’esito |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to.     |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | assumer |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | seguent |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | valori: |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 1. Paga |
|         |         |         |         |         |         | mento   |
|         |         |         |         |         |         | eseg    |
|         |         |         |         |         |         | uito    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 2. Paga |
|         |         |         |         |         |         | mento   |
|         |         |         |         |         |         | non     |
|         |         |         |         |         |         | eseg    |
|         |         |         |         |         |         | uito    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 3. Paga |
|         |         |         |         |         |         | mento   |
|         |         |         |         |         |         | parz    |
|         |         |         |         |         |         | ialment |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | eseg    |
|         |         |         |         |         |         | uito    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 4. Deco |
|         |         |         |         |         |         | rrenza  |
|         |         |         |         |         |         | term    |
|         |         |         |         |         |         | ini     |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 5. Deco |
|         |         |         |         |         |         | rrenza  |
|         |         |         |         |         |         | term    |
|         |         |         |         |         |         | ini     |
|         |         |         |         |         |         | parz    |
|         |         |         |         |         |         | iale    |
+---------+---------+---------+---------+---------+---------+---------+
| imp     | 2       | an      | 1..1    | 3..12   | Amount  | Campo   |
| ortoTot |         |         |         |         |         | numeric |
| alePaga |         |         |         |         |         | o       |
| to      |         |         |         |         |         | (due    |
|         |         |         |         |         |         | cifre   |
|         |         |         |         |         |         | per la  |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | decimal |
|         |         |         |         |         |         | e,      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | separat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | centesi |
|         |         |         |         |         |         | mi      |
|         |         |         |         |         |         | è il    |
|         |         |         |         |         |         | punto   |
|         |         |         |         |         |         | “.”),   |
|         |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | relativ |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | totale  |
|         |         |         |         |         |         | delle   |
|         |         |         |         |         |         | somme   |
|         |         |         |         |         |         | versate |
|         |         |         |         |         |         | .       |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | uguale  |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | somma   |
|         |         |         |         |         |         | delle   |
|         |         |         |         |         |         | varie   |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | (da 1 a |
|         |         |         |         |         |         | 5)      |
|         |         |         |         |         |         | dell’in |
|         |         |         |         |         |         | formazi |
|         |         |         |         |         |         | one     |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | Importo |
|         |         |         |         |         |         | Versato |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | struttu |
|         |         |         |         |         |         | ra      |
|         |         |         |         |         |         | DatiSin |
|         |         |         |         |         |         | goloVer |
|         |         |         |         |         |         | samento |
|         |         |         |         |         |         | .       |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Se      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | non è   |
|         |         |         |         |         |         | stato   |
|         |         |         |         |         |         | eseguit |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | (cod    |
|         |         |         |         |         |         | iceEsit |
|         |         |         |         |         |         | oPagame |
|         |         |         |         |         |         | nto=    |
|         |         |         |         |         |         | 1),     |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | imposta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | 0.00    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Se la   |
|         |         |         |         |         |         | RT      |
|         |         |         |         |         |         | viene   |
|         |         |         |         |         |         | generat |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | per     |
|         |         |         |         |         |         | decorre |
|         |         |         |         |         |         | nza     |
|         |         |         |         |         |         | termini |
|         |         |         |         |         |         | (codice |
|         |         |         |         |         |         | EsitoPa |
|         |         |         |         |         |         | gamento |
|         |         |         |         |         |         | =3)     |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | imposta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | a 0.00  |
|         |         |         |         |         |         | anche   |
|         |         |         |         |         |         | se non  |
|         |         |         |         |         |         | se ne   |
|         |         |         |         |         |         | conosce |
|         |         |         |         |         |         | l’ammon |
|         |         |         |         |         |         | tare    |
|         |         |         |         |         |         | effetti |
|         |         |         |         |         |         | vo,     |
|         |         |         |         |         |         | in      |
|         |         |         |         |         |         | quanto  |
|         |         |         |         |         |         | non è   |
|         |         |         |         |         |         | disponi |
|         |         |         |         |         |         | bile    |
|         |         |         |         |         |         | dal PSP |
|         |         |         |         |         |         | l’esito |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to.     |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 2       | an      | 1..1    | 1..35   | Credito | Il dato |
| ntifica |         |         |         |         | r       | deve    |
| tivoUni |         |         |         |         | Referen | essere  |
| vocoVer |         |         |         |         | ce      | riporta |
| samento |         |         |         |         |         | to      |
|         |         |         |         |         |         | invaria |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | a cura  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | Prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | così    |
|         |         |         |         |         |         | come    |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | **RPT** |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica.    |
+---------+---------+---------+---------+---------+---------+---------+
| Cod     | 2       | an      | 1..1    | 1..35   | Message | Il dato |
| iceCont |         |         |         |         | Identif | deve    |
| estoPag |         |         |         |         | ication | essere  |
| amento  |         |         |         |         |         | riporta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | invaria |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | a cura  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | Prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | così    |
|         |         |         |         |         |         | come    |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | **RPT** |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica.    |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 2       | s       | 0..5    |         |         | Aggrega |
| iSingol |         |         |         |         |         | zione   |
| oPagame |         |         |         |         |         | “dati   |
| nto     |         |         |         |         |         | dei     |
|         |         |         |         |         |         | singoli |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | ti”,    |
|         |         |         |         |         |         | sino ad |
|         |         |         |         |         |         | un      |
|         |         |         |         |         |         | massimo |
|         |         |         |         |         |         | di 5    |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | versame |
|         |         |         |         |         |         | nto,    |
|         |         |         |         |         |         | facenti |
|         |         |         |         |         |         | capo ad |
|         |         |         |         |         |         | un      |
|         |         |         |         |         |         | unico   |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Univoco |
|         |         |         |         |         |         | Versame |
|         |         |         |         |         |         | nto.    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Le      |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | versame |
|         |         |         |         |         |         | nto     |
|         |         |         |         |         |         | devono  |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | riporta |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | nello   |
|         |         |         |         |         |         | stesso  |
|         |         |         |         |         |         | ordine  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | relativ |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | RPT.    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Obbli   |
|         |         |         |         |         |         | gatorio |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | caso in |
|         |         |         |         |         |         | cui     |
|         |         |         |         |         |         | l’eleme |
|         |         |         |         |         |         | nto     |
|         |         |         |         |         |         | codiceE |
|         |         |         |         |         |         | sitoPag |
|         |         |         |         |         |         | amento  |
|         |         |         |         |         |         | assuma  |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | valore  |
|         |         |         |         |         |         | 0, 2 o  |
|         |         |         |         |         |         | 4       |
+---------+---------+---------+---------+---------+---------+---------+
| sin     | 3       | an      | 1..1    | 3..12   | Amount  | Campo   |
| goloImp |         |         |         |         |         | numeric |
| ortoPag |         |         |         |         |         | o       |
| ato     |         |         |         |         |         | (due    |
|         |         |         |         |         |         | cifre   |
|         |         |         |         |         |         | per la  |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | decimal |
|         |         |         |         |         |         | e,      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | separat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | centesi |
|         |         |         |         |         |         | mi      |
|         |         |         |         |         |         | è il    |
|         |         |         |         |         |         | punto   |
|         |         |         |         |         |         | “.”),   |
|         |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | relativ |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | somma   |
|         |         |         |         |         |         | pagata. |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Se il   |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | non è   |
|         |         |         |         |         |         | stato   |
|         |         |         |         |         |         | effettu |
|         |         |         |         |         |         | ato     |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | imposta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | 0.00.   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Se la   |
|         |         |         |         |         |         | RT      |
|         |         |         |         |         |         | viene   |
|         |         |         |         |         |         | generat |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | per     |
|         |         |         |         |         |         | decorre |
|         |         |         |         |         |         | nza     |
|         |         |         |         |         |         | termini |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | è       |
|         |         |         |         |         |         | imposta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | a 0.00  |
|         |         |         |         |         |         | anche   |
|         |         |         |         |         |         | se non  |
|         |         |         |         |         |         | se ne   |
|         |         |         |         |         |         | conosce |
|         |         |         |         |         |         | l’ammon |
|         |         |         |         |         |         | tare    |
|         |         |         |         |         |         | effetti |
|         |         |         |         |         |         | vo,     |
|         |         |         |         |         |         | in      |
|         |         |         |         |         |         | quanto  |
|         |         |         |         |         |         | non è   |
|         |         |         |         |         |         | disponi |
|         |         |         |         |         |         | bile    |
|         |         |         |         |         |         | dal PSP |
|         |         |         |         |         |         | l’esito |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to.     |
+---------+---------+---------+---------+---------+---------+---------+
| esi     | 3       | an      | 0..1    | 1..35   | Status  |Contien  |
| toSingo |         |         |         |         | Reason  |e        |
| loPagam |         |         |         |         | Proprie |la       |
| ento    |         |         |         |         | tary    |descriz  |
|         |         |         |         |         |         |ione     |
|         |         |         |         |         |         |in       |
|         |         |         |         |         |         |formato  |
|         |         |         |         |         |         |testo    |
|         |         |         |         |         |         |dell’es  |
|         |         |         |         |         |         |ito      |
|         |         |         |         |         |         |del      |
|         |         |         |         |         |         |singolo  |
|         |         |         |         |         |         |pagamen  |
|         |         |         |         |         |         |to.      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         |Obbli    |
|         |         |         |         |         |         |gatorio  |
|         |         |         |         |         |         |nel      |
|         |         |         |         |         |         |caso     |
|         |         |         |         |         |         |che      |
|         |         |         |         |         |         |l’eleme  |
|         |         |         |         |         |         |nto      |
|         |         |         |         |         |         |*singol* |
|         |         |         |         |         |         |*oImport*|
|         |         |         |         |         |         |*oPagato*|
|         |         |         |         |         |         |sia      |
|         |         |         |         |         |         |0.00     |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 3       | an      | 1..1    | 10      | Accepta | Indica  |
| aEsitoS |         |         |         |         | nce     | la data |
| ingoloP |         |         |         |         | Date    | di      |
| agament |         |         |         |         |         | esecuzi |
| o       |         |         |         |         |         | one,    |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | rifiuto |
|         |         |         |         |         |         | o di    |
|         |         |         |         |         |         | revoca  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | formato |
|         |         |         |         |         |         | ISO     |
|         |         |         |         |         |         | 8601    |
|         |         |         |         |         |         | [YYYY]- |
|         |         |         |         |         |         | [MM]-[D |
|         |         |         |         |         |         | D].     |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 3       | an      | 1..1    | 1..35   | Transac | Riferim |
| ntifica |         |         |         |         | tion    | ento    |
| tivoUni |         |         |         |         | Referen | univoco |
| vocoRis |         |         |         |         | ce      | dell’op |
| cossion |         |         |         |         | Number  | erazion |
| e       |         |         |         |         |         | e       |
|         |         |         |         |         |         | assegna |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | dal     |
|         |         |         |         |         |         | Prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to.     |
|         |         |         |         |         |         | Può     |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | rappres |
|         |         |         |         |         |         | entato  |
|         |         |         |         |         |         | dal CRO |
|         |         |         |         |         |         | / TRN   |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | caso di |
|         |         |         |         |         |         | Bonific |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | Bancari |
|         |         |         |         |         |         | o,      |
|         |         |         |         |         |         | dal     |
|         |         |         |         |         |         | CODELIN |
|         |         |         |         |         |         | E       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | caso di |
|         |         |         |         |         |         | bollett |
|         |         |         |         |         |         | ino     |
|         |         |         |         |         |         | postale |
|         |         |         |         |         |         | ,       |
|         |         |         |         |         |         | ovvero  |
|         |         |         |         |         |         | da      |
|         |         |         |         |         |         | qualsia |
|         |         |         |         |         |         | si      |
|         |         |         |         |         |         | altro   |
|         |         |         |         |         |         | riferim |
|         |         |         |         |         |         | ento    |
|         |         |         |         |         |         | univoco |
|         |         |         |         |         |         | attribu |
|         |         |         |         |         |         | ito     |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | dal     |
|         |         |         |         |         |         | PSP.    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Il      |
|         |         |         |         |         |         | riferim |
|         |         |         |         |         |         | ento    |
|         |         |         |         |         |         | può     |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | lo      |
|         |         |         |         |         |         | stesso  |
|         |         |         |         |         |         | per     |
|         |         |         |         |         |         | tutte   |
|         |         |         |         |         |         | le      |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | datiSin |
|         |         |         |         |         |         | goloPag |
|         |         |         |         |         |         | amento  |
|         |         |         |         |         |         | facenti |
|         |         |         |         |         |         | capo ad |
|         |         |         |         |         |         | un      |
|         |         |         |         |         |         | unico   |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Univoco |
|         |         |         |         |         |         | Versame |
|         |         |         |         |         |         | nto.    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Deve    |
|         |         |         |         |         |         | coincid |
|         |         |         |         |         |         | ere     |
|         |         |         |         |         |         | con lo  |
|         |         |         |         |         |         | stesso  |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | flusso  |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | rendico |
|         |         |         |         |         |         | ntazion |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | (vedi   |
|         |         |         |         |         |         | Capitol |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | 7 delle |
|         |         |         |         |         |         | SACI)   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Se il   |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | non è   |
|         |         |         |         |         |         | stato   |
|         |         |         |         |         |         | effettu |
|         |         |         |         |         |         | ato     |
|         |         |         |         |         |         | il dato |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | imposta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | “n/a”.  |
|         |         |         |         |         |         |         |
+---------+---------+---------+---------+---------+---------+---------+
| cau     | 3       | an      | 1..1    | 1..140  | Unstruc | Il dato |
| saleVer |         |         |         |         | tured   | deve    |
| samento |         |         |         |         | Remitta | essere  |
|         |         |         |         |         | nce     | riporta |
|         |         |         |         |         | Informa | to      |
|         |         |         |         |         | tion    | invaria |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | a cura  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | Prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | così    |
|         |         |         |         |         |         | come    |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | **RPT** |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica.    |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 3       | an      | 1..1    | 1..140  | Additio | Il dato |
| iSpecif |         |         |         |         | nal     | deve    |
| iciRisc |         |         |         |         | Remitta | essere  |
| ossione |         |         |         |         | nce     | riporta |
|         |         |         |         |         | Informa | to      |
|         |         |         |         |         | tion    | invaria |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | a cura  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | Prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to,     |
|         |         |         |         |         |         | così    |
|         |         |         |         |         |         | come    |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ico     |
|         |         |         |         |         |         | **RPT** |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica.    |
+---------+---------+---------+---------+---------+---------+---------+
| com     | 3       | an      | 0..1    | 3..12   | Charges | Campo   |
| mission |         |         |         |         | Fees    | numeric |
| iApplic |         |         |         |         |         | o       |
| atePSP  |         |         |         |         |         | (due    |
|         |         |         |         |         |         | cifre   |
|         |         |         |         |         |         | per la  |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | decimal |
|         |         |         |         |         |         | e,      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | separat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | centesi |
|         |         |         |         |         |         | mi      |
|         |         |         |         |         |         | è il    |
|         |         |         |         |         |         | punto   |
|         |         |         |         |         |         | “.”),   |
|         |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | commiss |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | applica |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | dal PSP |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | proprio |
|         |         |         |         |         |         | cliente |
|         |         |         |         |         |         | (sogget |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | versant |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | soggett |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | pagator |
|         |         |         |         |         |         | e).     |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Il dato |
|         |         |         |         |         |         | diviene |
|         |         |         |         |         |         | obbliga |
|         |         |         |         |         |         | torio   |
|         |         |         |         |         |         | qualora |
|         |         |         |         |         |         | l'infor |
|         |         |         |         |         |         | mazione |
|         |         |         |         |         |         | si      |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ca      |
|         |         |         |         |         |         | ad una  |
|         |         |         |         |         |         | transaz |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | facente |
|         |         |         |         |         |         | riferim |
|         |         |         |         |         |         | ento    |
|         |         |         |         |         |         | ad una  |
|         |         |         |         |         |         | specifi |
|         |         |         |         |         |         | ca      |
|         |         |         |         |         |         | convenz |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | in      |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | tra il  |
|         |         |         |         |         |         | PSP e   |
|         |         |         |         |         |         | un Ente |
|         |         |         |         |         |         | Credito |
|         |         |         |         |         |         | r:      |
|         |         |         |         |         |         | in      |
|         |         |         |         |         |         | questo  |
|         |         |         |         |         |         | caso    |
|         |         |         |         |         |         | rappres |
|         |         |         |         |         |         | enta    |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | commiss |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | che il  |
|         |         |         |         |         |         | PSP     |
|         |         |         |         |         |         | avrebbe |
|         |         |         |         |         |         | applica |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | in      |
|         |         |         |         |         |         | assenza |
|         |         |         |         |         |         | di tale |
|         |         |         |         |         |         | convenz |
|         |         |         |         |         |         | ione.   |
+---------+---------+---------+---------+---------+---------+---------+
| all     | 3       | s       | 0..1    |         |         | Aggrega |
| egatoRi |         |         |         |         |         | zione   |
| cevuta  |         |         |         |         |         | contene |
|         |         |         |         |         |         | nte     |
|         |         |         |         |         |         | l'alleg |
|         |         |         |         |         |         | ato     |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to.     |
+---------+---------+---------+---------+---------+---------+---------+
| tip     | 4       | an      | 1..1    | 2       | Proprie | Identif |
| oAllega |         |         |         |         | tary    | ica     |
| toRicev |         |         |         |         | Code    | il tipo |
| uta     |         |         |         |         |         | di      |
|         |         |         |         |         |         | allegat |
|         |         |         |         |         |         | o:      |
|         |         |         |         |         |         | traspor |
|         |         |         |         |         |         | tato    |
|         |         |         |         |         |         | con la  |
|         |         |         |         |         |         | RT e    |
|         |         |         |         |         |         | può     |
|         |         |         |         |         |         | assumer |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | seguent |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | valori: |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | **ES**  |
|         |         |         |         |         |         | esito   |
|         |         |         |         |         |         | origina |
|         |         |         |         |         |         | rio     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | (come   |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | da PSP) |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | **BD**  |
|         |         |         |         |         |         | Marca   |
|         |         |         |         |         |         | da      |
|         |         |         |         |         |         | bollo   |
|         |         |         |         |         |         | digital |
|         |         |         |         |         |         | e       |
+---------+---------+---------+---------+---------+---------+---------+
| tes     | 4       | an      | 1..1    |         |         | Contien |
| toAlleg |         |         |         |         |         | e       |
| ato     |         |         |         |         |         | l’alleg |
|         |         |         |         |         |         | ato     |
|         |         |         |         |         |         | vero e  |
|         |         |         |         |         |         | proprio |
|         |         |         |         |         |         | ,       |
|         |         |         |         |         |         | il cui  |
|         |         |         |         |         |         | signifi |
|         |         |         |         |         |         | cato    |
|         |         |         |         |         |         | è       |
|         |         |         |         |         |         | indicat |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | dal     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | tipoAll |
|         |         |         |         |         |         | egatoRi |
|         |         |         |         |         |         | cevuta. |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | L’eleme |
|         |         |         |         |         |         | nto     |
|         |         |         |         |         |         | testoAl |
|         |         |         |         |         |         | legato  |
|         |         |         |         |         |         | è       |
|         |         |         |         |         |         | traspor |
|         |         |         |         |         |         | tato    |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | secondo |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | codific |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | in      |
|         |         |         |         |         |         | “base64 |
|         |         |         |         |         |         | binary” |
|         |         |         |         |         |         | .       |
+---------+---------+---------+---------+---------+---------+---------+

Richiesta di Revoca (RR)
~~~~~~~~~~~~~~~~~~~~~~~~
.. _Richiesta di Revoca (RR):

È il documento informatico inviato dal prestatore di servizi di
pagamento all’Ente Creditore per richiedere la revoca di un pagamento
effettuato, ovvero inviato dall’Ente Creditore al prestatore di servizi
di pagamento per richiedere lo “storno” di un pagamento.

**Tabella** **3 - Elementi componenti la RR**

+---------+---------+---------+---------+---------+---------+---------+
| **Dato**| **Liv** |**Gener**| **Occ** | **Len** |**UNIFI**|**Conte**|
|         |         |**e**    |         |         |         | **nuto**|
+=========+=========+=========+=========+=========+=========+=========+
| ver     | 1       | an      | o       | 1..16   | Version | Riporta |
| sioneOg |         |         |         |         | Number  | la      |
| getto   |         |         |         |         |         | stessa  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zione   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | “versio |
|         |         |         |         |         |         | neOgget |
|         |         |         |         |         |         | to”     |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | **RT**  |
+---------+---------+---------+---------+---------+---------+---------+
| Dom     | 1       | s       | 1..1    |         | Initiat | Riporta |
| inio    |         |         |         |         | ing     | le      |
|         |         |         |         |         | Party   | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “Domini |
|         |         |         |         |         |         | o”      |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | **RT**  |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 1       | an      | 1..1    | 1..35   | Message | Identif |
| ntifica |         |         |         |         | Identif | icativo |
| tivoMes |         |         |         |         | ication | legato  |
| saggioR |         |         |         |         |         | alla    |
| evoca   |         |         |         |         |         | trasmis |
|         |         |         |         |         |         | sione   |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca. |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | univoco |
|         |         |         |         |         |         | nell’am |
|         |         |         |         |         |         | bito    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | stessa  |
|         |         |         |         |         |         | data    |
|         |         |         |         |         |         | riferit |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | all’ele |
|         |         |         |         |         |         | mento   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | dataMes |
|         |         |         |         |         |         | saggioR |
|         |         |         |         |         |         | evoca.  |
|         |         |         |         |         |         |         |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 1       | an      | 1..1    | 19      | Creatio | Indica  |
| aOraMes |         |         |         |         | n       | la data |
| saggioR |         |         |         |         | Date    | e ora   |
| evoca   |         |         |         |         | Time    | del     |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca, |
|         |         |         |         |         |         | secondo |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | formato |
|         |         |         |         |         |         | ISO     |
|         |         |         |         |         |         | 8601    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | [YYYY   |
|         |         |         |         |         |         | ]-[MM]- |
|         |         |         |         |         |         | [DD]T[h |
|         |         |         |         |         |         | h]:[mm] |
|         |         |         |         |         |         | :[ss]   |
+---------+---------+---------+---------+---------+---------+---------+
| ist     | 1       | s       | 1..1    |         | Debtor  | Aggrega |
| itutoAt |         |         |         |         | Agent   | zione   |
| testant |         |         |         |         |         | relativ |
| e       |         |         |         |         |         | a       |
|         |         |         |         |         |         | al PSP  |
|         |         |         |         |         |         | che ha  |
|         |         |         |         |         |         | emesso  |
|         |         |         |         |         |         | la RT   |
|         |         |         |         |         |         | oggetto |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | revoca. |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Riporta |
|         |         |         |         |         |         | le      |
|         |         |         |         |         |         | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “sogget |
|         |         |         |         |         |         | toAttes |
|         |         |         |         |         |         | tante”  |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | **RT**  |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca. |
+---------+---------+---------+---------+---------+---------+---------+
| sog     | 1       | s       | 0..1    |         | Debtor  | Riporta |
| gettoVe |         |         |         |         |         | le      |
| rsante  |         |         |         |         |         | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “sogget |
|         |         |         |         |         |         | toVersa |
|         |         |         |         |         |         | nte”    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | **RT**  |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca. |
|         |         |         |         |         |         | .       |
+---------+---------+---------+---------+---------+---------+---------+
| sog     | 1       | s       | 1..1    |         | Ultimat | Riporta |
| gettoPa |         |         |         |         | e       | le      |
| gatore  |         |         |         |         | Debtor  | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |  |      | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         | Debtor  | i       |
|         |         |         |         |         | [4]_    | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “sogget |
|         |         |         |         |         |         | toPagat |
|         |         |         |         |         |         | ore”    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | **RT**  |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca. |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 1       | s       | 1..1    |         |         | Aggrega |
| iRevoca |         |         |         |         |         | zione   |
|         |         |         |         |         |         | “dati   |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | revoca” |
|         |         |         |         |         |         | costitu |
|         |         |         |         |         |         | ita     |
|         |         |         |         |         |         | dai     |
|         |         |         |         |         |         | seguent |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | element |
|         |         |         |         |         |         | i:      |
+---------+---------+---------+---------+---------+---------+---------+
| imp     | 2       | an      | 1..1    | 3..12   | Amount  | Campo   |
| ortoTot |         |         |         |         |         | numeric |
| aleRevo |         |         |         |         |         | o       |
| cato    |         |         |         |         |         | (due    |
|         |         |         |         |         |         | cifre   |
|         |         |         |         |         |         | per la  |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | decimal |
|         |         |         |         |         |         | e,      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | separat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | centesi |
|         |         |         |         |         |         | mi      |
|         |         |         |         |         |         | è il    |
|         |         |         |         |         |         | punto   |
|         |         |         |         |         |         | “.”),   |
|         |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | relativ |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | totale  |
|         |         |         |         |         |         | delle   |
|         |         |         |         |         |         | somme   |
|         |         |         |         |         |         | versate |
|         |         |         |         |         |         | .       |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | uguale  |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | somma   |
|         |         |         |         |         |         | delle   |
|         |         |         |         |         |         | varie   |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | (da 1 a |
|         |         |         |         |         |         | 5)      |
|         |         |         |         |         |         | dell’in |
|         |         |         |         |         |         | formazi |
|         |         |         |         |         |         | one     |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | Importo |
|         |         |         |         |         |         | Revocat |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | struttu |
|         |         |         |         |         |         | ra      |
|         |         |         |         |         |         | DatiSin |
|         |         |         |         |         |         | golaRev |
|         |         |         |         |         |         | oca.    |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 2       | an      | 1..1    | 1..35   | Credito | Il dato |
| ntifica |         |         |         |         | r       | deve    |
| tivoUni |         |         |         |         | Referen | essere  |
| vocoVer |         |         |         |         | ce      | riporta |
| samento |         |         |         |         |         | to      |
|         |         |         |         |         |         | invaria |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | così    |
|         |         |         |         |         |         | come    |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | (**RT** |
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca. |
+---------+---------+---------+---------+---------+---------+---------+
| cod     | 2       | an      | 1..1    | 1..35   | Message | Il dato |
| iceCont |         |         |         |         | Identif | deve    |
| estoPag |         |         |         |         | ication | essere  |
| amento  |         |         |         |         |         | riporta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | invaria |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | così    |
|         |         |         |         |         |         | come    |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | Ricevut |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | Telemat |
|         |         |         |         |         |         | ica     |
|         |         |         |         |         |         | (**RT** |
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca. |
|         |         |         |         |         |         | .       |
+---------+---------+---------+---------+---------+---------+---------+
| tip     | 2       | n       | 0..1    | 1..1    | Proprie | Contien |
| oRevoca |         |         |         |         | tary    | e       |
|         |         |         |         |         | Code    | il tipo |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | che     |
|         |         |         |         |         |         | viene   |
|         |         |         |         |         |         | utilizz |
|         |         |         |         |         |         | ata     |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | process |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | revoca  |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | RT      |
|         |         |         |         |         |         | (vedi § |
|         |         |         |         |         |         | 2.3).   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Il dato |
|         |         |         |         |         |         | è       |
|         |         |         |         |         |         | Obblig  |
|         |         |         |         |         |         | atorio  |
|         |         |         |         |         |         | in caso |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | utilizz |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | da      |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | del PSP |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | process |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | RT e    |
|         |         |         |         |         |         | può     |
|         |         |         |         |         |         | assumer |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | seguent |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | valori: |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 1. tipo |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | non     |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | codific |
|         |         |         |         |         |         | ato     |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 2. annu |
|         |         |         |         |         |         | llo     |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | tecnico |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | 3. proc |
|         |         |         |         |         |         | edura   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | *charge |
|         |         |         |         |         |         | back*   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Il dato |
|         |         |         |         |         |         | non     |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | in caso |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | utilizz |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | da      |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | dell'En |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | Credito |
|         |         |         |         |         |         | re      |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | process |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Storno  |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | (vedi § |
|         |         |         |         |         |         | 2.1.4). |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 2       | s       | 1..1    |         |         | Aggrega |
| iSingol |         |         |         |         |         | zione   |
| aRevoca |         |         |         |         |         | “dati   |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | singoli |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | ti      |
|         |         |         |         |         |         | revocat |
|         |         |         |         |         |         | i”,     |
|         |         |         |         |         |         | da un   |
|         |         |         |         |         |         | minimo  |
|         |         |         |         |         |         | di uno  |
|         |         |         |         |         |         | ad un   |
|         |         |         |         |         |         | massimo |
|         |         |         |         |         |         | di 5    |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | revoca, |
|         |         |         |         |         |         | facenti |
|         |         |         |         |         |         | capo ad |
|         |         |         |         |         |         | un      |
|         |         |         |         |         |         | unico   |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Univoco |
|         |         |         |         |         |         | Versame |
|         |         |         |         |         |         | nto.    |
+---------+---------+---------+---------+---------+---------+---------+
| sin     | 3       | an      | 1..1    | 3..12   | Amount  | Campo   |
| goloImp |         |         |         |         |         | numeric |
| ortoRev |         |         |         |         |         | o       |
| ocato   |         |         |         |         |         | (due    |
|         |         |         |         |         |         | cifre   |
|         |         |         |         |         |         | per la  |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | decimal |
|         |         |         |         |         |         | e,      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | separat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | centesi |
|         |         |         |         |         |         | mi      |
|         |         |         |         |         |         | è il    |
|         |         |         |         |         |         | punto   |
|         |         |         |         |         |         | “.”),   |
|         |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | relativ |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | somma   |
|         |         |         |         |         |         | revocat |
|         |         |         |         |         |         | a.      |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 3       | an      | 1..1    | 1..35   | Transac | Riferim |
| ntifica |         |         |         |         | tion    | ento    |
| tivoUni |         |         |         |         | Referen | univoco |
| vocoRis |         |         |         |         | ce      | dell’op |
| cossion |         |         |         |         | Number  | erazion |
| e       |         |         |         |         |         | e       |
|         |         |         |         |         |         | assegna |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | dal     |
|         |         |         |         |         |         | Prestat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | servizi |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to.     |
+---------+---------+---------+---------+---------+---------+---------+
| cau     | 3       | an      | 1..1    | 1..140  | Unstruc | Rappres |
| saleRev |         |         |         |         | tured   | enta    |
| oca     |         |         |         |         |         | la      |
|         |         |         |         |         | Remitta | descriz |
|         |         |         |         |         | nce     | ione    |
|         |         |         |         |         | Informa | del     |
|         |         |         |         |         | tion    | motivo  |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | revoca. |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 3       | an      | 1..1    | 1..140  | Additio | Informa |
| iAggiun |         |         |         |         | nal     | zioni   |
| tiviRev |         |         |         |         | Remitta | aggiunt |
| oca     |         |         |         |         | nce     | ive     |
|         |         |         |         |         | Informa | circa   |
|         |         |         |         |         | tion    | la      |
|         |         |         |         |         |         | descriz |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | motivo  |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | revoca. |
+---------+---------+---------+---------+---------+---------+---------+

Esito della Revoca (ER)
~~~~~~~~~~~~~~~~~~~~~~~
.. _Esito della Revoca (ER):

È il documento informatico inviato dall’Ente Creditore al prestatore di
servizi di pagamento per indicare l’esito di una richiesta di revoca di
un pagamento, ovvero inviato dal prestatore di servizi di pagamento
all’Ente Creditore per indicare l’esito di una richiesta di revoca
relativa allo “storno” di un pagamento.

**Tabella** **4 - Elementi componenti la ER**

+---------+---------+---------+---------+---------+---------+---------+
| **Dato**| **Liv** |**Gener**| **Occ** | **Len** |**UNIFI**|**Conte**|
|         |         |**e**    |         |         |         |**nuto** |
+=========+=========+=========+=========+=========+=========+=========+
| ver     | 1       | an      | 1..1    | 1..16   | Version | Riporta |
| sioneOg |         |         |         |         | Number  | la      |
| getto   |         |         |         |         |         | stessa  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zione   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | “versio |
|         |         |         |         |         |         | neOgget |
|         |         |         |         |         |         | to”     |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | ).      |
+---------+---------+---------+---------+---------+---------+---------+
| Dom     | 1       | s       | 1..1    |         | Initiat | Riporta |
| inio    |         |         |         |         | ing     | le      |
|         |         |         |         |         | Party   | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “Domini |
|         |         |         |         |         |         | o”      |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | ).      |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 1       | an      | 1..1    | 1..35   | Message | Identif |
| ntifica |         |         |         |         | Identif | icativo |
| tivoMes |         |         |         |         | ication | legato  |
| saggioE |         |         |         |         |         | alla    |
| sito    |         |         |         |         |         | trasmis |
|         |         |         |         |         |         | sione   |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | Esito   |
|         |         |         |         |         |         | Revoca. |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | univoco |
|         |         |         |         |         |         | nell’am |
|         |         |         |         |         |         | bito    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | stessa  |
|         |         |         |         |         |         | data    |
|         |         |         |         |         |         | riferit |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | all’ele |
|         |         |         |         |         |         | mento   |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | dataMes |
|         |         |         |         |         |         | saggioR |
|         |         |         |         |         |         | evoca.  |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 1       | an      | 1..1    | 19      | Creatio | Indica  |
| aOraMes |         |         |         |         | n       | la data |
| saggioE |         |         |         |         | Date    | e ora   |
| sito    |         |         |         |         | Time    | del     |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Esito   |
|         |         |         |         |         |         | Revoca, |
|         |         |         |         |         |         | secondo |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | formato |
|         |         |         |         |         |         | ISO     |
|         |         |         |         |         |         | 8601    |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | [YYYY   |
|         |         |         |         |         |         | ]-[MM]- |
|         |         |         |         |         |         | [DD]T[h |
|         |         |         |         |         |         | h]:[mm] |
|         |         |         |         |         |         | :[ss]   |
+---------+---------+---------+---------+---------+---------+---------+
| rif     | 1       | an      | 1..1    | 1..35   | Origina | Con     |
| eriment |         |         |         |         | l       | riferim |
| oMessag |         |         |         |         | Message | ento    |
| gioRevo |         |         |         |         | Identif | al      |
| ca      |         |         |         |         | ication | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Esito   |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**ER** |
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | l’eleme |
|         |         |         |         |         |         | nto     |
|         |         |         |         |         |         | contien |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | il dato |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Messagg |
|         |         |         |         |         |         | ioRevoc |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | legato  |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | trasmis |
|         |         |         |         |         |         | sione   |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | ).      |
+---------+---------+---------+---------+---------+---------+---------+
| rif     | 1       | an      | 1..1    | 10      | Origina | Indica  |
| eriment |         |         |         |         | l       | la data |
| oDataRe |         |         |         |         | Creatio | secondo |
| voca    |         |         |         |         | n       | il      |
|         |         |         |         |         | Date    | formato |
|         |         |         |         |         | Time    | ISO     |
|         |         |         |         |         |         | 8601    |
|         |         |         |         |         |         | [YYYY   |
|         |         |         |         |         |         | ]-[MM]- |
|         |         |         |         |         |         | [DD]    |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | la      |
|         |         |         |         |         |         | generaz |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | riferim |
|         |         |         |         |         |         | entoMes |
|         |         |         |         |         |         | saggioR |
|         |         |         |         |         |         | evoca.  |
+---------+---------+---------+---------+---------+---------+---------+
| ist     | 1       | s       | 1..1    |         | Debtor  | Riporta |
| itutoAt |         |         |         |         | Agent   | le      |
| testant |         |         |         |         |         | stesse  |
| e       |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “istitu |
|         |         |         |         |         |         | toAttes |
|         |         |         |         |         |         | tante”  |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Esito   |
|         |         |         |         |         |         | Revoca. |
+---------+---------+---------+---------+---------+---------+---------+
| sog     | 1       | s       | 0..1    |         | Debtor  | Riporta |
| gettoVe |         |         |         |         |         | le      |
| rsante  |         |         |         |         |         | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         |         | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “sogget |
|         |         |         |         |         |         | toVersa |
|         |         |         |         |         |         | nte”    |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Esito   |
|         |         |         |         |         |         | Revoca. |
|         |         |         |         |         |         | .       |
+---------+---------+---------+---------+---------+---------+---------+
| sog     | 1       | s       | 1..1    |         | Ultimat | Riporta |
| gettoPa |         |         |         |         | e       | le      |
| gatore  |         |         |         |         | Debtor  | stesse  |
|         |         |         |         |         |         | informa |
|         |         |         |         |         | \|      | zioni   |
|         |         |         |         |         |         | present |
|         |         |         |         |         | Debtor  | i       |
|         |         |         |         |         | [5]_    | nel     |
|         |         |         |         |         |         | blocco  |
|         |         |         |         |         |         | “sogget |
|         |         |         |         |         |         | toPagat |
|         |         |         |         |         |         | ore”    |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | )       |
|         |         |         |         |         |         | cui si  |
|         |         |         |         |         |         | riferis |
|         |         |         |         |         |         | ce      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | messagg |
|         |         |         |         |         |         | io      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Esito   |
|         |         |         |         |         |         | Revoca. |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 1       | s       | 1..1    |         |         | Aggrega |
| iRevoca |         |         |         |         |         | zione   |
|         |         |         |         |         |         | “dati   |
|         |         |         |         |         |         | del     |
|         |         |         |         |         |         | versame |
|         |         |         |         |         |         | nto”    |
|         |         |         |         |         |         | costitu |
|         |         |         |         |         |         | ita     |
|         |         |         |         |         |         | dai     |
|         |         |         |         |         |         | seguent |
|         |         |         |         |         |         | i       |
|         |         |         |         |         |         | element |
|         |         |         |         |         |         | i:      |
+---------+---------+---------+---------+---------+---------+---------+
| imp     | 2       | an      | 1..1    | 3..12   | Amount  | Campo   |
| ortoTot |         |         |         |         |         | numeric |
| aleRevo |         |         |         |         |         | o       |
| cato    |         |         |         |         |         | (due    |
|         |         |         |         |         |         | cifre   |
|         |         |         |         |         |         | per la  |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | decimal |
|         |         |         |         |         |         | e,      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | separat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | centesi |
|         |         |         |         |         |         | mi      |
|         |         |         |         |         |         | è il    |
|         |         |         |         |         |         | punto   |
|         |         |         |         |         |         | “.”),   |
|         |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | relativ |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | al      |
|         |         |         |         |         |         | totale  |
|         |         |         |         |         |         | delle   |
|         |         |         |         |         |         | somme   |
|         |         |         |         |         |         | versate |
|         |         |         |         |         |         | .       |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | uguale  |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | somma   |
|         |         |         |         |         |         | delle   |
|         |         |         |         |         |         | varie   |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | (da 1 a |
|         |         |         |         |         |         | 5)      |
|         |         |         |         |         |         | dell’in |
|         |         |         |         |         |         | formazi |
|         |         |         |         |         |         | one     |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | Importo |
|         |         |         |         |         |         | Revocat |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | struttu |
|         |         |         |         |         |         | ra      |
|         |         |         |         |         |         | DatiSin |
|         |         |         |         |         |         | golaRev |
|         |         |         |         |         |         | oca.    |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 2       | an      | 1..1    | 1..35   | Credito | Riporta |
| ntifica |         |         |         |         | r       | la      |
| tivoUni |         |         |         |         | Referen | stessa  |
| vocoVer |         |         |         |         | ce      | informa |
| samento |         |         |         |         |         | zione   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Univoco |
|         |         |         |         |         |         | Versame |
|         |         |         |         |         |         | nto     |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | ).      |
+---------+---------+---------+---------+---------+---------+---------+
| cod     | 2       | an      | 1..1    | 1..35   | Message | Riporta |
| iceCont |         |         |         |         | Identif | la      |
| estoPag |         |         |         |         | ication | stessa  |
| amento  |         |         |         |         |         | informa |
|         |         |         |         |         |         | zione   |
|         |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | codiceC |
|         |         |         |         |         |         | ontesto |
|         |         |         |         |         |         | Pagamen |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | ).      |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 2       | s       | 1..1    |         |         | Aggrega |
| iSingol |         |         |         |         |         | zione   |
| aRevoca |         |         |         |         |         | “dati   |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | singoli |
|         |         |         |         |         |         | pagamen |
|         |         |         |         |         |         | ti      |
|         |         |         |         |         |         | revocat |
|         |         |         |         |         |         | i”,     |
|         |         |         |         |         |         | da un   |
|         |         |         |         |         |         | minimo  |
|         |         |         |         |         |         | di uno  |
|         |         |         |         |         |         | ad un   |
|         |         |         |         |         |         | massimo |
|         |         |         |         |         |         | di 5    |
|         |         |         |         |         |         | occorre |
|         |         |         |         |         |         | nze     |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | revoca, |
|         |         |         |         |         |         | facenti |
|         |         |         |         |         |         | capo ad |
|         |         |         |         |         |         | un      |
|         |         |         |         |         |         | unico   |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Univoco |
|         |         |         |         |         |         | Versame |
|         |         |         |         |         |         | nto.    |
+---------+---------+---------+---------+---------+---------+---------+
| sin     | 3       | an      | 1..1    | 3..12   | Amount  | Campo   |
| goloImp |         |         |         |         |         | numeric |
| ortoRev |         |         |         |         |         | o       |
| ocato   |         |         |         |         |         | (due    |
|         |         |         |         |         |         | cifre   |
|         |         |         |         |         |         | per la  |
|         |         |         |         |         |         | parte   |
|         |         |         |         |         |         | decimal |
|         |         |         |         |         |         | e,      |
|         |         |         |         |         |         | il      |
|         |         |         |         |         |         | separat |
|         |         |         |         |         |         | ore     |
|         |         |         |         |         |         | dei     |
|         |         |         |         |         |         | centesi |
|         |         |         |         |         |         | mi      |
|         |         |         |         |         |         | è il    |
|         |         |         |         |         |         | punto   |
|         |         |         |         |         |         | “.”),   |
|         |         |         |         |         |         | indican |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | l’impor |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | relativ |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | alla    |
|         |         |         |         |         |         | somma   |
|         |         |         |         |         |         | revocat |
|         |         |         |         |         |         | a.      |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | Se la   |
|         |         |         |         |         |         | richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | non è   |
|         |         |         |         |         |         | stata   |
|         |         |         |         |         |         | accolta |
|         |         |         |         |         |         | deve    |
|         |         |         |         |         |         | essere  |
|         |         |         |         |         |         | imposta |
|         |         |         |         |         |         | to      |
|         |         |         |         |         |         | a       |
|         |         |         |         |         |         | 0.00.   |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 3       | an      | 1..1    | 1..35   | Transac | Riporta |
| ntifica |         |         |         |         | tion    | la      |
| tivoUni |         |         |         |         | Referen | stessa  |
| vocoRis |         |         |         |         | ce      | informa |
| cossion |         |         |         |         | Number  | zione   |
| e       |         |         |         |         |         | present |
|         |         |         |         |         |         | e       |
|         |         |         |         |         |         | nel     |
|         |         |         |         |         |         | dato    |
|         |         |         |         |         |         | identif |
|         |         |         |         |         |         | icativo |
|         |         |         |         |         |         | Univoco |
|         |         |         |         |         |         | Riscoss |
|         |         |         |         |         |         | ione    |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | Richies |
|         |         |         |         |         |         | ta      |
|         |         |         |         |         |         | di      |
|         |         |         |         |         |         | Revoca  |
|         |         |         |         |         |         | (**RR** |
|         |         |         |         |         |         | ).      |
+---------+---------+---------+---------+---------+---------+---------+
| cau     | 3       | an      | 1..1    | 1..140  | Unstruc | Rappres |
| saleEsi |         |         |         |         | tured   | enta    |
| to      |         |         |         |         |         | la      |
|         |         |         |         |         | Remitta | descriz |
|         |         |         |         |         | nce     | ione    |
|         |         |         |         |         | Informa | dell’es |
|         |         |         |         |         | tion    | ito     |
|         |         |         |         |         |         | della   |
|         |         |         |         |         |         | revoca. |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 3       | an      | 1..1    | 1..140  | Additio | Informa |
| iAggiun |         |         |         |         | nal     | zioni   |
| tiviEsi |         |         |         |         | Remitta | aggiunt |
| to      |         |         |         |         | nce     | ive     |
|         |         |         |         |         | Informa | circa   |
|         |         |         |         |         | tion    | il      |
|         |         |         |         |         |         | provved |
|         |         |         |         |         |         | imento  |
|         |         |         |         |         |         | adottat |
|         |         |         |         |         |         | o       |
|         |         |         |         |         |         | dall’En |
|         |         |         |         |         |         | te      |
|         |         |         |         |         |         | Credito |
|         |         |         |         |         |         | re      |
|         |         |         |         |         |         | .       |
+---------+---------+---------+---------+---------+---------+---------+

Flusso di rendicontazione
~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Flusso di rendicontazione:

È il flusso informatico inviato dal prestatore di servizi di pagamento o
dal suo intermediario al Nodo dei Pagamenti-SPC e che quest’ultimo invia
all’Ente Creditore accreditato; tale documento è rappresentato da un
insieme omogeneo di dati contenente tutte le informazioni che devono
essere registrate «*in apposito sistema informatico, a disposizione*
*dell'amministrazione*», ai sensi dell’articolo 5, comma 1, lettera b)
del CAD.

Il dettaglio di dette informazioni è riportato nella Sezione II delle
*"Specifiche attuative dei codici identificativi di versamento,*
*riversamento e rendicontazione*", allegato A alle “Linee guida per
l'effettuazione dei pagamenti a favore delle pubbliche amministrazioni e
dei gestori di pubblici servizi” alle quali si deve fare riferimento.

Tabella delle controparti
~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Tabella delle controparti:

La “*Tabella delle controparti*” è il documento informatico che
contiene l’elenco degli Enti Creditori aderenti al Nodo dei
Pagamenti-SPC. Tale elenco ha valenza giornaliera: dalle ore 0 alle ore
24. Nella Tabella 5 sono specificate le informazioni che il Nodo dei
Pagamenti-SPC invia ad ogni prestatore di servizi di pagamento aderente.

**Tabella** **5 - Elementi componenti la “Tabella delle controparti”**

+---------+---------+---------+---------+---------+---------+---------+
| **Dato**| **Liv** |**Gener**| **c**   | **Len** |**Conte**|         |
|         |         | **e**   |         |         |**nuto** |         |
+=========+=========+=========+=========+=========+=========+=========+
| inf     | 1       | s       | 1..n    |         | Struttu |         |
| ormativ |         |         |         |         | ra      |         |
| aContro |         |         |         |         | che     |         |
| parte   |         |         |         |         | raggrup |         |
|         |         |         |         |         | pa      |         |
|         |         |         |         |         | le      |         |
|         |         |         |         |         | informa |         |
|         |         |         |         |         | zioni   |         |
|         |         |         |         |         | inviate |         |
|         |         |         |         |         | dall’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | al Nodo |         |
|         |         |         |         |         | dei     |         |
|         |         |         |         |         | Pagamen |         |
|         |         |         |         |         | ti-SPC  |         |
|         |         |         |         |         | e rese  |         |
|         |         |         |         |         | disponi |         |
|         |         |         |         |         | bili    |         |
|         |         |         |         |         | ai PSP. |         |
+---------+---------+---------+---------+---------+---------+---------+
| ide     | 2       | an      | 1..1    | 35      | identif |         |
| ntifica |         |         |         |         | icativo |         |
| tivoDom |         |         |         |         | Dominio |         |
| inio    |         |         |         |         | dell’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | (codice |         |
|         |         |         |         |         | utilizz |         |
|         |         |         |         |         | ato     |         |
|         |         |         |         |         | nella   |         |
|         |         |         |         |         | RPT).   |         |
+---------+---------+---------+---------+---------+---------+---------+
| rag     | 2       | an      | 1..1    | 70      | Ragione |         |
| ioneSoc |         |         |         |         | sociale |         |
| iale    |         |         |         |         | dell’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re.     |         |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 2       | an      | 1..1    | 10      | Data in |         |
| aInizio |         |         |         |         | cui     |         |
| Validit |         |         |         |         | inizia  |         |
| a       |         |         |         |         | la      |         |
|         |         |         |         |         | validit |         |
|         |         |         |         |         | à       |         |
|         |         |         |         |         | delle   |         |
|         |         |         |         |         | informa |         |
|         |         |         |         |         | zioni   |         |
|         |         |         |         |         | relativ |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | all’Ent |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | nel     |         |
|         |         |         |         |         | formato |         |
|         |         |         |         |         | ISO     |         |
|         |         |         |         |         | 8601:   |         |
|         |         |         |         |         | [YYYY   |         |
|         |         |         |         |         | ]-[MM]- |         |
|         |         |         |         |         | [DD]    |         |
+---------+---------+---------+---------+---------+---------+---------+
| pag     | 2       | n       | 1..1    | 1       | Indica  |         |
| amentiP |         |         |         |         | se      |         |
| ressoPS |         |         |         |         | l’Ente  |         |
| P       |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | consent |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | pagamen |         |
|         |         |         |         |         | ti      |         |
|         |         |         |         |         | presso  |         |
|         |         |         |         |         | i PSP   |         |
|         |         |         |         |         | (vedi § |         |
|         |         |         |         |         | 2.2);   |         |
|         |         |         |         |         | può     |         |
|         |         |         |         |         | assumer |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | seguent |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | valori: |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | 1. NON  |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | consent |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | pagamen |         |
|         |         |         |         |         | ti      |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | c/o     |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | PSP     |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | 2. CONS |         |
|         |         |         |         |         | ENTE    |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | pagamen |         |
|         |         |         |         |         | ti      |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | c/o     |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | PSP     |         |
+---------+---------+---------+---------+---------+---------+---------+
| con     | 2       | an      | 1..1    | 255     | Recapit |         |
| tactCen |         |         |         |         | i       |         |
| terEnte |         |         |         |         | dell'En |         |
| Credito |         |         |         |         | te      |         |
| re      |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | (Numero |         |
|         |         |         |         |         | telefon |         |
|         |         |         |         |         | ico     |         |
|         |         |         |         |         | e/o     |         |
|         |         |         |         |         | indiriz |         |
|         |         |         |         |         | zo      |         |
|         |         |         |         |         | e-mail) |         |
|         |         |         |         |         | presso  |         |
|         |         |         |         |         | il      |         |
|         |         |         |         |         | quale   |         |
|         |         |         |         |         | l'utili |         |
|         |         |         |         |         | zzatore |         |
|         |         |         |         |         | finale  |         |
|         |         |         |         |         | e il    |         |
|         |         |         |         |         | PSP     |         |
|         |         |         |         |         | possono |         |
|         |         |         |         |         | rivolge |         |
|         |         |         |         |         | rsi     |         |
|         |         |         |         |         | per     |         |
|         |         |         |         |         | ottener |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | informa |         |
|         |         |         |         |         | zioni.  |         |
+---------+---------+---------+---------+---------+---------+---------+
| mod     | 2       | s       | 0..1    |         | Struttu |         |
| Spontan |         |         |         |         | che, se |         |
| elloTre |         |         |         |         | ra      |         |
| eo      |         |         |         |         | present |         |
|         |         |         |         |         | e,      |         |
|         |         |         |         |         | indica  |         |
|         |         |         |         |         | che     |         |
|         |         |         |         |         | l’Ente  |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | consent |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | ai      |         |
|         |         |         |         |         | propri  |         |
|         |         |         |         |         | utenti  |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | effettu |         |
|         |         |         |         |         | are     |         |
|         |         |         |         |         | pagamen |         |
|         |         |         |         |         | ti      |         |
|         |         |         |         |         | spontan |         |
|         |         |         |         |         | ei      |         |
|         |         |         |         |         | presso  |         |
|         |         |         |         |         | i PSP   |         |
|         |         |         |         |         | (vedi § |         |
|         |         |         |         |         | 2.2.3   |         |
+---------+---------+---------+---------+---------+---------+---------+
| ser     | 3       | s       | 0..n    |         | Struttu |         |
| viziMod |         |         |         |         | ra      |         |
| elloTre |         |         |         |         | contene |         |
| Spontan |         |         |         |         | nte     |         |
| eo      |         |         |         |         | l'elenc |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | dei     |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | che     |         |
|         |         |         |         |         | possono |         |
|         |         |         |         |         | essere  |         |
|         |         |         |         |         | pagati  |         |
|         |         |         |         |         | in      |         |
|         |         |         |         |         | modalit |         |
|         |         |         |         |         | à       |         |
|         |         |         |         |         | spontan |         |
|         |         |         |         |         | ea      |         |
|         |         |         |         |         | i PSP.  |         |
|         |         |         |         |         | presso  |         |
+---------+---------+---------+---------+---------+---------+---------+
| idS     | 4       | an      | 1..1    | 5       | Codice  |         |
| ervizio |         |         |         |         | numeric |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | che     |         |
|         |         |         |         |         | identif |         |
|         |         |         |         |         | ica     |         |
|         |         |         |         |         | il      |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | che può |         |
|         |         |         |         |         | essere  |         |
|         |         |         |         |         | pagato  |         |
|         |         |         |         |         | in      |         |
|         |         |         |         |         | à       |         |
|         |         |         |         |         | modalit |         |
|         |         |         |         |         | spontan |         |
|         |         |         |         |         | ea      |         |
|         |         |         |         |         | presso  |         |
|         |         |         |         |         | i PSP.  |         |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 4       | an      | 1..1    | 10      | Data da |         |
| aInizio |         |         |         |         | cui è   |         |
| Attivaz |         |         |         |         | attiva  |         |
|         |         |         |         |         | zione   |         |
| ione    |         |         |         |         | l'eroga |         |
|         |         |         |         |         | dello   |         |
|         |         |         |         |         | specifi |         |
|         |         |         |         |         | co      |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | da      |         |
|         |         |         |         |         | parte   |         |
|         |         |         |         |         | dell’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | nel     |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | formato |         |
|         |         |         |         |         | ISO     |         |
|         |         |         |         |         | 8601:   |         |
|         |         |         |         |         | [YYYY   |         |
|         |         |         |         |         | ]-[MM]- |         |
|         |         |         |         |         | [DD]    |         |
+---------+---------+---------+---------+---------+---------+---------+
| avv     | 2       | n       | 0..1    | 1       | Indica  |         |
| isatura |         |         |         |         | che     |         |
| Pull    |         |         |         |         | l’Ente  |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | consent |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | attivar |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | le      |         |
|         |         |         |         |         | funzion |         |
|         |         |         |         |         | alità   |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | avvisat |         |
|         |         |         |         |         | ura     |         |
|         |         |         |         |         | digital |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | *pull*  |         |
|         |         |         |         |         | (vedi § |         |
|         |         |         |         |         | 2.10);  |         |
|         |         |         |         |         | può     |         |
|         |         |         |         |         | assumer |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | seguent |         |
|         |         |         |         |         | valori: |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | 1. NON  |         |
|         |         |         |         |         | consente|         |
|         |         |         |         |         | avvi    |         |
|         |         |         |         |         | satura  |         |
|         |         |         |         |         | *pul*   |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | 2. CONS |         |
|         |         |         |         |         | ENTE    |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | avvisat |         |
|         |         |         |         |         | ura     |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | *pull*  |         |
+---------+---------+---------+---------+---------+---------+---------+
| ero     | 2       | s       | 0..1    |         | Aggrega |         |
| gazione |         |         |         |         | zione   |         |
| Servizi |         |         |         |         | relativ |         |
| o       |         |         |         |         | a       |         |
|         |         |         |         |         | alle    |         |
|         |         |         |         |         | fasce   |         |
|         |         |         |         |         | orarie  |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | erogazi |         |
|         |         |         |         |         | one     |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | da      |         |
|         |         |         |         |         | parte   |         |
|         |         |         |         |         | dell’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re.     |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | L’inf   |         |
|         |         |         |         |         | ormazio |         |
|         |         |         |         |         | ne      |         |
|         |         |         |         |         | è       |         |
|         |         |         |         |         | obbliga |         |
|         |         |         |         |         | toria   |         |
|         |         |         |         |         | nel     |         |
|         |         |         |         |         | caso in |         |
|         |         |         |         |         | cui il  |         |
|         |         |         |         |         | dato    |         |
|         |         |         |         |         | pagamen |         |
|         |         |         |         |         | tiPress |         |
|         |         |         |         |         | oPSP    |         |
|         |         |         |         |         | assuma  |         |
|         |         |         |         |         | il      |         |
|         |         |         |         |         | valore  |         |
|         |         |         |         |         | 1.      |         |
+---------+---------+---------+---------+---------+---------+---------+
| dis     | 3       | s       | 1..n    |         | Aggrega |         |
| ponibil |         |         |         |         | zione   |         |
| ita     |         |         |         |         | relativ |         |
|         |         |         |         |         | a       |         |
|         |         |         |         |         | al      |         |
|         |         |         |         |         | giorno  |         |
|         |         |         |         |         | della   |         |
|         |         |         |         |         | settima |         |
|         |         |         |         |         | na,     |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | mese o  |         |
|         |         |         |         |         | dell’an |         |
|         |         |         |         |         | no      |         |
|         |         |         |         |         | contene |         |
|         |         |         |         |         | nte     |         |
|         |         |         |         |         | le      |         |
|         |         |         |         |         | fasce   |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | orarie  |         |
|         |         |         |         |         | disponi |         |
|         |         |         |         |         | bilità  |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | dell’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re.     |         |
+---------+---------+---------+---------+---------+---------+---------+
| tipo    | 4       | an      | 0..1    | 7..11   | La      |         |
| Periodo |         |         |         |         | periodi |         |
|         |         |         |         |         | cità    |         |
|         |         |         |         |         | con il  |         |
|         |         |         |         |         | quale   |         |
|         |         |         |         |         | il      |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | è reso  |         |
|         |         |         |         |         | disponi |         |
|         |         |         |         |         | bile;   |         |
|         |         |         |         |         | può     |         |
|         |         |         |         |         | assumer |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | seguent |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | valori: |         |
|         |         |         |         |         | - gior  |         |
|         |         |         |         |         | naliera |         |
|         |         |         |         |         | - setti |         |
|         |         |         |         |         | manale  |         |
|         |         |         |         |         | - mensi |         |
|         |         |         |         |         | ile     |         |
|         |         |         |         |         | - annua |         |
|         |         |         |         |         | le      |         |
+---------+---------+---------+---------+---------+---------+---------+
| giorno  | 4       | an      | 0..1    | 35      | Descriz |         |
|         |         |         |         |         | ione    |         |
|         |         |         |         |         | in      |         |
|         |         |         |         |         | formato |         |
|         |         |         |         |         | testo   |         |
|         |         |         |         |         | delle   |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | giornat |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | disponi |         |
|         |         |         |         |         | bilità. |         |
|         |         |         |         |         | Assume  |         |
|         |         |         |         |         | valori  |         |
|         |         |         |         |         | differe |         |
|         |         |         |         |         | nti     |         |
|         |         |         |         |         | in      |         |
|         |         |         |         |         | relazio |         |
|         |         |         |         |         | ne      |         |
|         |         |         |         |         | al      |         |
|         |         |         |         |         | tipoPer |         |
|         |         |         |         |         | iodo.   |         |
+---------+---------+---------+---------+---------+---------+---------+
|         |         |         |         |         | giorn   | il campo|
|         |         |         |         |         | aliera: | viene   |
|         |         |         |         |         |         | omesso  |
|         |         |         |         |         |         |         |
+---------+---------+---------+---------+---------+---------+---------+
|         |         |         |         |         | setti   |"lunedi",|
|         |         |         |         |         | manale: | oppure  |
|         |         |         |         |         |         |"martedi"|
|         |         |         |         |         |         | ...     |
+---------+---------+---------+---------+---------+---------+---------+
|         |         |         |         |         | mensile:| giorno  |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | di calen|
|         |         |         |         |         |         | dario   |
|         |         |         |         |         |         | es. “25”|
|         |         |         |         |         |         |         |
+---------+---------+---------+---------+---------+---------+---------+
|         |         |         |         |         | annuale:| giorno  |
|         |         |         |         |         |         | singolo |
|         |         |         |         |         |         | nella   |
|         |         |         |         |         |         | forma   |
|         |         |         |         |         |         | “gg-mm” |
|         |         |         |         |         |         |         |
|         |         |         |         |         |         | es.     |
|         |         |         |         |         |         | “01-05” |
|         |         |         |         |         |         |         |
+---------+---------+---------+---------+---------+---------+---------+
| fascia  | 4       | s       | 0..n    |         | Aggrega |         |
| Oraria  |         |         |         |         | zione   |         |
|         |         |         |         |         | relativ |         |
|         |         |         |         |         | a       |         |
|         |         |         |         |         | alla    |         |
|         |         |         |         |         | fascia  |         |
|         |         |         |         |         | oraria  |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | disponi |         |
|         |         |         |         |         | bilità  |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | dall’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re.     |         |
+---------+---------+---------+---------+---------+---------+---------+
| fascia  | 5       | an      | 0..1    | 8       | Orario  |         |
| OrariaDa|         |         |         |         | di      |         |
|         |         |         |         |         | inizio  |         |
|         |         |         |         |         | disponi |         |
|         |         |         |         |         | bilità  |         |
|         |         |         |         |         | nell’am |         |
|         |         |         |         |         | bito    |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | giorno  |         |
|         |         |         |         |         | nel     |         |
|         |         |         |         |         | formato |         |
|         |         |         |         |         | [hh]:   |         |
|         |         |         |         |         | [mm]:[s |         |
|         |         |         |         |         | s].     |         |
+---------+---------+---------+---------+---------+---------+---------+
| fascia  | 5       | an      | 0..1    | 8       | Orario  |         |
| OrariaA |         |         |         |         | di fine |         |
|         |         |         |         |         | disponi |         |
|         |         |         |         |         | bilità  |         |
|         |         |         |         |         | nell’am |         |
|         |         |         |         |         | bito    |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | giorno  |         |
|         |         |         |         |         | nel     |         |
|         |         |         |         |         | formato |         |
|         |         |         |         |         | [hh]:   |         |
|         |         |         |         |         | [mm]:[s |         |
|         |         |         |         |         | s].     |         |
+---------+---------+---------+---------+---------+---------+---------+
| ind     | 3       | s       | 0..n    |         | Aggrega |         |
| isponib |         |         |         |         | zione   |         |
| ilita   |         |         |         |         | relativ |         |
|         |         |         |         |         | a       |         |
|         |         |         |         |         | al      |         |
|         |         |         |         |         | giorno  |         |
|         |         |         |         |         | della   |         |
|         |         |         |         |         | settima |         |
|         |         |         |         |         | na,     |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | mese o  |         |
|         |         |         |         |         | dell’an |         |
|         |         |         |         |         | no,     |         |
|         |         |         |         |         | contene |         |
|         |         |         |         |         | nte     |         |
|         |         |         |         |         | le      |         |
|         |         |         |         |         | fasce   |         |
|         |         |         |         |         | di      |         |
|         |         |         |         |         | orarie  |         |
|         |         |         |         |         | indispo |         |
|         |         |         |         |         | nibilit |         |
|         |         |         |         |         | à       |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | dell’En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         | La      |         |
|         |         |         |         |         | struttu |         |
|         |         |         |         |         | ra      |         |
|         |         |         |         |         | contien |         |
|         |         |         |         |         | e       |         |
|         |         |         |         |         | le      |         |
|         |         |         |         |         | stesse  |         |
|         |         |         |         |         | informa |         |
|         |         |         |         |         | zioni   |         |
|         |         |         |         |         | della   |         |
|         |         |         |         |         | struttu |         |
|         |         |         |         |         | ra      |         |
|         |         |         |         |         | “di     |         |
|         |         |         |         |         | sponibi |         |
|         |         |         |         |         | lita”   |         |
|         |         |         |         |         | con il  |         |
|         |         |         |         |         | cato    |         |
|         |         |         |         |         | signifi |         |
|         |         |         |         |         | attribu |         |
|         |         |         |         |         | ito     |         |
|         |         |         |         |         | all’ind |         |
|         |         |         |         |         | isponib |         |
|         |         |         |         |         | ilità   |         |
|         |         |         |         |         | del     |         |
|         |         |         |         |         | servizi |         |
|         |         |         |         |         | o.      |         |
+---------+---------+---------+---------+---------+---------+---------+
| inf     | 2       | s       | 0..n    |         | Elenco  |         |
| ormativ |         |         |         |         | dei     |         |
| aContoA |         |         |         |         | conti   |         |
| ccredit |         |         |         |         | di      |         |
| o       |         |         |         |         | accredi |         |
|         |         |         |         |         | to      |         |
|         |         |         |         |         | attivi  |         |
|         |         |         |         |         | per     |         |
|         |         |         |         |         | quell'E |         |
|         |         |         |         |         | nte     |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re.     |         |
+---------+---------+---------+---------+---------+---------+---------+
| dat     | 3       | an      | 1..1    | 10      | Indica  |         |
| aAttiva |         |         |         |         | la data |         |
| zioneIb |         |         |         |         | di      |         |
| an      |         |         |         |         | attivaz |         |
|         |         |         |         |         | ione    |         |
|         |         |         |         |         | dello   |         |
|         |         |         |         |         | specifi |         |
|         |         |         |         |         | co      |         |
|         |         |         |         |         | IBAN di |         |
|         |         |         |         |         | accredi |         |
|         |         |         |         |         | to.     |         |
+---------+---------+---------+---------+---------+---------+---------+
| iban    | 3       | an      | 1..1    | 35      | Identif |         |
| Accred  |         |         |         |         | ica     |         |
| ito     |         |         |         |         | l’Inter |         |
|         |         |         |         |         | nationa |         |
|         |         |         |         |         | l       |         |
|         |         |         |         |         | Bank    |         |
|         |         |         |         |         | Account |         |
|         |         |         |         |         | Number, |         |
|         |         |         |         |         | definit |         |
|         |         |         |         |         | o       |         |
|         |         |         |         |         | secondo |         |
|         |         |         |         |         | lo      |         |
|         |         |         |         |         | standar |         |
|         |         |         |         |         | d       |         |
|         |         |         |         |         | ISO     |         |
|         |         |         |         |         | 13616.  |         |
+---------+---------+---------+---------+---------+---------+---------+
| Seller  | 3       | an      | 1..1    | 50      | Identif |         |
| Bank    |         |         |         |         | icativo |         |
|         |         |         |         |         | MyBank  |         |
|         |         |         |         |         | della   |         |
|         |         |         |         |         | Seller  |         |
|         |         |         |         |         | prescel |         |
|         |         |         |         |         | Bank    |         |
|         |         |         |         |         | ta      |         |
|         |         |         |         |         | dall'En |         |
|         |         |         |         |         | te      |         |
|         |         |         |         |         | Credito |         |
|         |         |         |         |         | re      |         |
|         |         |         |         |         | (vedi   |         |
|         |         |         |         |         | Elenco  |         |
|         |         |         |         |         | dei PSP |         |
|         |         |         |         |         | aderent |         |
|         |         |         |         |         | i       |         |
|         |         |         |         |         | pubblic |         |
|         |         |         |         |         | ato     |         |
|         |         |         |         |         | sul     |         |
|         |         |         |         |         | sito    |         |
|         |         |         |         |         | AgID).  |         |
+---------+---------+---------+---------+---------+---------+---------+
| idNe    | 3       | an      | 0..1    | 15      |Identif  |         |
| gozio   |         |         |         |         |icativo  |         |
|         |         |         |         |         |da       |         |
|         |         |         |         |         |utilizz  |         |
|         |         |         |         |         |are      |         |
|         |         |         |         |         |nel      |         |
|         |         |         |         |         |colloqu  |         |
|         |         |         |         |         |io       |         |
|         |         |         |         |         |tra      |         |
|         |         |         |         |         |*Wrapper*|         |
|         |         |         |         |         |MyBank   |         |
|         |         |         |         |         |ed       |         |
|         |         |         |         |         |Initiat  |         |
|         |         |         |         |         |ing      |         |
|         |         |         |         |         |Party    |         |
|         |         |         |         |         |della    |         |
|         |         |         |         |         |Seller   |         |
|         |         |         |         |         |Bank.    |         |
|         |         |         |         |         |         |         |
|         |         |         |         |         |Il dato  |         |
|         |         |         |         |         |può      |         |
|         |         |         |         |         |essere   |         |
|         |         |         |         |         |valoriz  |         |
|         |         |         |         |         |zato     |         |
|         |         |         |         |         |o meno,  |         |
|         |         |         |         |         |a        |         |
|         |         |         |         |         |seconda  |         |
|         |         |         |         |         |del      |         |
|         |         |         |         |         |tipo di  |         |
|         |         |         |         |         |modalit  |         |
|         |         |         |         |         |à        |         |
|         |         |         |         |         |di       |         |
|         |         |         |         |         |attribu  |         |
|         |         |         |         |         |zione    |         |
|         |         |         |         |         |di       |         |
|         |         |         |         |         |detto    |         |
|         |         |         |         |         |codice   |         |
|         |         |         |         |         |(Standa  |         |
|         |         |         |         |         |rd       |         |
|         |         |         |         |         |o        |         |
|         |         |         |         |         |concord  |         |
|         |         |         |         |         |tra      |         |
|         |         |         |         |         |ata      |         |
|         |         |         |         |         |AgID e   |         |
|         |         |         |         |         |Seller   |         |
|         |         |         |         |         |Bank).   |         |
+---------+---------+---------+---------+---------+---------+---------+

Le informazioni sono codificate in un file XML secondo il tracciato di
Tabella 6 e devono essere richieste dai singoli prestatori di servizi di
pagamento al NodoSPC utilizzando le apposite funzioni allo scopo messe a
disposizione (`vedi § 9.2.10 della Sezione III <../16-Capitolo_9/Capitolo9.rst#interrogazione-delle-basi-dati-del-nodospc>`__).

**Tabella** **6 - Formato file XML della “Tabella delle controparti”**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **c**     | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| lista     | 1         | s         | 1..1      |           | Lista     |
| Informati |           |           |           |           | delle     |
| vaControp |           |           |           |           | informati |
| arte      |           |           |           |           | ve        |
|           |           |           |           |           | Contropar |
|           |           |           |           |           | te        |
|           |           |           |           |           | valide    |
|           |           |           |           |           | nella     |
|           |           |           |           |           | giornata  |
|           |           |           |           |           | corrente  |
|           |           |           |           |           | (hh       |
|           |           |           |           |           | 00-24)    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| infor     | 2         | s         | 1..n      |           | Numero    |
| mativaCon |           |           |           |           | non       |
| troparte  |           |           |           |           | definito  |
|           |           |           |           |           | di        |
|           |           |           |           |           | occorrenz |
|           |           |           |           |           | e         |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | informati |
|           |           |           |           |           | vaControp |
|           |           |           |           |           | arte      |
|           |           |           |           |           | definita  |
|           |           |           |           |           | nella     |
|           |           |           |           |           | precedent |
|           |           |           |           |           | e         |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 5.        |
+-----------+-----------+-----------+-----------+-----------+-----------+

Informazioni inviate dagli Enti Creditori
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Informazioni inviate dagli Enti Creditori:

La “*Tabella delle controparti*” viene prodotta sulla base delle
informazioni inviate dai singoli Enti Creditori all’Agenzia per l’Italia
Digitale via PEC, codificate in uno o più file XML.

In particolare il primo di questi file XML contiene le informazioni
relative alla erogazione dei servizi e riporta il seguente tracciato,
che ricalca in parte quello indicato al paragrafo precedente e riportato
in Tabella 7.

**Tabella** **7 - Tracciato XML per comunicazione "Erogazione servizi EC"**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **c**     | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| infor     | 1         | s         | 1..n      |           | Struttura |
| mativaCon |           |           |           |           | che       |
| troparte  |           |           |           |           | raggruppa |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | inviate   |
|           |           |           |           |           | dall’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | al Nodo   |
|           |           |           |           |           | dei       |
|           |           |           |           |           | Pagamenti |
|           |           |           |           |           | -SPC      |
|           |           |           |           |           | e rese    |
|           |           |           |           |           | disponibi |
|           |           |           |           |           | li        |
|           |           |           |           |           | ai PSP.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 35        | Identific |
| ificativo |           |           |           |           | ativo     |
| Flusso    |           |           |           |           | del       |
|           |           |           |           |           | flusso    |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | ,         |
|           |           |           |           |           | con un    |
|           |           |           |           |           | codice    |
|           |           |           |           |           | utile ad  |
|           |           |           |           |           | identific |
|           |           |           |           |           | are       |
|           |           |           |           |           | univocame |
|           |           |           |           |           | nte       |
|           |           |           |           |           | la        |
|           |           |           |           |           | comunicaz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | (es.      |
|           |           |           |           |           | numero di |
|           |           |           |           |           | protocoll |
|           |           |           |           |           | o).       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 35        | identific |
| ificativo |           |           |           |           | ativo     |
| Dominio   |           |           |           |           | Dominio   |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | (codice   |
|           |           |           |           |           | utilizzat |
|           |           |           |           |           | o         |
|           |           |           |           |           | nella     |
|           |           |           |           |           | RPT).     |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ragio     | 2         | an        | 1..1      | 70        | Ragione   |
| neSociale |           |           |           |           | sociale   |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataP     | 2         | an        | 1..1      | 19        | Data e    |
| ubblicazi |           |           |           |           | ora di    |
| one       |           |           |           |           | “pubblica |
|           |           |           |           |           | zione”    |
|           |           |           |           |           | del       |
|           |           |           |           |           | flusso    |
|           |           |           |           |           | informati |
|           |           |           |           |           | vo        |
|           |           |           |           |           | da parte  |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | ,         |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601. |
|           |           |           |           |           |           |
|           |           |           |           |           | Corrispon |
|           |           |           |           |           | de        |
|           |           |           |           |           | alla data |
|           |           |           |           |           | e ora di  |
|           |           |           |           |           | invio     |
|           |           |           |           |           | della     |
|           |           |           |           |           | comunicaz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | relativa  |
|           |           |           |           |           | all’ident |
|           |           |           |           |           | ificativo |
|           |           |           |           |           | Flusso    |
|           |           |           |           |           | corrente. |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
|           |           |           |           |           |           |
|           |           |           |           |           | Dev’esser |
|           |           |           |           |           | e         |
|           |           |           |           |           | maggiore  |
|           |           |           |           |           | della     |
|           |           |           |           |           | dataPubbl |
|           |           |           |           |           | icazione  |
|           |           |           |           |           | contenuta |
|           |           |           |           |           | nell’ulti |
|           |           |           |           |           | mo        |
|           |           |           |           |           | flusso di |
|           |           |           |           |           | informati |
|           |           |           |           |           | va        |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | caricato  |
|           |           |           |           |           | nel Nodo. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataI     | 2         | an        | 1..1      | 19        | Data in   |
| nizioVali |           |           |           |           | cui       |
| dita      |           |           |           |           | inizia la |
|           |           |           |           |           | validità  |
|           |           |           |           |           | delle     |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | relative  |
|           |           |           |           |           | all’Ente  |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | nel       |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601: |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| pagam     | 2         | n         | 1..1      | 1         | Indica se |
| entiPress |           |           |           |           | l’Ente    |
| oPSP      |           |           |           |           | Creditore |
|           |           |           |           |           | consente  |
|           |           |           |           |           | i         |
|           |           |           |           |           | pagamenti |
|           |           |           |           |           | presso i  |
|           |           |           |           |           | PSP (vedi |
|           |           |           |           |           | § 2.2);   |
|           |           |           |           |           | può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | 0. NON    |
|           |           |           |           |           | consente  |
|           |           |           |           |           | i         |
|           |           |           |           |           | pagamenti |
|           |           |           |           |           | c/o i PSP |
|           |           |           |           |           |           |
|           |           |           |           |           | 1. CONSEN |
|           |           |           |           |           | TE        |
|           |           |           |           |           | i         |
|           |           |           |           |           | pagamenti |
|           |           |           |           |           | c/o i PSP |
|           |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| eroga     | 2         | s         | 0..1      |           | Aggregazi |
| zioneServ |           |           |           |           | one       |
| izio      |           |           |           |           | relativa  |
|           |           |           |           |           | alle      |
|           |           |           |           |           | fasce     |
|           |           |           |           |           | orarie di |
|           |           |           |           |           | erogazion |
|           |           |           |           |           | e         |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | da parte  |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
|           |           |           |           |           |           |
|           |           |           |           |           | L’infor   |
|           |           |           |           |           | mazione   |
|           |           |           |           |           | è         |
|           |           |           |           |           | obbligato |
|           |           |           |           |           | ria       |
|           |           |           |           |           | nel caso  |
|           |           |           |           |           | in cui il |
|           |           |           |           |           | dato      |
|           |           |           |           |           | pagamenti |
|           |           |           |           |           | PressoPSP |
|           |           |           |           |           | sia 1.    |
+-----------+-----------+-----------+-----------+-----------+-----------+

Per ciò che attiene alla comunicazione le informazioni relative ai conti
da accreditare, gli Enti Creditori inviano ad AgID il tracciato indicato
in Tabella 8.

**Tabella** **8 - Tracciato XML per comunicazione "IBAN di accredito"**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| infor     | 1         | s         | 1..1      |           | Informati |
| mativaCon |           |           |           |           | va        |
| toAccredi |           |           |           |           | inviata   |
| to        |           |           |           |           | dall’ente |
|           |           |           |           |           | creditore |
|           |           |           |           |           | al Nodo   |
|           |           |           |           |           | dei       |
|           |           |           |           |           | Pagamenti |
|           |           |           |           |           | -SPC      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 35        | Identific |
| ificativo |           |           |           |           | ativo     |
| Flusso    |           |           |           |           | del       |
|           |           |           |           |           | flusso    |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | ,         |
|           |           |           |           |           | con un    |
|           |           |           |           |           | codice    |
|           |           |           |           |           | utile ad  |
|           |           |           |           |           | identific |
|           |           |           |           |           | are       |
|           |           |           |           |           | univocame |
|           |           |           |           |           | nte       |
|           |           |           |           |           | la        |
|           |           |           |           |           | comunicaz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | (es.      |
|           |           |           |           |           | numero di |
|           |           |           |           |           | protocoll |
|           |           |           |           |           | o).       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 35        | identific |
| ificativo |           |           |           |           | ativo     |
| Dominio   |           |           |           |           | Dominio   |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | (codice   |
|           |           |           |           |           | utilizzat |
|           |           |           |           |           | o         |
|           |           |           |           |           | nella     |
|           |           |           |           |           | RPT)      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ragio     | 2         | an        | 1..1      | 35        | Ragione   |
| neSociale |           |           |           |           | sociale   |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataP     | 2         | an        | 1..1      | 19        | Data e    |
| ubblicazi |           |           |           |           | ora di    |
| one..     |           |           |           |           | “pubblica |
|           |           |           |           |           | zione”    |
|           |           |           |           |           | del       |
|           |           |           |           |           | flusso    |
|           |           |           |           |           | informati |
|           |           |           |           |           | vo        |
|           |           |           |           |           | da parte  |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | ,         |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601. |
|           |           |           |           |           |           |
|           |           |           |           |           | Corrispon |
|           |           |           |           |           | de        |
|           |           |           |           |           | alla data |
|           |           |           |           |           | e ora di  |
|           |           |           |           |           | invio     |
|           |           |           |           |           | della     |
|           |           |           |           |           | comunicaz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | relativa  |
|           |           |           |           |           | all’ident |
|           |           |           |           |           | ificativo |
|           |           |           |           |           | Flusso    |
|           |           |           |           |           | corrente. |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
|           |           |           |           |           |           |
|           |           |           |           |           | Dev’esser |
|           |           |           |           |           | e         |
|           |           |           |           |           | maggiore  |
|           |           |           |           |           | della     |
|           |           |           |           |           | dataPubbl |
|           |           |           |           |           | icazione  |
|           |           |           |           |           | contenuta |
|           |           |           |           |           | nell’ulti |
|           |           |           |           |           | mo        |
|           |           |           |           |           | flusso di |
|           |           |           |           |           | informati |
|           |           |           |           |           | va        |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | caricato  |
|           |           |           |           |           | nel Nodo. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataI     | 2         | an        | 1..1      | 19        | Data e    |
| nizioVali |           |           |           |           | ora da    |
| dita      |           |           |           |           | cui       |
|           |           |           |           |           | saranno   |
|           |           |           |           |           | considera |
|           |           |           |           |           | ti        |
|           |           |           |           |           | validi    |
|           |           |           |           |           | dal Nodo  |
|           |           |           |           |           | solamente |
|           |           |           |           |           | gli IBAN  |
|           |           |           |           |           | di        |
|           |           |           |           |           | Accredito |
|           |           |           |           |           | contenuti |
|           |           |           |           |           | nel       |
|           |           |           |           |           | presente  |
|           |           |           |           |           | flusso.   |
|           |           |           |           |           | Deve      |
|           |           |           |           |           | seguire   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601: |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
|           |           |           |           |           |           |
|           |           |           |           |           | Dev’esser |
|           |           |           |           |           | e         |
|           |           |           |           |           | maggiore  |
|           |           |           |           |           | o uguale  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | dataPubbl |
|           |           |           |           |           | icazione  |
|           |           |           |           |           | e         |
|           |           |           |           |           | maggiore  |
|           |           |           |           |           | della     |
|           |           |           |           |           | data      |
|           |           |           |           |           | corrente. |
|           |           |           |           |           |           |
|           |           |           |           |           | La        |
|           |           |           |           |           | validità  |
|           |           |           |           |           | parte     |
|           |           |           |           |           | comunque  |
|           |           |           |           |           | dalle     |
|           |           |           |           |           | 00:00:00  |
|           |           |           |           |           | del       |
|           |           |           |           |           | giorno    |
|           |           |           |           |           | indicato. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| conti     | 2         | s         | 1..n      |           | Aggregazi |
| DiAccredi |           |           |           |           | one       |
| to        |           |           |           |           | relativa  |
|           |           |           |           |           | agli IBAN |
|           |           |           |           |           | di        |
|           |           |           |           |           | accredito |
|           |           |           |           |           | di        |
|           |           |           |           |           | pertinenz |
|           |           |           |           |           | a         |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| iban      | 3         | an        | 0..1      | 1..35     | Identific |
| Accredito |           |           |           |           | a         |
|           |           |           |           |           | l’Interna |
|           |           |           |           |           | tional    |
|           |           |           |           |           | Bank      |
|           |           |           |           |           | Account   |
|           |           |           |           |           | Number,,  |
|           |           |           |           |           | definito  |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | lo        |
|           |           |           |           |           | standard  |
|           |           |           |           |           | ISO       |
|           |           |           |           |           | 13616,    |
|           |           |           |           |           | del conto |
|           |           |           |           |           | da        |
|           |           |           |           |           | accredita |
|           |           |           |           |           | re        |
|           |           |           |           |           | presso la |
|           |           |           |           |           | Banca di  |
|           |           |           |           |           | accredito |
|           |           |           |           |           | indicata  |
|           |           |           |           |           | dall’ente |
|           |           |           |           |           | creditore |
|           |           |           |           |           | ,         |
|           |           |           |           |           | di norma  |
|           |           |           |           |           | la Banca  |
|           |           |           |           |           | Tesoriera.|
+-----------+-----------+-----------+-----------+-----------+-----------+
| Oppure,   |                                                           |
| in        |                                                           |
| alternati |                                                           |
| va,       |                                                           |
| la        |                                                           |
| struttura |                                                           |
| sotto     |                                                           |
| indicata  |                                                           |
|           |                                                           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| infoC     | 3         | s         | 0..1      |           | Aggregazi |
| ontoDiAcc |           |           |           |           | one       |
| reditoPai |           |           |           |           | relativa  |
| r         |           |           |           |           | agli IBAN |
|           |           |           |           |           | di        |
|           |           |           |           |           | accredito |
|           |           |           |           |           | di        |
|           |           |           |           |           | pertinenz |
|           |           |           |           |           | a         |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ibanA     | 4         | an        | 1..1      | 1..35     | Vedi      |
| ccredito  |           |           |           |           | analogo   |
|           |           |           |           |           | elemento  |
|           |           |           |           |           | sopra     |
|           |           |           |           |           | descritto |
|           |           |           |           |           | ..        |
+-----------+-----------+-----------+-----------+-----------+-----------+
| idBan     | 4         | an        | 1..1      | 50        | Identific |
| caSeller  |           |           |           |           | ativo     |
|           |           |           |           |           | della     |
|           |           |           |           |           | *Seller   |
|           |           |           |           |           | Bank*     |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | la        |
|           |           |           |           |           | codifica  |
|           |           |           |           |           | MyBank    |
|           |           |           |           |           | (vedi     |
|           |           |           |           |           | Elenco    |
|           |           |           |           |           | dei PSP   |
|           |           |           |           |           | aderenti  |
|           |           |           |           |           | pubblicat |
|           |           |           |           |           | o         |
|           |           |           |           |           | sul sito  |
|           |           |           |           |           | AgID).    |
+-----------+-----------+-----------+-----------+-----------+-----------+

Catalogo Dati Informativi
~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Catalogo Dati Informativi:

Il catalogo dei dati informativi è lo strumento con il quale il PSP
comunica ai propri potenziali clienti, utilizzatori del sistema pagoPA,
le condizioni di utilizzo relative ai servizi che rende disponibile ed
il costo di commissione massimo che potrà essere applicato.

Per ogni servizio attivato (canale) il PSP produce le informazioni che
il sistema pagoPA rende disponibile ai pagatori tramite la componente
WISP. Il PSP è autonomo nel mantenimento di tali informazioni: purché
renda disponibile un catalogo semanticamente corretto che superi i
controlli applicativi previsti.

Gli aggiornamenti delle informazioni fornite dal PSP sono rese
disponibili dalla data di validità specificata, purché non inferiore al
giorno successivo all’invio. In tabella 9 è riportata la struttura del
catalogo:

**Tabella** **9 - Elementi componenti il “Catalogo Dati Informativi”**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **c**     | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| informati | 1         | s         | 1..1      |           | Informati |
| vaPSP     |           |           |           |           | va        |
|           |           |           |           |           | fornita   |
|           |           |           |           |           | dal PSP   |
|           |           |           |           |           | al Nodo   |
|           |           |           |           |           | dei       |
|           |           |           |           |           | Pagamenti |
|           |           |           |           |           | -SPC      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 35        | Identific |
| ificativo |           |           |           |           | ativo     |
| Flusso    |           |           |           |           | dell’info |
|           |           |           |           |           | rmativa   |
|           |           |           |           |           | del PSP,  |
|           |           |           |           |           | utile ad  |
|           |           |           |           |           | identific |
|           |           |           |           |           | are       |
|           |           |           |           |           | la        |
|           |           |           |           |           | versione  |
|           |           |           |           |           | del set   |
|           |           |           |           |           | di        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | fornite.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 35        | Identific |
| ificativo |           |           |           |           | ativo     |
| PSP       |           |           |           |           | del PSP a |
|           |           |           |           |           | cui si    |
|           |           |           |           |           | riferisce |
|           |           |           |           |           | il set di |
|           |           |           |           |           | dati      |
|           |           |           |           |           | component |
|           |           |           |           |           | i         |
|           |           |           |           |           | il        |
|           |           |           |           |           | "Catalog  |
|           |           |           |           |           | o         |
|           |           |           |           |           | Dati      |
|           |           |           |           |           | Informati |
|           |           |           |           |           | vi".      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ragio     | 2         | an        | 1..1      | 70        | Ragione   |
| neSociale |           |           |           |           | sociale   |
|           |           |           |           |           | del PSP.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| infor     | 2         | s         | 1..1      |           | Aggregazi |
| mativaMas |           |           |           |           | one       |
| ter       |           |           |           |           | corrispon |
|           |           |           |           |           | dente     |
|           |           |           |           |           | ai dati   |
|           |           |           |           |           | comuni    |
|           |           |           |           |           | del       |
|           |           |           |           |           | presente  |
|           |           |           |           |           | flusso di |
|           |           |           |           |           | informati |
|           |           |           |           |           | va.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataP     | 3         | an        | 1..1      | 19        | Data e    |
| ubblicazi |           |           |           |           | ora di    |
| one       |           |           |           |           | pubblicaz |
|           |           |           |           |           | ione      |
|           |           |           |           |           | del set   |
|           |           |           |           |           | di        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | fornite   |
|           |           |           |           |           | da parte  |
|           |           |           |           |           | del PSP.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataI     | 3         | an        | 1..1      | 19        | Data e    |
| nizioVali |           |           |           |           | ora in    |
| dita      |           |           |           |           | cui       |
|           |           |           |           |           | inizierà  |
|           |           |           |           |           | la        |
|           |           |           |           |           | validità  |
|           |           |           |           |           | del set   |
|           |           |           |           |           | di        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | fornite   |
|           |           |           |           |           | da parte  |
|           |           |           |           |           | del PSP.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| urlIn     | 3         | an        | 1..1      | 255       | URL di    |
| formazion |           |           |           |           | una       |
| iPSP      |           |           |           |           | pagina/si |
|           |           |           |           |           | to        |
|           |           |           |           |           | web       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | specifich |
|           |           |           |           |           | e         |
|           |           |           |           |           | del PSP.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| storn     | 3         | n         | 1..1      | 1         | Indica se |
| oPagament |           |           |           |           | il PSP è  |
| o         |           |           |           |           | in grado  |
|           |           |           |           |           | di        |
|           |           |           |           |           | gestire   |
|           |           |           |           |           | il        |
|           |           |           |           |           | processo  |
|           |           |           |           |           | di storno |
|           |           |           |           |           | di un     |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | (cfr. §   |
|           |           |           |           |           | 2.1.5     |
|           |           |           |           |           | delle     |
|           |           |           |           |           | SANP).    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| marca     | 3         | n         | 1..1      | 1         | Indica se |
| BolloDigi |           |           |           |           | il PSP è  |
| tale      |           |           |           |           | abilitato |
|           |           |           |           |           | a vendere |
|           |           |           |           |           | la marca  |
|           |           |           |           |           | da bollo  |
|           |           |           |           |           | digitale  |
|           |           |           |           |           | (cfr.§    |
|           |           |           |           |           | 2.7 delle |
|           |           |           |           |           | SANP).    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| logoPSP   | 3         | an        | 1..1      |           | Logotipo  |
|           |           |           |           |           | del PSP.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 2         | s         | 1..1      |           | Aggregazi |
| Informati |           |           |           |           | one       |
| vaDetail  |           |           |           |           | corrispon |
|           |           |           |           |           | dente     |
|           |           |           |           |           | alla      |
|           |           |           |           |           | lista di  |
|           |           |           |           |           | informati |
|           |           |           |           |           | ve        |
|           |           |           |           |           | relative  |
|           |           |           |           |           | ai        |
|           |           |           |           |           | servizi   |
|           |           |           |           |           | erogati   |
|           |           |           |           |           | dal PSP.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| infor     | 3         | s         | 1..n      |           | Struttura |
| mativaDet |           |           |           |           | contenent |
| ail       |           |           |           |           | e         |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | relative  |
|           |           |           |           |           | ai        |
|           |           |           |           |           | singoli   |
|           |           |           |           |           | servizi   |
|           |           |           |           |           | erogati   |
|           |           |           |           |           | dal PSP   |
|           |           |           |           |           | attravers |
|           |           |           |           |           | o         |
|           |           |           |           |           | Intermedi |
|           |           |           |           |           | ari       |
|           |           |           |           |           | e Canali. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 35        | Identific |
| ificativo |           |           |           |           | ativo     |
| Intermedi |           |           |           |           | dell’Inte |
| ario      |           |           |           |           | rmediario |
|           |           |           |           |           | del PSP   |
|           |           |           |           |           | che       |
|           |           |           |           |           | fornisce  |
|           |           |           |           |           | lo        |
|           |           |           |           |           | specifico |
|           |           |           |           |           | accesso   |
|           |           |           |           |           | (Canale)  |
|           |           |           |           |           | al PSP    |
|           |           |           |           |           | per       |
|           |           |           |           |           | l'erogazi |
|           |           |           |           |           | one       |
|           |           |           |           |           | del.      |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 35        | Identific |
| ificativo |           |           |           |           | ativo     |
| Canale    |           |           |           |           | del       |
|           |           |           |           |           | Canale    |
|           |           |           |           |           | attravers |
|           |           |           |           |           | o         |
|           |           |           |           |           | il quale  |
|           |           |           |           |           | è erogato |
|           |           |           |           |           | il        |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoV     | 4         | an        | 1..1      | 4         | Tipo di   |
| ersamento |           |           |           |           | versament |
|           |           |           |           |           | o         |
|           |           |           |           |           | associato |
|           |           |           |           |           | allo      |
|           |           |           |           |           | specifico |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | (cfr. §   |
|           |           |           |           |           | 5.3.1     |
|           |           |           |           |           | delle     |
|           |           |           |           |           | SANP).    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| model     | 4         | n         | 1..1      | 2         | Indica    |
| loPagamen |           |           |           |           | quale     |
| to        |           |           |           |           | modello   |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | (cfr.     |
|           |           |           |           |           | capitolo  |
|           |           |           |           |           | 2 delle   |
|           |           |           |           |           | SANP) è   |
|           |           |           |           |           | gestito   |
|           |           |           |           |           | attravers |
|           |           |           |           |           | o         |
|           |           |           |           |           | il canale |
|           |           |           |           |           | specifico |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| prior     | 4         | n         | 1..1      | 2         | Numero    |
| ita       |           |           |           |           | intero    |
|           |           |           |           |           | indicante |
|           |           |           |           |           | la        |
|           |           |           |           |           | priorità  |
|           |           |           |           |           | con la    |
|           |           |           |           |           | quale     |
|           |           |           |           |           | viene     |
|           |           |           |           |           | scelto    |
|           |           |           |           |           | dal       |
|           |           |           |           |           | NodoSPC   |
|           |           |           |           |           | il Canale |
|           |           |           |           |           | per       |
|           |           |           |           |           | l’invio   |
|           |           |           |           |           | al PSP,   |
|           |           |           |           |           | nel caso  |
|           |           |           |           |           | in cui    |
|           |           |           |           |           | quest'ult |
|           |           |           |           |           | imo       |
|           |           |           |           |           | non sia   |
|           |           |           |           |           | specifica |
|           |           |           |           |           | to        |
|           |           |           |           |           | dall’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| canal     | 4         | n         | 1..1      | 1         | Indica se |
| eApp      |           |           |           |           | il        |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | è erogato |
|           |           |           |           |           | attravers |
|           |           |           |           |           | o         |
|           |           |           |           |           | una App.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| servi     | 4         | n         | 0..1      | 1         | Indica se |
| zioAlleIm |           |           |           |           | il        |
| prese     |           |           |           |           | servizio  |
|           |           |           |           |           | erogato   |
|           |           |           |           |           | dal PSP è |
|           |           |           |           |           | destinato |
|           |           |           |           |           | ad un     |
|           |           |           |           |           | utilizzo  |
|           |           |           |           |           | solo da   |
|           |           |           |           |           | parte     |
|           |           |           |           |           | delle     |
|           |           |           |           |           | imprese.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | s         | 0..1      |           | Struttura |
| ificazion |           |           |           |           | che       |
| eServizio |           |           |           |           | contiene  |
|           |           |           |           |           | i dati    |
|           |           |           |           |           | che       |
|           |           |           |           |           | identific |
|           |           |           |           |           | ano       |
|           |           |           |           |           | il        |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | nei       |
|           |           |           |           |           | confronti |
|           |           |           |           |           | della     |
|           |           |           |           |           | clientela |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| nomeS     | 5         | an        | 1..1      | 35        | Nome      |
| ervizio   |           |           |           |           | commercia |
|           |           |           |           |           | le        |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | / app.    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| logoS     | 5         | an        | 1..1      |           | Logotipo  |
| ervizio   |           |           |           |           | del       |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | / app.    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 4         | s         | 1..1      |           | Aggregazi |
| Informazi |           |           |           |           | one       |
| oniServiz |           |           |           |           | di        |
| io        |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | relative  |
|           |           |           |           |           | al        |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | erogato   |
|           |           |           |           |           | dal PSP.. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| infor     | 5         | s         | 1..n      |           | Struttura |
| mazioniSe |           |           |           |           | contenent |
| rvizio    |           |           |           |           | e         |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | specifich |
|           |           |           |           |           | e         |
|           |           |           |           |           | del       |
|           |           |           |           |           | singolo   |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | espresse  |
|           |           |           |           |           | in lingue |
|           |           |           |           |           | diverse.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| codic     | 6         | an        | 1..1      | 2         | Codifica  |
| eLingua   |           |           |           |           | della     |
|           |           |           |           |           | lingua    |
|           |           |           |           |           | nella     |
|           |           |           |           |           | quale     |
|           |           |           |           |           | sono      |
|           |           |           |           |           | fornite   |
|           |           |           |           |           | tutte le  |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | di cui    |
|           |           |           |           |           | alla      |
|           |           |           |           |           | struttura |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oniServiz |
|           |           |           |           |           | io.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| descr     | 6         | an        | 0..1      | 140       | Testo     |
| izioneSer |           |           |           |           | libero in |
| vizio     |           |           |           |           | cui è     |
|           |           |           |           |           | possibile |
|           |           |           |           |           | specifica |
|           |           |           |           |           | re        |
|           |           |           |           |           | natura e  |
|           |           |           |           |           | condizion |
|           |           |           |           |           | i         |
|           |           |           |           |           | (non      |
|           |           |           |           |           | economich |
|           |           |           |           |           | e)        |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dispo     | 6         | an        | 1..1      | 140       | Testo     |
| nibilitaS |           |           |           |           | libero in |
| ervizio   |           |           |           |           | cui è     |
|           |           |           |           |           | possibile |
|           |           |           |           |           | specifica |
|           |           |           |           |           | re        |
|           |           |           |           |           | orari o   |
|           |           |           |           |           | restrizio |
|           |           |           |           |           | ni        |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| limit     | 6         | an        | 0..1      | 140       | Indica    |
| azioniSer |           |           |           |           | eventuali |
| vizio     |           |           |           |           | limitazio |
|           |           |           |           |           | ni        |
|           |           |           |           |           | poste dal |
|           |           |           |           |           | PSP       |
|           |           |           |           |           | nell'erog |
|           |           |           |           |           | azione    |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| urlIn     | 6         | an        | 0..1      | 255       | URL di    |
| formazion |           |           |           |           | una       |
| iCanale   |           |           |           |           | pagina/si |
|           |           |           |           |           | to        |
|           |           |           |           |           | web       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | specifich |
|           |           |           |           |           | e         |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 4         | an        | 0..1      |           | Elenco di |
| ParoleChi |           |           |           |           | parole    |
| ave       |           |           |           |           | chiave.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| parol     | 5         | an        | 1..5      | 16        | Dato a    |
| eChiave   |           |           |           |           | testo     |
|           |           |           |           |           | libero in |
|           |           |           |           |           | cui è     |
|           |           |           |           |           | possibile |
|           |           |           |           |           | inserire  |
|           |           |           |           |           | termini   |
|           |           |           |           |           | utili per |
|           |           |           |           |           | facilitar |
|           |           |           |           |           | e         |
|           |           |           |           |           | la        |
|           |           |           |           |           | ricerca   |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| costi     | 4         | s         | 1..n      |           | Struttura |
| Servizio  |           |           |           |           | che       |
|           |           |           |           |           | contiene  |
|           |           |           |           |           | i costi   |
|           |           |           |           |           | associati |
|           |           |           |           |           | alle      |
|           |           |           |           |           | modalità  |
|           |           |           |           |           | di        |
|           |           |           |           |           | erogazion |
|           |           |           |           |           | e         |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoC     | 5         | n         | 1..1      | 1         | Modalità  |
| ostoTrans |           |           |           |           | di        |
| azione    |           |           |           |           | calcolo   |
|           |           |           |           |           | del costo |
|           |           |           |           |           | della     |
|           |           |           |           |           | transazio |
|           |           |           |           |           | ne.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoC     | 5         | n         | 1..1      | 1         | Tipo di   |
| ommission |           |           |           |           | commissio |
| e         |           |           |           |           | ne        |
|           |           |           |           |           | da        |
|           |           |           |           |           | utilizzar |
|           |           |           |           |           | e         |
|           |           |           |           |           | per il    |
|           |           |           |           |           | calcolo   |
|           |           |           |           |           | del costo |
|           |           |           |           |           | da        |
|           |           |           |           |           | applicare |
|           |           |           |           |           | alla      |
|           |           |           |           |           | transazio |
|           |           |           |           |           | ne.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoC     | 5         | n         | 0..1      | 1         | Canale    |
| analeServ |           |           |           |           | attravers |
| izio      |           |           |           |           | o         |
|           |           |           |           |           | il quale  |
|           |           |           |           |           | è erogato |
|           |           |           |           |           | il        |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| plate     | 5         | n         | 0..1      | 1         | Tipologia |
| aErogazio |           |           |           |           | di        |
| neServizi |           |           |           |           | clientela |
| o         |           |           |           |           | verso la  |
|           |           |           |           |           | quale     |
|           |           |           |           |           | viene     |
|           |           |           |           |           | erogato   |
|           |           |           |           |           | il        |
|           |           |           |           |           | servizio. |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 5         | s         | 1..1      |           | Aggregazi |
| FasceCost |           |           |           |           | one       |
| oServizio |           |           |           |           | delle     |
|           |           |           |           |           | fasce di  |
|           |           |           |           |           | importo.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| fasci     | 6         | s         | 1..8      |           | Occorrenz |
| aCostoSer |           |           |           |           | e         |
| vizio     |           |           |           |           | di una    |
|           |           |           |           |           | struttura |
|           |           |           |           |           | che       |
|           |           |           |           |           | indica,   |
|           |           |           |           |           | per       |
|           |           |           |           |           | fascia di |
|           |           |           |           |           | importo,  |
|           |           |           |           |           | il costo  |
|           |           |           |           |           | della     |
|           |           |           |           |           | transazio |
|           |           |           |           |           | ne.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| impor     | 7         | an        | 1..1      | 12        | Importo   |
| toMassimo |           |           |           |           | massimo   |
| Fascia    |           |           |           |           | della     |
|           |           |           |           |           | fascia.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| costo     | 7         | an        | 1..1      | 12        | Eventuale |
| Fisso     |           |           |           |           | costo     |
|           |           |           |           |           | fisso da  |
|           |           |           |           |           | applicare |
|           |           |           |           |           | al        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | in        |
|           |           |           |           |           | aggiunta  |
|           |           |           |           |           | al costo  |
|           |           |           |           |           | della     |
|           |           |           |           |           | commissio |
|           |           |           |           |           | ne.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| valor     | 7         | an        | 1..1      | 12        | Valore    |
| eCommissi |           |           |           |           | massimo   |
| one       |           |           |           |           | del costo |
|           |           |           |           |           | della     |
|           |           |           |           |           | commissio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | applicabi |
|           |           |           |           |           | le        |
|           |           |           |           |           | al        |
|           |           |           |           |           | singolo   |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | o alla    |
|           |           |           |           |           | transazio |
|           |           |           |           |           | ne.       |
+-----------+-----------+-----------+-----------+-----------+-----------+

La semantica dei dati che devono essere forniti con il "*Catalogo Dati*
*Informativi*" è riportata di seguito, specificando inoltre il formato
del dato, i valori ammessi, nonché i controlli applicabili. I segni ‘+’
tra le parentesi dopo il nome del dato (la barra verticale ‘|’ segnala
il valore 5) indicano il livello d’indentazione dello stesso all’interno
della struttura del “*Catalogo Dati Informativi*”.


**identificativoFlusso (++):**

Identificativo dell’informativa del PSP (catalogo dati
informativi), utile ad identificare la versione del set di
informazioni fornite (esempio: numero di protocollo).

*Controlli:* Deve essere diverso da un valore attribuito in
precedenza a questo dato.

**identificativoPSP (++):**

Codice utilizzato nelle primitive *web service* di colloquio e
negli oggetti scambiati con il NodoSPC.

Il codice è rappresentato generalmente dal codice BIC del PSP (su
8 o 11 posizioni, a seconda dei casi).

In mancanza del codice BIC, o per gestire situazioni particolari,
può essere utilizzato un altro codice, purché individui in modo
univoco il PSP.

**ragioneSociale (++):**

Ragione sociale del PSP.

**informativaMaster (++):**

Struttura che contiene informazioni relative al PSP.

**dataPubblicazione (+++):**

Data e ora di pubblicazione del set di informazioni fornite da
parte del PSP.

*Formato:* ISO 8601 [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].

*Controlli:* Deve essere maggiore del valore attribuito in
precedenza a questo dato.

**dataInizioValidita (+++):**

Data e ora in cui inizierà la validità del flusso informativo
caricato nel NodoSPC.

La validità delle informazioni ha inizio a partire dalle 00:00:00
del giorno indicato.

*Formato:* ISO 8601 [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].

*Controlli:* Deve essere maggiore o uguale all'elemento
**dataPubblicazione** e maggiore della data corrente.

**informazioniPSP (+++):**

Nessuna, una o più occorrenze di una struttura contenente
l'indirizzo di pagine web nelle quali il PSP può inserire
informazioni che lo riguardano. Le pagine possono essere esposte
in più lingue.

**urlInformazioniPSP (++++):**

URL di una sito/pagina web contenente informazioni specifiche del
PSP.

*Controlli:* Deve contenere un indirizzo URL valido.

**stornoPagamento (+++):**

Indica se il PSP è in grado di gestire il processo di storno di
un pagamento (`cfr. § 2.1.4 delle SANP <../07-Capitolo_2/Capitolo2.rst#storno-del-pagamento>`__).

Vale per tutti servizi indicati all’interno di
**listaInformativaDetail.**

*Valori Ammessi:*

1. il PSP non è in grado di gestire il processo di storno

2. è in grado di gestire il processo di storno

**marcaBolloDigitale (+++):**

Indica se il PSP è un concessionario abilitato a vendere la marca
da bollo digitale.

Vale per tutti servizi indicati all’interno di
**listaInformativaDetail.**

*Valori Ammessi:*

1. il PSP non è un concessionario abilitato

2. il PSP è un concessionario abilitato

**logoPSP (+++)**

Logotipo del PSP nel formato 40 x 80 pixel.

*Formato:* L’elemento è trasportato secondo la codifica “base 64
binary”.

**listaInformativaDetail (++):**

Struttura che può contenere uno o più occorrenze associate ai
servizi erogati dal PSP.

**informativaDetail (+++):**

Struttura contenente le informazioni relative ai singoli servizi
erogati dal PSP attraverso Intermediari e Canali.

**identificativoIntermediario (++++):**

Identificativo dell’Intermediario del PSP che fornisce lo
specifico accesso (Canale) al PSP per l'erogazione del. servizio.

*Note*: L'intermediario può coincidere con il PSP stesso.

**identificativoCanale (++++):**

Identificativo del CANALE attraverso il quale viene effettuata la
transazione.

**tipoVersamento (++++):**

Tipo di versamento associato allo specifico servizio.

Assume gli stessi valori dell’omonimo campo della RPT (`cfr. §
5.3.1 delle SANP <../11-Capitolo_5/Capitolo5.rst#richiesta-pagamento-telematico-rpt>`__).

*Controlli:* Il dato deve essere un valore ammesso.

**modelloPagamento (++++):**

Indica quale modello di pagamento (cfr. capitolo 2 delle SANP) è
gestito attraverso il canale specifico.

*Valori Ammessi:*

**Tabella** **10 – Modello di pagamento**

+------------------------------------------------------------+----------+
|                                                            |          |
|  **Modello di pagamento**                                  |**Valore**|
|                                                            |          |
+============================================================+==========+
|                                                            |          |
| Processo di pagamento con re indirizzamento on-line        | 0-1      |
|                                                            |          |
+------------------------------------------------------------+----------+
|                                                            |          |
| Processo di pagamento con autorizzazione gestita dal PSP   | 2        |
|                                                            |          |
+------------------------------------------------------------+----------+
|                                                            |          |
| Processo di pagamento attivato presso il PSP               | 4        |
|                                                            |          |
+------------------------------------------------------------+----------+

**priorita (++++):**

Se ad un Canale corrispondono più dati tipoVersamento, un valore
differente di priorità consente al PSP di specificare una
preferenza.

*Formato:* Numero intero cui, a un valore minore, corrisponde una
priorità più elevata.

**canaleApp (++++):**

Indica se il servizio è erogato attraverso una App messa a
disposizione dal PSP.

*Valori Ammessi:*

1. il canale non fa riferimento ad una App del PSP

2. il canale fa riferimento ad una App del PSP

**servizioAlleImprese (++++):**

**Il dato è stato inserito per usi futuri. Può non essere valorizzato**.
Indica che lo specifico servizio erogato dal PSP è
destinato ad un utilizzo solo da parte delle imprese.

*Valori Ammessi:*

1. il servizio non è dedicato ad una clientela corporate

2. il servizio è dedicato ad una clientela corporate

**identificazioneServizio (++++):**

Struttura che contiene i dati che identificano il servizio nei
confronti della clientela.

*Controlli:* Obbligatorio se il dato canaleApp è uguale a 1.

**nomeServizio (++++):**

Nome commerciale del servizio erogato o della app messa
disposizione dal PSP.

**logoServizio (++++):**

Logotipo del servizio / app nel formato 40 x 80 pixel.

*Formato:* L’elemento è trasportato secondo la codifica “base 64
binary”.

**listaInformazioniServizio (++++):**

Aggregazione di informazioni relative al servizio erogato dal
PSP.

**informazioniServizio (++++):**

Una o più occorrenze di una struttura contenente informazioni
specifiche del singolo servizio erogato dal PSP espresse in
lingue diverse (di cui almeno una in lingua italiana).

**codiceLingua (+++++):**

Codifica della lingua nella quale sono fornite tutte le
informazioni di cui alla struttura informazioniServizio.

*Formato:* ISO 693-1.

*Valori Ammessi:*

**Tabella** **11 – Codici ISO 693-1 previsti per il WISP**

+----------------------+----------------+
| **Codice ISO 693-1** | **Linguaggio** |
+======================+================+
| IT                   | Italiano       |
+----------------------+----------------+
| EN                   | Inglese        |
+----------------------+----------------+
| FR                   | Francese       |
+----------------------+----------------+
| DE                   | Tedesco        |
+----------------------+----------------+
| SL                   | Sloveno        |
+----------------------+----------------+


*Controlli:* Deve essere presente almeno un'occorrenza contenente
il valore IT.

**descrizioneServizio (+++++):**

Breve testo libero in cui è possibile specificare la natura del
servizio nella lingua di cui al dato codiceLingua.

**disponibilitaServizio (+++++):**

Breve testo libero in cui è possibile specificare orari o
restrizioni nell'erogazione tecnica del servizio, nella lingua di
cui al dato codiceLingua.

**limitazioniServizio (+++++):**

**Il dato è stato inserito per usi futuri. Può non essere valorizzato**.
Informazioni in formato testo che riportano
eventuali limitazioni poste dal PSP nell'erogazione del servizio,
nella lingua di cui al dato codiceLingua (esempio: Il servizio è
dedicato ad una particolare categoria di professionisti o
imprese).

Tale informazione verrà evidenziata dal WISP per preventivamente
metterne al corrente l'utilizzatore finale.

**urlInformazioniCanale (+++++):**

URL di una sito/pagina web contenente informazioni relative allo
specifico servizio.

*Controlli:* Deve contenere un indirizzo URL valido.

**listaParoleChiave (++++):**

Elenco di parole chiave,

**paroleChiave (++++):**

Da una a cinque occorrenze che saranno utilizzate per la funzione
di ricerca.

*Valori Ammessi:*

-  American Express

-  Diners

-  Maestro

-  Mastercard

-  MyBank

-  PagoBancomat

-  PayPal

-  Visa

-  Visa Electron

-  V-Pay

-  Wallet

**costiServizio (++++):**

Struttura contenente le informazioni necessarie a caratterizzare
il costo del servizio erogato dal PSP.

**tipoCostoTransazione (++++):**

**Il dato è stato inserito per usi futuri. Allo stato è ammesso
solo il valore 1.** Modalità di calcolo del costo nel caso in cui
siano presenti più pagamenti in una singola transazione, sia che
si tratti di una RPT con più pagamenti, sia che si tratti di un
carrello di RPT.

*Valori Ammessi:*

1. numero, il costo totale sarà calcolato in base al numero dei
pagamenti presenti nella transazione

2. valore, il costo sarà calcolato sulla base dell’importo della
transazione e degli altri parametri di costo specificati dal
PSP



*Impostazioni:* se il PSP associa all'elemento
tipoCostoTransazione il valore 0 (costo calcolato in base al
numero dei pagamenti) allora:

- il numero delle occorrenze della struttura fasceCostoServizio dovrà
  essere pari a 1.

- l'elemento tipoCommissione dovrà essere 0 (in valore assoluto).

- l'elemento costoFisso dovrà essere 0.

**tipoCommissione (++++):**

**Il dato è stato inserito per usi futuri. Allo stato è ammesso solo il valore 0.**
Tipo di commissione da utilizzare per il
calcolo del costo da applicare alla transazione.

*Valori Ammessi:*

1. Valore assoluto

2. Percentuale


*Impostazioni:* Se il dato tipoCostoTransazione assume il valore
0, allora il dato tipoCommissione dovrà essere 0.

**tipoCanaleServizio (++++):**

**Il dato è definito, ma non utilizzato nella corrente versione**
**del Catalogo dati Informati.**

Modalità attraverso il quale è erogato il servizio.

*Valori Ammessi:*

1. Presso i propri sportelli

2. On-line (home banking o Portale dedicato)

3. Mobile banking (app)

4. Phone banking

5. ATM

**plateaErogazioneServizio (++++):**

**Il dato è definito, ma non utilizzato nella corrente versione**
**del Catalogo dati Informativi.**

Tipologia di clientela verso la quale viene erogato il servizio.

*Valori Ammessi:*

1. Verso la propria clientela

2. Verso tutti

3. Verso tutti, solo con bollettino postale

**listaFasceCostoServizio (++++):**

Una più occorrenze di una struttura organizzata per “fasce” di
importo, contenente informazioni relative ai costi della singola
fascia.

*Controlli:* Se l'elemento tipoCostoTransazione assume il valore
0, allora è consentita un’unica occorrenza.

**fasciaCostoServizio (+++++):**

Una più occorrenze di una struttura organizzata per “fasce” di
importo, contenente informazioni relative ai costi della singola
fascia.

*Controlli:* Se l'elemento tipoCostoTransazione assume il valore
0, allora è consentita un’unica occorrenza.

**importoMassimoFascia (++++++):**

Importo massimo della fascia che contiene tutti i parametri di
costo del servizio.

*Formato:* Campo numerico (due cifre per la parte decimale, il
separatore dei centesimi è il punto “.”).

*Note:* L’ultima fascia può contenere il valore 999999999.99, in
questo caso assumere il significato di importo massimo
contrattualizzato con il cliente per il servizio scelto.

Si tenga presente che il limite minimo della fascia è
rappresentato dal valore **importoMassimoFascia** relativo alla
fascia precedente aumentato di 1. Per la prima fascia tale valore
è zero.

*Filtri*: importo della transazione (vedi § 2.1 del documento
"*Wizard Interattivo di Scelta del PSP - Evoluzione della user
experience*").

**costoFisso (++++++):**

Eventuale costo fisso di commissione da applicare al pagamento in
aggiunta al costo della commissione.

*Formato:* Campo numerico (due cifre per la parte decimale, il
separatore dei centesimi è il punto “.”).

Nel caso che il dato tipoCostoTransazione (vedi sopra) assuma
valore 0 (valore attualmente non ammesso), allora il dato
costoFisso dovrà essere 0.

**valoreCommissione (++++++):**

Valore massimo del costo della commissione applicabile al singolo
pagamento o alla transazione nel suo complesso, qualora fosse
composta da una RPT con più pagamenti oppure da un insieme di RPT
(carrello).

*Formato:* Campo numerico (due cifre per la parte decimale, il
separatore dei centesimi è il punto “.”).


Il “*Catalogo Dati Informativi*” è quindi il documento informatico,
inviato dal Nodo SPC ad ogni Ente Creditore, che contiene l’elenco dei
prestatori di servizi di pagamento aderenti al sistema pagoPA. Tale
elenco ha valenza giornaliera dalle ore 0 alle ore 24.

Le informazioni sono codificate in un file XML secondo lo schema di
Tabella 12 e devono essere inviate al Nodo dei Pagamenti-SPC via PEC dal
PSP, con le modalità indicate sul sito dell’Agenzia. per l’Italia
Digitale.

**Tabella** **12 - Tracciato XML per comunicazione “Catalogo Dati Informativi”**


+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **c**     | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| lista     | 1         | s         | 1..1      |           | Lista     |
| Informati |           |           |           |           | delle     |
| vePSP     |           |           |           |           | informati |
|           |           |           |           |           | ve        |
|           |           |           |           |           | PSP       |
|           |           |           |           |           | valide    |
|           |           |           |           |           | nella     |
|           |           |           |           |           | giornata  |
|           |           |           |           |           | corrente  |
|           |           |           |           |           | (hh       |
|           |           |           |           |           | 00-24)    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| infor     | 1         | s         | 1..n      |           | Numero    |
| mativaPSP |           |           |           |           | non       |
|           |           |           |           |           | definito  |
|           |           |           |           |           | di        |
|           |           |           |           |           | occorrenz |
|           |           |           |           |           | e         |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | informati |
|           |           |           |           |           | vaPSP     |
|           |           |           |           |           | definita  |
|           |           |           |           |           | nella     |
|           |           |           |           |           | tabella   |
|           |           |           |           |           | precedent |
|           |           |           |           |           | e         |
+-----------+-----------+-----------+-----------+-----------+-----------+

Flusso “Totali di Traffico” per gli Enti Creditori
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Flusso “Totali di Traffico” per gli Enti Creditori:

È il flusso informatico inviato dal Nodo dei Pagamenti-SPC all’Ente
Creditore o al suo intermediario e contenente tutte le interazioni (RPT
e RT) transitate attraverso il NodoSPC di stretta pertinenza del singolo
richiedente.

**Tabella** **13 - Tracciato XML del flusso "Totali di Traffico - EC"**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| versi     | 1         | an        | 1..1      | 1..16     | Versione  |
| oneOggett |           |           |           |           | che       |
| o         |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | l’oggetto |
|           |           |           |           |           | scambiato |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 1         | an        | 1..1      | 1..35     | Identific |
| ificativo |           |           |           |           | ativo     |
| Flusso    |           |           |           |           | del       |
|           |           |           |           |           | Flusso    |
|           |           |           |           |           | specifico |
|           |           |           |           |           | di        |
|           |           |           |           |           | Quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | generato  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataO     | 1         | an        | 1..1      | 19        | Data e    |
| raFlusso  |           |           |           |           | ora di    |
|           |           |           |           |           | generazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | del       |
|           |           |           |           |           | flusso,   |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| sogge     | 1         | s         | 1..1      | 1..35     | Elemento  |
| ttoRichie |           |           |           |           | che       |
| denteFlus |           |           |           |           | contiene  |
| so        |           |           |           |           | il        |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | che       |
|           |           |           |           |           | richiede  |
|           |           |           |           |           | il flusso |
|           |           |           |           |           | di        |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | al Nodo   |
|           |           |           |           |           | mediante  |
|           |           |           |           |           | primitiva |
|           |           |           |           |           | .         |
|           |           |           |           |           |           |
|           |           |           |           |           | Questo    |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | è stato   |
|           |           |           |           |           | specifica |
|           |           |           |           |           | to        |
|           |           |           |           |           | nella     |
|           |           |           |           |           | richiesta |
|           |           |           |           |           | PEC dal   |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | finale    |
|           |           |           |           |           | del       |
|           |           |           |           |           | flusso.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..35     | Identific |
| ificativo |           |           |           |           | ativo     |
| Intermedi |           |           |           |           | dell’inte |
| arioPA    |           |           |           |           | rmediario |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che può   |
|           |           |           |           |           | richieder |
|           |           |           |           |           | e         |
|           |           |           |           |           | il flusso |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataI     | 1         | an        | 1..1      | 19        | Data di   |
| nizioPeri |           |           |           |           | inizio    |
| odo       |           |           |           |           | periodo   |
|           |           |           |           |           | di        |
|           |           |           |           |           | rilevazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | dei dati  |
|           |           |           |           |           | che fanno |
|           |           |           |           |           | parte dei |
|           |           |           |           |           | totali di |
|           |           |           |           |           | traffico  |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataF     | 1         | an        | 1..1      | 19        | Data di   |
| inePeriod |           |           |           |           | fine      |
| o         |           |           |           |           | periodo   |
|           |           |           |           |           | di        |
|           |           |           |           |           | rilevazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | dei dati  |
|           |           |           |           |           | che fanno |
|           |           |           |           |           | parte dei |
|           |           |           |           |           | totali di |
|           |           |           |           |           | traffico  |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]  - |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| uadr      | 1         | s         | 1..1      |           | Aggregazi |
| aturaRPT  |           |           |           |           | one       |
|           |           |           |           |           | relativa  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | delle     |
|           |           |           |           |           | RPT.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 2         | s         | 1..1      |           | Aggregazi |
| Totali    |           |           |           |           | one       |
|           |           |           |           |           | corrispon |
|           |           |           |           |           | dente     |
|           |           |           |           |           | alla      |
|           |           |           |           |           | lista dei |
|           |           |           |           |           | totaliAgg |
|           |           |           |           |           | regati    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 3         | s         | 0..n      |           | Aggregazi |
| iAggregat |           |           |           |           | one       |
| i         |           |           |           |           | dei       |
|           |           |           |           |           | totali,   |
|           |           |           |           |           | relativi  |
|           |           |           |           |           | alle RPT  |
|           |           |           |           |           | inviate   |
|           |           |           |           |           | dal       |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | a cui è   |
|           |           |           |           |           | riferita  |
|           |           |           |           |           | la        |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | (Dominio  |
|           |           |           |           |           | o         |
|           |           |           |           |           | Intermedi |
|           |           |           |           |           | ario      |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | ).        |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| DominioMi |           |           |           |           | del       |
| ttente    |           |           |           |           | Dominio   |
|           |           |           |           |           | della     |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che invia |
|           |           |           |           |           | la RPT    |
|           |           |           |           |           | mediante  |
|           |           |           |           |           | l’Interme |
|           |           |           |           |           | diario    |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| StazioneI |           |           |           |           | della     |
| ntermedia |           |           |           |           | StazioneI |
| rioPAMitt |           |           |           |           | ntermedia |
| ente      |           |           |           |           | rioPA     |
|           |           |           |           |           | mittente  |
|           |           |           |           |           | tecnico   |
|           |           |           |           |           | delle RPT |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| Intermedi |           |           |           |           | dell’Inte |
| arioPSPDe |           |           |           |           | rmediario |
| stinatari |           |           |           |           | del PSP   |
| o         |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | delle RPT |
|           |           |           |           |           | transitat |
|           |           |           |           |           | e         |
|           |           |           |           |           | dal Nodo  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iInAttesa |           |           |           |           | relativi  |
|           |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RPT di    |
|           |           |           |           |           | cui non   |
|           |           |           |           |           | si è      |
|           |           |           |           |           | ancora    |
|           |           |           |           |           | ricevuta  |
|           |           |           |           |           | la        |
|           |           |           |           |           | conferma  |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..15     | totale    |
| eOggetti  |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iConsegna |           |           |           |           | relativi  |
| te        |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RPT       |
|           |           |           |           |           | confermat |
|           |           |           |           |           | i         |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..15     | totale    |
| eOggetti  |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| quadr     | 1         | s         | 1..1      |           | Aggregazi |
| aturaRT   |           |           |           |           | one       |
|           |           |           |           |           | relativa  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | delle RT. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 2         | s         | 1..1      |           | Elemento  |
| Totali    |           |           |           |           | che       |
|           |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | la lista  |
|           |           |           |           |           | dei       |
|           |           |           |           |           | totali    |
|           |           |           |           |           | aggregati |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 3         | s         | 0..1      |           | Aggregazi |
| iAggregat |           |           |           |           | one       |
| i         |           |           |           |           | dei       |
|           |           |           |           |           | totali,   |
|           |           |           |           |           | relativi  |
|           |           |           |           |           | alle RT   |
|           |           |           |           |           | inviate   |
|           |           |           |           |           | al        |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | a cui è   |
|           |           |           |           |           | riferita  |
|           |           |           |           |           | la        |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | (Dominio  |
|           |           |           |           |           | o         |
|           |           |           |           |           | Intermedi |
|           |           |           |           |           | ario      |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | ).        |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| Intermedi |           |           |           |           | dell’Inte |
| arioPSPMi |           |           |           |           | rmediario |
| ttente    |           |           |           |           | PSP       |
|           |           |           |           |           | mittente  |
|           |           |           |           |           | della RT  |
|           |           |           |           |           | generata  |
|           |           |           |           |           | dal PSP   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| DominioDe |           |           |           |           | del       |
| stinatari |           |           |           |           | Dominio   |
| o         |           |           |           |           | della     |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | destinata |
|           |           |           |           |           | ria       |
|           |           |           |           |           | della RT  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| StazioneI |           |           |           |           | StazioneI |
| ntermedia |           |           |           |           | ntermedia |
| rioPADest |           |           |           |           | rioPA     |
| inatario  |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | delle RT  |
|           |           |           |           |           | transitat |
|           |           |           |           |           | e         |
|           |           |           |           |           | dal Nodo  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iInAttesa |           |           |           |           | relativi  |
|           |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RT di cui |
|           |           |           |           |           | non si è  |
|           |           |           |           |           | ancora    |
|           |           |           |           |           | ricevuta  |
|           |           |           |           |           | la        |
|           |           |           |           |           | conferma  |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..15     | totale    |
| eOggetti  |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iConsegna |           |           |           |           | relativi  |
| te        |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RT        |
|           |           |           |           |           | confermat |
|           |           |           |           |           | i         |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| totale    | 5         | an        | 1..1      | 1..15     | totale    |
| Oggetti   |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+

Flusso “Totali di Traffico” per i prestatori di servizi di pagamento
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Flusso “Totali di Traffico” per i prestatori di servizi di pagamento:

È il flusso informatico inviato dal Nodo dei Pagamenti-SPC al prestatore
di servizi di pagamento o al suo intermediario contenente tutte le
interazioni (RPT e RT) transitate attraverso il Nodo dei Pagamenti-SPC e
di stretta pertinenza del singolo richiedente.

**Tabella** **14 - Tracciato XML del flusso "Totali di Traffico - PSP"**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| versi     | 1         | an        | 1..1      | 1..16     | Versione  |
| oneOggett |           |           |           |           | che       |
| o         |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | l’oggetto |
|           |           |           |           |           | scambiato |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 1         | an        | 1..1      | 1..35     | Identific |
| ificativo |           |           |           |           | ativo     |
| Flusso    |           |           |           |           | del       |
|           |           |           |           |           | Flusso    |
|           |           |           |           |           | specifico |
|           |           |           |           |           | di        |
|           |           |           |           |           | Quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | generato  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataO     | 1         | an        | 1..1      | 19        | Data e    |
| raFlusso  |           |           |           |           | ora di    |
|           |           |           |           |           | generazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | del       |
|           |           |           |           |           | flusso    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| sogge     | 1         | s         | 1..1      | 1..35     | Elemento  |
| ttoRichie |           |           |           |           | che       |
| denteFLus |           |           |           |           | contiene  |
| so        |           |           |           |           | il        |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | che       |
|           |           |           |           |           | richiede  |
|           |           |           |           |           | il flusso |
|           |           |           |           |           | di        |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | al Nodo   |
|           |           |           |           |           | mediante  |
|           |           |           |           |           | primitiva |
|           |           |           |           |           | .         |
|           |           |           |           |           |           |
|           |           |           |           |           | Questo    |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | è stato   |
|           |           |           |           |           | specifica |
|           |           |           |           |           | to        |
|           |           |           |           |           | nella     |
|           |           |           |           |           | richiesta |
|           |           |           |           |           | PEC dal   |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | finale    |
|           |           |           |           |           | del       |
|           |           |           |           |           | flusso.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| Intermedi |           |           |           |           | dell’inte |
| arioPSP   |           |           |           |           | rmediario |
|           |           |           |           |           | PSP che   |
|           |           |           |           |           | può       |
|           |           |           |           |           | richieder |
|           |           |           |           |           | e         |
|           |           |           |           |           | il flusso |
+-----------+-----------+-----------+-----------+-----------+-----------+
| quadr     | 1         | s         | 1..1      |           | Aggregazi |
| aturaRPT  |           |           |           |           | one       |
|           |           |           |           |           | relativa  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | delle     |
|           |           |           |           |           | RPT.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 2         | s         | 1..1      |           | Aggregazi |
| Totali    |           |           |           |           | one       |
|           |           |           |           |           | corrispon |
|           |           |           |           |           | dente     |
|           |           |           |           |           | alla      |
|           |           |           |           |           | lista dei |
|           |           |           |           |           | totaliAgg |
|           |           |           |           |           | regati    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataI     | 1         | an        | 1..1      | 19        | Data di   |
| nizioPeri |           |           |           |           | inizio    |
| odo       |           |           |           |           | periodo   |
|           |           |           |           |           | di        |
|           |           |           |           |           | rilevazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | dei dati  |
|           |           |           |           |           | che fanno |
|           |           |           |           |           | parte dei |
|           |           |           |           |           | totali di |
|           |           |           |           |           | traffico  |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataF     | 1         | an        | 1..1      | 19        | Data di   |
| inePeriod |           |           |           |           | fine      |
| o         |           |           |           |           | periodo   |
|           |           |           |           |           | di        |
|           |           |           |           |           | rilevazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | dei dati  |
|           |           |           |           |           | che fanno |
|           |           |           |           |           | parte dei |
|           |           |           |           |           | totali di |
|           |           |           |           |           | traffico  |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           | T[hh]:[mm |
|           |           |           |           |           | ]:[ss]    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| quadr     | 1         | s         | 1..1      |           | Aggregazi |
| aturaRPT  |           |           |           |           | one       |
|           |           |           |           |           | relativa  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | delle     |
|           |           |           |           |           | RPT.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 2         | s         | 1..1      |           | Elemento  |
| Totali    |           |           |           |           | che       |
|           |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | la lista  |
|           |           |           |           |           | dei       |
|           |           |           |           |           | totali    |
|           |           |           |           |           | aggregati |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 3         | s         | 0..n      |           | Aggregazi |
| iAggregat |           |           |           |           | one       |
| i         |           |           |           |           | dei       |
|           |           |           |           |           | totali,   |
|           |           |           |           |           | relativi  |
|           |           |           |           |           | alle RPT  |
|           |           |           |           |           | inviate   |
|           |           |           |           |           | dal       |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | a cui è   |
|           |           |           |           |           | riferita  |
|           |           |           |           |           | la        |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | (PSP o    |
|           |           |           |           |           | Intermedi |
|           |           |           |           |           | ario      |
|           |           |           |           |           | PSP).     |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | s         | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| DominioMi |           |           |           |           | dell’Ente |
| ttente    |           |           |           |           | Creditore |
|           |           |           |           |           | che invia |
|           |           |           |           |           | la RPT.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | s         | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| PSPDestin |           |           |           |           | della PSP |
| atario    |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | finale    |
|           |           |           |           |           | della     |
|           |           |           |           |           | RPT.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | s         | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| CanaleDes |           |           |           |           | del       |
| tinatario |           |           |           |           | Canale    |
|           |           |           |           |           | dell’Inte |
|           |           |           |           |           | rmediario |
|           |           |           |           |           | del PSP,  |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | delle RPT |
|           |           |           |           |           | transitat |
|           |           |           |           |           | e         |
|           |           |           |           |           | dal Nodo. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iInAttesa |           |           |           |           | relativi  |
|           |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RPT di    |
|           |           |           |           |           | cui non   |
|           |           |           |           |           | si è      |
|           |           |           |           |           | ancora    |
|           |           |           |           |           | ricevuta  |
|           |           |           |           |           | la        |
|           |           |           |           |           | conferma  |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..15     | totale    |
| eOggetti  |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iConsegna |           |           |           |           | relativi  |
| te        |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RPT       |
|           |           |           |           |           | confermat |
|           |           |           |           |           | i         |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | tecnico   |
|           |           |           |           |           | (canale   |
|           |           |           |           |           | dell’Inte |
|           |           |           |           |           | rmediario |
|           |           |           |           |           | )         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..15     | totale    |
| eOggetti  |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| quadr     | 1         | s         | 1..1      |           | Aggregazi |
| aturaRT   |           |           |           |           | one       |
|           |           |           |           |           | relativa  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | delle RT. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| lista     | 2         | s         | 1..1      |           | Elemento  |
| Totali    |           |           |           |           | che       |
|           |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | la lista  |
|           |           |           |           |           | dei       |
|           |           |           |           |           | totali    |
|           |           |           |           |           | aggregati |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 3         | s         | 0..n      |           | Aggregazi |
| iAggregat |           |           |           |           | one       |
| i         |           |           |           |           | dei       |
|           |           |           |           |           | totali,   |
|           |           |           |           |           | relativi  |
|           |           |           |           |           | alle RT   |
|           |           |           |           |           | inviate   |
|           |           |           |           |           | dal       |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | a cui è   |
|           |           |           |           |           | riferita  |
|           |           |           |           |           | la        |
|           |           |           |           |           | quadratur |
|           |           |           |           |           | a         |
|           |           |           |           |           | (PSP o    |
|           |           |           |           |           | Intermedi |
|           |           |           |           |           | ario      |
|           |           |           |           |           | PSP).     |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| PSPMitten |           |           |           |           | del PSP   |
| te        |           |           |           |           | che ha    |
|           |           |           |           |           | generato  |
|           |           |           |           |           | la RT     |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 4         | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| CanaleMit |           |           |           |           | del       |
| tente     |           |           |           |           | Canale    |
|           |           |           |           |           | dell’Inte |
|           |           |           |           |           | rmediario |
|           |           |           |           |           | PSP,      |
|           |           |           |           |           | mittente  |
|           |           |           |           |           | tecnico   |
|           |           |           |           |           | della RT. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     |           | an        | 1..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| DominioDe |           |           |           |           | dell’Ente |
| stinatari |           |           |           |           | Creditore |
| o         |           |           |           |           | che       |
|           |           |           |           |           | riceve la |
|           |           |           |           |           | RT.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iInAttesa |           |           |           |           | relativi  |
|           |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RT di cui |
|           |           |           |           |           | non si è  |
|           |           |           |           |           | ancora    |
|           |           |           |           |           | ricevuta  |
|           |           |           |           |           | la        |
|           |           |           |           |           | conferma  |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | tecnico   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..15     | totale    |
| eOggetti  |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 4         | s         | 1..1      |           | totali    |
| iConsegna |           |           |           |           | relativi  |
| te        |           |           |           |           | agli      |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | RT        |
|           |           |           |           |           | confermat |
|           |           |           |           |           | e         |
|           |           |           |           |           | dal       |
|           |           |           |           |           | destinata |
|           |           |           |           |           | rio       |
|           |           |           |           |           | tecnico   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| total     | 5         | an        | 1..1      | 1..18     | totale    |
| eImporti  |           |           |           |           | degli     |
|           |           |           |           |           | importi   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| totale    | 5         | an        | 1..1      | 1..15     | totale    |
| Oggetti   |           |           |           |           | relativo  |
|           |           |           |           |           | al numero |
|           |           |           |           |           | degli     |
|           |           |           |           |           | oggetti   |
|           |           |           |           |           | nello     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | cui al    |
|           |           |           |           |           | livello   |
|           |           |           |           |           | superiore |
|           |           |           |           |           | di        |
|           |           |           |           |           | aggregazi |
|           |           |           |           |           | one       |
+-----------+-----------+-----------+-----------+-----------+-----------+

Si noti che l'elemento identificativoIntermediarioPAMittente, presente
nella versione 1.6.1, è stato sostituito con l'elemento
identificativoDominioMittente.

Si noti che l'elemento identificativoIntermediarioPADestinatario,
presente nella versione 1.6.1, è stato eliminato sostituito con
l'elemento identificativoDominioDestinatario.

Messaggio di conferma ricezione della RT (ACK)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Messaggio di conferma ricezione della RT (ACK):

È il documento informatico con il quale il Nodo dei Pagamenti-SPC
conferma al prestatore di servizi di pagamento la ricezione della RT
richiesta con l'apposita primitiva **pspInviaAckRT** (`vedi § 9.2.2.3 <../16-Capitolo_9/Capitolo9.rst#pspinviaackrt>`__).

Si precisa che il messaggio era già presente nelle versioni precedenti
delle specifiche attuative, ma non erano stati formalmente specificati
gli elementi componenti il messaggio stesso, ora indicati nella Tabella
15.

**Tabella** **15 - Elementi componenti il Messaggio di ACK**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| ident     | 1         | an        | 1..1      | 35        | Identific |
| ificativo |           |           |           |           | ativo     |
| ACK       |           |           |           |           | legato    |
|           |           |           |           |           | alla      |
|           |           |           |           |           | trasmissi |
|           |           |           |           |           | one       |
|           |           |           |           |           | del file  |
|           |           |           |           |           | di ACK.   |
|           |           |           |           |           |           |
|           |           |           |           |           | Deve      |
|           |           |           |           |           | essere    |
|           |           |           |           |           | univoco   |
|           |           |           |           |           | nell’ambi |
|           |           |           |           |           | to        |
|           |           |           |           |           | della     |
|           |           |           |           |           | stessa    |
|           |           |           |           |           | data      |
|           |           |           |           |           | definita  |
|           |           |           |           |           | da        |
|           |           |           |           |           | dataOraAC |
|           |           |           |           |           | K.        |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataO     | 1         | an        | 1..1      | 19        | Data e    |
| raACK     |           |           |           |           | ora di    |
|           |           |           |           |           | generazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           | del       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | di ACK    |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-[M |
|           |           |           |           |           | M]-[DD]T[ |
|           |           |           |           |           | hh]:[mm]: |
|           |           |           |           |           | [ss]      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| mitte     | 1         | an        | 1..1      | 1..25     | Mittente  |
| nteACK    |           |           |           |           | del       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | di ACK    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| datiM     | 1         | s         | 1..1      |           | Dati      |
| essaggioR |           |           |           |           | relativi  |
| eferenzia |           |           |           |           | al        |
| to        |           |           |           |           | messaggio |
|           |           |           |           |           | referenzi |
|           |           |           |           |           | ato       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..35     | Campo     |
| ificativo |           |           |           |           | alfanumer |
| Dominio   |           |           |           |           | ico       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | che       |
|           |           |           |           |           | inoltra   |
|           |           |           |           |           | la        |
|           |           |           |           |           | richiesta |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..35     | Riferimen |
| ificativo |           |           |           |           | to        |
| UnivocoVe |           |           |           |           | univoco   |
| rsamento  |           |           |           |           | assegnato |
|           |           |           |           |           | al        |
|           |           |           |           |           | versament |
|           |           |           |           |           | o         |
|           |           |           |           |           | dall’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
|           |           |           |           |           |           |
|           |           |           |           |           | Si faccia |
|           |           |           |           |           | riferimen |
|           |           |           |           |           | to        |
|           |           |           |           |           | al        |
|           |           |           |           |           | capitolo  |
|           |           |           |           |           | 7.1 della |
|           |           |           |           |           | presente  |
|           |           |           |           |           | Sezione.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Codic     | 2         | an        | 1..1      | 1..35     | Codice    |
| eContesto |           |           |           |           | univoco   |
| Pagamento |           |           |           |           | necessari |
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
|           |           |           |           |           | o.        |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..35     | Campo     |
| ificativo |           |           |           |           | alfanumer |
| Messaggio |           |           |           |           | ico       |
| Referenzi |           |           |           |           | contenent |
| ato       |           |           |           |           | e         |
|           |           |           |           |           | l'identif |
|           |           |           |           |           | icativo   |
|           |           |           |           |           | del       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | referenzi |
|           |           |           |           |           | ato,      |
|           |           |           |           |           | legato    |
|           |           |           |           |           | alla      |
|           |           |           |           |           | trasmissi |
|           |           |           |           |           | one       |
|           |           |           |           |           | della     |
|           |           |           |           |           | Ricevuta  |
|           |           |           |           |           | Telematic |
|           |           |           |           |           | a.        |
|           |           |           |           |           |           |
|           |           |           |           |           | Si        |
|           |           |           |           |           | riferisce |
|           |           |           |           |           | al campo  |
|           |           |           |           |           | identific |
|           |           |           |           |           | ativoMess |
|           |           |           |           |           | aggio     |
|           |           |           |           |           | presente  |
|           |           |           |           |           | nel       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | di        |
|           |           |           |           |           | riferimen |
|           |           |           |           |           | to.       |
|           |           |           |           |           |           |
|           |           |           |           |           | Risulta   |
|           |           |           |           |           | univoco   |
|           |           |           |           |           | nell’ambi |
|           |           |           |           |           | to        |
|           |           |           |           |           | della     |
|           |           |           |           |           | stessa    |
|           |           |           |           |           | data      |
|           |           |           |           |           | riferita  |
|           |           |           |           |           | all’eleme |
|           |           |           |           |           | nto       |
|           |           |           |           |           | dataOraMe |
|           |           |           |           |           | ssaggioRe |
|           |           |           |           |           | ferenziat |
|           |           |           |           |           | o.        |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataO     | 2         | an        | 1..1      | 19        | Data e    |
| raMessagg |           |           |           |           | ora di    |
| ioReferen |           |           |           |           | generazio |
| ziato     |           |           |           |           | ne        |
|           |           |           |           |           | del       |
|           |           |           |           |           | messaggio |
|           |           |           |           |           | referenzi |
|           |           |           |           |           | ato       |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY]-[M |
|           |           |           |           |           | M]-[DD]T[ |
|           |           |           |           |           | hh]:[mm]: |
|           |           |           |           |           | [ss]      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipol     | 2         | an        | 1..1      | 1..16     | Tipologia |
| ogiaMessa |           |           |           |           | di        |
| ggioRefer |           |           |           |           | messaggio |
| enziato   |           |           |           |           | referenzi |
|           |           |           |           |           | ato       |
|           |           |           |           |           | può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | uno dei   |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | **RPT**   |
|           |           |           |           |           |           |
|           |           |           |           |           | **RT**    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| mitte     | 2         | an        | 1..1      | 1..25     | Mittente  |
| nteMessag |           |           |           |           | del       |
| gioRefere |           |           |           |           | messaggio |
| nziato    |           |           |           |           | al quale  |
|           |           |           |           |           | l'ACK si  |
|           |           |           |           |           | riferisce |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| infor     | 1         | s         | 1..1      |           | Informazi |
| mazioniSt |           |           |           |           | oni       |
| atoMessag |           |           |           |           | sullo     |
| gioRefere |           |           |           |           | stato del |
| nziato    |           |           |           |           | messaggio |
|           |           |           |           |           | referenzi |
|           |           |           |           |           | ato       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| stato     | 2         | an        | 1..1      | 1.16      | Stato del |
| Messaggio |           |           |           |           | messaggio |
| Referenzi |           |           |           |           | referenzi |
| ato       |           |           |           |           | ato.      |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | **ACTC**  |
|           |           |           |           |           | (accettat |
|           |           |           |           |           | o)        |
|           |           |           |           |           |           |
|           |           |           |           |           | **RJCT**  |
|           |           |           |           |           | (rifiutat |
|           |           |           |           |           | o)        |
+-----------+-----------+-----------+-----------+-----------+-----------+
| motiv     | 2         | s         | 0..1      |           | Nel caso  |
| azioneSta |           |           |           |           | di stato  |
| toErrato  |           |           |           |           | rifiutato |
|           |           |           |           |           | ,         |
|           |           |           |           |           | dà        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | riguardo  |
|           |           |           |           |           | all'error |
|           |           |           |           |           | e         |
|           |           |           |           |           | riscontra |
|           |           |           |           |           | to.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| codic     | 3         | an        | 1..1      | 1..10     | Codice di |
| eErrore   |           |           |           |           | errore.   |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i valori  |
|           |           |           |           |           | indicati  |
|           |           |           |           |           | nella     |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 53 a      |
|           |           |           |           |           | pagina    |
|           |           |           |           |           | 234.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Eleme     | 3         | an        | 0..1      | 1..140    | Elemento  |
| ntoRefere |           |           |           |           | sul quale |
| nziato    |           |           |           |           | è stato   |
|           |           |           |           |           | rilevato  |
|           |           |           |           |           | l'errore. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Infor     | 3         | an        | 0..n      | 1..140    | Informazi |
| mazioniAg |           |           |           |           | oni       |
| giuntive  |           |           |           |           | aggiuntiv |
|           |           |           |           |           | e         |
|           |           |           |           |           | sullo     |
|           |           |           |           |           | stato di  |
|           |           |           |           |           | errore.   |
+-----------+-----------+-----------+-----------+-----------+-----------+

Catalogo dei servizi
~~~~~~~~~~~~~~~~~~~~
.. _Catalogo dei servizi:

Il “*Catalogo dei Servizi*” è il documento informatico che contiene
l’elenco dei servizi, attivati dagli Enti Creditori, utilizzabili
attraverso il modello di pagamento attivato presso i PSP in modalità
spontanea (`vedi § 2.2.3 <../07-Capitolo_2/Capitolo2.rst#pagamento-spontaneo-presso-i-psp>`__). Tale elenco ha valenza giornaliera: dalle ore
0 alle ore 24.

Nella Tabella 16 sono specificate le informazioni che il Nodo dei
Pagamenti-SPC invia ad ogni prestatore di servizi di pagamento aderente.

**Tabella** **16 - Elementi componenti il “Catalogo dei Servizi”**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| idSer     | 1         | an        | 1..1      | 5         | Codice    |
| vizio     |           |           |           |           | numerico  |
|           |           |           |           |           | che       |
|           |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | il        |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| descr     | 1         | an        | 1.1       | 70        | Descrizio |
| izioneSer |           |           |           |           | ne        |
| vizio     |           |           |           |           | del       |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | erogato.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| elenc     | 1         | s         | 1..1      |           | Struttura |
| oSoggetti |           |           |           |           | che       |
| Eroganti  |           |           |           |           | contiene  |
|           |           |           |           |           | l’elenco  |
|           |           |           |           |           | degli     |
|           |           |           |           |           | Enti      |
|           |           |           |           |           | Creditori |
|           |           |           |           |           | che       |
|           |           |           |           |           | erogano   |
|           |           |           |           |           | lo        |
|           |           |           |           |           | specifico |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| sogge     | 2         | s         | 1..n      |           | Struttura |
| ttoErogan |           |           |           |           | che       |
| te        |           |           |           |           | contiene  |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che eroga |
|           |           |           |           |           | lo        |
|           |           |           |           |           | specifico |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| idDom     | 3         | n         | 1.1       | 35        | Campo     |
| inio      |           |           |           |           | alfanumer |
|           |           |           |           |           | ico       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | dell'Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che eroga |
|           |           |           |           |           | quel      |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| denom     | 3         | an        | 1..1      | 70        | Contiene  |
| inazioneE |           |           |           |           | la        |
| nteCredit |           |           |           |           | denominaz |
| ore       |           |           |           |           | ione      |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che eroga |
|           |           |           |           |           | lo        |
|           |           |           |           |           | specifico |
|           |           |           |           |           | servizio. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataI     | 3         | an        | 1..1      | 10        | Data da   |
| nizioVali |           |           |           |           | cui è     |
| dita      |           |           |           |           | attiva    |
|           |           |           |           |           | l'erogazi |
|           |           |           |           |           | one       |
|           |           |           |           |           | del       |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | da parte  |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | nel       |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601: |
|           |           |           |           |           | [YYYY]    |
|           |           |           |           |           | - [MM] -  |
|           |           |           |           |           | [DD]      |
|           |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| xsdRi     | 1         | an        | 1.1       | 35        | Nome      |
| ferimento |           |           |           |           | dello XSD |
|           |           |           |           |           | utilizzat |
|           |           |           |           |           | o         |
|           |           |           |           |           | per       |
|           |           |           |           |           | verificar |
|           |           |           |           |           | e         |
|           |           |           |           |           | la        |
|           |           |           |           |           | congruenz |
|           |           |           |           |           | a         |
|           |           |           |           |           | dei dati  |
|           |           |           |           |           | forniti   |
|           |           |           |           |           | per lo    |
|           |           |           |           |           | specifico |
|           |           |           |           |           | servizio  |
|           |           |           |           |           | attravers |
|           |           |           |           |           | o         |
|           |           |           |           |           | una       |
|           |           |           |           |           | apposita  |
|           |           |           |           |           | struttura |
|           |           |           |           |           | XML.      |
|           |           |           |           |           |           |
|           |           |           |           |           | La        |
|           |           |           |           |           | struttura |
|           |           |           |           |           | XML       |
|           |           |           |           |           | contiene  |
|           |           |           |           |           | i dati    |
|           |           |           |           |           | che       |
|           |           |           |           |           | consenton |
|           |           |           |           |           | o         |
|           |           |           |           |           | il        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | spontaneo |
|           |           |           |           |           | c/o PSP.  |
+-----------+-----------+-----------+-----------+-----------+-----------+

Le informazioni del “*Catalogo dei Servizi*” sono codificate in un
file XML secondo il tracciato di Tabella 17 e devono essere richieste
dai singoli prestatori di servizi di pagamento al NodoSPC utilizzando
l'apposita primitiva allo scopo messa a disposizione dal NodoSPC (`vedi §
8.2.6 Sezione III <../15-Capitolo_8/Capitolo8.rst#ricezione-del-flusso-di-rendicontazione>`__).

Le informazioni sono codificate in un file XML secondo lo schema di
Tabella 12 e devono essere inviate al Nodo dei Pagamenti-SPC via PEC dal
PSP, con le modalità indicate sul sito dell’Agenzia. per l’Italia
Digitale.

**Tabella** **17 - Tracciato XML per comunicazione “Catalogo dei Servizi”**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **c**     | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| lista     | 1         | s         | 1..1      |           | Lista     |
| CatalogoS |           |           |           |           | delle     |
| ervizi    |           |           |           |           | informati |
|           |           |           |           |           | ve        |
|           |           |           |           |           | Contropar |
|           |           |           |           |           | te        |
|           |           |           |           |           | valide    |
|           |           |           |           |           | nella     |
|           |           |           |           |           | giornata  |
|           |           |           |           |           | corrente  |
|           |           |           |           |           | (hh       |
|           |           |           |           |           | 00-24)    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| catal     | 2         | s         | 1..n      |           | Numero    |
| ogoServiz |           |           |           |           | non       |
| i         |           |           |           |           | definito  |
|           |           |           |           |           | di        |
|           |           |           |           |           | occorrenz |
|           |           |           |           |           | e         |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | catalog   |
|           |           |           |           |           | oServizi  |
|           |           |           |           |           | definita  |
|           |           |           |           |           | nella     |
|           |           |           |           |           | precedent |
|           |           |           |           |           | e         |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 5.        |
+-----------+-----------+-----------+-----------+-----------+-----------+

Ad ogni servizio presente nel Catalogo dei Servizi è associato un
insieme di dati, specifici del servizio, e necessari all'Ente Creditore
per fornire al PSP il Numero Avviso: tale insieme di dati viene
veicolato dal Nodo dei Pagamenti-SPC in forma di file XML (si vedano il
parametro **I-7** della primitiva nodoChiediNumeroAvviso `al § 9.2.3.4 <../16-Capitolo_9/Capitolo9.rst#nodochiedinumeroavviso>`__ e
I-3 della primitiva paaChiediNumeroAvviso `al § 8.2.3.4 <../15-Capitolo_8/Capitolo8.rst#paachiedinumeroavviso>`__) a cui è
associato uno schema XSD che ne definisce il contenuto e permette il
controllo delle informazioni presenti nel file XML stesso.

Il nome dello schema XSD che rappresenta i dati contenuti nel file XML
che viene inviato all'Ente Creditore attraverso il NodoSPC è riportato
nell'elemento xsdRiferimento del *Catalogo dei Servizi* (vedi Tabella 16
a pagina 99).

Dati specifici del servizio nel caso d'uso della Tassa Automobilistica
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Dati specifici del servizio nel caso d'uso della Tassa Automobilistica:

Nella Tabella 18 sono specificate le informazioni che il PSP deve
fornire per il pagamento della Tassa Automobilistica e che devono essere
codificate nel file XML da inviare all'Ente Creditore tramite NodoSPC
nel parametro datiSpecificiServizio (`cfr. §§ 8.2.3.4 <../15-Capitolo_8/Capitolo8.rst#paachiedinumeroavviso>`__ e `9.2.3.4 <../16-Capitolo_9/Capitolo9.rst#nodochiedinumeroavviso>`__).

**Tabella** **18 - Struttura dati pagamento spontaneo nel caso d'uso Tassa Automobilistica**


+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|**Da |**Li |**Gen|**Oc |**Le |**Con|     |     |     |     |     |
|to** |v**  |ere**|c**  |n**  |tenut|     |     |     |     |     |
|     |     |     |     |     |o**  |     |     |     |     |     |
|     |     |     |     |     |     |     |     |     |     |     |
+=====+=====+=====+=====+=====+=====+=====+=====+=====+=====+=====+
|tassa| 1   | s   | 1.1 |     | Str |     |     |     |     |     |
|Auto |     |     |     |     | utt |     |     |     |     |     |
|     |     |     |     |     | ura |     |     |     |     |     |
|     |     |     |     |     | che |     |     |     |     |     |
|     |     |     |     |     | con |     |     |     |     |     |
|     |     |     |     |     | tie |     |     |     |     |     |
|     |     |     |     |     | ne  |     |     |     |     |     |
|     |     |     |     |     | le  |     |     |     |     |     |
|     |     |     |     |     | inf |     |     |     |     |     |
|     |     |     |     |     | orm |     |     |     |     |     |
|     |     |     |     |     | azi |     |     |     |     |     |
|     |     |     |     |     | oni |     |     |     |     |     |
|     |     |     |     |     | rel |     |     |     |     |     |
|     |     |     |     |     | ati |     |     |     |     |     |
|     |     |     |     |     | ve  |     |     |     |     |     |
|     |     |     |     |     | al  |     |     |     |     |     |
|     |     |     |     |     | pag |     |     |     |     |     |
|     |     |     |     |     | ame |     |     |     |     |     |
|     |     |     |     |     | nto |     |     |     |     |     |
|     |     |     |     |     | del |     |     |     |     |     |
|     |     |     |     |     | la  |     |     |     |     |     |
|     |     |     |     |     | tas |     |     |     |     |     |
|     |     |     |     |     | sa  |     |     |     |     |     |
|     |     |     |     |     | aut |     |     |     |     |     |
|     |     |     |     |     | omo |     |     |     |     |     |
|     |     |     |     |     | bil |     |     |     |     |     |
|     |     |     |     |     | ist |     |     |     |     |     |
|     |     |     |     |     | ica |     |     |     |     |     |
|     |     |     |     |     | .   |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|regio| 2   | an  | 1.. | 11  | Cod |     |     |     |     |     |
|neRes|     |     | 1   |     | ice |     |     |     |     |     |
|idenz|     |     |     |     | Fis |     |     |     |     |     |
|a    |     |     |     |     | cal |     |     |     |     |     |
|     |     |     |     |     | e   |     |     |     |     |     |
|     |     |     |     |     | del |     |     |     |     |     |
|     |     |     |     |     | la  |     |     |     |     |     |
|     |     |     |     |     | Reg |     |     |     |     |     |
|     |     |     |     |     | ion |     |     |     |     |     |
|     |     |     |     |     | e   |     |     |     |     |     |
|     |     |     |     |     | di  |     |     |     |     |     |
|     |     |     |     |     | res |     |     |     |     |     |
|     |     |     |     |     | ide |     |     |     |     |     |
|     |     |     |     |     | nza |     |     |     |     |     |
|     |     |     |     |     | del |     |     |     |     |     |
|     |     |     |     |     | l'i |     |     |     |     |     |
|     |     |     |     |     | nte |     |     |     |     |     |
|     |     |     |     |     | sta |     |     |     |     |     |
|     |     |     |     |     | tar |     |     |     |     |     |
|     |     |     |     |     | io  |     |     |     |     |     |
|     |     |     |     |     | del |     |     |     |     |     |
|     |     |     |     |     | vei |     |     |     |     |     |
|     |     |     |     |     | col |     |     |     |     |     |
|     |     |     |     |     | o.  |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|veico| 2   | s   | 1.1 |     | Str |     |     |     |     |     |
|ConTa|     |     |     |     | utt |     |     |     |     |     |
|rga  |     |     |     |     | ura |     |     |     |     |     |
|     |     |     |     |     | che |     |     |     |     |     |
|     |     |     |     |     | con |     |     |     |     |     |
|     |     |     |     |     | tie |     |     |     |     |     |
|     |     |     |     |     | ne  |     |     |     |     |     |
|     |     |     |     |     | inf |     |     |     |     |     |
|     |     |     |     |     | orm |     |     |     |     |     |
|     |     |     |     |     | azi |     |     |     |     |     |
|     |     |     |     |     | oni |     |     |     |     |     |
|     |     |     |     |     | di  |     |     |     |     |     |
|     |     |     |     |     | vei |     |     |     |     |     |
|     |     |     |     |     | col |     |     |     |     |     |
|     |     |     |     |     | i   |     |     |     |     |     |
|     |     |     |     |     | ide |     |     |     |     |     |
|     |     |     |     |     | nti |     |     |     |     |     |
|     |     |     |     |     | fic |     |     |     |     |     |
|     |     |     |     |     | abi |     |     |     |     |     |
|     |     |     |     |     | li  |     |     |     |     |     |
|     |     |     |     |     | con |     |     |     |     |     |
|     |     |     |     |     | la  |     |     |     |     |     |
|     |     |     |     |     | tar |     |     |     |     |     |
|     |     |     |     |     | ga. |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|tipoV| 3   | n   | 1.1 | 1   | Tip |     |     |     |     |     |
|eicol|     |     |     |     | o   |     |     |     |     |     |
|oTarg|     |     |     |     | del |     |     |     |     |     |
|a    |     |     |     |     | vei |     |     |     |     |     |
|     |     |     |     |     | col |     |     |     |     |     |
|     |     |     |     |     | o.  |     |     |     |     |     |
|     |     |     |     |     | Può |     |     |     |     |     |
|     |     |     |     |     | ass |     |     |     |     |     |
|     |     |     |     |     | ume |     |     |     |     |     |
|     |     |     |     |     | re  |     |     |     |     |     |
|     |     |     |     |     | i   |     |     |     |     |     |
|     |     |     |     |     | seg |     |     |     |     |     |
|     |     |     |     |     | uen |     |     |     |     |     |
|     |     |     |     |     | ti  |     |     |     |     |     |
|     |     |     |     |     | val |     |     |     |     |     |
|     |     |     |     |     | ori |     |     |     |     |     |
|     |     |     |     |     | :   |     |     |     |     |     |
|     |     |     |     |     |     |     |     |     |     |     |
|     |     |     |     |     | 1.  |     |     |     |     |     |
|     |     |     |     |     | Aut |     |     |     |     |     |
|     |     |     |     |     | ove |     |     |     |     |     |
|     |     |     |     |     | ico |     |     |     |     |     |
|     |     |     |     |     | li  |     |     |     |     |     |
|     |     |     |     |     |     |     |     |     |     |     |
|     |     |     |     |     | 2.  |     |     |     |     |     |
|     |     |     |     |     | Rim |     |     |     |     |     |
|     |     |     |     |     | orc |     |     |     |     |     |
|     |     |     |     |     | hi  |     |     |     |     |     |
|     |     |     |     |     |     |     |     |     |     |     |
|     |     |     |     |     | 4.  |     |     |     |     |     |
|     |     |     |     |     | Mot |     |     |     |     |     |
|     |     |     |     |     | ove |     |     |     |     |     |
|     |     |     |     |     | ico |     |     |     |     |     |
|     |     |     |     |     | lo  |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|veico| 3   | an  | 1.1 | 7.. | Tar |     |     |     |     |     |
|loTar|     |     |     | 8   | ga  |     |     |     |     |     |
|ga   |     |     |     |     | del |     |     |     |     |     |
|     |     |     |     |     | vei |     |     |     |     |     |
|     |     |     |     |     | col |     |     |     |     |     |
|     |     |     |     |     | o.  |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|**opp|     |     |     |     |     |     |     |     |     |     |
|ure, |     |     |     |     |     |     |     |     |     |     |
|in al|     |     |     |     |     |     |     |     |     |     |
|terna|     |     |     |     |     |     |     |     |     |     |
|tiva |     |     |     |     |     |     |     |     |     |     |
|a    |     |     |     |     |     |     |     |     |     |     |
|veico|     |     |     |     |     |     |     |     |     |     |
|loCon|     |     |     |     |     |     |     |     |     |     |
|Tar  |     |     |     |     |     |     |     |     |     |     |
|ga** |     |     |     |     |     |     |     |     |     |     |
|     |     |     |     |     |     |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|veico| 2   | s   | 1.1 |     | Str |     |     |     |     |     |
|ConTe|     |     |     |     | utt |     |     |     |     |     |
|laio |     |     |     |     | ura |     |     |     |     |     |
|     |     |     |     |     | che |     |     |     |     |     |
|     |     |     |     |     | con |     |     |     |     |     |
|     |     |     |     |     | tie |     |     |     |     |     |
|     |     |     |     |     | ne  |     |     |     |     |     |
|     |     |     |     |     | inf |     |     |     |     |     |
|     |     |     |     |     | orm |     |     |     |     |     |
|     |     |     |     |     | azi |     |     |     |     |     |
|     |     |     |     |     | oni |     |     |     |     |     |
|     |     |     |     |     | di  |     |     |     |     |     |
|     |     |     |     |     | vei |     |     |     |     |     |
|     |     |     |     |     | col |     |     |     |     |     |
|     |     |     |     |     | i   |     |     |     |     |     |
|     |     |     |     |     | ide |     |     |     |     |     |
|     |     |     |     |     | nti |     |     |     |     |     |
|     |     |     |     |     | fic |     |     |     |     |     |
|     |     |     |     |     | abi |     |     |     |     |     |
|     |     |     |     |     | li  |     |     |     |     |     |
|     |     |     |     |     | con |     |     |     |     |     |
|     |     |     |     |     | il  |     |     |     |     |     |
|     |     |     |     |     | num |     |     |     |     |     |
|     |     |     |     |     | ero |     |     |     |     |     |
|     |     |     |     |     | di  |     |     |     |     |     |
|     |     |     |     |     | tel |     |     |     |     |     |
|     |     |     |     |     | aio |     |     |     |     |     |
|     |     |     |     |     | .   |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|tipoV| 3   | n   | 1.1 | 1   | Tip |     |     |     |     |     |
|eicol|     |     |     |     | o   |     |     |     |     |     |
|oTela|     |     |     |     | del |     |     |     |     |     |
|io   |     |     |     |     | vei |     |     |     |     |     |
|     |     |     |     |     | col |     |     |     |     |     |
|     |     |     |     |     | o.  |     |     |     |     |     |
|     |     |     |     |     | Può |     |     |     |     |     |
|     |     |     |     |     | ass |     |     |     |     |     |
|     |     |     |     |     | ume |     |     |     |     |     |
|     |     |     |     |     | re  |     |     |     |     |     |
|     |     |     |     |     | i   |     |     |     |     |     |
|     |     |     |     |     | seg |     |     |     |     |     |
|     |     |     |     |     | uen |     |     |     |     |     |
|     |     |     |     |     | ti  |     |     |     |     |     |
|     |     |     |     |     | val |     |     |     |     |     |
|     |     |     |     |     | ori |     |     |     |     |     |
|     |     |     |     |     | :   |     |     |     |     |     |
|     |     |     |     |     |     |     |     |     |     |     |
|     |     |     |     |     | 3.  |     |     |     |     |     |
|     |     |     |     |     | Cic |     |     |     |     |     |
|     |     |     |     |     | lom |     |     |     |     |     |
|     |     |     |     |     | oto |     |     |     |     |     |
|     |     |     |     |     | ri  |     |     |     |     |     |
|     |     |     |     |     |     |     |     |     |     |     |
|     |     |     |     |     | 7.  |     |     |     |     |     |
|     |     |     |     |     | Qua |     |     |     |     |     |
|     |     |     |     |     | dri |     |     |     |     |     |
|     |     |     |     |     | cic |     |     |     |     |     |
|     |     |     |     |     | lo  |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|numer| 3   | an  | 1.1 | 17  | Num |     |     |     |     |     |
|oTela|     |     |     |     | ero |     |     |     |     |     |
|ioVei|     |     |     |     | di  |     |     |     |     |     |
|colo |     |     |     |     | tel |     |     |     |     |     |
|     |     |     |     |     | aio |     |     |     |     |     |
|     |     |     |     |     | del |     |     |     |     |     |
|     |     |     |     |     | vei |     |     |     |     |     |
|     |     |     |     |     | col |     |     |     |     |     |
|     |     |     |     |     | o.  |     |     |     |     |     |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+
|intes| 3   | an  | 1.. | 16  | Cod |     |     | 1.. | 11  | Cod |
|tatar|     |     | 1   |     | ice |     |     | 1   |     | ice |
|ioVei|     |     |     |     | Fis |     |     |     |     | Fis |
|colo |     |     |     |     | cal |     |     |     |     | cal |
|     |     |     |     |     | e   |     |     |     |     | e   |
|     |     |     |     |     | del |     |     |     |     | del |
|     |     |     |     |     | l'i |     |     |     |     | la  |
|     |     |     |     |     | nte |     |     |     |     | Reg |
|     |     |     |     |     | sta |     |     |     |     | ion |
|     |     |     |     |     | tar |     |     |     |     | e   |
|     |     |     |     |     | io  |     |     |     |     | di  |
|     |     |     |     |     | del |     |     |     |     | res |
|     |     |     |     |     | vei |     |     |     |     | ide |
|     |     |     |     |     | col |     |     |     |     | nza |
|     |     |     |     |     | o.  |     |     |     |     | del |
|     |     |     |     |     |     |     |     |     |     | l'i |
|     |     |     |     |     |     |     |     |     |     | nte |
|     |     |     |     |     |     |     |     |     |     | sta |
|     |     |     |     |     |     |     |     |     |     | tar |
|     |     |     |     |     |     |     |     |     |     | io  |
|     |     |     |     |     |     |     |     |     |     | del |
|     |     |     |     |     |     |     |     |     |     | vei |
|     |     |     |     |     |     |     |     |     |     | col |
|     |     |     |     |     |     |     |     |     |     | o.  |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+

I Prestatori di servizi di pagamento che implementano il servizio sono
tenuti a sviluppare solo l'opzione, definita in Tabella 18, con la
struttura veicoloConTarga, mentre possono non gestire l'opzione definita
con la struttura veicoloConTelaio.

Avvisatura digitale
-------------------
.. _Avvisatura digitale:

Di seguito sono descritti gli oggetti che costituiscono la
rappresentazione telematica delle informazioni che dovranno essere
scambiate nell’ambito del processo di avvisatura digitale in modalità
*push*:

-  Avviso digitale

-  Esito inoltro Avviso digitale

-  Segnalazione di presa in carico

-  Parametri Web service

Avviso digitale
~~~~~~~~~~~~~~~
.. _Avviso digitale:

È un oggetto informatico, predisposto da un Ente Creditore o da un suo
intermediario, per consentire l’invio al Nodo dei Pagamenti-SPC delle
informazioni relative ad una richiesta di inoltro di avviso di pagamento
in formato digitale.

**Tabella** **19 - Elementi componenti l’Avviso digitale**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| avviso    | 1         | s         | 1..1      |           | Struttura |
| Digitale  |           |           |           |           | che       |
|           |           |           |           |           | contiene  |
|           |           |           |           |           | i dati    |
|           |           |           |           |           | dell'Avvi |
|           |           |           |           |           | so        |
|           |           |           |           |           | Digitale. |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..35     | Campo     |
| ificativo |           |           |           |           | alfanumer |
| Dominio   |           |           |           |           | ico       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | che invia |
|           |           |           |           |           | l'avviso  |
|           |           |           |           |           | Digitale. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| anagr     | 2         | an        | 1..1      | 1..35     | Denominaz |
| aficaBene |           |           |           |           | ione      |
| ficiario  |           |           |           |           | dell’Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che invia |
|           |           |           |           |           | la        |
|           |           |           |           |           | richiesta |
|           |           |           |           |           | di avviso |
|           |           |           |           |           | digitale. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..20     | Identific |
| ificativo |           |           |           |           | ativo     |
| Messaggio |           |           |           |           | univoco   |
| Richiesta |           |           |           |           | dell'avvi |
|           |           |           |           |           | so        |
|           |           |           |           |           | digitale. |
|           |           |           |           |           | Identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | lo        |
|           |           |           |           |           | specifico |
|           |           |           |           |           | avviso e  |
|           |           |           |           |           | consente  |
|           |           |           |           |           | di        |
|           |           |           |           |           | riconosce |
|           |           |           |           |           | re        |
|           |           |           |           |           | la        |
|           |           |           |           |           | trasmissi |
|           |           |           |           |           | one       |
|           |           |           |           |           | duplicata |
|           |           |           |           |           |           |
|           |           |           |           |           | Deve      |
|           |           |           |           |           | essere    |
|           |           |           |           |           | univoco   |
|           |           |           |           |           | nell’ambi |
|           |           |           |           |           | to        |
|           |           |           |           |           | di 365    |
|           |           |           |           |           | giorni    |
|           |           |           |           |           | consecuti |
|           |           |           |           |           | vi.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tasso     | 2         | n         | 1..1      | 2         | Macro     |
| nomiaAvvi |           |           |           |           | categoria |
| so        |           |           |           |           | di        |
|           |           |           |           |           | classific |
|           |           |           |           |           | azione    |
|           |           |           |           |           | dell'avvi |
|           |           |           |           |           | so        |
|           |           |           |           |           | ad uso    |
|           |           |           |           |           | delle app |
|           |           |           |           |           | e         |
|           |           |           |           |           | dell'Util |
|           |           |           |           |           | izzatore  |
|           |           |           |           |           | finale.   |
|           |           |           |           |           |           |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | 0 -       |
|           |           |           |           |           | Cartelle  |
|           |           |           |           |           | esattoria |
|           |           |           |           |           | li        |
|           |           |           |           |           |           |
|           |           |           |           |           | 1 -       |
|           |           |           |           |           | Diritti e |
|           |           |           |           |           | concessio |
|           |           |           |           |           | ni        |
|           |           |           |           |           |           |
|           |           |           |           |           | 2 -       |
|           |           |           |           |           | Imposte e |
|           |           |           |           |           | tasse     |
|           |           |           |           |           |           |
|           |           |           |           |           | 3 -       |
|           |           |           |           |           | IMU, TASI |
|           |           |           |           |           | e         |
|           |           |           |           |           | altre     |
|           |           |           |           |           | tasse     |
|           |           |           |           |           | comunali  |
|           |           |           |           |           |           |
|           |           |           |           |           | 4 -       |
|           |           |           |           |           | Ingressi  |
|           |           |           |           |           | a         |
|           |           |           |           |           | mostre e  |
|           |           |           |           |           | musei     |
|           |           |           |           |           |           |
|           |           |           |           |           | 5 -       |
|           |           |           |           |           | Multe e   |
|           |           |           |           |           | sanzioni  |
|           |           |           |           |           | ammin     |
|           |           |           |           |           | istrative |
|           |           |           |           |           |           |
|           |           |           |           |           | 6 -       |
|           |           |           |           |           | Previ     |
|           |           |           |           |           | denza e   |
|           |           |           |           |           | infortuni |
|           |           |           |           |           |           |
|           |           |           |           |           | 7 -       |
|           |           |           |           |           | Servizi   |
|           |           |           |           |           | erogati   |
|           |           |           |           |           | dal comun |
|           |           |           |           |           | e         |
|           |           |           |           |           |           |
|           |           |           |           |           | 8 -       |
|           |           |           |           |           | Servizi   |
|           |           |           |           |           | erogati   |
|           |           |           |           |           | da        |
|           |           |           |           |           | altri     |
|           |           |           |           |           | enti      |
|           |           |           |           |           |           |
|           |           |           |           |           | 9 -       |
|           |           |           |           |           | Servizi   |
|           |           |           |           |           | scolastici|
|           |           |           |           |           |           |
|           |           |           |           |           | 10 -      |
|           |           |           |           |           | Tassa     |
|           |           |           |           |           | automobili|
|           |           |           |           |           | stica     |
|           |           |           |           |           |           |
|           |           |           |           |           | 11 -      |
|           |           |           |           |           | Ticket e  |
|           |           |           |           |           | prestazio |
|           |           |           |           |           | ni        |
|           |           |           |           |           | sanitarie |
|           |           |           |           |           |           |
|           |           |           |           |           | 12 -      |
|           |           |           |           |           | Trasporti,|
|           |           |           |           |           | mobilità e|
|           |           |           |           |           | parcheggi |
+-----------+-----------+-----------+-----------+-----------+-----------+
| codic     | 2         | n         | 1..1      | 18        | Codice    |
| eAvviso   |           |           |           |           | dell’avvi |
|           |           |           |           |           | so        |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | predispos |
|           |           |           |           |           | to        |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | quanto    |
|           |           |           |           |           | indicato  |
|           |           |           |           |           | al §      |
|           |           |           |           |           | 7.4.1     |
|           |           |           |           |           | delle     |
|           |           |           |           |           | SANP.     |
|           |           |           |           |           |           |
|           |           |           |           |           | Contiene  |
|           |           |           |           |           | il codice |
|           |           |           |           |           | IUV.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| soggetto  | 2         | s         | 1..1      |           | Aggregazi |
| Pagatore  |           |           |           |           | one       |
|           |           |           |           |           | che       |
|           |           |           |           |           | riporta   |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | concernen |
|           |           |           |           |           | ti        |
|           |           |           |           |           | il        |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | pagatore  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| anagrafica| 3         | an        | 1..1      | 1..70     | Indica il |
| Pagatore  |           |           |           |           | nominativ |
|           |           |           |           |           | o         |
|           |           |           |           |           | o la      |
|           |           |           |           |           | ragione   |
|           |           |           |           |           | sociale   |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagatore  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 3         | s         | 1..1      |           | Aggregazi |
| ificativo |           |           |           |           | one       |
| UnivocoPa |           |           |           |           | che       |
| gatore    |           |           |           |           | riporta   |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | concernen |
|           |           |           |           |           | ti        |
|           |           |           |           |           | l’identif |
|           |           |           |           |           | icazione  |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagatore. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoI     | 4         | an        | 1..1      | 1         | Dato      |
| dentifica |           |           |           |           | alfanumer |
| tivoUnivo |           |           |           |           | ico       |
| co        |           |           |           |           | che       |
|           |           |           |           |           | indica la |
|           |           |           |           |           | natura    |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagatore. |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘F’**\ =|
|           |           |           |           |           |           |
|           |           |           |           |           | Persona   |
|           |           |           |           |           | fisica    |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘G’**\ =|
|           |           |           |           |           |           |
|           |           |           |           |           | Persona   |
|           |           |           |           |           | Giuridica.|
+-----------+-----------+-----------+-----------+-----------+-----------+
| codic     | 4         | an        | 1..1      | 1..35     | Campo     |
| eIdentifi |           |           |           |           | alfanumer |
| cativoUni |           |           |           |           | ico       |
| voco      |           |           |           |           | che può   |
|           |           |           |           |           | contenere |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | o, in     |
|           |           |           |           |           | alternati |
|           |           |           |           |           | va,       |
|           |           |           |           |           | la        |
|           |           |           |           |           | partita   |
|           |           |           |           |           | IVA del   |
|           |           |           |           |           | pagatore. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataS     | 2         | an        | 1..1      | 10        | Indica la |
| cadenzaPa |           |           |           |           | data      |
| gamento   |           |           |           |           | entro la  |
|           |           |           |           |           | quale si  |
|           |           |           |           |           | richiede  |
|           |           |           |           |           | che venga |
|           |           |           |           |           | effettuat |
|           |           |           |           |           | o         |
|           |           |           |           |           | il        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataS     | 2         | an        | 1..1      | 10        | Indica la |
| cadenzaAv |           |           |           |           | data,     |
| viso      |           |           |           |           | successiv |
|           |           |           |           |           | a         |
|           |           |           |           |           | alla data |
|           |           |           |           |           | di        |
|           |           |           |           |           | scadenza  |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | ,         |
|           |           |           |           |           | sino alla |
|           |           |           |           |           | quale si  |
|           |           |           |           |           | ritiene   |
|           |           |           |           |           | valido    |
|           |           |           |           |           | l'avviso, |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| impor     | 2         | an        | 1..1      | 3..12     | Campo     |
| toAvviso  |           |           |           |           | numerico  |
|           |           |           |           |           | (due      |
|           |           |           |           |           | cifre per |
|           |           |           |           |           | la parte  |
|           |           |           |           |           | decimale, |
|           |           |           |           |           | il        |
|           |           |           |           |           | separator |
|           |           |           |           |           | e         |
|           |           |           |           |           | dei       |
|           |           |           |           |           | centesimi |
|           |           |           |           |           | è il      |
|           |           |           |           |           | punto     |
|           |           |           |           |           | “.”),     |
|           |           |           |           |           | indicante |
|           |           |           |           |           | l’importo |
|           |           |           |           |           | relativo  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | somma da  |
|           |           |           |           |           | versare.  |
|           |           |           |           |           |           |
|           |           |           |           |           | Deve      |
|           |           |           |           |           | essere    |
|           |           |           |           |           | maggiore  |
|           |           |           |           |           | di        |
|           |           |           |           |           | “0.10”.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| eMail     | 2         | an        | 0..1      | 1..256    | Indirizzo |
| Soggetto  |           |           |           |           | di posta  |
|           |           |           |           |           | elettroni |
|           |           |           |           |           | ca        |
|           |           |           |           |           | del       |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | al quale  |
|           |           |           |           |           | è         |
|           |           |           |           |           | indirizza |
|           |           |           |           |           | to        |
|           |           |           |           |           | l'avviso. |
|           |           |           |           |           |           |
|           |           |           |           |           | Se        |
|           |           |           |           |           | presente, |
|           |           |           |           |           | l'avviso  |
|           |           |           |           |           | sarà      |
|           |           |           |           |           | inviato   |
|           |           |           |           |           | anche     |
|           |           |           |           |           | tramite   |
|           |           |           |           |           | e-mail.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| cellulare | 2         | an        | 0..1      | 1..35     | Numero di |
| Soggetto  |           |           |           |           | cellulare |
|           |           |           |           |           | del       |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | al quale  |
|           |           |           |           |           | è         |
|           |           |           |           |           | indirizza |
|           |           |           |           |           | to        |
|           |           |           |           |           | l'avviso. |
|           |           |           |           |           | Nel       |
|           |           |           |           |           | formato:  |
|           |           |           |           |           |           |
|           |           |           |           |           | +NN       |
|           |           |           |           |           | NNN-NNNNN |
|           |           |           |           |           | NN        |
|           |           |           |           |           |           |
|           |           |           |           |           | Se        |
|           |           |           |           |           | presente, |
|           |           |           |           |           | l'avviso  |
|           |           |           |           |           | sarà      |
|           |           |           |           |           | inviato   |
|           |           |           |           |           | anche     |
|           |           |           |           |           | tramite   |
|           |           |           |           |           | SMS.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| descrizio | 2         | an        | 1..1      | 1..140    | Testo     |
| nePagamen |           |           |           |           | libero a  |
| to        |           |           |           |           | disposizi |
|           |           |           |           |           | one       |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | per       |
|           |           |           |           |           | descriver |
|           |           |           |           |           | e         |
|           |           |           |           |           | le        |
|           |           |           |           |           | motivazio |
|           |           |           |           |           | ni        |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| urlAvviso | 2         | an        | 0..1      | 1..140    | URL di    |
|           |           |           |           |           | una       |
|           |           |           |           |           | pagina    |
|           |           |           |           |           | web messa |
|           |           |           |           |           | a         |
|           |           |           |           |           | disposizi |
|           |           |           |           |           | one       |
|           |           |           |           |           | dall'Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | dove      |
|           |           |           |           |           | l'Utilizz |
|           |           |           |           |           | atore     |
|           |           |           |           |           | finale    |
|           |           |           |           |           | può       |
|           |           |           |           |           | consultar |
|           |           |           |           |           | e         |
|           |           |           |           |           | l'avviso  |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| datiSingo | 2         | s         | 1..5      |           | Aggregazi |
| loVersame |           |           |           |           | one       |
| nto       |           |           |           |           | dei dati  |
|           |           |           |           |           | per       |
|           |           |           |           |           | l’accredi |
|           |           |           |           |           | to        |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | ,         |
|           |           |           |           |           | da un     |
|           |           |           |           |           | minimo di |
|           |           |           |           |           | uno ad un |
|           |           |           |           |           | massimo   |
|           |           |           |           |           | di 5      |
|           |           |           |           |           | occorrenz |
|           |           |           |           |           | e,        |
|           |           |           |           |           | facenti   |
|           |           |           |           |           | capo ad   |
|           |           |           |           |           | un unico  |
|           |           |           |           |           | avviso di |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ibanAccre | 3         | an        | 0..1      | 1..35     | Vedi      |
| dito      |           |           |           |           | omonimo   |
|           |           |           |           |           | dato      |
|           |           |           |           |           | presente  |
|           |           |           |           |           | nella     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | della RPT |
|           |           |           |           |           | (§        |
|           |           |           |           |           | 5.3.1).   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ibanAppog | 3         | an        | 0..1      | 1..35     | Vedi      |
| gio       |           |           |           |           | omonimo   |
|           |           |           |           |           | dato      |
|           |           |           |           |           | presente  |
|           |           |           |           |           | nella     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | della RPT |
|           |           |           |           |           | (§        |
|           |           |           |           |           | 5.3.1).   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoPaga  | 2         | n         | 1..1      | 1         | Dato      |
| mento     |           |           |           |           | numerico  |
|           |           |           |           |           | che       |
|           |           |           |           |           | indica la |
|           |           |           |           |           | natura    |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | .         |
|           |           |           |           |           |           |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | **0** =   |
|           |           |           |           |           | Conte     |
|           |           |           |           |           | stuale    |
|           |           |           |           |           |           |
|           |           |           |           |           | **1** =   |
|           |           |           |           |           | Non       |
|           |           |           |           |           | conte     |
|           |           |           |           |           | stuale    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoOpera | 2         | an        | 1..1      | 1         | Dato      |
| zione     |           |           |           |           | alfanumer |
|           |           |           |           |           | ico       |
|           |           |           |           |           | che       |
|           |           |           |           |           | indica il |
|           |           |           |           |           | tipo di   |
|           |           |           |           |           | operazion |
|           |           |           |           |           | e         |
|           |           |           |           |           | connessa  |
|           |           |           |           |           | con       |
|           |           |           |           |           | l’avviso. |
|           |           |           |           |           |           |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘C’** = |
|           |           |           |           |           | Creazione |
|           |           |           |           |           | ione      |
|           |           |           |           |           | di un     |
|           |           |           |           |           | nuovo     |
|           |           |           |           |           | avviso    |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘U’**\ =|
|           |           |           |           |           | Modifica  |
|           |           |           |           |           | di un     |
|           |           |           |           |           | avviso    |
|           |           |           |           |           | esistente |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘D’**\ =|
|           |           |           |           |           | Cance     |
|           |           |           |           |           | llazione  |
|           |           |           |           |           | di un     |
|           |           |           |           |           | avviso    |
|           |           |           |           |           | esistente |
+-----------+-----------+-----------+-----------+-----------+-----------+

Esito inoltro di Avviso digitale
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Esito inoltro di Avviso digitale:

È un oggetto informatico, predisposto dal Nodo dei Pagamenti-SPC, per
consentire l’invio all’Ente Creditore o al suo intermediario delle
informazioni relative agli esiti di una precedente richiesta di inoltro
di avviso di pagamento in formato digitale.

**Tabella** **20 - Elementi componenti l’Esito Avviso digitale**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| esito     | 1         | s         | 1..1      |           | Struttura |
| AvvisoDig |           |           |           |           | che       |
| itale     |           |           |           |           | contiene  |
|           |           |           |           |           | i dati    |
|           |           |           |           |           | circa     |
|           |           |           |           |           | l'esito   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | avvisi    |
|           |           |           |           |           | digitali. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..35     | Campo     |
| ificativo |           |           |           |           | alfanumer |
| Dominio   |           |           |           |           | ico       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | che ha    |
|           |           |           |           |           | inviato   |
|           |           |           |           |           | l'avviso  |
|           |           |           |           |           | Digitale  |
|           |           |           |           |           | di cui il |
|           |           |           |           |           | sistema   |
|           |           |           |           |           | sta       |
|           |           |           |           |           | fornendo  |
|           |           |           |           |           | l’Esito.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..20     | Identific |
| ificativo |           |           |           |           | ativo     |
| Messaggio |           |           |           |           | univoco   |
| Richiesta |           |           |           |           | dell'avvi |
|           |           |           |           |           | so        |
|           |           |           |           |           | digitale  |
|           |           |           |           |           | di cui il |
|           |           |           |           |           | sistema   |
|           |           |           |           |           | sta       |
|           |           |           |           |           | fornendo  |
|           |           |           |           |           | l’Esito.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| esito     | 2         | s         | 0..n      |           | Struttura |
| Avvisatur |           |           |           |           | che       |
| a         |           |           |           |           | contiene  |
|           |           |           |           |           | gli esiti |
|           |           |           |           |           | del       |
|           |           |           |           |           | singolo   |
|           |           |           |           |           | invio di  |
|           |           |           |           |           | Avviso    |
|           |           |           |           |           | Digitale. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoC     | 3         | n         | 1..1      | 1         | Tipologia |
| analeEsit |           |           |           |           | di canale |
| o         |           |           |           |           | usato per |
|           |           |           |           |           | inviare   |
|           |           |           |           |           | l’avviso  |
|           |           |           |           |           | all'utent |
|           |           |           |           |           | e.        |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumer i |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | 1. Nessun |
|           |           |           |           |           |    canale |
|           |           |           |           |           |           |
|           |           |           |           |           | 2. SMS    |
|           |           |           |           |           |           |
|           |           |           |           |           | 3. e-mail |
|           |           |           |           |           |           |
|           |           |           |           |           | 4. mobile |
|           |           |           |           |           | -payment  |
|           |           |           |           |           |           |
|           |           |           |           |           | 5. altro  |
|           |           |           |           |           |    canale |
|           |           |           |           |           |    del    |
|           |           |           |           |           |    PSP    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Ident     | 3         | an        | 0..1      | 1..35     | identific |
| ificativo |           |           |           |           | ativo     |
| Canale    |           |           |           |           | del       |
|           |           |           |           |           | canale    |
|           |           |           |           |           | “mobile”  |
|           |           |           |           |           | a cui si  |
|           |           |           |           |           | riferisce |
|           |           |           |           |           | l’esito   |
|           |           |           |           |           | dell’avvi |
|           |           |           |           |           | satura.   |
|           |           |           |           |           |           |
|           |           |           |           |           | Deve      |
|           |           |           |           |           | essere    |
|           |           |           |           |           | presente  |
|           |           |           |           |           | e         |
|           |           |           |           |           | valorizza |
|           |           |           |           |           | to        |
|           |           |           |           |           | nel caso  |
|           |           |           |           |           | di        |
|           |           |           |           |           | tipoCanal |
|           |           |           |           |           | eEsito    |
|           |           |           |           |           | = 2       |
|           |           |           |           |           | oppure    |
|           |           |           |           |           | 4         |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataEsito | 3         | an        | 1..1      | 10        | Data di   |
|           |           |           |           |           | produzion |
|           |           |           |           |           | e         |
|           |           |           |           |           | dell'esit |
|           |           |           |           |           | o         |
|           |           |           |           |           | da parte  |
|           |           |           |           |           | del       |
|           |           |           |           |           | NodoSPC o |
|           |           |           |           |           | del       |
|           |           |           |           |           | canale di |
|           |           |           |           |           | avvisatur |
|           |           |           |           |           | a         |
|           |           |           |           |           | utilizzat |
|           |           |           |           |           | o         |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           | [YYYY]-   |
|           |           |           |           |           | [MM]-[DD] |
|           |           |           |           |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| codice    | 3         | n         | 1..1      | 5         | Esito     |
| Esito     |           |           |           |           | dell'invi |
|           |           |           |           |           | o         |
|           |           |           |           |           | riferito  |
|           |           |           |           |           | al        |
|           |           |           |           |           | singolo   |
|           |           |           |           |           | canale.   |
|           |           |           |           |           |           |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | **0**     |
|           |           |           |           |           | esito     |
|           |           |           |           |           | positivo  |
|           |           |           |           |           |           |
|           |           |           |           |           | **1**     |
|           |           |           |           |           | esito     |
|           |           |           |           |           | negativo  |
|           |           |           |           |           |           |
|           |           |           |           |           | **n>1**   |
|           |           |           |           |           | altri     |
|           |           |           |           |           | esiti     |
|           |           |           |           |           | da        |
|           |           |           |           |           | definire  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| descr     | 3         | an        | 0..1      | 140       | Testo     |
| izioneEsi |           |           |           |           | libero    |
| to        |           |           |           |           | che, in   |
|           |           |           |           |           | caso di   |
|           |           |           |           |           | esito     |
|           |           |           |           |           | negativo  |
|           |           |           |           |           | (codiceEs |
|           |           |           |           |           | ito<>0),  |
|           |           |           |           |           | descrive  |
|           |           |           |           |           | l’evento  |
|           |           |           |           |           | stesso.   |
+-----------+-----------+-----------+-----------+-----------+-----------+

File XML scambiati con l’Ente Creditore
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _File XML scambiati con l’Ente Creditore:

La comunicazione delle richieste via file transfer di avviso digitale
tra Ente Creditore e Nodo dei Pagamenti-SPC è prevista mediante scambio
di file XML. L’Ente Creditore deve accorpare le richieste di avvisatura
in un file giornaliero unico, ciascuna richiesta deve essere codificata
secondo lo schema di Tabella 12. Il file così predisposto deve essere
compresso con algoritmo gzip e inviato via SFTP al Nodo dei
Pagamenti-SPC il quale risponderà mediante i file di esito descritti in
seguito.

File delle richieste di inoltro dell’avviso digitale e di esito
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _File delle richieste di inoltro dell’avviso digitale e di esito:

Lo schema di Tabella 19 definisce la struttura XML che l’Ente Creditore
deve utilizzare per comporre il file contenente le richieste di inoltro
degli avvisi.

**Tabella** **21 - Tracciato XML per comunicazione “Lista Avvisi digitali”**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **c**     | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| lista     | 1         | s         | 1..1      |           | Lista     |
| AvvisiDig |           |           |           |           | degli     |
| itali     |           |           |           |           | avvisi    |
|           |           |           |           |           | digitali  |
|           |           |           |           |           | trasmessi |
+-----------+-----------+-----------+-----------+-----------+-----------+
| versi     | 2         | an        | 1..1      | 1..16     | Versione  |
| oneOggett |           |           |           |           | che       |
| o         |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | l’oggetto |
|           |           |           |           |           | scambiato |
|           |           |           |           |           | e lo      |
|           |           |           |           |           | schema    |
|           |           |           |           |           | XSD per   |
|           |           |           |           |           | la        |
|           |           |           |           |           | verifica  |
|           |           |           |           |           | sintattic |
|           |           |           |           |           | a         |
|           |           |           |           |           | dell’avvi |
|           |           |           |           |           | so.       |
|           |           |           |           |           |           |
|           |           |           |           |           | (Esempio: |
|           |           |           |           |           | 1.0)      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| avvis     | 2         | s         | 1..10\ :s |           | Numero    |
| oDigitale |           |           | up:`5`    |           | non       |
|           |           |           |           |           | definito  |
|           |           |           |           |           | di        |
|           |           |           |           |           | occorrenz |
|           |           |           |           |           | e         |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | avvisoDig |
|           |           |           |           |           | itale     |
|           |           |           |           |           | così come |
|           |           |           |           |           | definita  |
|           |           |           |           |           | in        |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 19.       |
+-----------+-----------+-----------+-----------+-----------+-----------+

Per problemi di gestibilità del servizio di avvisatura, il numero
massimo delle occorrenze di avvisi digitali presenti in un flusso
scambiato è fissato in 100.000.

La struttura utilizzata dal Nodo dei Pagamenti-SPC per comunicare gli
esiti relativi all'inoltro degli avvisi digitali richiesti dall’Ente
Creditore con il flusso di cui sopra è indicata in Tabella 22.

**Tabella** **22 - Tracciato XML per comunicazione “Lista esito inoltro Avvisi digitali”**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **c**     | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| lista     | 1         | s         | 1..1      |           | Lista     |
| EsitoAvvi |           |           |           |           | degli     |
| siDigital |           |           |           |           | esiti di  |
| i         |           |           |           |           | inoltro   |
|           |           |           |           |           | degli     |
|           |           |           |           |           | avvisi    |
|           |           |           |           |           | digitali. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| versi     | 2         | an        | 1..1      | 1..16     | Versione  |
| oneOggett |           |           |           |           | che       |
| o         |           |           |           |           | identific |
|           |           |           |           |           | a         |
|           |           |           |           |           | l’oggetto |
|           |           |           |           |           | scambiato |
|           |           |           |           |           | e lo      |
|           |           |           |           |           | schema    |
|           |           |           |           |           | XSD per   |
|           |           |           |           |           | la        |
|           |           |           |           |           | verifica  |
|           |           |           |           |           | sintattic |
|           |           |           |           |           | a         |
|           |           |           |           |           | dell’avvi |
|           |           |           |           |           | so.       |
|           |           |           |           |           |           |
|           |           |           |           |           | (Esempio: |
|           |           |           |           |           | 1.0)      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..70     | Identific |
| ificativo |           |           |           |           | ativo     |
| Flusso    |           |           |           |           | del       |
|           |           |           |           |           | flusso    |
|           |           |           |           |           | così come |
|           |           |           |           |           | definito  |
|           |           |           |           |           | al §      |
|           |           |           |           |           | 8.5.2.1.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| esito     | 2         | s         | 1..10\ :s |           | Numero    |
| AvvisoDig |           |           | up:`5`    |           | non       |
| itale     |           |           |           |           | definito  |
|           |           |           |           |           | di        |
|           |           |           |           |           | occorrenz |
|           |           |           |           |           | e         |
|           |           |           |           |           | della     |
|           |           |           |           |           | struttura |
|           |           |           |           |           | esitoAvvi |
|           |           |           |           |           | soDigital |
|           |           |           |           |           | e         |
|           |           |           |           |           | così come |
|           |           |           |           |           | definita  |
|           |           |           |           |           | in        |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 20.       |
+-----------+-----------+-----------+-----------+-----------+-----------+

Si ricorda che, per problemi di gestibilità del servizio di avvisatura,
il numero massimo delle occorrenze di esiti di avvisi digitali presenti
in un flusso scambiato è fissato in 100.000.

File di segnalazione di presa in carico
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _MFile di segnalazione di presa in carico:

Lo schema di Tabella 23 rappresenta il file, predisposto da un Ente
Creditore o dal Nodo dei Pagamenti-SPC, per segnalare alla controparte
la presa in carico di un file relativo allo scambio di avvisi digitali o
del loro esito.

**Tabella** **23 - Tracciato XML per la segnalazione di “Presa in carico” (File di ACK)**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| esito     | 1         | s         | 1..1      |           | Struttura |
| PresaInCa |           |           |           |           | che       |
| rico      |           |           |           |           | contiene  |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | relative  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | presa in  |
|           |           |           |           |           | carico    |
|           |           |           |           |           | delle     |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | trasmesse |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..70     | Identific |
| ificativo |           |           |           |           | ativo     |
| Flusso    |           |           |           |           | del       |
|           |           |           |           |           | flusso    |
|           |           |           |           |           | così come |
|           |           |           |           |           | definito  |
|           |           |           |           |           | al §      |
|           |           |           |           |           | 8.5.2.1.  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| codic     | 2         | n         | 1..1      | 1         | Rappresen |
| eEsitoPre |           |           |           |           | ta        |
| saInCaric |           |           |           |           | il codice |
| o         |           |           |           |           | circa     |
|           |           |           |           |           | l’esito   |
|           |           |           |           |           | della     |
|           |           |           |           |           | presa in  |
|           |           |           |           |           | carico    |
|           |           |           |           |           | del       |
|           |           |           |           |           | flusso di |
|           |           |           |           |           | avvisi    |
|           |           |           |           |           | digitali. |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | uno dei   |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | 1. Preso  |
|           |           |           |           |           | in carico |
|           |           |           |           |           |           |
|           |           |           |           |           | 2. File   |
|           |           |           |           |           | compreso  |
|           |           |           |           |           | illegibile|
|           |           |           |           |           |           |
|           |           |           |           |           | 3. Errori |
|           |           |           |           |           | di        |
|           |           |           |           |           | *parsing* |
|           |           |           |           |           | file      |
|           |           |           |           |           | XML       |
|           |           |           |           |           |           |
|           |           |           |           |           | 4. Errore |
|           |           |           |           |           | di valida |
|           |           |           |           |           | zione     |
|           |           |           |           |           | con       |
|           |           |           |           |           | XSD       |
|           |           |           |           |           |           |
|           |           |           |           |           | 5. Errore |
|           |           |           |           |           | di valida |
|           |           |           |           |           | zione     |
|           |           |           |           |           | extra     |
|           |           |           |           |           | XSD       |
|           |           |           |           |           |           |
|           |           |           |           |           | 6. Invio  |
|           |           |           |           |           | duplicato |
|           |           |           |           |           |           |
|           |           |           |           |           | 7. Altri  |
|           |           |           |           |           | errori    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| descr     | 2         | an        | 0..1      | 1..140    | Testo     |
| izioneEsi |           |           |           |           | descritti |
| toPresaIn |           |           |           |           | vo        |
| Carico    |           |           |           |           | dell’erro |
|           |           |           |           |           | re        |
|           |           |           |           |           | rilevato. |
|           |           |           |           |           |           |
|           |           |           |           |           | Obbliga   |
|           |           |           |           |           | torio     |
|           |           |           |           |           | se        |
|           |           |           |           |           | l'esito è |
|           |           |           |           |           | diverso   |
|           |           |           |           |           | da 0.     |
+-----------+-----------+-----------+-----------+-----------+-----------+

Scambio informazioni via web service
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Scambio informazioni via web service:

Lo scambio delle informazioni relative all'avvisatura digitale tra Nodo
dei Pagamenti-SPC, Ente Creditore e PSP avviene, come indicato nei
paragrafi successivi, attraverso protocollo SOAP. In questo paragrafo
sono definiti puntualmente alcuni parametri previsti dalle primitive di
colloquio. In particolare saranno descritti nel dettaglio gli elementi
componenti i seguenti parametri:

1) I-4 avvisoDigitaleWS, *request* della primitiva
   **nodoInviaAvvisoDigitale**

2) O-2 esitoAvvisoDigitaleWS, *response* della primitiva
   **nodoInviaAvvisoDigitale**,

3) I-4 avvisoDigitale, *request* della primitiva
   **pspInviaAvvisoDigitale**

4) I-5 datiNotifica, *request* della primitiva
   **nodoAggiornaIscrizioneAvvisatura**

Invio dell’avviso digitale al NodoSPC
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Invio dell’avviso digitale al NodoSPC:

Le informazioni elencate di seguito (vedi Tabella 26) definiscono il
parametro avvisoDigitaleWS presente nella *request* della primitiva
**nodoInviaAvvisoDigitale**; il livello della struttura così definita
inizia da 2 in quanto descritta formalmente all'interno del WSDL del
servizio.

**Tabella** **24 - Componenti del parametro avvisoDigitaleWS**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| avvis     | 2         | s         | 1..1      |           | Contiene  |
| oDigitale |           |           |           |           | le stesse |
| WS        |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | definite  |
|           |           |           |           |           | per la    |
|           |           |           |           |           | struttura |
|           |           |           |           |           | avvisoDig |
|           |           |           |           |           | itale,    |
|           |           |           |           |           | specifica |
|           |           |           |           |           | ta        |
|           |           |           |           |           | nella     |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 19 al §   |
|           |           |           |           |           | 5.4.1.    |
+-----------+-----------+-----------+-----------+-----------+-----------+

In Tabella 25 sono elencate le informazioni che definiscono il parametro
esitoAvvisoDigitaleWS presente nella *response* della primitiva
**nodoInviaAvvisoDigitale**; il livello della struttura così definita
inizia da 2 in quanto descritta formalmente all'interno del WSDL del
servizio.

**Tabella** **25 - Componenti del parametro esitoAvvisoDigitaleWS**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| esito     | 2         | s         | 1..1      |           | Contiene  |
| AvvisoDig |           |           |           |           | le stesse |
| italeWS   |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | specifica |
|           |           |           |           |           | te        |
|           |           |           |           |           | per la    |
|           |           |           |           |           | struttura |
|           |           |           |           |           | esitoAvvi |
|           |           |           |           |           | soDigital |
|           |           |           |           |           | e,        |
|           |           |           |           |           | definita  |
|           |           |           |           |           | nella     |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 20 al §   |
|           |           |           |           |           | 5.4.1.    |
+-----------+-----------+-----------+-----------+-----------+-----------+

Recapito dell’avviso digitale ai PSP
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Recapito dell’avviso digitale ai PSP:

Le informazioni elencate di seguito (vedi Tabella 26) definiscono il
parametro avvisoDigitale presente nella *request* della primitiva
**pspInviaAvvisoDigitale** (`cfr. § 9.2.7.1 <../16-Capitolo_9/Capitolo9.rst#pspinviaavvisodigitale>`__); il livello della
struttura così definita inizia da 2 in quanto descritta formalmente
all'interno del WSDL del servizio.

**Tabella** **26 - Componenti del parametro avvisoDigitale**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| avviso    | 2         | s         | 1..1      |           | Contiene  |
| Digitale  |           |           |           |           | le stesse |
| WS        |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | definite  |
|           |           |           |           |           | per la    |
|           |           |           |           |           | struttura |
|           |           |           |           |           | avvisoDig |
|           |           |           |           |           | itale,    |
|           |           |           |           |           | specifica |
|           |           |           |           |           | ta        |
|           |           |           |           |           | nella     |
|           |           |           |           |           | Tabella   |
|           |           |           |           |           | 19 al §   |
|           |           |           |           |           | 5.4.1.    |
+-----------+-----------+-----------+-----------+-----------+-----------+

Notifica dell’iscrizione al servizio di avvisatura digitale
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Notifica dell’iscrizione al servizio di avvisatura digitale:

Le informazioni elencate di seguito definiscono la componente
"datiNotifica" (parametro I-5) presente nella *request* della primitiva
**nodoAggiornaIscrizioneAvvisatura** (`cfr. § 9.2.7.2 <../16-Capitolo_9/Capitolo9.rst#nodoaggiornaiscrizioniavvisatura>`__); il livello
della struttura così definita inizia da 2 in quanto descritta
formalmente all'interno del WSDL del servizio.

**Tabella** **27 - Componenti del parametro datiNotifica**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| dataOra   | 2         | an        | 1..1      | 1..19     | Indica la |
| Richiesta |           |           |           |           | data e    |
|           |           |           |           |           | l’ora     |
|           |           |           |           |           | dell’even |
|           |           |           |           |           | to        |
|           |           |           |           |           | di invio  |
|           |           |           |           |           | della     |
|           |           |           |           |           | richiesta |
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
|           |           |           |           |           | ]:[ss]    |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | an        | 1..1      | 1..20     | Identific |
| ificativo |           |           |           |           | ativo     |
| Messaggio |           |           |           |           | legato    |
| Richiesta |           |           |           |           | alla      |
|           |           |           |           |           | trasmissi |
|           |           |           |           |           | one       |
|           |           |           |           |           | della     |
|           |           |           |           |           | segnalazi |
|           |           |           |           |           | one       |
|           |           |           |           |           | digitale  |
|           |           |           |           |           | e         |
|           |           |           |           |           | consente  |
|           |           |           |           |           | di        |
|           |           |           |           |           | riconosce |
|           |           |           |           |           | re        |
|           |           |           |           |           | la        |
|           |           |           |           |           | trasmissi |
|           |           |           |           |           | one       |
|           |           |           |           |           | duplicata |
|           |           |           |           |           |           |
|           |           |           |           |           | Deve      |
|           |           |           |           |           | essere    |
|           |           |           |           |           | univoco   |
|           |           |           |           |           | nell’ambi |
|           |           |           |           |           | to        |
|           |           |           |           |           | di 365    |
|           |           |           |           |           | giorni    |
|           |           |           |           |           | consecuti |
|           |           |           |           |           | vi.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| ident     | 2         | s         | 1..1      |           | Aggregazi |
| ificativo |           |           |           |           | one       |
| UnivocoSo |           |           |           |           | che       |
| ggetto    |           |           |           |           | riporta   |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | concernen |
|           |           |           |           |           | ti        |
|           |           |           |           |           | l’identif |
|           |           |           |           |           | icazione  |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagatore. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| tipoI     | 3         | an        | 1..1      | 1         | Campo     |
| dentifica |           |           |           |           | alfanumer |
| tivoUnivo |           |           |           |           | ico       |
| co        |           |           |           |           | che       |
|           |           |           |           |           | indica la |
|           |           |           |           |           | natura    |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagatore, |
|           |           |           |           |           | può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘F’**\ =|
|           |           |           |           |           | Persona   |
|           |           |           |           |           | fisica    |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘G’**\ =|
|           |           |           |           |           | Persona   |
|           |           |           |           |           | Giuridica.|
+-----------+-----------+-----------+-----------+-----------+-----------+
| codic     | 3         | an        | 1..1      | 1..35     | Campo     |
| eIdentifi |           |           |           |           | alfanumer |
| cativoUni |           |           |           |           | ico       |
| voco      |           |           |           |           | che può   |
|           |           |           |           |           | contenere |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | o, in     |
|           |           |           |           |           | alternati |
|           |           |           |           |           | va,       |
|           |           |           |           |           | la        |
|           |           |           |           |           | partita   |
|           |           |           |           |           | IVA del   |
|           |           |           |           |           | pagatore. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| azion     | 2         | an        | 1..1      | 1         | Indica il |
| eDiAggior |           |           |           |           | tipo di   |
| namento   |           |           |           |           | aggiornam |
|           |           |           |           |           | ento      |
|           |           |           |           |           | richiesto |
|           |           |           |           |           | :         |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘A’**\ =|
|           |           |           |           |           | Attivazio |
|           |           |           |           |           | ne        |
|           |           |           |           |           |           |
|           |           |           |           |           | **‘D’**\ =|
|           |           |           |           |           | disattiva |
|           |           |           |           |           | zione     |
+-----------+-----------+-----------+-----------+-----------+-----------+

Richiesta posizione debitoria presso un Ente Creditore
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. _Richiesta posizione debitoria presso un Ente Creditore:

Le informazioni elencate in Tabella 28 definiscono il parametro O-2
elencoAvvisiDigitali presente nella *response* della primitiva
**nodoChiediElencoAvvisiDigitali** disponibile per i PSP che erogano
il servizio di invio degli avvisi su iniziativa del PSP (modalità pull)
e della correlata primitiva **paaChiediElencoAvvisiDigitali** (`cfr. §
8.2.8.1 <../15-Capitolo_8/Capitolo8.rst#paachiedielencoavvisidigitali>`__) messa a disposizione dall'Ente Creditore; il livello della
struttura così definita inizia da 2 in quanto descritta formalmente
all'interno del WSDL del servizio.

**Tabella** **28 - Componenti del parametro elencoAvvisiDigitali**

+-----------+-----------+-----------+-----------+-----------+-----------+
| **Dato**  | **Liv**   | **Genere**| **Occ**   | **Len**   |**Contenu**|
|           |           |           |           |           |**to**     |
+===========+===========+===========+===========+===========+===========+
| ident     | 2         | an        | 1..1      | 1..35     | Campo     |
| ificativo |           |           |           |           | alfanumer |
| Dominio   |           |           |           |           | ico       |
|           |           |           |           |           | contenent |
|           |           |           |           |           | e         |
|           |           |           |           |           | il codice |
|           |           |           |           |           | fiscale   |
|           |           |           |           |           | dell'Ente |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | che invia |
|           |           |           |           |           | l'elenco  |
|           |           |           |           |           | degli     |
|           |           |           |           |           | avvisi    |
|           |           |           |           |           | Digitali. |
+-----------+-----------+-----------+-----------+-----------+-----------+
| elenc     | 2         | n         | 1..1      | 1         | Indica se |
| oCompleto |           |           |           |           | l'elenco  |
|           |           |           |           |           | fornito   |
|           |           |           |           |           | contiene  |
|           |           |           |           |           | tutte le  |
|           |           |           |           |           | posizioni |
|           |           |           |           |           | di debito |
|           |           |           |           |           | per quel  |
|           |           |           |           |           | soggetto  |
|           |           |           |           |           | debitore  |
|           |           |           |           |           | presso    |
|           |           |           |           |           | l'Ente    |
|           |           |           |           |           | Creditore |
|           |           |           |           |           | .         |
|           |           |           |           |           |           |
|           |           |           |           |           | Può       |
|           |           |           |           |           | assumere  |
|           |           |           |           |           | i         |
|           |           |           |           |           | seguenti  |
|           |           |           |           |           | valori:   |
|           |           |           |           |           |           |
|           |           |           |           |           | 1. Elenco |
|           |           |           |           |           | completo  |
|           |           |           |           |           |           |
|           |           |           |           |           | 2. Elenco |
|           |           |           |           |           | incompleto|
+-----------+-----------+-----------+-----------+-----------+-----------+
| numer     | 2         | n         | 1..1      | 3         | Numero    |
| oAvvisi   |           |           |           |           | avvisi    |
|           |           |           |           |           | presenti  |
|           |           |           |           |           | nell'elen |
|           |           |           |           |           | co.       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| avvis     | 2         | s         | 0..n      |           | Struttura |
| oDigitale |           |           |           |           | facoltati |
|           |           |           |           |           | va        |
|           |           |           |           |           | che       |
|           |           |           |           |           | contiene  |
|           |           |           |           |           | le        |
|           |           |           |           |           | informazi |
|           |           |           |           |           | oni       |
|           |           |           |           |           | dell'avvi |
|           |           |           |           |           | so        |
|           |           |           |           |           | digitale  |
|           |           |           |           |           | in        |
|           |           |           |           |           | modalità  |
|           |           |           |           |           | *pull*.   |
|           |           |           |           |           |           |
|           |           |           |           |           | La        |
|           |           |           |           |           | struttura |
|           |           |           |           |           | è         |
|           |           |           |           |           | obbliga   |
|           |           |           |           |           | toria     |
|           |           |           |           |           | se        |
|           |           |           |           |           | l'element |
|           |           |           |           |           | o         |
|           |           |           |           |           | numeroA   |
|           |           |           |           |           | vvisi     |
|           |           |           |           |           | e         |
|           |           |           |           |           | maggiore  |
|           |           |           |           |           | di 0.     |
+-----------+-----------+-----------+-----------+-----------+-----------+
| codice    | 3         | an        | 1..1      | 18        | Codice    |
| Avviso    |           |           |           |           | dell’avvi |
|           |           |           |           |           | so        |
|           |           |           |           |           | di        |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | predispos |
|           |           |           |           |           | to        |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | quanto    |
|           |           |           |           |           | indicato  |
|           |           |           |           |           | al §      |
|           |           |           |           |           | 7.4.1     |
|           |           |           |           |           | delle     |
|           |           |           |           |           | SANP.     |
|           |           |           |           |           |           |
|           |           |           |           |           | Contiene  |
|           |           |           |           |           | il codice |
|           |           |           |           |           | IUV.      |
+-----------+-----------+-----------+-----------+-----------+-----------+
| stato     | 3         | an        | 1..1      | 1.2       | 00 –      |
| Pagamento |           |           |           |           | L’avviso  |
|           |           |           |           |           | è         |
|           |           |           |           |           | pagabile  |
|           |           |           |           |           |           |
|           |           |           |           |           | 01 –      |
|           |           |           |           |           | L’avviso  |
|           |           |           |           |           | è già     |
|           |           |           |           |           | stato     |
|           |           |           |           |           | pagato    |
|           |           |           |           |           |           |
|           |           |           |           |           | 02 –      |
|           |           |           |           |           | L’avviso  |
|           |           |           |           |           | non è     |
|           |           |           |           |           | pagabile  |
+-----------+-----------+-----------+-----------+-----------+-----------+
| dataScade | 3         | an        | 0..1      | 10        | Indica la |
| nzaAvviso |           |           |           |           | data,     |
|           |           |           |           |           | successiv |
|           |           |           |           |           | a         |
|           |           |           |           |           | alla data |
|           |           |           |           |           | di        |
|           |           |           |           |           | scadenza  |
|           |           |           |           |           | sino alla |
|           |           |           |           |           | quale si  |
|           |           |           |           |           | ritiene   |
|           |           |           |           |           | valido    |
|           |           |           |           |           | l'avviso, |
|           |           |           |           |           | secondo   |
|           |           |           |           |           | il        |
|           |           |           |           |           | formato   |
|           |           |           |           |           | ISO 8601  |
|           |           |           |           |           |           |
|           |           |           |           |           | [YYYY     |
|           |           |           |           |           | ]-[MM]-[  |
|           |           |           |           |           | DD]       |
+-----------+-----------+-----------+-----------+-----------+-----------+
| importo   | 3         | an        | 1..1      | 3..12     | Campo     |
| Avviso    |           |           |           |           | numerico  |
|           |           |           |           |           | (due      |
|           |           |           |           |           | cifre per |
|           |           |           |           |           | la parte  |
|           |           |           |           |           | decimale, |
|           |           |           |           |           | il        |
|           |           |           |           |           | separator |
|           |           |           |           |           | e         |
|           |           |           |           |           | dei       |
|           |           |           |           |           | centesimi |
|           |           |           |           |           | è il      |
|           |           |           |           |           | punto     |
|           |           |           |           |           | “.”),     |
|           |           |           |           |           | indicante |
|           |           |           |           |           | l’importo |
|           |           |           |           |           | relativo  |
|           |           |           |           |           | alla      |
|           |           |           |           |           | somma da  |
|           |           |           |           |           | versare.  |
|           |           |           |           |           |           |
|           |           |           |           |           | Deve      |
|           |           |           |           |           | essere    |
|           |           |           |           |           | maggiore  |
|           |           |           |           |           | di        |
|           |           |           |           |           | “0.10”.   |
+-----------+-----------+-----------+-----------+-----------+-----------+
| descr     | 3         | an        | 1..1      | 1..249    | Testo     |
| izionePag |           |           |           |           | libero a  |
| amento    |           |           |           |           | disposizi |
|           |           |           |           |           | one       |
|           |           |           |           |           | dell’Ente |
|           |           |           |           |           | per       |
|           |           |           |           |           | descriver |
|           |           |           |           |           | e         |
|           |           |           |           |           | le        |
|           |           |           |           |           | motivazio |
|           |           |           |           |           | ni        |
|           |           |           |           |           | del       |
|           |           |           |           |           | pagamento |
|           |           |           |           |           | .         |
+-----------+-----------+-----------+-----------+-----------+-----------+

`Torna all'indice <../index.rst>`__

.. [1]
   Ai fini della corrispondenza UNIFI, il soggetto pagatore è associato
   al Message Element *Ultimate Debtor* nel caso sia presente il
   soggetto versante, mentre nel caso contrario è associato al Message
   Element *Debtor*.

.. [2]
   Vedi
   `https://www.w3.org/TR/xmlenc-core/#sec-SHA256 <https://www.w3.org/TR/xmlenc-core/#sec-SHA256>`__

.. [3]
   Vedi nota 1.

.. [4]
   Vedi nota 1.

.. [5]
   Vedi nota 1.

.. |AGID_logo_carta_intestata-02.png| image:: ../media/header.png
   :width: 5.90551in
   :height: 1.30277in
