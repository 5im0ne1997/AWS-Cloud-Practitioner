# Modulo 1 - Introduzione ad Amazon Web Services

## Introduzione

AWS offre molti servizi, ad esempio il Computing, lo storage, il network security, blockchain, machine learning e intelligenza artificiale.

Il modelo è di tipo client-server. IN AWS la parte server è rappresentata un servizio, ad esempio Amazon Elastic Compute Cloud (Amazon EC2) dove risiedono i server virtuali.

Una delle chiavi di AWS è che paghi solo quello che utilizzi. Questo significa che, qiuando hai bisogno di più potenza di calcolo, aumenti la potenza o il numero di server e paghi per il nuovo utilizzo. Ma quando non servono più li puoi "distruggere" e smettere di pagare, in un datacenter on-prem questa cosa non la puoi fare, i server consumano sempre corrente e costano in manutenzione. La scalabilità è ridotta, per aumentare le performance dovresti comprare dei nuovi server, ma poi non puoi restituirli e continueresti a pagare per qualcosa che non è più necessaria.

## Cloud computing

Il cloud computing è la consegna a richiesta di risorse IT via Internet che paghi ad uso e consumo.

La consegna a richiesta rappresenta la possibilità di avere le risorse che ti servono quando ti servono, ed eliminarle quando non servono più.

Le risorse IT sono qualsiasi cosa che possa essere utile ad una azienda, saper installare un programma come MySQL non rende l'azienda o te migliore degli altri. Saperlo backuppare ancora meno, ma saper gestire i dati al suo interno e ottimizzarli rende te e l'azienda competitiva. AWS ti permette di eliminare queste attività che consumano tempo per focalizzarsi su attività più competitive.

Via Internet perché risiede all'esterno dell'azienda. Quindi le risorse possono essere fruite utilizzando Internet e delle connessioni sicure.

Paghi ad uso e consumo perché, quando spegni un server non paghi più per il suo utilizzo. Se non hai più bisogno dello storage, lo puoi eliminare e non paghi più lo spazio non utilizzato. Se un servizio non è necessario nel fine settimana, perché pagare se non utilizzato.

### Modelli di cloud computing

Quando selezioni una strategia di cloud, bisogna considerare diversi fattori. Esistono 3 modelli, cloud-based, on-premeses e ibrido.

#### Cloud-based

- Esegui tutte le applicazioni nel cloud
- Migra le applicazioni esistenti nel cloud
- Progetta e costruisci le nuove applicazioni nel cloud

In un modello Cloud based, puoi migrare tutto su cloud o progettare e costruire nuove applicazioni nel cloud. Puoi costruire queste applicazioni in una infrastruttura a basso livello che richiede la gestione da parte del reparto IT, oppure costruirla ad alto livello utilizzando servizi già esistenti all'interno di AWS riducendone la gestione, l'architettura e semplica la scalabilità.

Per esempio, un'azienda può creare una applicazione che utilizza server virtuali, database e network tutto su cloud.

#### On-premise

- Distribuisci le risorse utlizzando la virtualizzazione e i tool di gestione delle risorse
- Aumenta l'utilizzo delle risorse utilizzando prodotti di gestione e di virtualizzazione

Il modello on-premise è conosciuto anche come private cloud. Quindi distribuisci le tue applicazioni in un datacenter on-premise. Questo modello è molto simile a infrastrutture IT legacy.

#### Hybrid

- Connetti le risorse cloud con l'infrastruttura on-premise
- Integri le risorse cloud con le applicazioni legacy

In un modello hybrid, le risose cloud sono connesse con l'infrastruttura on premise. Questo approccio può essere preso in considerazione in varie circostanze, per esempio si hanno delle applicazioni vecchie che si preferisce tenere on-prem, oppure sono presenti dei dati che per legge devono essere custoditi in casa.

### Benefici del cloud computing

