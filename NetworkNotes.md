# Network&Security
## Appunti & Note (in Italian)

## NIC: Network Computer Card
è la scheda di rete del computer, serve per connettere qualsiasi dispositivo alla rete.
## Network Protocol:
E’ un insieme di regole e di standard che permettono ai computer di poter comunicare tra loro
## Home Network:
il router riceve i dati e li indirizza da un interfaccia ad un’altra, scegliendo il giusto percorso da eseguire. Questo permette 
di scegliere una strada che sia più rapida, ottimizzando i tempi di risposta.
## SOHO: Small Office & Home Office:
uno switch ti permette di avere più punti di connessione per connettere più dispositivi alla rete.
## IP ADDRESS: Internet Protocol Access
è un indirizzo numerico assegnato ad ogni device che si interfaccia ad internet. Funziona similmente all’indirizzo di casa.
## DHCP: Dinamic Host Configuration Protocol
permette di allocare dinamicamente gli indirizzi IP dei device connessi al router.
## DNS: Domain Name System
converte nomi o nomi di dominio, come google.com, da HUMAN READABLE in indirizzi IP, in questo modo i computer riescono ad 
identificare un nome scritto nella URL e tradurlo in un indirizzo IP, in modo da permettere al device di interfacciarsi al sito.
## MAC ADDRESS:
indirizzo fisico della scheda di rete, è unico per ogni scheda. E’ lungo 48bit, è una combinazione del valore della società 
produttrice della scheda di rete (OUI →Organization Unique Identifier) e di una porzione unica.
## OSI Model:
E’ la suddivisione in Layer, serve per comprendere meglio come funziona il networking. La necessità di creare un modello è nata 
dal crescente bisogno di interoperabilità degli strumenti di networking, che essendo inizialmente chiusi, e operando su sistemi 
proprietari, rallentavano lo sviluppo di sistemi di rete. Oggi, con l’OSI MODEL, questo non avviene, poiché tutti i sistemi 
operano su questo tipo di modello che è STANDARD.
## I Layer sono 7. 
Ogni Layer è indipendente dall’altro,
 
 ### LAYER 7: application 
– Network processes to application(Si parla di protocolli, non app)
 ### LAYER 6: presentation 
– si assicura che i dati siano leggibili dai sistemi al ricevimento
 ### LAYER 5: session 
 – InterHost Communication, stabilisce, mantiene e termina le sessioni di connessione tra le varie applicazioni che si 
 interfacciano tra di loro.
 ### LAYER 4: transport 
– end-to-end connection, mediante segmetazione dei messaggi in pacchetti. Il PC ricevente, riassembla le informazioni che riceve, 
ricostruendo il 
messaggio iniziale. Usa TCP (Transmission Control Protocol) e UDP (User Data Protocol).
 ### LAYER 3: network 
– permette la consegna dei pacchetti di dati da un device ad un altro attraverso il path più efficiente per poter consegnare i 
pacchetti. I criteri di 
scelta del path, sono determinati dal costo, dalla lunghezza di banda, dalla hop count, o dalla longest match of network address. 
Non cè reiability in Layer 3, esso 
determina il path da seguire ed il Logical Addressing.
 ### LAYER 2: data link 
– permette agli indirizzi fisici di accedere ai media. Definisce come vengono formattati dati per la trasmissione e come è 
controllato l’accesso al  
networking. Ci permette anche di capire se ci sono errori nel network (Provides Error Detecting).
 ### LAYER 1: physical 
– binary transmission, definisce i segnali, fisici, elettronici, procedurali, le funzionalità specifiche, per 
attivare/disattivare/mantenere i segnali fisici.
### Layer 1:
comprende tutte le caratteristiche fisiche e le proprietà dei cavi, degli strumenti, delle connessioni FISICHE, che avvengono tra 
un device ed un altro.
### HANDSHAKE: 
procedura standard di stabilimento di connessione tra 2 device, è simile al processo umano, mediante la quale, quando due persone 
si incontrano, si salutano, iniziando una conversazione.
## TCP-3WAY HANDSHAKE:
permette di reinviare pacchetti che vengono persi durante la connessione di 2 dispositivi, a differenza di UDP, che quando un 
pacchetto subisce un DROP, viene perso.
### SESSION MULTIPLEXING:
lavora su Layer 4, permette il multiplexing di molti messaggi in stream o sessioni in un unico link logico, mantenendo traccia di 
quali messaggi appartengono a quale sessione. UDP non lo permette, esso viene usato maggiormente per VoIP o applicazioni che non 
necessitano di ritrasmettere i pacchetti.
### TCP → Telephone call
### UDP → postal service
### HOST COMMUNICATION: 
ogni HOST che cerca di mettersi in contatto con un altro HOST, mette in contatto un LAYER con il LAYER corrispondente dell’altro 
HOST.
 Es:
 LAYER 7 → può parlare solo con LAYER 7
 LAYER 3 → può parlare solo con LAYER 3
 ecc ecc…
