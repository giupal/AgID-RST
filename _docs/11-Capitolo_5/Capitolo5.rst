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

+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
|         **Dato**        | **Liv** | **Genere** | **Occ** | **Len** | **UNIFI**       | **Contenuto**                             |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| versioneOggetto         | 1       | an         | 1..1    | 1..16   | VersionNumber   | Versione che identifica                   |
|                         |         |            |         |         |                 | l’oggetto scambiato.                      |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| Dominio                 | 1       | s          | 1..1    |         | Initiating      | Aggregato “dominio”                       |
|                         |         |            |         |         | Party           | che riporta le informazioni               |
|                         |         |            |         |         |                 | che consentono di                         |
|                         |         |            |         |         |                 | individuare                               |
|                         |         |            |         |         |                 | univocamente l’ambito di                  |
|                         |         |            |         |         |                 | applicazione della                        |
|                         |         |            |         |         |                 | richiesta.                                |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| identificativoDominio   | 2       | an         | 1..1    | 1..35   | Tax             | Campo alfanumerico                        |
|                         |         |            |         |         | Identification  | contenente il                             |
|                         |         |            |         |         | Number          | codice fiscale della struttura            |
|                         |         |            |         |         |                 | che invia                                 |
|                         |         |            |         |         |                 | la richiesta di pagamento.                |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| identificativoStazione  | 2       | an         |         | 1..35   | Name            | Identifica la stazione                    |
| Richiedente             |         |            |         |         |                 | richiedente il                            |
|                         |         |            |         |         |                 | pagamento secondo                         |
|                         |         |            |         |         |                 | una codifica                              |
|                         |         |            |         |         |                 | predefinita dal mittente                  |
|                         |         |            |         |         |                 | che ne deve                               |
|                         |         |            |         |         |                 | dare evidenza a richiesta.                |
|                         |         |            |         |         |                 | Il Nodo dei                               |
|                         |         |            |         |         |                 | Pagamenti-SPC non                         |
|                         |         |            |         |         |                 | effettuaverifiche di                      |
|                         |         |            |         |         |                 | congruenza                                |
|                         |         |            |         |         |                 | su tale dato.                             |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| identificativoMessaggio | 1       | an         |         | 1..35   | Message         | Identificativo legato alla                |
| Richiesta               |         |            |         |         | Identification  | trasmissione della                        |
|                         |         |            |         |         |                 | richiesta di pagamento.                   |
|                         |         |            |         |         |                 | Deve essere univoco                       |
|                         |         |            |         |         |                 | nell’ambito della stessa                  |
|                         |         |            |         |         |                 | data riferita all’elemento,               |
|                         |         |            |         |         |                 | dataOraMessaggioRichiesta.                |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| dataOraMessaggio        | 1       | an         |         | 19      | Creation        | Indica la data e l’ora digenerazione      |
| Richiesta               |         |            |         |         | Date            | del messaggio di richiesta di             |
|                         |         |            |         |         | Time            | pagamento secondo il formato              |
|                         |         |            |         |         |                 | ISO 8601                                  |
|                         |         |            |         |         |                 | [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]           |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| autenticazione          | 1       | an         |         | 4       | Proprietary     | Contiene la modalità di                   |
| Soggetto                |         |            |         |         | Code            | identificazione                           |
|                         |         |            |         |         |                 | applicata al soggetto che deve            |
|                         |         |            |         |         |                 | essere addebitato per il pagamento:       |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | - **CNS** = CIE/CNS,                      |
|                         |         |            |         |         |                 | - **USR** = Userid e password,            |
|                         |         |            |         |         |                 | - **OTH** = Altro,                        |
|                         |         |            |         |         |                 | - **N/A** = Non applicabile               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| SoggettoVersante        | 1       | s          |         |         | Debtor          | Aggregazione “versante” che               |
|                         |         |            |         |         |                 | riporta le informazioni concernenti       |
|                         |         |            |         |         |                 | il soggetto che                           |
|                         |         |            |         |         |                 | effettua il pagamento per conto           |
|                         |         |            |         |         |                 | del soggetto                              |
|                         |         |            |         |         |                 | Pagatore.                                 |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| identificativoUnivoco   | 2       | s          |         |         |                 | Aggregazione che riporta le               |
| Versante                |         |            |         |         |                 | informazioni                              |
|                         |         |            |         |         |                 | concernenti l’identificazione             |
|                         |         |            |         |         |                 | fiscale del                               |
|                         |         |            |         |         |                 | versante.                                 |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| tipoIdentificativo      | 3       | an         |         | 1       | Proprietary     | Campo alfanumerico che indica la          |
| Univoco                 |         |            |         |         | Code            | natura del versante;                      |
|                         |         |            |         |         |                 | può assumere i seguenti valori:           |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | - **F** = Persona fisica                  |
|                         |         |            |         |         |                 | - **G** = Persona Giuridica.              |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| codiceIdentificativo    | 3       | an         |         | 1..35   | Tax             | Campo alfanumerico che può                |
| Univoco                 |         |            |         |         | Identification  | contenere il,codice fiscale o,            |
|                         |         |            |         |         | Number          | in alternativa, la partita IVA            |
|                         |         |            |         |         |                 | del soggetto versante.                    |
|                         |         |            |         |         |                 | Nei casi applicabili,                     |
|                         |         |            |         |         |                 | quando non è                              |
|                         |         |            |         |         |                 | possibile identificare                    |
|                         |         |            |         |         |                 | fiscalmente il soggetto,                  |
|                         |         |            |         |         |                 | può essere utilizzato il valore           |
|                         |         |            |         |         |                 | **ANONIMO**                               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| anagraficaVersante      | 2       | an         |         | 1..70   | Name            | Indica il nominativo o la ragione         |
|                         |         |            |         |         |                 | sociale del versante.                     |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| indirizzoVersante       | 3       | an         |         | 1..70   | StreetName      | Indica l’indirizzo del versante.          |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| civicoVersante          | 3       | an         |         | 1..16   | Building        | Indica il                                 |
|                         |         |            |         |         | Number          | numero civico del versante.               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| capVersante             | 3       | an         |         | 1..16   | Postal Code     | Indica il                                 |
|                         |         |            |         |         |                 | CAP del versante.                         |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| localitaVersante        | 3       | an         |         | 1..35   | Town Name       | Indica la                                 |
|                         |         |            |         |         |                 | località del versante.                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| provinciaVersante       | 3       | an         |         | 1..35   | Country         | Indica la                                 |
|                         |         |            |         |         | SubDivision     | provincia del versante.                   |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| nazioneVersante         | 3       | an         |         | 2       | Country         | Indica il                                 |
|                         |         |            |         |         |                 | codice nazione del versante               |
|                         |         |            |         |         |                 | secondo lo standard ISO 3166.             |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| e-mailVersante          | 3       | an         |         | 1..256  | Remittance      | Indirizzo                                 |
|                         |         |            |         |         | Location        | di posta elettronica del versante.        |
|                         |         |            |         |         | Electronic      |                                           |
|                         |         |            |         |         | Address         |                                           |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| soggettoPagatore        | 1       | s          |         |         | Ultimate        | Aggregazione                              |
|                         |         |            |         |         | Debtor/Debtor   | “soggetto pagatore”                       |
|                         |         |            |         |         |                 | che rappresenta il                        |
|                         |         |            |         |         |                 | **soggetto**                              |
|                         |         |            |         |         |                 | (Persona Fisica 1..1 Giuridica)           |
|                         |         |            |         |         |                 | debitore di somme di denaro nei           |
|                         |         |            |         |         |                 | confronti                                 |
|                         |         |            |         |         |                 | della Pubblica Amministrazione            |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| identificativoUnivoco   | 2       | s          |         |         |                 | Aggregazione                              |
| Pagatore                |         |            |         |         |                 | che riporta le informazioni               |
|                         |         |            |         |         |                 | concernenti l’identificazione             |
|                         |         |            |         |         |                 | fiscale del pagatore.                     |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| tipoIdentificativo      | 3       | an         |         | 1       | Proprietary     | Campo alfanumerico che indica             |
| Univoco                 |         |            |         |         | Code            | la natura del pagatore                    |
|                         |         |            |         |         |                 | può assumere i seguenti                   |
|                         |         |            |         |         |                 | valori:                                   |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | - **F** = Persona fisica,                 |
|                         |         |            |         |         |                 | - **G** = Persona Giuridica.              |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| codiceIdentificativo    | 3       | an         |         | 1..35   | Tax             | Campo alfanumerico che può                |
| Univoco                 |         |            |         |         | Identification  | contenere il codice fiscale o,            |
|                         |         |            |         |         | Number          | in alternativa, la partita                |
|                         |         |            |         |         |                 | IVA del pagatore.                         |
|                         |         |            |         |         |                 | Nei casi applicabili,                     |
|                         |         |            |         |         |                 | quando non è possibile                    |
|                         |         |            |         |         |                 | identificare fiscalmente                  |
|                         |         |            |         |         |                 | il oggetto, può essere                    |
|                         |         |            |         |         |                 | utilizzato il valore                      |
|                         |         |            |         |         |                 | **“ANONIMO”**                             |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| anagraficaPagatore      | 2       | an         |         | 1..70   | Name            | Indica il                                 |
|                         |         |            |         |         |                 | nominativo o la ragione                   |
|                         |         |            |         |         |                 | sociale del pagatore                      |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| indirizzoPagatore       | 2       | an         |         | 1..70   | Street Name     | Indica                                    |
|                         |         |            |         |         |                 | l’indirizzo del pagatore                  |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| civicoPagatore          | 2       | an         |         | 1..16   | Building        | Indica il                                 |
|                         |         |            |         |         | Number          | numero civico del pagatore.               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| capPagatore             | 2       | an         |         | 1..16   | Postal Code     | Indica il                                 |
|                         |         |            |         |         |                 | CAP del pagatore                          |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| localitaPagatore        | 2       | an         |         | 1..35   | Town Name       | Indica la                                 |
|                         |         |            |         |         |                 | località del pagatore.                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| provinciaPagatore       | 2       | an         |         | 1..35   | Country         | Indica la                                 |
|                         |         |            |         |         | SubDivision     | provincia del pagatore                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| nazionePagatore         | 2       | an         |         | 2       | Country         | Indica ilcodice nazione del               |
|                         |         |            |         |         |                 | pagatore secondo lo standard              |
|                         |         |            |         |         |                 | ISO 3166.                                 |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| e-mailPagatore          | 2       | an         |         | 1..256  | Remittance      | Indirizzo di posta elettronica            |
|                         |         |            |         |         | Location        | del pagatore                              |
|                         |         |            |         |         | Electronic      |                                           |
|                         |         |            |         |         | Address         |                                           |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| enteBeneficiario        | 1       | s          |         |         | Creditor        | Aggregazione                              |
|                         |         |            |         |         |                 | “ente beneficiario” creditore             |
|                         |         |            |         |         |                 | di somme nei confronti del                |
|                         |         |            |         |         |                 | soggetto                                  |
|                         |         |            |         |         |                 | pagatore; è costituita dai                |
|                         |         |            |         |         |                 | seguenti elementi:                        |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| identificativoUnivoco   | 2       | s          |         |         |                 | Aggregazione                              |
| Beneficiario            |         |            |         |         |                 | che riporta le informazioni               |
|                         |         |            |         |         |                 | concernenti l’identificazione             |
|                         |         |            |         |         |                 | fiscale                                   |
|                         |         |            |         |         |                 | dell’ente beneficiario.                   |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| tipoIdentificativo      | 3       | an         |         | 1       | Proprietary     | Campo                                     |
| Univoco                 |         |            |         |         | Code            | alfanumerico che indica la natura         |
|                         |         |            |         |         |                 | dell’ente beneficiario; se presente       |
|                         |         |            |         |         |                 | deve assumere il valore **G**             |
|                         |         |            |         |         |                 | Identificativo fiscale Persona            |
|                         |         |            |         |         |                 | Giuridica.                                |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| codiceIdentificativo    | 3       | an         |         | 1..35   | Tax             | Campo                                     |
| Univoco                 |         |            |         |         | Identification  | alfanumerico contenente il codice         |
|                         |         |            |         |         | Number          | fiscale dell’Ente Creditore               |
|                         |         |            |         |         |                 | destinatario del pagamento.               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| denominazione           | 2       | an         |         | 1..70   | Name            | Contiene la denominazione                 |
| Beneficiario            |         |            |         |         |                 | dell’Ente Creditore                       |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| codiceUnitOper          | 2       | an         |         | 1..35   |                 | Indica il codice                          |
| Beneficiario            |         |            |         |         |                 | dell’unità operativa                      |
|                         |         |            |         |         |                 | destinataria                              |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| denomUnitOper           | 2       | an         |         | 1..70   |                 | Contiene la                               |
| Beneficiario            |         |            |         |         |                 | denominazione dell’unità                  |
|                         |         |            |         |         |                 | operativa destinataria.                   |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| indirizzo               | 2       | an         |         | 1..70   | Street Name     | Indica l’indirizzo dell’ente              |
| Beneficiario            |         |            |         |         |                 | beneficiario.                             |
|                         |         |            |         |         |                 | Può coincidere con quello                 |
|                         |         |            |         |         |                 | dell’unità                                |
|                         |         |            |         |         |                 | operativa destinataria                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| civicoBeneficiario      | 2       | an         |         | 1..16   | Building        | Indica il numero civico                   |
|                         |         |            |         |         | Number          | dell’ente beneficiario.                   |
|                         |         |            |         |         |                 | Può coincidere con quello                 |
|                         |         |            |         |         |                 | dell’unità                                |
|                         |         |            |         |         |                 | operativa destinataria.                   |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| capBeneficiario         | 2       | an         |         | 1..16   | Postal Code     | Indica il CAP dell’ente beneficiario.     |
|                         |         |            |         |         |                 | Può coincidere con quello dell’unità      |
|                         |         |            |         |         |                 | operativa destinataria                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| localita                | 2       | an         |         | 1..35   | Town Name       | Indica la località dell’ente              |
| Beneficiario            |         |            |         |         |                 | beneficiario.                             |
|                         |         |            |         |         |                 | Può coincidere con quello                 |
|                         |         |            |         |         |                 | dell’unità                                |
|                         |         |            |         |         |                 | operativa destinataria                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| provincia               | 2       | an         |         | 1..35   | Country         | Indica la provincia                       |
| Beneficiario            |         |            |         |         | SubDivision     | dell’ente beneficiario.                   |
|                         |         |            |         |         |                 | Può coincidere con quello                 |
|                         |         |            |         |         |                 | dell’unità                                |
|                         |         |            |         |         |                 | operativa destinataria                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| nazione                 | 2       | an         |         | 2       | Country         | Indica il                                 |
| Beneficiario            |         |            |         |         |                 | codice nazione dell’ente                  |
|                         |         |            |         |         |                 | beneficiario                              |
|                         |         |            |         |         |                 | secondo lo standard ISO 3166.             |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| datiVersamento          | 1       | s          |         |         |                 | Aggregazione                              |
|                         |         |            |         |         |                 | “dati del Versamento”                     |
|                         |         |            |         |         |                 | costituita dai seguenti elementi:         |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| dataEsecuzione          | 2       | an         |         | 10      | Requested       | Indica la data in cui si richiede che     |
| Pagamento               |         |            |         |         | Execution       | venga effettuato                          |
|                         |         |            |         |         | Date            | il pagamento secondo il formato           |
|                         |         |            |         |         |                 | ISO 8601 [YYYY]-[MM]-[DD].                |
|                         |         |            |         |         |                 | Non                                       |
|                         |         |            |         |         |                 | può essere anteriore alla data            |
|                         |         |            |         |         |                 | di invio della RPT e non può essere       |
|                         |         |            |         |         |                 | superiore di                              |
|                         |         |            |         |         |                 | 30 giorni                                 |
|                         |         |            |         |         |                 | rispetto alla stessa data.                |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| importoTotale           | 2       | an         |         | 3..12   | Amount          | Campo numerico (due cifre per la          |
| DaVersare               |         |            |         |         |                 | parte decimale,                           |
|                         |         |            |         |         |                 | il separatore dei centesimi è il          |
|                         |         |            |         |         |                 | punto “.”), indicante l’importo           |
|                         |         |            |         |         |                 | relativo alla somma da versare.           |
|                         |         |            |         |         |                 | Deve essere uguale alla somma             |
|                         |         |            |         |         |                 | delle varie                               |
|                         |         |            |         |         |                 | occorrenze (da 1 a 5) del dato            |
|                         |         |            |         |         |                 | importoSingoloVersamento                  |
|                         |         |            |         |         |                 | presente nella struttura                  |
|                         |         |            |         |         |                 | DatiSingoloVersamento.                    |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| tipoVersamento          | 2       | an         |         | 4       | Proprietary     | Forma tecnica di pagamento attraverso     |
|                         |         |            |         |         | Code            | il quale                                  |
|                         |         |            |         |         |                 | viene effettuata la provvista presso      |
|                         |         |            |         |         |                 | il PSP. Può assumere i seguenti           |
|                         |         |            |         |         |                 | valori:                                   |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | - **BBT**  Bonifico Bancario di Tesoreria |
|                         |         |            |         |         |                 | - **BP**   Bollettino Postale             |
|                         |         |            |         |         |                 | - **AD**   Addebito diretto               |
|                         |         |            |         |         |                 | - **CP**   Carta di pagamento             |
|                         |         |            |         |         |                 | - **PO**   Pagamento attivato presso PSP  |
|                         |         |            |         |         |                 | - **OBEP** On-line banking e-payment      |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| identificativo          | 2       | an         |         | 1..35   | Creditor        | Riferimento univoco                       |
| UnivocoVersamento       |         |            |         |         | Reference       | assegnato al                              |
|                         |         |            |         |         |                 | versamento dall’Ente                      |
|                         |         |            |         |         |                 | Creditore, utilizzato ai fini             |
|                         |         |            |         |         |                 | specifici                                 |
|                         |         |            |         |         |                 | della rendicontazione e                   |
|                         |         |            |         |         |                 | riconciliazione                           |
|                         |         |            |         |         |                 | eseguita                                  |
|                         |         |            |         |         |                 | sui conti di tesoreria.,Si faccia         |
|                         |         |            |         |         |                 | riferimento al capitolo                   |
|                         |         |            |         |         |                 | 7.1 della presente Sezione.               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| CodiceContesto          | 2       | an         |         | 1..35   | Message         | Codice univoco necessario a               |
| Pagamento               |         |            |         |         | Identification  | definire il                               |
|                         |         |            |         |         |                 | contesto                                  |
|                         |         |            |         |         |                 | nel quale viene effettuato                |
|                         |         |            |         |         |                 | il versamento.                            |
|                         |         |            |         |         |                 | Si faccia riferimento al § 7.3            |
|                         |         |            |         |         |                 | della                                     |
|                         |         |            |         |         |                 | presente Sezione.                         |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| ibanAddebito            | 2       | an         |         | 1..35   | Debtor.         | Identifica l’International                |
|                         |         |            |         |         | Account         | Bank Account                              |
|                         |         |            |         |         | IBAN            | Number del conto da                       |
|                         |         |            |         |         |                 | addebitare definito secondo lo            |
|                         |         |            |         |         |                 | standard ISO 13616.                       |
|                         |         |            |         |         |                 | **Il dato è obbligatorio qualora,         |
|                         |         |            |         |         |                 | l’informazione                            |
|                         |         |            |         |         |                 | tipoPagamento assuma                      |
|                         |         |            |         |         |                 | il valore “AD”**                          |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| bicAddebito             | 2       | an         |         | 8 / 11  | Debtor Agent    | Bank                                      |
|                         |         |            |         |         | BIC             | Identifier Code della banca               |
|                         |         |            |         |         |                 | di addebito,                              |
|                         |         |            |         |         |                 | definito secondo                          |
|                         |         |            |         |         |                 | lo standard ISO 9362.                     |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| firmaRicevuta           | 2       | an         |         | 1..1    | Proprietary     | Codice del tipo di firma                  |
|                         |         |            |         |         | Code            | digitale o elettronica qualificata        |
|                         |         |            |         |         |                 | cui deve essere                           |
|                         |         |            |         |         |                 | sottoposto il messaggio                   |
|                         |         |            |         |         |                 | di Ricevuta,                              |
|                         |         |            |         |         |                 | Telematica, secondo le                    |
|                         |         |            |         |         |                 | tipologie di firma                        |
|                         |         |            |         |         |                 | previste dalle Regole Tecniche            |
|                         |         |            |         |         |                 | sulla firma                               |
|                         |         |            |         |         |                 | digitale.                                 |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | - **0** = Firma non richiesta             |
|                         |         |            |         |         |                 | - **1** = CaDes                           |
|                         |         |            |         |         |                 | - **3** = XaDes                           |
|                         |         |            |         |         |                 | Lapossibilità per l'Ente Creditore        |
|                         |         |            |         |         |                 | di richiedere                             |
|                         |         |            |         |         |                 | la firma della RT è deprecata.            |
|                         |         |            |         |         |                 | Il dato viene mantenuto per retro         |
|                         |         |            |         |         |                 | compatibilità.                            |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| datiSingolo             | 2       | S          |         |         |                 | Aggregazione “dati dei singoli            |
| Versamento              |         |            |         |         |                 | versamenti” da un minimo di uno           |
|                         |         |            |         |         |                 | ad un massimo di 5 occorrenze             |
|                         |         |            |         |         |                 | di versamento,                            |
|                         |         |            |         |         |                 | facenti capo                              |
|                         |         |            |         |         |                 | ad un unico                               |
|                         |         |            |         |         |                 | identificativoUnivocoVersamento.          |
|                         |         |            |         |         |                 | Si                                        |
|                         |         |            |         |         |                 | precisa che nell’aggregazione             |
|                         |         |            |         |         |                 | datiSingoloPagamento                      |
|                         |         |            |         |         |                 | della RT relativa, le occorrenze          |
|                         |         |            |         |         |                 | di versamento devono                      |
|                         |         |            |         |         |                 | essere riportate nello                    |
|                         |         |            |         |         |                 | stesso ordine della RPT.                  |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| importoSingolo          | 3       | an         |         | 3..12   | Amount          | Campo numerico                            |
| Versamento              |         |            |         |         |                 | (due cifre per la parte decimale,         |
|                         |         |            |         |         |                 | il separatore dei centesimi               |
|                         |         |            |         |         |                 | è il punto “.”),                          |
|                         |         |            |         |         |                 | indicante l’importo                       |
|                         |         |            |         |         |                 | relativo alla somma                       |
|                         |         |            |         |         |                 | da versare relativa al                    |
|                         |         |            |         |         |                 | singolo versamento.                       |
|                         |         |            |         |         |                 | Deve essere diverso da                    |
|                         |         |            |         |         |                 | **“0.00”**.                               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| commissione             | 3       | an         |         | 3..12   | Charges Fees    | Campo numerico                            |
| CaricoPA                |         |            |         |         |                 | (due cifre per la                         |
|                         |         |            |         |         |                 | parte decimale,                           |
|                         |         |            |         |         |                 | il separatore dei                         |
|                         |         |            |         |         |                 | centesimi è il punto “.”),                |
|                         |         |            |         |         |                 | indicante                                 |
|                         |         |            |         |         |                 | l’importo della eventuale                 |
|                         |         |            |         |         |                 | commissione                               |
|                         |         |            |         |         |                 | spettante al PSP di cui                   |
|                         |         |            |         |         |                 |  si fa carico                             |
|                         |         |            |         |         |                 | l’Ente Creditore.                         |
|                         |         |            |         |         |                 | Il dato è riportato a                     |
|                         |         |            |         |         |                 | solo titolo                               |
|                         |         |            |         |         |                 | indicativo e non                          |
|                         |         |            |         |         |                 | comporta attività a carico                |
|                         |         |            |         |         |                 | del PSP che                               |
|                         |         |            |         |         |                 | non abbiano attive                        |
|                         |         |            |         |         |                 | convenzioni specifiche                    |
|                         |         |            |         |         |                 | con uno o più                             |
|                         |         |            |         |         |                 | Enti Creditori.                           |
|                         |         |            |         |         |                 | Se presente deve essere                   |
|                         |         |            |         |         |                 |  diverso da                               |
|                         |         |            |         |         |                 | **“0.00”**.                               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| ibanAccredito           | 3       | an         |         | 1..35   | Creditor        | Identifica l’International                |
|                         |         |            |         |         | Account         | Bank Account                              |
|                         |         |            |         |         | IBAN            | Number,                                   |
|                         |         |            |         |         |                 | definito secondo lo                       |
|                         |         |            |         |         |                 | standard ISO 13616,                       |
|                         |         |            |         |         |                 |  del conto corrente                       |
|                         |         |            |         |         |                 | bancario o                                |
|                         |         |            |         |         |                 | postale da                                |
|                         |         |            |         |         |                 | accreditare, indicato                     |
|                         |         |            |         |         |                 | dall’Ente Creditore.                      |
|                         |         |            |         |         |                 | Non deve                                  |
|                         |         |            |         |         |                 | essere presente                           |
|                         |         |            |         |         |                 | qualora sia stata                         |
|                         |         |            |         |         |                 | popolata la struttura                     |
|                         |         |            |         |         |                 | datiMarcaBolloDigitale.                   |
|                         |         |            |         |         |                 | In tutti gli alti casi è                  |
|                         |         |            |         |         |                 | obbligatorio.                             |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| bicAccredito            | 3       | an         |         | 8 / 11  | Creditor        | Bank                                      |
|                         |         |            |         |         | Agent           | Identifier Code definito                  |
|                         |         |            |         |         | BIC             | secondo                                   |
|                         |         |            |         |         |                 | lo standard                               |
|                         |         |            |         |         |                 | ISO 9362 presso la                        |
|                         |         |            |         |         |                 | quale deve                                |
|                         |         |            |         |         |                 | essere effettuato                         |
|                         |         |            |         |         |                 | l’accredito.                              |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| ibanAppoggio            | 3       | an         |         | 1..35   | Creditor        | Identifica l’International                |
|                         |         |            |         |         | Account         | Bank Account                              |
|                         |         |            |         |         | IBAN            | Number,definito secondo                   |
|                         |         |            |         |         |                 | lo standard                               |
|                         |         |            |         |         |                 | ISO 13616,                                |
|                         |         |            |         |         |                 | del conto da accreditare                  |
|                         |         |            |         |         |                 | presso un,                                |
|                         |         |            |         |         |                 | PSP che provvederà a                      |
|                         |         |            |         |         |                 | trasferire i                              |
|                         |         |            |         |         |                 | fondi incassati sul conto                 |
|                         |         |            |         |         |                 | indicato,                                 |
|                         |         |            |         |         |                 | nell’elemento                             |
|                         |         |            |         |         |                 | ibanAccredito.                            |
|                         |         |            |         |         |                 | Per indicazioni circa                     |
|                         |         |            |         |         |                 | l’utilizzo vedi il,                       |
|                         |         |            |         |         |                 | paragrafo 8.1.1.5.                        |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| bicAppoggio             | 3       | an         |         | 8 / 11  | Creditor        | Bank Identifier Code                      |
|                         |         |            |         |         | Agent           | definito secondo lo standard              |
|                         |         |            |         |         | BIC             | ISO 9362 dell’elemento                    |
|                         |         |            |         |         |                 | ibanAppoggio.                             |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| credenziali             | 3       | an         |         | 1..35   |                 | Eventuali                                 |
| Pagatore                |         |            |         |         |                 | credenziali richieste dal                 |
|                         |         |            |         |         |                 | Prestatore                                |
|                         |         |            |         |         |                 | di servizi di Pagamento                   |
|                         |         |            |         |         |                 | necessarie per                            |
|                         |         |            |         |         |                 | completare l’operazione                   |
|                         |         |            |         |         |                 | (ad esempio:                              |
|                         |         |            |         |         |                 | un codice bilaterale                      |
|                         |         |            |         |         |                 | utilizzabile una sola                     |
|                         |         |            |         |         |                 | volta).                                   |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| causale                 | 3       | an         |         | 1..140  | Unstructured    | Rappresenta                               |
| Versamento              |         |            |         |         | Remittance      | la descrizione estesa                     |
|                         |         |            |         |         | Information     | della causale                             |
|                         |         |            |         |         |                 | del versamento che                        |
|                         |         |            |         |         |                 | deve essere                               |
|                         |         |            |         |         |                 | conforme                                  |
|                         |         |            |         |         |                 | a quanto indicato                         |
|                         |         |            |         |         |                 | nella Sezione I                           |
|                         |         |            |         |         |                 | dell’Allegato A                           |
|                         |         |            |         |         |                 | alle Linee guida.                         |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| datiSpecifici           | 3       | an         |         | 1..140  | Additional      | Rappresenta l’indicazione                 |
| Riscossione             |         |            |         |         | Remittance      | dell’imputazione della specifica          |
|                         |         |            |         |         | Information     | entrata ed è così articolato:             |
|                         |         |            |         |         |                 | **tipo contabilità”/”codice contabilità** |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | Dove tipo contabilità                     |
|                         |         |            |         |         |                 | ha il seguente                            |
|                         |         |            |         |         |                 | significato:                              |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | - **0** Capitolo e articolo di            |
|                         |         |            |         |         |                 |         Entrata del Bilancio              |
|                         |         |            |         |         |                 |         dello Stato                       |
|                         |         |            |         |         |                 | - **1** Numero della contabilità speciale |
|                         |         |            |         |         |                 | - **2** Codice,SIOPE                      |
|                         |         |            |         |         |                 | - **9** Altro codice ad uso               |
|                         |         |            |         |         |                 |         dell’Ente Creditore               |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| datiMarca               | 3       | s          |         |         |                 | Aggregazione che contiene                 |
| BolloDigitale           |         |            |         |         |                 | le informazioni necessarie al             |
|                         |         |            |         |         |                 | PSP per generare la marca                 |
|                         |         |            |         |         |                 | da bollo digitale. La struttura           |
|                         |         |            |         |         |                 | è obbligatoria qualora                    |
|                         |         |            |         |         |                 | l’informazione ibanAccredito              |
|                         |         |            |         |         |                 | non sia presente.                         |
|                         |         |            |         |         |                 | In tutti gli altri casi non deve          |
|                         |         |            |         |         |                 | essere                                    |
|                         |         |            |         |         |                 | popolata.                                 |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| tipoBollo               | 4       | an         |         | 2       | Proprietary     | Contiene la tipologia di                  |
|                         |         |            |         |         | Code            | Bollo Digitale.                           |
|                         |         |            |         |         |                 | Può assumere i seguenti                   |
|                         |         |            |         |         |                 | valori:                                   |
|                         |         |            |         |         |                 |                                           |
|                         |         |            |         |         |                 | **01 Imposta di bollo**                   |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| hashDocumento           | 4       | an         |         | 70      |                 | Contiene l’impronta                       |
|                         |         |            |         |         |                 | informatica (digest)                      |
|                         |         |            |         |         |                 | del documento informatico                 |
|                         |         |            |         |         |                 | cui è                                     |
|                         |         |            |         |         |                 | associata la                              |
|                         |         |            |         |         |                 | marca da bollo                            |
|                         |         |            |         |         |                 | digitale.                                 |
|                         |         |            |         |         |                 | L’algoritmo di hash                       |
|                         |         |            |         |         |                 | da utilizzare è SHA-256.                  |
|                         |         |            |         |         |                 | La stringa di 256 bit (32                 |
|                         |         |            |         |         |                 | ottetti) risultato di tale                |
|                         |         |            |         |         |                 | algoritmo deve essere                     |
|                         |         |            |         |         |                 | convertito                                |
|                         |         |            |         |         |                 | in base64                                 |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+
| provinciaResidenza      | 4       | an         |         | 2       | Proprietary     | Sigla automobilistica                     |
|                         |         |            |         |         | Code            | della provincia di                        |
|                         |         |            |         |         |                 | residenza del soggetto                    |
|                         |         |            |         |         |                 | pagatore.                                 |
|                         |         |            |         |         |                 | Nel caso di soggetto                      |
|                         |         |            |         |         |                 | residente                                 |
|                         |         |            |         |         |                 | all’estero                                |
|                         |         |            |         |         |                 | indicare la provincia della               |
|                         |         |            |         |         |                 | sede legale dell’Ente                     |
|                         |         |            |         |         |                 | Creditore.                                |
+-------------------------+---------+------------+---------+---------+-----------------+-------------------------------------------+