- Spesa unica contro spesa variabile. Per costruire una infrastruttura on-prem bisogna sostenere una grossa spesa iniziale e spendere tempo per configurarla e installarla. Con una spesa variabile, come il cloud, puoi iniziare si da subito senza nessun investimento iniziale e scalare a bisogno senza sovra dimensionare l'infrastruttura.
- Basta spendere soldi per mantere un datacenter. Un datacenter necessita di molti soldi per gestirlo e mantenerlo. COn il cloud, le abilità sono meno concentrate sulla gestione e possono essere spostate sulle applicazioni e i clienti.
- Basta indovinare la capacità. Nel cloud, non devi predire quanto dovrà essere grande l'infrastruttura prima di distribuire le applicazioni. Con EC2 puoi distribuire una applicazione pagando per sole risorse necessarie, aumentarle a bisogno e diminuirle di conseguenza.
- Beneficio della massiva economia di scala. Utilizzando il cloud puoi avere dei costi variabili più bassi di quelli che potresti avere da solo. Visto che viene utilizzato da centinaia di migliaia di persone, i cloud provider possono raggiungere una economia di scala più alta, di conseguenza si traduce in costi più bassi.
- Aumenta la velocità e l'agilità. La flessibilità del cloud permette di facilitare lo sviluppo e la distribuzione delle applicazioni. Questa flessibilità di da più tempo per sperimentare e innovare. Quando hai bisogno di nuove risorse in un datacenter, devi aspettare anche settimane per averle. Nel cloud le risorse le puoi avere in qualche minuto.
- Diventa glovale in un minuto. Visto che i provider cloud sono distribuiti a livello mondiale, puoi distribuire le tue applicazioni in giro per il mondo, avvicinandole agli utenti finali diminuendone la latenza e velocizzandone l'utilizzo.

# Modulo 2 - Compute nel cloud

## Introduzione

In questo modulo, gli argomenti sono:

- Descrizione dei benefici di Amazon EC2
- Identificare le differenze delle varie tipologie di istanze EC2
- Identificare le differenze delle opzioni di pagamento di EC2
- Descrizione dei benefici di Amazon EC2 Auto Scaling
- Descrizione dei benefici di Elastic Load Balancing
- Dare un esempio degli utlizzi di Elastic Load Balancing
- Descrivere le differenze tra Amazon SImple Notification Service (Amazon SNS) e Amazon Simple Queue Service (Amazon SQS)
- Descrivere le opzioni addizionali di AWS

EC2 di AWS ti permette di velocizzare le installazioni e diminuire i costi iniziali. Quando devi creare una nuova infrastruttura o apliarla, devi scegliere il tipo di hardware e la sua dimensione, pagare in anticipo, aspettare che arrivi e installarla. Inoltre devi pagare anche se non la utilizzi. Con EC2 di AWS, sarà quest'ultimo a preoccuparsi di comprare l'hardware, installarlo e gestirlo. Tu devi solo scegliere cosa caricarci sopra e averlo disponibile in tempo reale. Questo abbatte i costi iniziali e nel tempo, e il costo del tempo utilizzato per l'installazione e manutenzione oltre che lo spazio dove metterlo.

La sua flessibilità ti permette di scegliere il sistema operativo che si vuole, creare centinaia o migliaia di server a richiesta, anche singoli servizi e server specializzati per i vari compiti. Puoi scalare verticalmente le istanze a piacimento e istantaneamente. Inoltre puoi gestire la parte network sempre all'interno di AWS per permettere o bloccare il traffico di rete e la visibilità all'interno della rete.

## Tipologie di istanze EC2

Ogni tipologia di istanza e raggruppata sotto una famiglia, dove ogni famiglia è ottimizzata per determinati compiti. Ogniuno ha una quantità di CPU, RAM e capacità di rete differenti e ti permette di scegliere quella più adatta.

Le varie famiglie sono:

- General purpose
- Compute optimized
- Memory optimized
- Accelerated computing
- Storage optimize

Una famiglia General purpose ha una potenza bilanciata in termini di CPU, RAM e Network come un web server.

Una famiglia Compute optimized è specializzata per attività intense, come un servizio di gaming oppure server scientifici.

Una famiglia Memory optimized è simile alla precedente ma per consumo intenso di RAM.