## ENCAPSULATION:
quando un HOST (un pc) tenta di connettersi ad un sito (google.com) si interfaccia ad esso partendo da LAYER 7 fino a LAYER 1, 
con un approccio TOP-DOWN. Quindi i DATI vengono incapsulati dall’HEADER del LAYER 7, che vengono incapsulati dall’HEADER di 
LAYER 6, ecc… Arrivati a Layer 2, si aggiunge un FRAME CHECK SEQUENCE ai dati, che assicura che i dati non siano corrotti dal 
mittente al destinatario (ricordiamo che LAYER 2 permette di capire se ci sono errori!). LAYER 1, trasmette i BIT.
## DE-ENCAPSULATION:
quando un HOST (un pc), o un WEB SERVER riceve dei dati trasmessi da un altro HOST, deve rimuovere gli HEADER dell’incapsulamento 
per poter visualizzare i dati. Questo processo, contrario all’incapsulamento, viene chiamato DE- ENCAPSULATION, e lavora BOTTOM-
UP.
## P2P COMMUNICATION:
il peer-to-peer è la conversazione di un qualsiasi LAYER, con il suo corrispondente tra 2 pc.
## TCP vs OSI:
nel mondo reale, i Network Engineers non usano l’OSI Model nella sua forma classica. Tendono invece a concentrarsi sulla parte 
inferiore dell’OSI Model (i primi 4 LAYER). TCP/IP, unisci i primi 2 LAYER in Network Access LAYER, lascia invariati LAYER 3 e 4 
ed unisce i LAYER 5,6 e 7 in Application LAYER. Nel mondo reale, si tende ad usare un HYBRID dei 2 (che è uguale a TCP/IP eccetto 
per i primi 2 LAYER che sono mantenuti uguali all’OSI Model) però riferendosi ad esso come se fosse OSI Model.
## COME FA UN HOST A RICONOSCERE I PACCHETTI?
Può capitare che un HOST comunichi con un altro con un dato protocollo e contemporaneamente comunica con esso con un altro 
protocollo, come fa l’Host ricevente a riconoscerli ed a leggerli? Esiste un numero identificativo (TYPE FIELD) di ogni LAYER, 
che permette l’identificazione del pacchetto come appartenente ad un determinato LAYER, questo permette di riconoscere il 
pacchetto e di indirizzarlo (sempre bottom-up) al LAYER corrispondente. Il PROTOCOL NUMBER permette di riconoscere che il device 
sta usando un protocollo posto ad un dato LAYER (i più comuni sono UDP e TCP). Ogni protocollo usa un numero di porta specifico 
(TCP usa la porta 69, UDP usa la porta 80).
## COME CATTURARE I PACCHETTI?
Con WireShark! Programma Open Source che permette di “Sniffare” il traffico e quindi le informazioni che vengono inviate da un pc 
ad un altro.
## COME CONVERTIRE UN INDIRIZZO IP?
IPv4 Addresses è formato da 4 ottetti in lunghezza, ovvero 4 gruppi di 8 bits (range 0-255). esso può essere rappresentato in 
decimale ed in binario.

 Es:
 10.1.23.19 → decimale
 00001010.00000001.00010111.00010011 → binario
 
E’ importante capire che si può convertire un indirizzo IP in binario e decimale, perché ci permette di capire la Topologia di un 
Sistema di Reti.
 
## ARP & MAC ADDRESS REPRESENTATION: 
vengono riconosciuti e rappresentati tramite il sistema Esadecimale. l’ARP REQUEST è quello che richiede il MAC ADDRESS, tra 2 
pc.
## IP ADDRESSING: 
come possiamo assegnare un indirizzo IP? In IPv4 abbiamo delle classi di IP:
CLASSE A, CLASSE B, CLASSE C, CLASSE D, CLASSE e CIDR. Abbiamo inoltre degli indirizzi detti “speciali”:
loopback address;
local broadcast address;
e altri….