Ricevuta Telematica (RT)
~~~~~~~~~~~~~~~~~~~~~~~~
.. _Ricevuta Telematica (RT):

È il documento informatico rilasciato a cura dell’organizzazione che
effettua l’operazione di pagamento di somme nei confronti di enti
pubblici su ordine dell'utilizzatore finale.

**Tabella** **2 - Elementi componenti la RT**

+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
|       **Dato**       | **Liv** | **Genere** | **Occ** | **Len** | **UNIFI**              | **Contenuto**                        |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| versioneOggetto      | 1       | an         | 1..1    | 1..16   | VersionNumber          | Riporta la stessa informazione       |
|                      |         |            |         |         |                        | presente nel dato                    |
|                      |         |            |         |         |                        | “versioneOggetto” della              |
|                      |         |            |         |         |                        | Richiesta di Pagamento               |
|                      |         |            |         |         |                        | Telematico (RPT)                     |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| Dominio              | 1       | s          | 1..1    |         | Initiating             | Riporta le stesse informazioni       |
|                      |         |            |         |         | Party                  | presenti nel blocco                  |
|                      |         |            |         |         |                        | “Dominio” della Richiesta            |
|                      |         |            |         |         |                        | di Pagamento Telematico (RPT)        |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| identificativo       | 1       | an         | 1..1    | 1..35   | Message                | Identificativo legato alla           |
| Messaggio            |         |            |         |         | Identification         | trasmissione della                   |
| Richiesta            |         |            |         |         |                        | ricevuta telematica.                 |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | Deve essere univoco                  |
|                      |         |            |         |         |                        | nell’ambito della stessa             |
|                      |         |            |         |         |                        | data riferita all’elemento           |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | *dataOraMessaggioRicevuta*           |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| dataOraMessaggio     | 1       | an         | 1..1    | 19      | Creation               | Indica la data e l’ora               |
| Ricevuta             |         |            |         |         | Date                   | del messaggio di ricevuta,           |
|                      |         |            |         |         | Time                   | secondo il formato                   |
|                      |         |            |         |         |                        | ISO 8601                             |
|                      |         |            |         |         |                        | [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]      |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| riferimento          | 1       | an         | 1..1    | 1.35    | Original Message       | Con riferimento al                   |
| Messaggio            |         |            |         |         | Identification         | messaggio di Ricevuta                |
| Richiesta            |         |            |         |         |                        | Telematica                           |
|                      |         |            |         |         |                        | **(RT)**                             |
|                      |         |            |         |         |                        |  l’elemento contiene il dato         |
|                      |         |            |         |         |                        | identificativoMessaggioRichiesta     |
|                      |         |            |         |         |                        |  legato alla trasmissione della      |
|                      |         |            |         |         |                        | Richiesta di Pagamento               |
|                      |         |            |         |         |                        | Telematico                           |
|                      |         |            |         |         |                        | **(RPT)**                            |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| riferimentoData      | 1       | an         | 1..1    | 10      | Original Creation      | Indica la data                       |
| Richiesta            |         |            |         |         | Date Time              | secondo il formato ISO 8601          |
|                      |         |            |         |         |                        | **[YYYY]-[MM]-[DD]**                 |
|                      |         |            |         |         |                        | cui si riferisce la                  |
|                      |         |            |         |         |                        | generazione del dato                 |
|                      |         |            |         |         |                        | riferimentoMessaggioRichiesta.       |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| istitutoAttestante   | 1       | s          | 1..1    |         | Debtor Agent           | Aggregazione                         |
|                      |         |            |         |         |                        | relativa al soggetto Prestatore      |
|                      |         |            |         |         |                        | dei servizi di Pagamento che         |
|                      |         |            |         |         |                        |  emette il documento di              |
|                      |         |            |         |         |                        | attestazione                         |
|                      |         |            |         |         |                        | dell’avvenuto pagamento.             |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| identificativo       | 2       | s          | 1..1    |         | Financial              | Aggregazione che riporta             |
| Univoco              |         |            |         |         | Institution            | le informazioni                      |
| Attestante           |         |            |         |         | Identification         | concernenti l’identificazione        |
|                      |         |            |         |         |                        | fiscale dell’Istituto attestante     |
|                      |         |            |         |         |                        | il pagamento.                        |
|                      |         |            |         |         |                        | Si precisa inoltre che la struttura  |
|                      |         |            |         |         |                        | deve coincidere                      |
|                      |         |            |         |         |                        | con quella dell’elemento             |
|                      |         |            |         |         |                        | identificativoUnivocoMittente        |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | indicato nella Tabella 1             |
|                      |         |            |         |         |                        | riportata nel                        |
|                      |         |            |         |         |                        | capitolo 7 dell’Allegato             |
|                      |         |            |         |         |                        | A alle Linee guida.                  |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| tipoIdentificativo   | 3       | an         | 1..1    | 1       | ProprietaryCode        | Campo alfanumerico che               |
| Univoco              |         |            |         |         |                        | descrive la codifica                 |
|                      |         |            |         |         |                        | utilizzata per individuare           |
|                      |         |            |         |         |                        | l’Istituto attestante il pagamento;  |
|                      |         |            |         |         |                        | se presente può assumere i           |
|                      |         |            |         |         |                        | seguenti valori:                     |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | - **‘G’** = persona giuridica        |
|                      |         |            |         |         |                        | - **‘A’** = Codice ABI               |
|                      |         |            |         |         |                        | - **‘B’** = Codice BIC               |
|                      |         |            |         |         |                        | (standard ISO 9362)                  |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | Si precisa che il valore del dato    |
|                      |         |            |         |         |                        | deve essere sempre lo stesso         |
|                      |         |            |         |         |                        | per tutte le RT generate dal PSP.    |
|                      |         |            |         |         |                        | A tale scopo si evidenzia            |
|                      |         |            |         |         |                        | che il PSP è quello indicato         |
|                      |         |            |         |         |                        | nel dato identificativoPSP           |
|                      |         |            |         |         |                        |  del Catalogo Dati Informativi       |
|                      |         |            |         |         |                        | (vedi Tabella 9).                    |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| codiceIdentificativo | 3       | an         | 1..1    | 1..35   | BIC / Proprietary /    | Campo                                |
| Univoco              |         |            |         |         | Tax Identification     | alfanumerico che può contenere       |
|                      |         |            |         |         | Number                 | il codice fiscale o la partita IVA,  |
|                      |         |            |         |         |                        | o il codice ABI o il codice BIC      |
|                      |         |            |         |         |                        | del prestatore di servizi di         |
|                      |         |            |         |         |                        | pagamento attestante.                |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| denominazione        | 2       | an         | 1..1    | 1..70   | Name                   | Contiene la denominazione            |
| Attestante           |         |            |         |         |                        | del prestatore di                    |
|                      |         |            |         |         |                        | servizi di pagamento                 |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| codiceUnitOper       | 2       | an         | 0..1    | 1..35   |                        | Indica il codice dell’unità          |
| Attestante           |         |            |         |         |                        | operativa che rilascia               |
|                      |         |            |         |         |                        | la ricevuta.                         |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| denomUnitOper        | 2       | an         | 0..1    | 1..70   |                        | Indica la denominazione              |
| Attestante           |         |            |         |         |                        | dell’unità operativa attestante.     |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| indirizzoAttestante  | 2       | an         | 0..1    | 1..70   | StreetName             | Indica l’indirizzo                   |
|                      |         |            |         |         |                        | dell’attestante.                     |
|                      |         |            |         |         |                        | Può coincidere con quello            |
|                      |         |            |         |         |                        | dell’unità operativa                 |
|                      |         |            |         |         |                        | che rilascia la ricevuta.            |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| civicoAttestante     | 2       | an         | 0..1    | 1..16   | Building               | Indica il numero civico              |
|                      |         |            |         |         | Number                 | dell’attestante.                     |
|                      |         |            |         |         |                        | Può coincidere con quello            |
|                      |         |            |         |         |                        | dell’unità operativa                 |
|                      |         |            |         |         |                        | che rilascia la ricevuta             |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| capAttestante        | 2       | an         | 0..1    | 1..16   | Postal Code            | Indica il CAP dell’attestante.       |
|                      |         |            |         |         |                        | Può coincidere con quello            |
|                      |         |            |         |         |                        | dell’unità operativa                 |
|                      |         |            |         |         |                        | che rilascia la ricevuta.            |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| localitaAttestante   | 2       | an         | 0..1    | 1..35   | Town Name              | Indica la località                   |
|                      |         |            |         |         |                        | dell’attestante.                     |
|                      |         |            |         |         |                        | Può coincidere con quello            |
|                      |         |            |         |         |                        | dell’unità operativa                 |
|                      |         |            |         |         |                        | che rilascia la ricevuta.            |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| provinciaAttestante  | 2       | an         | 0..1    | 1..35   | Country                | Indica la provincia                  |
|                      |         |            |         |         | SubDivision            | dell’attestante.                     |
|                      |         |            |         |         |                        | Può coincidere con quello            |
|                      |         |            |         |         |                        | dell’unità operativa                 |
|                      |         |            |         |         |                        | che rilascia la ricevuta.            |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| nazioneAttestante    | 2       | an         | 0..1    | 2       | Country                | Indica il codice nazione             |
|                      |         |            |         |         |                        | dell’attestante                      |
|                      |         |            |         |         |                        | secondo lo standard ISO 3166.        |
|                      |         |            |         |         |                        | Può coincidere con quello            |
|                      |         |            |         |         |                        | dell’unità operativa                 |
|                      |         |            |         |         |                        | che rilascia la ricevuta.            |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| enteBeneficiario     | 1       | s          | 1..1    |         | Creditor               | Riporta                              |
|                      |         |            |         |         |                        | le stesse informazioni               |
|                      |         |            |         |         |                        | presenti nel blocco “                |
|                      |         |            |         |         |                        | enteBeneficiario                     |
|                      |         |            |         |         |                        | ” della Richiesta di                 |
|                      |         |            |         |         |                        | Pagamento Telematico                 |
|                      |         |            |         |         |                        | **(RPT)** cui si riferisce           |
|                      |         |            |         |         |                        | il messaggio di                      |
|                      |         |            |         |         |                        | Ricevuta Telematica.                 |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| soggettoVersante     | 1       | s          | 0..1    |         | Debtor                 | Riporta                              |
|                      |         |            |         |         |                        | le stesse informazioni               |
|                      |         |            |         |         |                        | presenti nel blocco “                |
|                      |         |            |         |         |                        | soggettoVersante                     |
|                      |         |            |         |         |                        | ” della Richiesta di                 |
|                      |         |            |         |         |                        | Pagamento Telematico                 |
|                      |         |            |         |         |                        | **(RPT)** cui si riferisce           |
|                      |         |            |         |         |                        | il messaggio di                      |
|                      |         |            |         |         |                        | Ricevuta Telematica.                 |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| soggettoPagatore     | 1       | s          | 1..1    |         | Ultimate Debtor        | Riporta                              |
|                      |         |            |         |         | /                      | le stesse informazioni               |
|                      |         |            |         |         | Debtor [3]_            | presenti nel blocco “                |
|                      |         |            |         |         |                        | soggettoPagatore                     |
|                      |         |            |         |         |                        | ” della Richiesta di                 |
|                      |         |            |         |         |                        | Pagamento Telematico                 |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | (RPT) cui si riferisce il            |
|                      |         |            |         |         |                        | messaggio di Ricevuta                |
|                      |         |            |         |         |                        | Telematica.                          |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| datiPagamento        | 1       | s          | 1..1    |         |                        | Aggregazione                         |
|                      |         |            |         |         |                        | “dati del versamento” costituita     |
|                      |         |            |         |         |                        | dai seguenti elementi:               |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| codiceEsito          | 2       | n          | 1..1    | 1       | Proprietary Code       | Campo numerico indicante             |
| Pagamento            |         |            |         |         |                        | l’esito del pagamento.               |
|                      |         |            |         |         |                        | Può assumere i                       |
|                      |         |            |         |         |                        | seguenti valori:                     |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **0** Pagamento eseguito             |
|                      |         |            |         |         |                        | **1** Pagamento non eseguito         |
|                      |         |            |         |         |                        | **2** Pagamento parzialmente         |
|                      |         |            |         |         |                        |            eseguito                  |
|                      |         |            |         |         |                        | **3** Decorrenza termini             |
|                      |         |            |         |         |                        | **4** Decorrenza termini parziale    |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| importoTotale        | 2       | an         | 1..1    | 3..12   | Amount                 | Campo numerico                       |
| Pagato               |         |            |         |         |                        | (due cifre per la parte decimale,    |
|                      |         |            |         |         |                        | il separatore dei centesimi è il     |
|                      |         |            |         |         |                        | punto “.”),                          |
|                      |         |            |         |         |                        | indicante l’importo relativo al      |
|                      |         |            |         |         |                        | totale delle somme versate.          |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | Deve essere uguale alla somma        |
|                      |         |            |         |         |                        | delle varie occorrenze               |
|                      |         |            |         |         |                        | (da 1 a 5) dell’informazione         |
|                      |         |            |         |         |                        | *singoloImportoVersato*              |
|                      |         |            |         |         |                        |  presente nella struttura            |
|                      |         |            |         |         |                        | *DatiSingoloVersamento*              |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | Se il pagamento non è stato          |
|                      |         |            |         |         |                        | eseguito                             |
|                      |         |            |         |         |                        | (codiceEsitoPagamento=1)             |
|                      |         |            |         |         |                        | l’importo deve essere                |
|                      |         |            |         |         |                        | impostato a 0.00.                    |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **Se la RT viene generata**          |
|                      |         |            |         |         |                        | **per decorrenza termini**           |
|                      |         |            |         |         |                        | **(codiceEsitoPagamento=3)**         |
|                      |         |            |         |         |                        | **l’importo del pagamento**          |
|                      |         |            |         |         |                        | **deve essere**                      |
|                      |         |            |         |         |                        | **impostato a 0.00 anche se**        |
|                      |         |            |         |         |                        | ** non se ne conosce**               |
|                      |         |            |         |         |                        | **l’ammontare effettivo, **          |
|                      |         |            |         |         |                        | **in quanto non è disponibile**      |
|                      |         |            |         |         |                        | **dal PSP l’esito del**              |
|                      |         |            |         |         |                        | **pagamento.**                       |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| identificativo       | 2       | an         | 1..1    | 1..35   | Creditor Reference     | Il dato                              |
| Univoco              |         |            |         |         |                        | deve essere riportato invariato,     |
| Versamento           |         |            |         |         |                        | a cura del Prestatore di servizi     |
|                      |         |            |         |         |                        | di pagamento, così come presente     |
|                      |         |            |         |         |                        | nella Richiesta di Pagamento         |
|                      |         |            |         |         |                        | Telematico **(RPT)**                 |
|                      |         |            |         |         |                        | cui si riferisce il messaggio di     |
|                      |         |            |         |         |                        | Ricevuta Telematica.                 |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| CodiceContesto       | 2       | an         | 1..1    | 1..35   | Message                | Il dato                              |
| Pagamento            |         |            |         |         | Identification         | deve essere riportato invariato,     |
|                      |         |            |         |         |                        | a cura del Prestatore di servizi     |
|                      |         |            |         |         |                        | di pagamento, così come              |
|                      |         |            |         |         |                        | presente nella Richiesta di          |
|                      |         |            |         |         |                        | Pagamento Telematico                 |
|                      |         |            |         |         |                        | **(RPT)** cui si riferisce           |
|                      |         |            |         |         |                        | il messaggio di                      |
|                      |         |            |         |         |                        | Ricevuta Telematica.                 |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| datiSingolo          | 2       | s          | 0..5    |         |                        | Aggregazione                         |
| Pagamento            |         |            |         |         |                        | “dati dei singoli pagamenti”,        |
|                      |         |            |         |         |                        | sino ad un massimo di 5              |
|                      |         |            |         |         |                        | occorrenze di                        |
|                      |         |            |         |         |                        | versamento, facenti capo ad          |
|                      |         |            |         |         |                        | un unico                             |
|                      |         |            |         |         |                        | *identificativoUnivocoVersamento*    |
|                      |         |            |         |         |                        | **Le occorrenze di versamento**      |
|                      |         |            |         |         |                        | **devono essere riportate nello**    |
|                      |         |            |         |         |                        | **stesso ordine**                    |
|                      |         |            |         |         |                        | **del relativo messaggio RPT.**      |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **Obbligatorio nel caso in cui**     |
|                      |         |            |         |         |                        | **l’elemento**                       |
|                      |         |            |         |         |                        | **codiceEsitoPagamento**             |
|                      |         |            |         |         |                        |  **assuma il valore 0, 2 o 4**       |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| singoloImportoPagato | 3       | an         | 1..1    | 3..12   | Amount                 | Campo numerico                       |
|                      |         |            |         |         |                        | (due cifre per la parte              |
|                      |         |            |         |         |                        | decimale, il separatore dei          |
|                      |         |            |         |         |                        | centesimi è il punto “.”),           |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | indicante l’importo                  |
|                      |         |            |         |         |                        | relativo alla somma pagata.          |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **Se il singolo pagamento**          |
|                      |         |            |         |         |                        | **non è stato effettuato**           |
|                      |         |            |         |         |                        | **l’importo deve essere**            |
|                      |         |            |         |         |                        | **impostato a 0.00.**                |
|                      |         |            |         |         |                        | **Se la RT viene generata**          |
|                      |         |            |         |         |                        | **per decorrenza termini**           |
|                      |         |            |         |         |                        | **l’importo del pagamento**          |
|                      |         |            |         |         |                        | **è impostato a 0.00**               |
|                      |         |            |         |         |                        | **anche se non se ne conosce**       |
|                      |         |            |         |         |                        | **l’ammontare effettivo, in**        |
|                      |         |            |         |         |                        | **quantonon è disponibile**          |
|                      |         |            |         |         |                        | **dal PSP l’esito del**              |
|                      |         |            |         |         |                        | **pagamento.**                       |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| esitoSingolo         | 3       | an         | 0..1    | 1..35   | Status Reason          | Contiene la descrizione in           |
| Pagamento            |         |            |         |         | Proprietary            | formato testo                        |
|                      |         |            |         |         |                        | dell’esito del singolo               |
|                      |         |            |         |         |                        | pagamento.                           |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **Obbligatorio nel caso che**        |
|                      |         |            |         |         |                        | **l’elemento**                       |
|                      |         |            |         |         |                        | **singoloImportoPagato**             |
|                      |         |            |         |         |                        | **sia 0.00**                         |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| dataEsitoSingolo     | 3       | an         | 1..1    | 10      | Acceptance Date        | Indica la                            |
| Pagamento            |         |            |         |         |                        | data di esecuzione, di rifiuto o     |
|                      |         |            |         |         |                        | di revoca del pagamento,             |
|                      |         |            |         |         |                        |  nel formato                         |
|                      |         |            |         |         |                        | ISO 8601                             |
|                      |         |            |         |         |                        | [YYYY]-[MM]-[DD].                    |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| identificativo       | 3       | an         | 1..1    | 1..35   | Transaction Reference  | Riferimento univoco                  |
| Univoco              |         |            |         |         | Number                 | dell’operazione                      |
| Riscossione          |         |            |         |         |                        | assegnato al pagamento               |
|                      |         |            |         |         |                        | dal Prestatore                       |
|                      |         |            |         |         |                        | dei servizi di Pagamento.            |
|                      |         |            |         |         |                        | Può essere rappresentato dal         |
|                      |         |            |         |         |                        | CRO / TRN nel caso                   |
|                      |         |            |         |         |                        | di Bonifico Bancario,                |
|                      |         |            |         |         |                        | dal CODELINE                         |
|                      |         |            |         |         |                        | nel caso di bollettino postale,      |
|                      |         |            |         |         |                        | ovvero da qualsiasi altro            |
|                      |         |            |         |         |                        | riferimento univoco attribuito       |
|                      |         |            |         |         |                        | al pagamento dal PSP.                |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | Il riferimento può essere lo         |
|                      |         |            |         |         |                        | stesso per tutte                     |
|                      |         |            |         |         |                        | le occorrenze di                     |
|                      |         |            |         |         |                        | datiSingoloPagamento                 |
|                      |         |            |         |         |                        |  facenti capo ad un unico            |
|                      |         |            |         |         |                        | *identificativoUnivocoVersamento*    |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **Deve coincidere con lo stesso**    |
|                      |         |            |         |         |                        | **dato presente nel**                |
|                      |         |            |         |         |                        | **flusso di rendicontazione          |
|                      |         |            |         |         |                        | **(vedi Capitolo 7**                 |
|                      |         |            |         |         |                        | **delle SACI)**                      |
|                      |         |            |         |         |                        | **Se il singolo pagamento non**      |
|                      |         |            |         |         |                        | **è stato effettuato il dato**       |
|                      |         |            |         |         |                        | **deve essere impostato a “n/a”.**   |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| causaleVersamento    | 3       | an         | 1..1    | 1..140  | Unstructured           | Il dato deve essere riportato        |
|                      |         |            |         |         | Remittance             | invariato, a cura del Prestatore     |
|                      |         |            |         |         | Information            | di servizi di                        |
|                      |         |            |         |         |                        | pagamento, così come presente        |
|                      |         |            |         |         |                        | nella                                |
|                      |         |            |         |         |                        | Richiesta di Pagamento               |
|                      |         |            |         |         |                        | Telematico                           |
|                      |         |            |         |         |                        | **(RPT)** cui si riferisceil         |
|                      |         |            |         |         |                        | messaggio                            |
|                      |         |            |         |         |                        | di Ricevuta Telematica.              |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| datiSpecifici        | 3       | an         | 1..1    | 1..140  | Additional             | Il dato                              |
| Riscossione          |         |            |         |         | Remittance             | deve essere riportato invariato,     |
|                      |         |            |         |         | Information            | a cura del Prestatore di servizi     |
|                      |         |            |         |         |                        | di pagamento,                        |
|                      |         |            |         |         |                        | così come presente nella             |
|                      |         |            |         |         |                        | Richiesta di Pagamento               |
|                      |         |            |         |         |                        | Telematico                           |
|                      |         |            |         |         |                        | **(RPT)**                            |
|                      |         |            |         |         |                        | cui si  riferisce il messaggio di    |
|                      |         |            |         |         |                        | Ricevuta Telematica.                 |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| commissioni          | 3       | an         | 0..1    | 3..12   | Charges Fees           | Campo numerico                       |
| ApplicatePSP         |         |            |         |         |                        | (due cifre per la parte              |
|                      |         |            |         |         |                        | decimale,                            |
|                      |         |            |         |         |                        | il separatore dei centesimi          |
|                      |         |            |         |         |                        | è il punto “.”), indicante           |
|                      |         |            |         |         |                        | l’importo della commissione          |
|                      |         |            |         |         |                        | applicata                            |
|                      |         |            |         |         |                        | dal PSP al proprio cliente           |
|                      |         |            |         |         |                        | (soggetto versante o                 |
|                      |         |            |         |         |                        | soggetto pagatore).                  |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | Il dato diviene obbligatorio         |
|                      |         |            |         |         |                        | qualora l'informazione si            |
|                      |         |            |         |         |                        | riferisca ad una transazione         |
|                      |         |            |         |         |                        | facente                              |
|                      |         |            |         |         |                        | riferimento ad una specifica         |
|                      |         |            |         |         |                        | convenzione in essere                |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | tra il PSP e un Ente                 |
|                      |         |            |         |         |                        | Creditor: in questo caso             |
|                      |         |            |         |         |                        | rappresenta la commissione           |
|                      |         |            |         |         |                        | che il PSP avrebbe                   |
|                      |         |            |         |         |                        | applicato in assenza di tale         |
|                      |         |            |         |         |                        | convenzione.                         |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| allegatoRicevuta     | 3       | s          | 0..1    |         |                        | Aggregazione                         |
|                      |         |            |         |         |                        | contenente l'allegato al             |
|                      |         |            |         |         |                        | singolo pagamento.                   |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| tipoAllegato         | 4       | an         | 1..1    | 2       | Proprietary Code       | dentifica il tipo di allegato:       |
| Ricevuta             |         |            |         |         |                        | trasportato                          |
|                      |         |            |         |         |                        | con la RT e può assumere i           |
|                      |         |            |         |         |                        | seguenti valori:                     |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **ES** esito originario              |
|                      |         |            |         |         |                        | pagamento                            |
|                      |         |            |         |         |                        | (come ricevuto da PSP)               |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | **BD** Marca da bollo digitale       |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+
| testoAllegato        | 4       | an         | 1..1    |         |                        | Contiene l’allegato vero             |
|                      |         |            |         |         |                        | e proprio, il cui significato        |
|                      |         |            |         |         |                        | è indicato dal dato                  |
|                      |         |            |         |         |                        | tipoAllegatoRicevuta                 |
|                      |         |            |         |         |                        |                                      |
|                      |         |            |         |         |                        | L’elemento                           |
|                      |         |            |         |         |                        | testoAllegato                        |
|                      |         |            |         |         |                        |  è trasportato nella                 |
|                      |         |            |         |         |                        | ricevuta telematica secondo la       |
|                      |         |            |         |         |                        | codifica in “base64 binary”.         |
+----------------------+---------+------------+---------+---------+------------------------+--------------------------------------+