Una famiglia Accelerated computing è utile per calcoli a virgola mobile, processazione grafica o che utilizza l'accelerazione hardware.

Una famiglia Storage optimize invece è utile per software che hanno bisogno di un accesso molto veloce ai dati.

## Prezzi di EC2

Per i prezzi a richiesta, paghi quello che usi e, quando lo spegni, non paghi più se non ti serve. Non devi comunicarlo, questo ti permette di gestirlo a piaciemnto.

Per il saving plan, ti viene chiesto un impegno di utilizzo di 1 o 3 anni a prezzo scontato. Quando si sfora, paghi i prezzi normali a richiesta. Non è necessario indicare la dimensione, il tipo di istanza e la zona dove si vuole utilizzare lo sconto. E' utile quando sai già il numero di ore spese per le istanze.

Le reserved istances invece ti permettono di avere delle risorse riservate a te, indicandone il numero di istanze e la tipologia. Puoi fare dei contratti di 1 o 3 anni e pagare prima, una parte subito e una dopo o non pagare nulla subito. Ti permette di risparmiare sul prezzo delle istanze.

Le istanze a spot invece possono essere utilizzate per attività a chiamata, dove una eventuale interruzione non impatta l'operatività dell'azienda. Quando viene fatta una richiesta, l'istanza viene eseguita quando ci sono abbastanza risorse non utilizzate e viene interrotta o non eseguita quando non ci sono più abbastanza risorse, le istanze hanno una priorità minore ma ti permettono di avere un prezzo molto più basso rispetto al normale.

Infine i server dedicati, non sono condivisi con altri tenant e sono dedicati solo a te. Possono essere utlizzati per questioni di sicurezza e segregazione dei dati.

A differenza delle istanze a richiesta, dove AWS non sa quante risorse serviranno finché non vengono utilizzate e per quanto tempo, le altre opzioni servono per avvisare AWS del tuo consumo futuro e permetterne la predisposizione delle risorse. In questo modo possono ottimizzare i processi e abbattere i costi di gestione, offrendo dei prezzi più bassi.

Quindi, utilizzare un prezzo a richiesta è utile all'inizio per capire quante risorse serviranno e studiare un piano di spesa che permette di abbattere i costi a te e ad AWS.

## Scalabilità

La scalabilità ti permette di avere le risorse necessarie solo quanto servono. Normalmente si hanno carichi diversi di lavoro in orari e periodi differenti. In un datacenter on prem, se viene dimensionato per il carico medio, hai delle risorse inutilizzate su cui paghi comunque e nei momenti di carico le risorse non bastano. Nel cloud puoi scalare automaticamente le risorse quando sono necessarie e smettere di pagare quando il carico diminuisce. In questo modo paghi solo per quello che usi.

Esistono due tipi di auto scaling. Quello dinamico, che aumenta quando è necessario e quello predittivo, che aumenta prima che sia necessario in base a degli algoritmi.

Inoltre esistono due tipi di scaling, aumentare le risorse o il numero di istanze.

Quando si distribuisce una nuova applicazione, ci sarà un numero minimo di istanze necessarie al suo funzionamento. Quando si specifica il desiderato, EC2 esegue le istanze necessarie per il carico minimo necessario all'esecuzione. Quando avrai bisogno di più potenza, le istanze scalano in automatico per soddisfare la richiesta (a livello di risorse o di numero, in base al gruppo e la tipologia di applicazione) e verranno eliminate quando non sono più necessarie. Puoi inoltre indicare la capacità massima, di conseguenza EC2 non supererà mai il limite prefissato. Questo si riflette sulla utilizzabilità del servizio e abbatte i costi in quanto paghi solo quello che utilizzi senza sivradimensionare le istanze.

## Direzionare il traffico con Elastic Load Balancing

Elastic Load Balancing permette di distribuire il traffico delle applicazioni in maniera automatica verso le risorse.