A differenza del MAC ADDRESS che è unico e viene creato quando viene creata la scheda di rete, l’IP ADDRESS è determinato da un 
amministratore di rete, viene quindi assegnato. Basta pensare a DHCP per capire che gli indirizzi IP possono cambiare. Possono 
essere utili anche per determinare chi sta parlando con chi (un indirizzo IP non identifica una persona fisica, ma permette di 
identificare il computer che sta dialogando con il Server). Risiede nel LAYER 3 dell’OSI Model, e anche se può cambiare, è unico. 
IP PRIVATI vengono usati all’interno di aziende per poter dialogare all’interno di una rete aziendale. Quando il DNS si 
interfaccia ad un sito (www.google.com) trasforma il nome del sito in indirizzo IP (si può pensare al ruolo del DNS come ad una 
rubrica telefonica, ogni nome corrisponde ad un numero, che nel caso di internet è un indirizzo IP).

## DEVICE IN INTERNET: 
i device che si interfacciano ad internet, vengono configurati con degli indirizzi IPv4, che vengono risolti dal DNS. MA esiste 
anche un indirizzo IPv6:
 Es:
 2001:20::2 (ma ne parleremo più avanti)
 
IPv4 è un protocollo di LAYER 3, cher non necessita di connessione, il trasmettitore invia i dati senza notificare il ricevente, 
e quindi non ritorna alcuna informazione dal ricevente (un po’ come una raccomandata senza ricevuta di ritorno). TCP è 
connection-oriented, e creerà una sessione tra trasmittente e ricevente con dei SYN, SYN ACK e ACK (aknowledge message). I 
Pacchetti vengono considerati singolarmente, ed è per questo che possono viaggiare secondo Path differenti (scelti dal ROUTER in 
base ai criteri).
 Es:
 RIP → hopcount
 OSPF → Bandwidth
 Routing Protocol → best path

La struttura di assegnamento degli indirizzi e gerarchica, IP deve cercare di garantire la massima efficienza di consegna dei 
pacchetti. I pacchetti tuttavia possono essere intercettati, duplicati, dirottati o persi durante la trasmissione. TCP però può 
ritrasmettere i pacchetti eventualmente (non UDP). Quindi ricapitolando, IP, non ha sessioni, non può recuperare i dati qualora 
vengano persi, non può ritrasmettere i pacchetti. TCP invece come protocollo, può ritrasmettere i pacchetti, accetta pacchetti 
corrotti/malfunzionanti ma è connected-oriented. IP ADDRESS è formato da 32 Bits diviso in 4 ottetti da 8 bits l’uno. Essendo 
gerarchico permette una struttura di routing, analogamente a come potrebbe funzionare l’indirizzo di casa con la posta. Il Router 
invece indirizza il traffico agli indirizzi di destinazione, mediante il DESTINATION ADDRESS.
## IP ADDRESS: Da cosa è formato?
Da NETWORK ADDRESS PORTION, che identifica un network specifico, permette al router di mantenere le routing tables che 
contengonoi log di routing. Esso permette di fare il match tra l’IP destinatario con il network address.E’ formato anche da HOST 
ADDRESS PORTION (HOST ID) che identifica uno specifico ENDPOINT di un network e altri device collegati (smartphone, tablet, 
ecc…).Sotto questo punto di vista, possiamo considerare un’analogia con le vie stradali. Per spiegare gli indirizzi ed il 
networking. Ogni casa di una strada ha un proprio indirizzo che è relativo al numero civico ed alla strada dove è collocata. 
Analogamente, quando un pc vuole dialogare con un server, vuole essere sicuro che il server alla quale si interfacci sia proprio 
quello, convertendo mediante il DNS il nome Human Readable in indirizzo IP. Ma questo può avvenire nel momento in cui ci sia un 
solo indirizzo IP chge fa riferimento a quel determinato server! Per questo, anche se può cambiare, l’indirizzo IP è unico, e 
permette di identificare il pc con la quale si 
dialoga ed il server con il quale si ha dialogato.
## ARP (ADDRESS RESOLUTIO PROTOCOL):
è usato per identificare uno specifico indirizzo IP di uno specifio HOST in un Network. Un IP ROUTING TABLE è popolato di Network 
ADDRESSES, ovvero gli indirizzi IP che hanno ottenuto il match con il router (il router si è collegato ad un sito, per cui si 
ricorda di aver dialogato con esso, ogni qual volta che si vuole dialogare con quel sito, visto che la prima volta la 
conversazione è andata a buon fine, il router mi permetterà di dialogare con esso). IP TABLE si ricorda inoltre la porta e 
l’indirizzo del destinatario, pertanto sa perfettamente a chi deve inoltrare i pacchetti che si vuole inviare per inziare a 
dialogare.
## IP CLASSES:
Le classi di indirizzi IP (o classful addressing) sono una formalità per dividere lo spazio di indirizzamento IPv4 introdotta dal 
RFC 791 nel 1981 ed in uso fino all'introduzione del Classless Inter-Domain Routing (CIDR) nel 1993. Questo sistema di i
ndirizzamento basato sulla classe prevede che dai primi bit di un indirizzo IP si possa determinare la classe e di conseguenza 
la subnet mask. In questo modo il tipo di classe si può determinare sulla base dei bit più significativi. Vediamo come: 