Richiesta di Revoca (RR)
~~~~~~~~~~~~~~~~~~~~~~~~
.. _Richiesta di Revoca (RR):

È il documento informatico inviato dal prestatore di servizi di
pagamento all’Ente Creditore per richiedere la revoca di un pagamento
effettuato, ovvero inviato dall’Ente Creditore al prestatore di servizi
di pagamento per richiedere lo “storno” di un pagamento.

**Tabella** **3 - Elementi componenti la RR**

+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
|      **Dato**      | **Liv** | **Genere** | **Occ** | **Len** | **UNIFI**        | **Contenuto**                           |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| versioneOggetto    | 1       | an         | 1..1    | 1..16   | VersionNumber    | Riporta                                 |
|                    |         |            |         |         |                  | la stessa informazione presente         |
|                    |         |            |         |         |                  | nel dato “versioneOggetto               |
|                    |         |            |         |         |                  | ” della Ricevuta Telematica             |
|                    |         |            |         |         |                  | **(RT).**                               |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| Dominio            | 1       | s          | 1..1    |         | Initiating       | Riporta le stesse informazioni          |
|                    |         |            |         |         | Party            | presenti nel blocco                     |
|                    |         |            |         |         |                  | “Dominio” della Ricevuta                |
|                    |         |            |         |         |                  | di Pagamento Telematico                 |
|                    |         |            |         |         |                  | **(RT)**                                |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| identificativo     | 1       | an         | 1..1    | 1..35   | Message          | Identificativo legato alla              |
| Messaggio          |         |            |         |         | Identification   | trasmissione della                      |
| Revoca             |         |            |         |         |                  | Richiesta di Revoca.                    |
|                    |         |            |         |         |                  | Deve essere univoco                     |
|                    |         |            |         |         |                  | nell’ambito della stessa                |
|                    |         |            |         |         |                  | data riferita all’elemento              |
|                    |         |            |         |         |                  | *dataMessaggioRevoca*                   |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| dataOraMessaggio   | 1       | an         | 1..1    | 19      | Creation         | Indica la data e l’ora                  |
| Revoca             |         |            |         |         | Date             | del messaggio di Revoca,                |
|                    |         |            |         |         | Time             | secondo il formato                      |
|                    |         |            |         |         |                  | ISO 8601                                |
|                    |         |            |         |         |                  | [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]         |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| istitutoAttestante | 1       | s          | 1..1    |         | Debtor Agent     | Aggregazione relativa al PSP            |
|                    |         |            |         |         |                  | che ha emesso la                        |
|                    |         |            |         |         |                  | RT oggetto di revoca.                   |
|                    |         |            |         |         |                  |                                         |
|                    |         |            |         |         |                  | Riporta le stesse informazioni          |
|                    |         |            |         |         |                  | presenti nel blocco                     |
|                    |         |            |         |         |                  | “soggettoAttestante” della              |
|                    |         |            |         |         |                  |  Ricevuta Telematica                    |
|                    |         |            |         |         |                  | **(RT)** cui si riferisce il            |
|                    |         |            |         |         |                  | messaggio di Richiesta di Revoca.       |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| soggettoVersante   | 1       | s          | 0..1    |         | Debtor           | Riporta                                 |
|                    |         |            |         |         |                  | le stesse informazioni                  |
|                    |         |            |         |         |                  | presenti nel blocco                     |
|                    |         |            |         |         |                  | “soggettoVersante” della                |
|                    |         |            |         |         |                  | Ricevuta di Telematica                  |
|                    |         |            |         |         |                  | **(RT)** cui si riferisce               |
|                    |         |            |         |         |                  | il messaggio di                         |
|                    |         |            |         |         |                  | Richiesta di Revoca.                    |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| soggettoPagatore   | 1       | s          | 1..1    |         | Ultimate Debtor  | Riporta                                 |
|                    |         |            |         |         | /                | le stesse informazioni                  |
|                    |         |            |         |         | Debtor [3]_      | presenti nel blocco                     |
|                    |         |            |         |         |                  | “soggettoPagatore”                      |
|                    |         |            |         |         |                  | della Ricevuta Telematica               |
|                    |         |            |         |         |                  | **(RT)** cui si riferisce il            |
|                    |         |            |         |         |                  | messaggio di Richiesta                  |
|                    |         |            |         |         |                  | di Revoca.                              |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| datiRevoca         | 1       | s          | 1..1    |         |                  | Aggregazione                            |
|                    |         |            |         |         |                  | “dati della richiesta di revoca”        |
|                    |         |            |         |         |                  | costituita dai seguenti elementi:       |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| importoTotale      | 2       | an         | 1..1    | 3..12   | Amount           | Campo numerico                          |
| Revocato           |         |            |         |         |                  | (due cifre per la parte decimale,       |
|                    |         |            |         |         |                  | il separatore dei centesimi è il        |
|                    |         |            |         |         |                  | punto “.”),                             |
|                    |         |            |         |         |                  | indicante l’importo relativo al         |
|                    |         |            |         |         |                  | totale delle somme versate.             |
|                    |         |            |         |         |                  |                                         |
|                    |         |            |         |         |                  | Deve essere uguale alla somma           |
|                    |         |            |         |         |                  | delle varie occorrenze                  |
|                    |         |            |         |         |                  | (da 1 a 5) dell’informazione            |
|                    |         |            |         |         |                  | *singoloImportoRevocato*                |
|                    |         |            |         |         |                  |  presente nella struttura               |
|                    |         |            |         |         |                  | *DatiSingolaRevoca.*                    |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| identificativo     | 2       | an         | 1..1    | 1..35   | Creditor         | l dato deve essere riportato            |
| Univoco            |         |            |         |         | Reference        | invariato così come presente            |
| Versamento         |         |            |         |         |                  | nella Ricevuta Telematica               |
|                    |         |            |         |         |                  | **(RT)** cui si riferisce il messaggio  |
|                    |         |            |         |         |                  | di Richiesta di Revoca.                 |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| CodiceContesto     | 2       | an         | 1..1    | 1..35   | Message          | Il dato                                 |
| Pagamento          |         |            |         |         | Identification   | deve essere riportato invariato così    |
|                    |         |            |         |         |                  | come presente nella Ricevuta            |
|                    |         |            |         |         |                  | Telematica **(RT)** cui si riferisce    |
|                    |         |            |         |         |                  | il messaggio di                         |
|                    |         |            |         |         |                  | Richiesta di Revoca..                   |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| tipoRevoca         | 2       | n          | 0..1    |         | Proprietary Code | Contiene il tipo di richiesta che       |
|                    |         |            |         |         |                  | viene utilizzata nel processo di        |
|                    |         |            |         |         |                  | revoca della RT                         |
|                    |         |            |         |         |                  | (vedi § 2.3).                           |
|                    |         |            |         |         |                  | Il dato è **obbligatorio** in caso      |
|                    |         |            |         |         |                  | di utilizzo della Richiesta Revoca da   |
|                    |         |            |         |         |                  | parte del PSP nel processo di           |
|                    |         |            |         |         |                  | Revoca della RT e può assumere          |
|                    |         |            |         |         |                  | i seguenti valori:                      |
|                    |         |            |         |         |                  |                                         |
|                    |         |            |         |         |                  |                                         |
|                    |         |            |         |         |                  |                                         |
|                    |         |            |         |         |                  | **0** tipo non codificato               |
|                    |         |            |         |         |                  | **1** annullo tecnico                   |
|                    |         |            |         |         |                  | **2** procedura di charge back          |
|                    |         |            |         |         |                  |                                         |
|                    |         |            |         |         |                  |                                         |
|                    |         |            |         |         |                  | Il dato **non deve essere presente**    |
|                    |         |            |         |         |                  | in caso di utilizzo della               |
|                    |         |            |         |         |                  | Richiesta Revoca da                     |
|                    |         |            |         |         |                  | parte dell'Ente Creditore nel processo  |
|                    |         |            |         |         |                  | di Storno del pagamento                 |
|                    |         |            |         |         |                  | (vedi § 2.1.4).                         |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| datiSingolaRevoca  | 2       | s          | 1..1    |         |                  | Aggregazione                            |
|                    |         |            |         |         |                  | “dati dei singoli pagamenti revocati”,  |
|                    |         |            |         |         |                  | da un minimo di uno ad un massimo       |
|                    |         |            |         |         |                  | di 5 occorrenze di revoca,              |
|                    |         |            |         |         |                  | facenti capo ad un unico                |
|                    |         |            |         |         |                  | *identificativoUnivocoVersamento*       |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| singoloImporto     | 3       | an         | 1..1    | 3..12   | Amount           | Campo numerico                          |
| Revocato           |         |            |         |         |                  | (due cifre per la parte decimale,       |
|                    |         |            |         |         |                  | il separatore dei centesimi è il        |
|                    |         |            |         |         |                  | punto “.”), indicante l’importo         |
|                    |         |            |         |         |                  | relativo alla somma revocata.           |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| identificativo     | 3       | an         | 1..1    | 1..35   | Transaction      | Riferimento                             |
| Univoco            |         |            |         |         | Reference        | univoco dell’operazione assegnato       |
| Riscossione        |         |            |         |         | Number           | al pagamento dal Prestatore             |
|                    |         |            |         |         |                  | dei servizi di Pagamento.               |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| causaleRevoca      | 3       | an         | 1..1    | 1..140  | Unstructured     | Rappresenta                             |
|                    |         |            |         |         | Remittance       | la descrizione del motivo della         |
|                    |         |            |         |         | Information      | richiesta di revoca.                    |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+
| datiAggiuntivi     | 3       | an         | 1..1    | 1..140  | Additional       | Informazioni                            |
| Revoca             |         |            |         |         | Remittance       | aggiuntive circa la descrizione         |
|                    |         |            |         |         | Information      | del motivo della richiesta di revoca.   |
|                    |         |            |         |         |                  |                                         |
+--------------------+---------+------------+---------+---------+------------------+-----------------------------------------+