Un load balancer è un punto singolo punto di contatto dove arrivano tutte le richieste verso il tuo gruppo di auto scale. Questo vuol dire che puoi aggiungere o togliere istanze EC2 per rispondere al traffico in arrivo senza doversi preccupare di modificare il traffico. Il load balancer, in automatico, ridireziona il traffico verso tutte le istanze EC2 e smette di inviare traffico quando la risorsa non è più disponibile.

Auto scale e load balancer sono due servizi separati, ma che possono lavorare assieme per aumentare le performance dell'infrastruttura semplificandone la gestione.

## Messaging e Queuing

Una applicazione è composta da vari componenti. Questi componenti comunicano tra di loro, inviando dati, richieste e permettono alle applicazioni di continuare a funzionare. Quando si ha una applicazione monolitica, formata una singola applicazione fatta da vari componenti che sono strettamente legati tra di loro, se un componente fallisce anche gli altri possono fallire e quindi tutta l'applicazione di blocca.

Con un approccio a microservizi, quando un componente fallisce, gli altri continuano a funzionare finché la comunicazione non riprende correttametne. Ogni componente ha una funzione ben precisa e sono tutti slegati tra di loro.

Con Amazon Simple Notification Service (SNS) è possibile utilizzare un servizio di publish/subscribe. Può essere utilizzato per inviare notifiche alle applicazioni, sms o email oppure ad altri servizi AWS. E' possibile dividere le notifiche per topic, in questo modo si possono raggiungere solo i servizi necessari oppure tutti.

Con Amazon Simple Queue Service (SQS), si può avere un servizio di queuing. Può ricevere, inviare e salvare i messaggi delle varie applicazioni senza perderli. Se un servizio non è disponibile, accumula i messaggi finché non torna operativo.

## Serivzi addizionali

### Serverless computing

Nel serverless compunting, è possibile eseguire applicazioni senza dover gestire e mantenere le istanze EC2. La parte di gestione, patching e altro viene gestito da AWS.

### AWS Lambda

Un esempio di serveless compunting è AWS Lambda. Permette di eseguire del codice direttamente su AWS senza dover gestire una o più istanze EC2. Puoi caricare del codice, impostare dei trigger che attivano la Lambda e aspettare che venga eseguito. In questo modo non è necessario gestire le istanze per l'esecuzione e paghi solo quando vengono eseguite (senza avere una istanza sempre accesa che non esegue nulla). E' pensata per esecuzioni brevi, sotto i 15 minuti. Se si ha bisogno di più tempo, è necessario pensare ad un diverso tipo di approccio.

### Container

I container danno la possibilità di avere uno standard per creare i pacchetti delle tue applicazioni e le proprie dipendenze tutte in un singolo oggetto. Si puossono utilizzare per applicazioni che hanno la necessità di essere sicure, affidabili e scalabili.

Avere una sola istanza con più container è facile da gestire, ma quando si hanno decine o centinaia di istanze, diventa molto più complicato. In aiuto arrivano gli orchestratori di container.

### Amazon Elastic Container Service (ECS)

ECS è un software con alta calabilità e performance per gestire i container e scalare l'infrastruttura. ECS supporta Docker.

### Amazon Elsatic Jubernates Service (EKS)

EKS è un servizio completametne gestito per usare Kubernates su AWS.

### AWS Fargate

AWS Fargate è un motore serverless per la gestione di container. Funziona sia con ECS che EKS. Quando viene utilizzato, non è necessario creare e gestire le istanze EC2. Fargate gestisce le istanze.

# Modulo 3 - Global Ingrastructure and Reliability

## Introduzione

Per avere una infrastruttura in grado di soddisfare tutti i requisiti ed essere sempre funzionante, è necessario che sia in alta affidabilità. Questo è possibile distribuendo le istanze su più regioni, in modo che se dovesse succedere qualcosa in una singola regione, l'infrastruttura è sempre raggiungibile da un'altra parte.

## AWS Global Infrastructure

Aws è divisa in regioni, ogni regione è una zona nel mondo, colelgate tra di loro da una rete di fibra e isolate, a livello di dato, l'una con l'altra. In ogni regione sono presenti più datacenter in modo da distribuire la potenza sul territorio e mitigare i disastri.