## Classe A 
Il primo byte rappresenta la rete; gli altri tre gli host per ogni rete. 
In notazione decimale gli IP variano nel modo seguente: 0-127.H.H.H; 
La maschera di rete è 255.0.0.0 (o anche detta /8 in quanto i bit di rete sono 8); 
Questi indirizzi in binario iniziano con il bit 0. 

## Classe B 
I primi due byte rappresentano la rete; gli altri due gli host per ogni rete. 
In notazione decimale gli IP variano nel modo seguente: 128-191.N.H.H; 
N varia da 0 a 255. 
La maschera di rete è 255.255.0.0 (o anche detta /16 in quanto i bit di rete sono 16); 
Questi indirizzi in binario iniziano con i bit 10. 

## Classe C 
I primi tre byte rappresentano la rete; l'ultimo gli host per ogni rete. 
In notazione decimale gli IP variano nel modo seguente: 192-223.N.N.H; 
La maschera di rete è 255.255.255.0 (o anche detta /24 in quanto i bit di rete sono 24); 
Questi indirizzi in binario iniziano con i bit 110. 

## Classe D 
È riservata agli indirizzi multicast. 
In notazione decimale gli IP variano nel modo seguente: 224-239.x.x.x; 
Non è definita una maschera di rete, essendo tutti e 32 i bit dell'indirizzo utilizzati per indicare un gruppo, non un singolo 
host; 
Questi indirizzi in binario iniziano con i bit 1110. 

## Classe E 
Riservata per usi futuri; 
In notazione decimale gli IP variano nel modo seguente: 240-255.x.x.x; 
Non è definita una maschera di rete; 
Questi indirizzi in binario iniziano con i bit 1111.

Esempio: 
Se occorresse analizzare l'indirizzo IP 130.165.4.2 privo di maschera di rete e fosse necessario trovarne la classe di 
appartenenza, si potrebbe iniziare considerando che convertito in binario il primo ottetto (il numero 130) risulterebbe 10000010, 
ovverosia un numero appartenente alla classe B proprio perché gli indirizzi di classe B iniziano con i primi bit a 10.

Esempio: 
Se fosse necessario calcolare a mano il numero di reti e di host disponibili negli indirizzi di classe B, si effettuano i 
seguenti calcoli: 
Numero di reti: 214 (bit di rete) = 16 384 
Numero di host: 216 (bit di host) = 65 536 Sottraendo 2 (in quanto si escludono l'indirizzo di rete e quello di broadcast) = 
65 534

Per il calcolo della rete si effettua 214 in quanto questo è il calcolo per trovare tutte le combinazioni possibili su 14 bit. 
Infatti in classe B vi sono 16 bit utilizzati per la rete (vedere riferimenti alla tabella: In classe B il numero di bit per la 
rete N è 16) ma considerando che i primi 2 bit sono sempre fissi a 10, allora i bit che veramente possono variare scendono a 14. 
Analogo discorso per il calcolo degli host, dove si effettua 216 in quanto questo è il calcolo per trovare tutte le combinazioni 
possibili di host su 16 bit disponibili a tale scopo (vedere riferimenti alla tabella: In classe B il numero di bit per gli host 
H è 16). È molto importante sottolineare come non siano mai considerati host sia l'indirizzo di broadcast (tutti i bit degli host 
H a 1) che l'indirizzo di rete (tutti i bit degli host H a 0); per cui nel calcolo degli host si sottrae sempre 2 al risultato 
ottenuto proprio per escludere questi due indirizzi particolari che non sono host. L'intervallo di indirizzi utilizzati da ogni 
classe sono indicati nello schema successivo mediante notazione decimale puntata (dot-decimal notation).