Esito della Revoca (ER)
~~~~~~~~~~~~~~~~~~~~~~~
.. _Esito della Revoca (ER):

È il documento informatico inviato dall’Ente Creditore al prestatore di
servizi di pagamento per indicare l’esito di una richiesta di revoca di
un pagamento, ovvero inviato dal prestatore di servizi di pagamento
all’Ente Creditore per indicare l’esito di una richiesta di revoca
relativa allo “storno” di un pagamento.

**Tabella** **4 - Elementi componenti la ER**

+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
|         **Dato**        | **Liv** | **Genere** | **Occ** | **Len** | **UNIFI**          | **Contenuto**                             |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| versioneOggetto         | 1       | an         | 1..1    | 1..16   | Version            | Riporta la stessa informazione            |
|                         |         |            |         |         | Number             | presente nel dato “versioneOggetto”       |
|                         |         |            |         |         |                    | della Richiesta di Revoca                 |
|                         |         |            |         |         |                    | **(RR).**                                 |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| Dominio                 | 1       | s          | 1..1    |         | Initiating         | Riporta le stesse informazioni            |
|                         |         |            |         |         | Party              | presenti nel blocco “Dominio”             |
|                         |         |            |         |         |                    | della Richiesta di Revoca                 |
|                         |         |            |         |         |                    | **(RR).**                                 |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| identificativo          | 1       | an         | 1..1    | 1..35   | Message            | Identificativo legato alla                |
| Messaggio               |         |            |         |         | Identification     | trasmissione del                          |
| Esito                   |         |            |         |         |                    | messaggio Esito Revoca.                   |
|                         |         |            |         |         |                    | Deve essere univoco nell’ambito           |
|                         |         |            |         |         |                    | della stessa                              |
|                         |         |            |         |         |                    | data riferita all’elemento                |
|                         |         |            |         |         |                    | *dataMessaggioRevoca.*                    |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| dataOraMessaggio        | 1       | an         | 1..1    | 19      | Creation Date Time | Indica la data e l’ora                    |
| Esito                   |         |            |         |         |                    | del messaggio di Esito Revoca,            |
|                         |         |            |         |         |                    | secondo il formato                        |
|                         |         |            |         |         |                    | ISO 8601                                  |
|                         |         |            |         |         |                    | [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]           |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| riferimentoMessaggio    | 1       | an         | 1..1    | 1..35   | Original Message   | Con riferimento al messaggio              |
| Revoca                  |         |            |         |         | Identification     | di Esito Revoca **(ER)**                  |
|                         |         |            |         |         |                    | l’elemento contiene il dato               |
|                         |         |            |         |         |                    | identificativoMessaggioRevoca             |
|                         |         |            |         |         |                    |  legato alla trasmissione della           |
|                         |         |            |         |         |                    | Richiesta di Revoca **(RR).**             |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| riferimentoData         | 1       | an         | 1..1    | 10      | Original Creation  | Indica la data                            |
| Revoca                  |         |            |         |         | Date Time          | secondo il formato ISO 8601               |
|                         |         |            |         |         |                    | **[YYYY]-[MM]-[DD]**                      |
|                         |         |            |         |         |                    | cui si riferisce la                       |
|                         |         |            |         |         |                    | generazione del dato                      |
|                         |         |            |         |         |                    | riferimentoMessaggioRevoca.               |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| istitutoAttestante      | 1       | s          | 1..1    |         | Debtor Agent       | Riporta                                   |
|                         |         |            |         |         |                    | le stesse informazioni                    |
|                         |         |            |         |         |                    | presenti nel blocco “istitutoAttestante”  |
|                         |         |            |         |         |                    | della Richiesta di Revoca                 |
|                         |         |            |         |         |                    | **(RR)** cui si riferisce il messaggio    |
|                         |         |            |         |         |                    | di Esito Revoca.                          |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| soggettoVersante        | 1       | s          | 0..1    |         | Debtor             | Riporta le stesse informazioni            |
|                         |         |            |         |         |                    | presenti nel blocco                       |
|                         |         |            |         |         |                    | “soggettoVersante”                        |
|                         |         |            |         |         |                    | del messaggio Richiesta di Revoca         |
|                         |         |            |         |         |                    | **(RR)** cui si riferisce il              |
|                         |         |            |         |         |                    | messaggio di Eito Revoca.                 |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| soggettoPagatore        | 1       | s          | 1..1    |         | Ultimate Debtor    | Riporta                                   |
|                         |         |            |         |         |                    | le stesse informazioni presenti nel       |
|                         |         |            |         |         | /                  | blocco “soggettoPagatore” del             |
|                         |         |            |         |         |                    | messaggio Richiesta                       |
|                         |         |            |         |         | Debtor [3]_        | di Revoca (RR)                            |
|                         |         |            |         |         |                    | cui si riferisce il messaggio di          |
|                         |         |            |         |         |                    | Esito Revoca.                             |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| datiRevoca              | 1       | s          | 1..1    |         |                    | Aggregazione                              |
|                         |         |            |         |         |                    | “dati del versamento” costituita dai      |
|                         |         |            |         |         |                    | seguenti elementi:                        |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| importo                 | 2       | an         | 1..1    | 3..12   | Amount             | Campo numerico (due cifre per la          |
| Totale                  |         |            |         |         |                    | parte decimale, il separatore dei         |
| Revocato                |         |            |         |         |                    | centesimi è il punto “.”),                |
|                         |         |            |         |         |                    | indicante l’importo                       |
|                         |         |            |         |         |                    | relativo al totale delle somme            |
|                         |         |            |         |         |                    | versate.                                  |
|                         |         |            |         |         |                    |                                           |
|                         |         |            |         |         |                    |                                           |
|                         |         |            |         |         |                    |                                           |
|                         |         |            |         |         |                    |                                           |
|                         |         |            |         |         |                    | Deve essere uguale alla somma             |
|                         |         |            |         |         |                    | delle varie                               |
|                         |         |            |         |         |                    | occorrenze                                |
|                         |         |            |         |         |                    | (da 1 a 5) dell’informazione              |
|                         |         |            |         |         |                    | singoloImportoRevocato                    |
|                         |         |            |         |         |                    |  presente nella struttura                 |
|                         |         |            |         |         |                    | DatiSingolaRevoca                         |
|                         |         |            |         |         |                    | .                                         |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| identificativo          | 2       | an         | 1..1    | 1..35   | Creditor Reference | Riporta la stessa informazione            |
| Univoco                 |         |            |         |         |                    | presente nel dato                         |
| Versamento              |         |            |         |         |                    | *identificativoUnivocoVersamento*         |
|                         |         |            |         |         |                    | della Richiesta di Revoca (RR).           |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| codiceContestoPagamento | 2       | an         | 1..1    | 1..35   | Message            | Riporta la stessa informazione            |
|                         |         |            |         |         | Identification     | presente nel dato                         |
|                         |         |            |         |         |                    | codiceContestoPagamento                   |
|                         |         |            |         |         |                    |  della Richiesta di Revoca                |
|                         |         |            |         |         |                    | **(RR).**                                 |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| datiSingolaRevoca       | 2       | s          | 1..1    |         |                    | Aggregazione “dati dei singoli            |
|                         |         |            |         |         |                    | pagamenti  revocati”,                     |
|                         |         |            |         |         |                    | da un minimo di uno ad                    |
|                         |         |            |         |         |                    | un massimo di 5                           |
|                         |         |            |         |         |                    | occorrenze di revoca, facenti capo        |
|                         |         |            |         |         |                    | ad un unico                               |
|                         |         |            |         |         |                    | *identificativoUnivocoVersamento*         |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| singoloImporto          | 3       | an         | 1..1    | 3..12   | Amount             | Campo numerico                            |
| Revocato                |         |            |         |         |                    | (due cifre per la parte decimale,         |
|                         |         |            |         |         |                    | il separatore dei centesimi               |
|                         |         |            |         |         |                    | è il punto “.”),                          |
|                         |         |            |         |         |                    | indicante l’importo                       |
|                         |         |            |         |         |                    | relativo alla somma revocata.             |
|                         |         |            |         |         |                    |                                           |
|                         |         |            |         |         |                    | **Se la richiesta non è stata accolta**   |
|                         |         |            |         |         |                    | **deve essere impostato a 0.00.**         |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| identificativo          | 3       | an         | 1..1    | 1..35   | Transaction        | Riporta la stessa informazione            |
| Univoco                 |         |            |         |         | Reference          | presente nel dato                         |
| Riscossione             |         |            |         |         | Number             | identificativoUnivocoRiscossione          |
|                         |         |            |         |         |                    |  della Richiesta di Revoca                |
|                         |         |            |         |         |                    | **(RR).**                                 |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| causaleEsito            | 3       | an         | 1..1    | 1..140  | Unstructured       | Rappresenta                               |
|                         |         |            |         |         | Remittance         | la descrizione dell’esito della revoca.   |
|                         |         |            |         |         | Information        |                                           |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+
| datiAggiuntiviEsito     | 3       | an         | 1..1    | 1..140  | Additional         | Informazioni                              |
|                         |         |            |         |         | Remittance         | aggiuntive circa il provvedimento         |
|                         |         |            |         |         | Information        | adottato                                  |
|                         |         |            |         |         |                    | dall’Ente Creditore .                     |
+-------------------------+---------+------------+---------+---------+--------------------+-------------------------------------------+

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

