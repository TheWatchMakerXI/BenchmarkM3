### Repository BenchmarkM3

#### Panoramica
Benvenuti nella repository BenchmarkM3. Questa repository contiene la documentazione e i file relativi a una serie di valutazioni delle vulnerabilità effettuate utilizzando Nessus su una macchina Kali Linux che prende di mira un'istanza di Metasploitable2.

#### Contenuti
1. **Scansione iniziale.pdf**: Report della scansione delle vulnerabilità iniziale.
2. **Descrizione remedetions.pdf**: Descrizione dettagliata dei passaggi di remediation intrapresi per risolvere le vulnerabilità identificate.
3. **Scansione finale.pdf**: Report della scansione delle vulnerabilità finale che mostra i risultati dopo la remediation.

#### Dettagli dell'Ambiente
- **Macchina di Scansione**: Kali Linux
  - **Indirizzo IP**: 192.168.50.100
- **Macchina di Destinazione**: Metasploitable2
  - **Indirizzo IP**: 192.168.50.101

#### Vulnerabilità Critiche Risolte
La scansione iniziale ha identificato sei vulnerabilità critiche sulla macchina di destinazione, che sono state successivamente risolte. Queste vulnerabilità e i relativi passaggi di remediation sono descritti di seguito:

1. **NFS Exported Share Information Disclosure**
   - **Problema**: Accesso non autorizzato alle directory condivise tramite NFS.
   - **Remediation**: Aggiornamento delle impostazioni NFS per limitare l'accesso, configurazione dei permessi corretti e aggiornamento delle regole di esportazione.

2. **Password del Server VNC 'password'**
   - **Problema**: Password del server VNC debole/predefinita.
   - **Remediation**: Cambio della password predefinita con una complessa utilizzando `sudo vncpasswd`.

3. **Iniezione di Richieste del Connettore AJP di Apache Tomcat (Ghostcat)**
   - **Problema**: Possibilità di iniezione di richieste tramite il connettore AJP.
   - **Remediation**: Disabilitazione del connettore AJP nel file `server.xml` e riavvio del servizio Tomcat.

4. **Rilevazione del Protocollo SSL Versione 2 e 3**
   - **Problema**: Uso di protocolli SSL obsoleti e insicuri.
   - **Remediation**: Configurazione delle regole del firewall per bloccare l'accesso alle porte associate a questi protocolli.

5. **Rilevazione della Backdoor Bind Shell**
   - **Problema**: Presenza di una backdoor bind shell.
   - **Remediation**: Identificazione e terminazione del processo associato, rimozione dell'eseguibile e assicurazione che la backdoor non possa riavviarsi.

6. **Debian OpenSSH/OpenSSL Package Random Number Generator Weakness**
   - **Problema**: Debolezza nel generatore di numeri casuali che compromette le chiavi crittografiche.
   - **Remediation**: Aggiornamento dei pacchetti OpenSSL, rimozione delle chiavi compromesse, rigenerazione delle chiavi SSH e riavvio dei servizi rilevanti.

#### Utilizzo
1. **Report della Scansione Iniziale**: Fornisce una linea di base delle vulnerabilità presenti prima di qualsiasi intervento di remediation.
2. **Descrizione della Remediation**: Delinea i passaggi intrapresi per risolvere ciascuna vulnerabilità critica.
3. **Report della Scansione Finale**: Verifica che le vulnerabilità critiche identificate nella scansione iniziale siano state risolte con successo.


Seguendo questo modello di README, gli utenti e i collaboratori possono facilmente comprendere l'ambito del progetto, le vulnerabilità affrontate e la struttura della repository.