## Sostituzione delle classi
A lungo andare, le classi di tipo C si sono rivelate troppo poche per le esigenze di indirizzamento e si è dovuto assegnare 
subnet di grana più fine anche all'interno delle classi A e B. A partire dal 1993 si abbandonò quindi il concetto di classful 
routing in favore del Classless Inter-Domain Routing (CIDR). 

## LOOPBACK ADDRESS: 
viene usato per inviare messaggi dal sistema a se stesso, per operazioni di testing ed è veramente utile per controllare che lo 
STACK TCP/IP sia correttamente installato all’interno della macchina. Si riconosce in 127.0.0.1 (127.x.x.x), è una CLASSE A (16 
milioni di IP) in IPv6 è rapprestentato da ::1, in modo da essere sicuri che si faccia riferimento esattamente a quell’indirizzo 
e non ad uno dei 16 milioni. I router hanno un loopback addresses che sono diversi rispetto al local loopback address. Questi 
LOOPBACK ADDRESSES sono molto utili per il routing di protocolli come OSPF

## RCF1918: REQUEST FOR COMMENTS:
sono degli internet standards, e non viene cambiato facilmente, ma può essere aggiornato, 
quando un nuovo RFC sostituisce uno obsoleto. Specificano come agiscono i protocolli e come devono rapportarsi. Essendo dei 
documenti molto lunghi, può risultare noioso consultarli, per questo, a volte vengono resi divertenti. RFC 1149 ad esempio, 
tratta come i pacchetti possano essere inviati da 2 IP l’un l’altro attraverso dei piccioni (Avian Carriers). Tuttavia, RFC 1918 
è molto importante poiché discute gli IP PRIVATE ADDRESSES, che sono indirizzi non raggiungibili mediante il routing, poiché gli 
ISP bloccano il traffico verso questi indirizzi. Poiché gli indirizzi IPv4 sono terminati, per aumentare la longevità di IPv4, si 
è utilizzato gli RFC, che finora hanno funzionato abbastanza bene, posponendo la fine di IPv4. Questi tipi di IP privati, possono 
essere utilizzati all’interno delle organizzazioni. Essi verrebbero passati attraverso un NAT, o mascherati in qualche altro 
modo. Questi indirizzi riservati, sono:
a single number Class A, 16 contiguous of Class B numbers and a set of 256 contiguous Class C numbers.

## NAT: NETWORK ADDRESSES TRANSLATION
prende un indirizzo IP in entrata e lo maschera, cambiandolo.
## DHCP CONFIGURATION:
quando un pc, ha come configurazione il DHCP, e quando il server non è raggiungibile, il range di IP che 
viene assegnato, nei vecchi Windows, era 
169.254.0.0/16 (CLASSE B → subnetmask 16).

Ovviamente se 2 computer sono collegati tra loro con un cavo, comunicano senza bisogno di alcun tipo di di server o 
configurazione, e generano randomicamente la parte HOST 
dell’indirizzo IP. Questo però genera traffico che non può effettuare routing, comunicano solo sulla linea locale generata dal 
cavo di collegamento. Ogni qual volta che 
vedo tramite il mio terminale, un indirizzo IP della famiglia 169.254.x.x, posso dire che si tratta di un indirizzo IP che non è 
stato allocato dinamicamente, ma ha 
semplicemente scelto un IP in quel range.

## SUBNETMASK: 
è usato per determinare quale parte di un IP ADDRESS e l’HOST portion e quale è il NETWORKING. Se 2 pc sono nella stessa subnet, 
allora posso comunicare tra loro. Se però 
sono su diversi subnet, bisogna effettuare il routing del traffico tra i 2 pc. In base alla maschera, posso determinare se sono 
sulla stessa linea oppure no. Determinare 
questo, mi permette di capire se devo effettuare il routing del traffico, oppure no. La CIDR è quella che ha inserito le maschere 
per sopperire le classi. Le Classi A, B e 
C, possiedono una maschera cosiddetta “naturale” (/8, /16, /24). infatti, usando ipcalc (“sudo apt install ipcalc”) su un IP, 
esso mi dice la sua maschera “naturale”, 
tuttavia, se necessario, la maschera può essere specificata.
Lo SWITCH a volte può decidere di determinare ad una macchina di avere IP STATICO, soppiantando il DHCP.