+----------------------------+---------+------------+---------+---------+---------------------------------------------+
|          **Dato**          | **Liv** | **Genere** | **Occ** | **Len** | **Contenuto**                               |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| informativaControparte     | 0       | s          | 1..n    |         | Struttura che raggruppa                     |
|                            |         |            |         |         | le informazioni inviate                     |
|                            |         |            |         |         | dall’Ente Creditore al                      |
|                            |         |            |         |         | Nodo dei Pagamenti-SPC                      |
|                            |         |            |         |         | e rese disponibili ai PSP.                  |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| identificativoDominio      | 2       | an         | 1..1    | 35      | identificativo Dominio                      |
|                            |         |            |         |         | dell’Ente Creditore                         |
|                            |         |            |         |         | (codice utilizzato nella RPT).              |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| ragioneSociale             | 2       | an         | 1..1    | 70      | Ragione sociale                             |
|                            |         |            |         |         | dell’Ente Creditore.                        |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| dataInizioValidita         | 2       | an         | 1..1    | 10      | Data in cui inizia la validità              |
|                            |         |            |         |         | delle informazioni relative                 |
|                            |         |            |         |         | all’Ente Creditore nel                      |
|                            |         |            |         |         | formato ISO 8601: [YYYY]-[MM]-[DD]          |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| pagamentiPressoPSP         | 2       | n          | 1..1    | 1       | Indica se l’Ente Creditore                  |
|                            |         |            |         |         | consente i pagamenti                        |
|                            |         |            |         |         | pressoi PSP                                 |
|                            |         |            |         |         | (vedi § 2.2)                                |
|                            |         |            |         |         | può assumere i seguenti valori:             |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **0** NON consente i                      |
|                            |         |            |         |         | pagamenti c/o i PSP                         |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **1** CONSENTE i                          |
|                            |         |            |         |         | agamenti c/o i PSP                          |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| contactCenterEnteCreditore | 2       | an         | 1..1    | 255     | Recapiti dell'Ente Creditore                |
|                            |         |            |         |         | (Numero telefonico e/o                      |
|                            |         |            |         |         | indirizzo e-mail)                           |
|                            |         |            |         |         | presso il quale l'utilizzatore              |
|                            |         |            |         |         | finale e il PSP                             |
|                            |         |            |         |         | possono rivolgersi per                      |
|                            |         |            |         |         | ottenere informazioni.                      |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| modelloTreSpontaneo        | 2       | s          | 0..1    |         | Struttura che, se presente,                 |
|                            |         |            |         |         | indica che l’Ente                           |
|                            |         |            |         |         | Creditore consente ai                       |
|                            |         |            |         |         | propri utenti di                            |
|                            |         |            |         |         | effettuare pagamenti                        |
|                            |         |            |         |         | spontanei presso i PSP                      |
|                            |         |            |         |         | (vedi § 2.2.3)                              |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| serviziModelloTreSpontaneo | 3       | s          | 0..n    |         | Struttura contenente                        |
|                            |         |            |         |         | l'elenco dei servizi che                    |
|                            |         |            |         |         | possono essere                              |
|                            |         |            |         |         | pagati in modalità                          |
|                            |         |            |         |         | spontanea                                   |
|                            |         |            |         |         | presso i PSP.                               |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| idServizio                 | 4       | an         | 1..1    | 5       | Codice                                      |
|                            |         |            |         |         | numerico che identifica                     |
|                            |         |            |         |         | il servizio che può essere                  |
|                            |         |            |         |         | pagato in modalità spontanea                |
|                            |         |            |         |         | presso i PSP.                               |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| dataInizioAttivazione      | 4       | an         | 1..1    | 10      | Data da                                     |
|                            |         |            |         |         | cui è attiva l'erogazione dello specifico   |
|                            |         |            |         |         | servizio da parte dell’Ente Creditore       |
|                            |         |            |         |         | nel formato ISO 8601:                       |
|                            |         |            |         |         | [YYYY]-[MM]-[DD]                            |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| avvisaturaPull             | 2       | n          | 0..1    | 1       | Indica                                      |
|                            |         |            |         |         | che l’Ente Creditore consente di attivare   |
|                            |         |            |         |         | le funzionalità di avvisatura               |
|                            |         |            |         |         | digitale pull (vedi § 2.10)                 |
|                            |         |            |         |         | può assumere i seguenti valori:             |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **0 NON consente avvisatura pull**        |
|                            |         |            |         |         | - **1 CONSENTE avvisatura pull**            |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| erogazioneServizio         | 2       | s          | 0..1    |         | Aggregazione relativa alle fasce orarie di  |
|                            |         |            |         |         | erogazione del servizio da parte dell’Ente  |
|                            |         |            |         |         | Creditore.                                  |
|                            |         |            |         |         | **L’informazione**                          |
|                            |         |            |         |         | **è obbligatoria nel caso in cui il dato**  |
|                            |         |            |         |         | **pagamentiPressoPSP**                      |
|                            |         |            |         |         | **assuma il valore 1.**                     |
|                            |         |            |         |         |                                             |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| disponibilita              | 3       | s          | 1..n    |         | Aggregazione                                |
|                            |         |            |         |         | relativa al giorno della settimana,         |
|                            |         |            |         |         | del mese o dell’anno contenente             |
|                            |         |            |         |         | le fasceorarie di disponibilità del         |
|                            |         |            |         |         | servizio dell’Ente                          |
|                            |         |            |         |         | Creditore.                                  |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| tipoPeriodo                | 4       | an         | 0..1    | 7..11   | La periodicità con il quale il              |
|                            |         |            |         |         | servizio è reso disponibile; può            |
|                            |         |            |         |         | assumere i seguenti valori:                 |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **giornaliera**                           |
|                            |         |            |         |         | - **settimanale**                           |
|                            |         |            |         |         | - **mensile**                               |
|                            |         |            |         |         | - **annuale**                               |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| giorno                     | 4       | an         | 0..1    | 35      | Descrizione in formato testo delle          |
|                            |         |            |         |         | iornate di disponibilità. Assume            |
|                            |         |            |         |         | valori differenti in relazione al           |
|                            |         |            |         |         | tipoPeriodo                                 |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **giornaliera:**                          |
|                            |         |            |         |         | il campo viene omesso                       |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **settimanale:**                          |
|                            |         |            |         |         | "lunedi”, oppure “martedi”, ...             |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **mensile:**                              |
|                            |         |            |         |         | giorno singolo di calendario es. “25”       |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | - **annuale:**                              |
|                            |         |            |         |         | giorno singolo nella forma                  |
|                            |         |            |         |         | “gg-mm” es. “01-05”                         |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| fasciaOraria               | 4       | s          | 0..n    |         | Aggregazione                                |
|                            |         |            |         |         | relativa alla fascia oraria di              |
|                            |         |            |         |         | disponibilità del                           |
|                            |         |            |         |         | servizio dall’Ente Creditore.               |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| fasciaOrariaDa             | 5       | an         | 0..1    | 8       | Orario di inizio disponibilità              |
|                            |         |            |         |         | nell’ambito del                             |
|                            |         |            |         |         | giorno nel formato                          |
|                            |         |            |         |         | [hh]:[mm]:[ss].                             |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| fasciaOrariaA              | 5       | an         | 0..1    | 8       | Orario di fine disponibilità                |
|                            |         |            |         |         | nell’ambito del giorno nel                  |
|                            |         |            |         |         | formato                                     |
|                            |         |            |         |         | [hh]:[mm]:[ss].                             |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| indisponibilita            | 3       | s          | 0..n    |         | Aggregazione relativa al                    |
|                            |         |            |         |         | giorno della settimana,                     |
|                            |         |            |         |         | del mese o dell’anno,                       |
|                            |         |            |         |         | contenente le fasce                         |
|                            |         |            |         |         | orarie di indisponibilità                   |
|                            |         |            |         |         | del servizio dell’Ente Creditore.           |
|                            |         |            |         |         | La strutturacontiene le stesse              |
|                            |         |            |         |         | informazioni                                |
|                            |         |            |         |         | della struttura “disponibilita”             |
|                            |         |            |         |         | con il significato attribuito               |
|                            |         |            |         |         | all’indisponibilità                         |
|                            |         |            |         |         | del servizio.                               |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| informativaContoAccredito  | 2       | s          | 0..n    |         | Elenco dei conti di accredito               |
|                            |         |            |         |         | attivi per quell'Ente Creditore.            |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| dataAttivazioneIban        | 3       | an         | 1..1    | 10      | Indica la                                   |
|                            |         |            |         |         | data di attivazione dello specifico         |
|                            |         |            |         |         | IBAN di accredito.                          |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| ibanAccredito              | 3       | an         | 1..1    | 35      | Identifica l’International                  |
|                            |         |            |         |         | Bank Account Number,                        |
|                            |         |            |         |         | definito secondo lo standard                |
|                            |         |            |         |         | ISO 13616.                                  |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| sellerBank                 | 3       | an         | 1..1    | 50      | Identificativo                              |
|                            |         |            |         |         | MyBank della Seller Bank                    |
|                            |         |            |         |         | prescelta dall'Ente Creditore               |
|                            |         |            |         |         | (vedi Elenco dei PSP aderenti               |
|                            |         |            |         |         | pubblicato sul sito AgID).                  |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+
| idNegozio                  | 3       | an         | 0..1    | 15      | Identificativo da utilizzare nel            |
|                            |         |            |         |         | colloquio tra                               |
|                            |         |            |         |         | Wrapper MyBank ed Initiating                |
|                            |         |            |         |         | Party della Seller Bank.                    |
|                            |         |            |         |         |                                             |
|                            |         |            |         |         | Il dato può essere valorizzato o            |
|                            |         |            |         |         | meno, a seconda del                         |
|                            |         |            |         |         | tipo di modalità di                         |
|                            |         |            |         |         | attribuzione di detto codice                |
|                            |         |            |         |         | (Standard o concordata tra                  |
|                            |         |            |         |         | AgID e Seller Bank).                        |
+----------------------------+---------+------------+---------+---------+---------------------------------------------+