Ci sono vari fattori da considerare quando si sceglie una regione. La compliance è la prima da considerare. Se il dato deve risiedere all'interno di una regione specifica, per esempio in Italia deve risiedere solo in Italia, l'unica scelta da fare è la regione Italiana. Se la compliance non è una limitazione sulla scelta allora ci sono altri fattori da considerare. Per esempio la prossimità, se il business è a Singapore, allora ha senso scegliere quella regione, in questo modo si abbatte la latenza tra il servizio e l'utente finale. Un'altra opzione è la scelta delle funzionalità, non tutte le funzionalità di AWS sono disponibili in tutte le regioni, verranno implementate nel tempo ma non possono essere distribuite sempre a livello globale poiché potrebbero richiedere dell'hardware specifico. Ultimo, ma non meno importante, è il prezzo. Ogni regione ha un prezzo differente, causati da vari aspetti che possono essere il prezzo della corrente alla tassazione. Per esempio in Brasile, la tassazione è estremamente alta, può costare oltre il 50% in più rispetto agli stati uniti.

Ogni regione è fatta da più gruppi di datacenter, e questi gruppi sono distribuiti a livello geografico nella regione. In questo modo, se dovesse esserci un disservizio in un datacenter, saranno presenti gli altri all'interno del gruppo, ma se dovesse esserci un disservizio generalizzato in un gruppo, le risorse sarebbero irraggiungibili. Questi gruppi vengono chiamiti Availability Zone. Per rendere il servizio sempre disponibile, è bene avere 2 o più istanze in Availability Zone diverse, in questo modo viene mitigato il problema e il servizio sarebbe sempre raggiungibile.

Sono presenti, inoltre, servizi dedicati alle regioni (per esempio il Load Balancer). Questi servizi, essendo specifici per regione, sono già distribuiti su più availability zone per essere sempre disponibili.

## Edge Locations

Per distribuire i dati nel mondo, il problema è la latenza. Immaginando di essere in Brasile e un utente in Cina vuole accedere ad un video sulla piattaforma, dovrebbe scaricarlo dal Brasile con una certa difficoltà. Le Edge Location sono delle copie dei dati posizionati in una specifica regione in modo che il dato sia sempre disponibile e più vicino possibile all'utente che ci accedere. Non è necessario rifare l'intera infrastruttura, viene creata una copia del dato quindi il sito magari è sempre disponibile dal Brasile, ma quando viene scaricato qualcosa, il file è disponibile in Cina, con tempistiche minori.

Con AWS Outposts è possibile avere dei server fisici, posseduti e mantenuti da AWS, nel proprio datacenter. Può essere utile in specifiche situazioni.

## How to provision AWS resources

Sono presenti vari modi per interagire con AWS, la prima è la Management Console. E' una console via web che ti permette di fare qualsiasi cosa all'interno di AWS, è utile per esporare i servizi e testare le funzionalità. Ma, in un ambiente molto grande, può essere tedioso eseguire molti click, o dimenticarsi una spunta, navigare in molte finestre per eseguire tante azioni. Quindi vengono in aiuto le APIs, le APIs ti permettono di cominicare con tutti i servizi di AWS sia via CLI che tramite SDK. Con la CLI si possono eseguire comandi e creare script che eseguono pià azioni, così da non perdere nessun passaggio, oppure con l'SDK (che supporta vari linguaggi di programmazione) creare dei veri e prorpi programmi che eseguono azioni e automatizzare qualsiasi cosa in AWS.

Con AWS Elastic Beanstalk, è possibile creare delle configurazioni personalizzate, utilizzando un linguaggio di programmazione, e il servizio si preoccuperà di creare in autonomia gli ambienti e le configurazioni necessarie, senza cliccare in molte finestre o eseguire svariati comandi da CLI.

AWS CloudFormation è un infrastucture as a Code, ti permette di scrivere uno Yaml o Json indicando come vuoi l'infrastruttura senza specificare dati specifici e CloudFormation creerà tutto in autonomia.
