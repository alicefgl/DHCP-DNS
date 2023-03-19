# DHCP-DNS

CONSEGNA:
Ampliare l'esercizio 3 in questo modo:
 - ogni rete deve avere il proprio DHCP Server, tutti i PC sono configurati dinamicamente
 - su una delle reti ( a vostra scelta) è presente un server DNS che offre il servizio a tutte e 4 le sottoreti.
- sulla stessa rete del DNS è presente anche un server HTTP che deve esporre le proprie pagine web con dominio "SIRulez.it"
 
Consegnare sul repo DHCP-DNS di GitHub descrivendo in sintesi il lavoro svolto sul file README.md

CONOSCENZE TEORICHE:
Subnetting:
Il subnetting è una suddivisione di una rete principale in diverse sottoreti che possono contenere un determinato numero di dispositivi ai quali corrisponde un indirizzo ip, per eseguire il calcolo del subnetting è perciò necessario definire gli intervalli delle combinazioni di indirizzi ip per ogni sottorete e la subnet mask relativa all'insieme.
Questo processo si applica in base a determinate esigenze che costringono quindi chi struttura una rete ad abbandonare le classi di indirizzi, si avranno perciò delle configurazioni classless.
[Subnetting di due reti](https://github.com/alicefgl/Subnetting)

[Subnetting di quattro reti](https://github.com/alicefgl/Subnetting4)

DHCP:
DHCP (Dynamic Host COnfiguration Prootcol) è un servizio che si utilizza per assegnare indirizzi IP a dei dispositivi in modo automatico. E’ possibile impostare su di esso il range di indirizzi IP che possono essere forniti, specificando un valore minimo e uno massimo. Si può impostare inoltre l’indirizzo IP del gateway (che nel caso della prova coincideva con il router) ed il DNS Server della rete. Su filius dopo aver configurato il DHCP Server è necessario abilitare il servizio su ogni dispositivo
che ne necessita.

DNS:
DNS (Domain Name Server) è un servizio che ha lo scopo di assegnare dei nomi a degli indirizzi IP, è utilizzato ad esempio per pagine web in quanto sarebbe scomodo e
soprattutto inefficiente dover scrivere ogni volta l’intero indirizzo IP relativo alla pagina che si vuole visitare: come soluzione si sceglie abitualmente
questo servizio.

SVOLGIMENTO:
- impostazione DHCP Server
Dopo aver effettuato la [suddivisione delle quattro sottoreti](https://github.com/alicefgl/Subnetting4), ed aver quindi definito i range di indirizzi ip disponibili per ogni sottorete, si passa alla configurazione del DHCP server.
Al DHCP, DNS e HTTP server si assegnano manualmente degli indirizzi ip che, come nel caso del router, possono essere i massimi o i minimi disponibili.
In questo caso, siccome ogni sottorete varia ad intervalli di 64 indirizzi, l'ip del router della prima rete è stato impostato a 172.130.20.62, quello del DHCP 172.130.20.61, quello del DNS 172.130.20.60, mentre quello dell'HTTP server 172.130.20.59 .
Il range di ip che il DHCP server può fornire ai dispositivi rimanenti (per quanto riguarda la prima sottorete) è quindi compreso tra 172.130.20.1 e 172.130.20.58 .
Quando si configura il DHCP server come tale è necessario specificare il gateway ed il DNS server relativo ai dispositivi di una determinata sottorete, nel caso della prima di questo esercizio si impostano i valori sopra riportati.

- impostazione DNS Server
Per impostare il DNS Server si inizia la simulazione e si installa l'applicazione "DNS Server".
Dopo aver avviato l'applicazione appena installata si imposta il nome del dominio (in questo caso "SIRulez") e l'indirizzo ip relativo all'HTTP Server, che verrà impostato in seguito. Dopo aver definito la entry, premendo su "Start" si da inizio al servizio.

- impostazione HTTP Server
Per impostare l'HTTP Server si inizia la simulazione e si installa l'applicazione "HTTP Server".
Se è stato impostato correttamente il DNS Server, per far iniziare il servizio HTTP basterà avviare l'applicazione appena installata e premere "Start".