Le informazioni sono codificate in un file XML secondo il tracciato di
Tabella 6 e devono essere richieste dai singoli prestatori di servizi di
pagamento al NodoSPC utilizzando le apposite funzioni allo scopo messe a
disposizione (`vedi § 9.2.10 della Sezione III <../16-Capitolo_9/Capitolo9.rst#interrogazione-delle-basi-dati-del-nodospc>`__).

**Tabella** **6 - Formato file XML della “Tabella delle controparti”**

+------------------------+---------+------------+----------+-----------+-----------------------------------------------------+
| **Dato**               | **Liv** | **Genere** | **Occ**  | **Len**   |**Contenuto**                                        |
|                        |         |            |          |           |                                                     |
+========================+=========+============+==========+===========+=====================================================+
| listaInformativa       | 1       | s          | 1..1     |           | Lista delle informative Controparte valide nella    |
| Controparte            |         |            |          |           | giornata corrente (hh 00-24)                        |
|                        |         |            |          |           |                                                     |
+------------------------+---------+------------+----------+-----------+-----------------------------------------------------+
| informativa            | 2       | s          | 1..n     |           | Numero non definito di occorrenze della struttura   |
| Controparte            |         |            |          |           | informativaControparte definita nella precedente    |
|                        |         |            |          |           | Tabella 5.                                          |
+------------------------+---------+------------+----------+-----------+-----------------------------------------------------+

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

+------------------------+---------+------------+---------+---------+---------------------------------------------+
|        **Dato**        | **Liv** | **Genere** | **Occ** | **Len** | **Contenuto**                               |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| informativaControparte | 1       | s          | 1..n    |         | Struttura che raggruppa                     |
|                        |         |            |         |         | le informazioni inviate                     |
|                        |         |            |         |         | dall’Ente Creditore al                      |
|                        |         |            |         |         | Nodo dei Pagamenti-SPC                      |
|                        |         |            |         |         | e rese disponibili ai PSP.                  |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| identificativoFlusso   | 2       | an         | 1..1    | 35      | Identificativo                              |
|                        |         |            |         |         | del flusso dell’Ente Creditore,             |
|                        |         |            |         |         | con un codice utile ad identificare         |
|                        |         |            |         |         | univocamente la comunicazione               |
|                        |         |            |         |         | (es. numero di protocollo).                 |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| identificativoDominio  | 2       | an         | 1..1    | 35      | identificativo Dominio                      |
|                        |         |            |         |         | dell’Ente Creditore                         |
|                        |         |            |         |         | (codice utilizzato nella RPT).              |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| ragioneSociale         | 2       | an         | 1..1    | 70      | Ragione sociale                             |
|                        |         |            |         |         | dell’Ente Creditore.                        |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| dataPubblicazione      | 2       | an         | 1..1    | 19      | Data e ora di “pubblicazione”               |
|                        |         |            |         |         | del flusso informativo da parte             |
|                        |         |            |         |         | dell’Ente Creditore secondo il              |
|                        |         |            |         |         | formato ISO 8601.                           |
|                        |         |            |         |         | Corrisponde alla data e ora di invio della  |
|                        |         |            |         |         | comunicazione                               |
|                        |         |            |         |         | relativa all’                               |
|                        |         |            |         |         | identificativoFlusso                        |
|                        |         |            |         |         |  corrente.                                  |
|                        |         |            |         |         |                                             |
|                        |         |            |         |         | **[YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]**         |
|                        |         |            |         |         | Dev’essere maggiore della                   |
|                        |         |            |         |         | dataPubblicazione                           |
|                        |         |            |         |         |  contenuta nell’ultimo flusso di            |
|                        |         |            |         |         | informativa dell’Ente Creditore             |
|                        |         |            |         |         |  caricato nel Nodo.                         |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| dataInizioValidita     | 2       | an         | 1..1    | 19      | Data in                                     |
|                        |         |            |         |         | cui inizia la validità delle informazioni   |
|                        |         |            |         |         | relative all’Ente Creditore nel             |
|                        |         |            |         |         | formato ISO 8601:                           |
|                        |         |            |         |         | **[YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]**         |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| pagamentiPressoPSP     | 2       | n          | 1..1    | 1       | Indica se l’Ente Creditore                  |
|                        |         |            |         |         | consente i pagamenti                        |
|                        |         |            |         |         | pressoi PSP                                 |
|                        |         |            |         |         | (vedi § 2.2)                                |
|                        |         |            |         |         | può assumere i seguenti valori:             |
|                        |         |            |         |         |                                             |
|                        |         |            |         |         | - **0** NON consente i                      |
|                        |         |            |         |         | pagamenti c/o i PSP                         |
|                        |         |            |         |         |                                             |
|                        |         |            |         |         | - **1** CONSENTE i                          |
|                        |         |            |         |         | agamenti c/o i PSP                          |
+------------------------+---------+------------+---------+---------+---------------------------------------------+
| erogazioneServizio     | 2       | s          | 0..1    |         | Aggregazione relativa alle fasce orarie di  |
|                        |         |            |         |         | erogazione del servizio da parte dell’Ente  |
|                        |         |            |         |         | Creditore.                                  |
|                        |         |            |         |         | **L’informazione**                          |
|                        |         |            |         |         | **è obbligatoria nel caso in cui il dato**  |
|                        |         |            |         |         | **pagamentiPressoPSP**                      |
|                        |         |            |         |         | **assuma il valore 1**                      |
+------------------------+---------+------------+---------+---------+---------------------------------------------+

Per ciò che attiene alla comunicazione le informazioni relative ai conti
da accreditare, gli Enti Creditori inviano ad AgID il tracciato indicato
in Tabella 8.

**Tabella** **8 - Tracciato XML per comunicazione "IBAN di accredito"**

+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
|             **Dato**            | **Liv** | **Genere** | **Occ** | **Len** | **Contenuto**                                |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| informativaContoAccredito       | 1       | s          | 1..1    |         | Informativa                                  |
|                                 |         |            |         |         | inviata dall’ente creditore al Nodo dei      |
|                                 |         |            |         |         | Pagamenti-SPC                                |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| identificativoFlusso            | 2       | an         | 1..1    | 35      | Identificativo                               |
|                                 |         |            |         |         | del flusso dell’Ente Creditore,              |
|                                 |         |            |         |         | con un codice utile ad identificare          |
|                                 |         |            |         |         | univocamente la comunicazione                |
|                                 |         |            |         |         | (es. numero di protocollo).                  |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| identificativoDominio           | 2       | an         | 1..1    | 35      | identificativo Dominio                       |
|                                 |         |            |         |         | dell’Ente Creditore                          |
|                                 |         |            |         |         | (codice utilizzato nella RPT).               |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| ragioneSociale                  | 2       | an         | 1..1    | 35      | Ragione sociale                              |
|                                 |         |            |         |         | dell’Ente Creditore.                         |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| dataPubblicazione               | 2       | an         | 1..1    | 19      | Data e ora di “pubblicazione”                |
|                                 |         |            |         |         | del flusso informativo da parte              |
|                                 |         |            |         |         | dell’Ente Creditore secondo il               |
|                                 |         |            |         |         | formato ISO 8601.                            |
|                                 |         |            |         |         | Corrisponde alla data e ora di invio della   |
|                                 |         |            |         |         | comunicazione                                |
|                                 |         |            |         |         | relativa all’identificativoFlusso corrente.  |
|                                 |         |            |         |         |                                              |
|                                 |         |            |         |         | **[YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]**          |
|                                 |         |            |         |         | Dev’essere maggiore della                    |
|                                 |         |            |         |         | dataPubblicazione                            |
|                                 |         |            |         |         |  contenuta nell’ultimo flusso di             |
|                                 |         |            |         |         | informativa dell’Ente Creditore              |
|                                 |         |            |         |         |  caricato nel Nodo.                          |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| dataInizioValidita              | 2       | an         | 1..1    | 19      | Data e ora da cui saranno considerati validi |
|                                 |         |            |         |         | dal Nodo solamente gli IBAN di Accredito     |
|                                 |         |            |         |         | contenuti nel presente flusso. Deve          |
|                                 |         |            |         |         | seguire il formato ISO 8601:                 |
|                                 |         |            |         |         |                                              |
|                                 |         |            |         |         | **[YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]**          |
|                                 |         |            |         |         |                                              |
|                                 |         |            |         |         | Dev’essere maggiore o uguale alla            |
|                                 |         |            |         |         | dataPubblicazione                            |
|                                 |         |            |         |         |  e maggiore della data                       |
|                                 |         |            |         |         | corrente.                                    |
|                                 |         |            |         |         | La validità parte comunque dalle 00:00:00    |
|                                 |         |            |         |         | del giorno indicato.                         |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| contiDiAccredito                | 2       | s          | 1..n    |         | Aggregazione                                 |
|                                 |         |            |         |         | relativa agli IBAN di accredito di           |
|                                 |         |            |         |         | pertinenza dell’Ente Creditore.              |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| ibanAccredito                   | 3       | an         | 0..1    | 1..35   | Identifica                                   |
|                                 |         |            |         |         | l’International Bank Account Number,         |
|                                 |         |            |         |         | definito secondo lo standard ISO 13616,      |
|                                 |         |            |         |         | del conto da accreditare presso la Banca     |
|                                 |         |            |         |         | di accredito indicata dall’ente              |
|                                 |         |            |         |         | creditore, di norma la Banca Tesoriera.      |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| **Oppure, in alternativa,**     |         |            |         |         |                                              |
| **la struttura sotto indicata** |         |            |         |         |                                              |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| infoContoDiAccreditoPair        | 3       | s          | 0..1    |         | Aggregazione                                 |
|                                 |         |            |         |         | relativa agli IBAN di accredito              |
|                                 |         |            |         |         | di pertinenza                                |
|                                 |         |            |         |         | dell’Ente Creditore                          |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| ibanAccredito                   | 4       | an         | 1..1    | 1..35   | Vedi analogo elemento sopra                  |
|                                 |         |            |         |         | descritto..                                  |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+
| idBancaSeller                   | 4       | an         | 1..1    | 50      | Identificativo                               |
|                                 |         |            |         |         | della Seller Bank secondo                    |
|                                 |         |            |         |         | la codifica MyBank                           |
|                                 |         |            |         |         | (vedi Elenco dei PSP aderenti                |
|                                 |         |            |         |         | pubblicato sul sito AgID).                   |
+---------------------------------+---------+------------+---------+---------+----------------------------------------------+

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

+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
|           **Dato**          | **Liv** | **Genere** | **Occ** | **Len** | **Contenuto**                                   |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| informativaPSP              | 1       | s          | 1..1    |         | Informativa                                     |
|                             |         |            |         |         | fornita dal PSP al Nodo dei                     |
|                             |         |            |         |         | Pagamenti-SPC                                   |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| identificativoFlusso        | 2       | an         | 1..1    | 35      | Identificativo                                  |
|                             |         |            |         |         | del flusso dell’Ente Creditore,                 |
|                             |         |            |         |         | con un codice utile ad identificare             |
|                             |         |            |         |         | univocamente la comunicazione                   |
|                             |         |            |         |         | (es. numero di protocollo).                     |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| identificativoPSP           | 2       | an         | 1..1    | 35      | Identificativo del PSP a cui si riferisce       |
|                             |         |            |         |         | il set di dati componenti il "Catalogo Dati     |
|                             |         |            |         |         | Informativi".                                   |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| ragioneSociale              | 2       | an         | 1..1    | 70      | Ragione sociale                                 |
|                             |         |            |         |         | dell’Ente Creditore.                            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| informativaMaster           | 2       | s          | 1..1    |         | Aggregazione                                    |
|                             |         |            |         |         | corrispondente ai dati comuni del presente      |
|                             |         |            |         |         | flusso di informativa.                          |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| dataPubblicazione           | 3       | an         | 1..1    | 19      | Data e                                          |
|                             |         |            |         |         | ora di pubblicazione del set di informazioni    |
|                             |         |            |         |         | fornite da parte del PSP.                       |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| dataInizioValidita          | 3       | an         | 1..1    | 19      | Data e                                          |
|                             |         |            |         |         | ora in cui inizierà la validità del set di      |
|                             |         |            |         |         | informazioni fornite da parte del               |
|                             |         |            |         |         | PSP.                                            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| urlInformazioniPSP          | 3       | an         | 1..1    | 255     | URL di                                          |
|                             |         |            |         |         | una pagina/sito web contenente informazioni     |
|                             |         |            |         |         | specifiche del PSP.                             |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| stornoPagamento             | 3       | n          | 1..1    | 1       | Indica se                                       |
|                             |         |            |         |         | il PSP è in grado di gestire il processo di     |
|                             |         |            |         |         | storno di un pagamento                          |
|                             |         |            |         |         | (cfr. § 2.1.5 delle SANP).                      |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| marcaBolloDigitale          | 3       | n          | 1..1    | 1       | Indica se                                       |
|                             |         |            |         |         | il PSP è abilitato a vendere la marca           |
|                             |         |            |         |         | da bollo digitale                               |
|                             |         |            |         |         | (cfr. § 2.7 delleSANP).                         |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| logoPSP                     | 3       | an         | 1..1    |         | Logotipo                                        |
|                             |         |            |         |         | del PSP.                                        |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| listaInformativaDetail      | 2       | s          | 1..1    |         | Aggregazione                                    |
|                             |         |            |         |         | corrispondente alla lista di informative        |
|                             |         |            |         |         | relative ai servizi erogati dal PSP.            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| informativaDetail           | 3       | s          | 1..n    |         | Struttura                                       |
|                             |         |            |         |         | contenente le informazioni relative ai          |
|                             |         |            |         |         | singoli servizi erogati dal PSP                 |
|                             |         |            |         |         | attraverso Intermediari e Canali.               |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| identificativoIntermediario | 4       | an         | 1..1    | 35      | Identificativo                                  |
|                             |         |            |         |         | dell’Intermediario del PSP che fornisce lo      |
|                             |         |            |         |         | specifico accesso (Canale) al PSP               |
|                             |         |            |         |         | per l'erogazione del. servizio.                 |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| identificativoCanale        | 4       | an         | 1..1    | 35      | Identificativo del Canale attraverso il quale è |
|                             |         |            |         |         | erogato il servizio.                            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| tipoVersamento              | 4       | an         | 1..1    | 4       | Tipo di versamento associato allo specifico     |
|                             |         |            |         |         | servizio                                        |
|                             |         |            |         |         | (cfr. § 5.3.1 delle SANP).                      |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| modelloPagamento            | 4       | n          | 1..1    | 2       | Indica quale modello di pagamento               |
|                             |         |            |         |         | (cfr. capitolo 2                                |
|                             |         |            |         |         | delle SANP)                                     |
|                             |         |            |         |         | è gestito attraverso il canale specifico.       |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| priorita                    | 4       | n          | 1..1    | 2       | Numero intero indicante la priorità con la      |
|                             |         |            |         |         | quale viene scelto dal NodoSPC il Canale        |
|                             |         |            |         |         | per l’invio al PSP, nel caso in cui             |
|                             |         |            |         |         | quest'ultimo non sia specificato                |
|                             |         |            |         |         | dall’Ente Creditore.                            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| canaleApp                   | 4       | n          | 1..1    | 1       | Indica se                                       |
|                             |         |            |         |         | il servizio è erogato attraverso una App.       |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| servizioAlleImprese         | 4       | n          | 0..1    | 1       | Indica se                                       |
|                             |         |            |         |         | il servizio erogato dal PSP è destinato         |
|                             |         |            |         |         | ad un utilizzo solo da parte delle              |
|                             |         |            |         |         | imprese.                                        |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| identificazioneServizio     | 4       | s          | 0..1    |         | Struttura                                       |
|                             |         |            |         |         | che contiene i dati che identificano il         |
|                             |         |            |         |         | servizio nei confronti della clientela.         |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| nomeServizio                | 5       | an         | 1..1    | 35      | Nome                                            |
|                             |         |            |         |         | commerciale del servizio / app.                 |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| logoServizio                | 5       | an         | 1..1    |         | Logotipo                                        |
|                             |         |            |         |         | del servizio / app.                             |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| listaInformazioniServizio   | 4       | s          | 1..1    |         | Aggregazione                                    |
|                             |         |            |         |         | di informazioni relative al servizio            |
|                             |         |            |         |         | erogato dal PSP..                               |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| informazioniServizio        | 5       | s          | 1..n    |         | Struttura                                       |
|                             |         |            |         |         | contenente informazioni specifiche del          |
|                             |         |            |         |         | singolo servizio espresse in lingue             |
|                             |         |            |         |         | diverse.                                        |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| codiceLingua                | 6       | an         | 1..1    | 2       | Codifica                                        |
|                             |         |            |         |         | della lingua nella quale sono fornite           |
|                             |         |            |         |         | tutte le informazioni di cui alla               |
|                             |         |            |         |         | struttura                                       |
|                             |         |            |         |         | informazioniServizio                            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| descrizioneServizio         | 6       | an         | 0..1    | 140     | Testo                                           |
|                             |         |            |         |         | libero in cui è possibile specificare           |
|                             |         |            |         |         | natura e condizioni (non economiche) del        |
|                             |         |            |         |         | servizio                                        |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| disponibilitaServizio       | 6       | an         | 1..1    | 140     | Testo                                           |
|                             |         |            |         |         | libero in cui è possibile specificare orari     |
|                             |         |            |         |         | o restrizioni del servizio                      |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| limitazioniServizio         | 6       | an         | 0..1    | 140     |  Indica eventuali limitazioni poste dal PSP     |
|                             |         |            |         |         |  nell'erogazione del servio                     |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| urlInformazioniCanale       | 6       | an         | 0..1    | 255     | URL di                                          |
|                             |         |            |         |         | una pagina/sito web contenente                  |
|                             |         |            |         |         | informazioni specifiche del servizio.           |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| listaParoleChiave           | 4       | an         | 0..1    |         | Elenco di parole chiave.                        |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| paroleChiave                | 5       | an         | 1..5    | 16      | Dato a testo libero in cui è possibile          |
|                             |         |            |         |         | inserire termini utili per facilitare           |
|                             |         |            |         |         | la ricerca del servizio.                        |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| costiServizio               | 4       | s          | 1..n    |         | Struttura                                       |
|                             |         |            |         |         | che contiene i costi associati alle             |
|                             |         |            |         |         | modalità di erogazione del servizio.            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| tipoCostoTransazione        | 5       | n          | 1..1    | 1       | Modalità                                        |
|                             |         |            |         |         | di calcolo del costo della transazione.         |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| tipoCommissione             | 5       | n          | 1..1    | 1       | Tipo di                                         |
|                             |         |            |         |         | commissione da utilizzare per il                |
|                             |         |            |         |         | calcolo del costo da applicare alla             |
|                             |         |            |         |         | transazione.                                    |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| tipoCanaleServizio          | 5       | n          | 0..1    | 1       | Canale                                          |
|                             |         |            |         |         | attraverso il quale è erogato il servizio.      |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| plateaErogazioneServizio    | 5       | n          | 0..1    | 1       | Tipologia                                       |
|                             |         |            |         |         | di clientela verso la quale viene               |
|                             |         |            |         |         | erogato il servizio..                           |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| listaFasceCostoServizio     | 5       | s          | 1..1    |         | Aggregazione                                    |
|                             |         |            |         |         | delle fasce di importo.                         |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| fasciaCostoServizio         | 6       | s          | 1..8    |         | Occorrenze                                      |
|                             |         |            |         |         | di una struttura che indica, per fascia         |
|                             |         |            |         |         | di importo,                                     |
|                             |         |            |         |         | il costo della transazione.                     |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| importoMassimoFascia        | 7       | an         | 1..1    | 12      | Importo                                         |
|                             |         |            |         |         | massimo della fascia.                           |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| costoFisso                  | 7       | an         | 1..1    | 12      | Eventuale                                       |
|                             |         |            |         |         | costo fisso da applicare al pagamento in        |
|                             |         |            |         |         | aggiunta al costo della commissione.            |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+
| valoreCommissione           | 7       | an         | 1..1    | 12      | Valore                                          |
|                             |         |            |         |         | massimo del costo della commissione             |
|                             |         |            |         |         | applicabile al singolo pagamento o alla         |
|                             |         |            |         |         | transazione.                                    |
+-----------------------------+---------+------------+---------+---------+-------------------------------------------------+

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

`Torna all'indice <../../index.rst>`__

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
