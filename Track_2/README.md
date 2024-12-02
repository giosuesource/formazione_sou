
# Step. 1
Lo scopo di questo esercizio è quello di configurare un Jenkins Master e un Jenkins Slave, utilizzando Vagrant per creare la VM e Ansible per tirare su i 2 containers. Il container Agent si dovrà collegare al container Master per poter svolgere le operazioni descritte negli step successivi.

Nel Vagrantfile è stata configurata la VirtualMachine "macchina", avente Rocky Linux 9 come sistema operativo. Sono state configurate le porte 8080 e 50000, le quali ci serviranno successivamente.

All' interno del playbook (quindi sulla VM) sono stati scaricati Python, Java, Docker e altre dipendenze, che ci serviranno per creare i 2 container richiesti per lo svolgimento dell' esercizio.

Difatti dopo aver creato un Docker Network e aver "pullato" l' immagine docker "jenkins/jenkins:lts" per il Master (ContainerM) e l' immagine docker jenkins/inbound-agent per l' Agent (ContainerS), siamo passati alla creazione dei containers.
Dopo aver utiizzato il comando "vagrant up" per tirare su Macchina Virtuale e containers, abbiamo verificato la corretta creazione sfruttando il comando "ping". 

Dopo esserci assicurati che non ci fossero problemi, abbiamo effettuato una connessione SSH sfruttando il comando "Vagrant SSH", per poi utilizzare il comando "sudo docker exec ContainerM cat /var/jenkins_home/secrets/initialAdminPassword". Grazie a questo comando ci siamo ricavati la password di Login che ci servirà per entrare sul sito di Jenkins.

Difatti dopo esserci copiati la password, navigando sul browser del nostro pc Host, siamo andati sulla pagina web di Jenkins all' indirizzo "http://localhost:8080". Dopo aver effettuato il login utilizzando come username "admin" e la suddetta password, abbiamo seguito il percorso Dashboard/nodi/ContainerS per ricavarci un'altra password, quella che ci avrebbe permesso di collegare Jenkins Slave a Jenkins Master.

Dopo aver copiato quest' ultima password, siamo andati ad intervenire sul playbook, andandola ad inserire nello spazio dedicato alla configurazione del Container Slave. 

Dopo aver salvato le nuove modifiche, abbiamo utilizzato il comando "vagrant provision macchina" per fare in modo che le stesse venissero applicate e si effettuasse il collegamento.

Infine, direttamente dall' interfaccia web di Jenkins, siamo andati ad aggiungere il nodo "ContainerS" dal percorso Dashboard/Nodi/nuovo nodo. 
Dopo aver salvato le modifiche apportate, abbiamo constatato che lo Slave fosse correttamente collegato a Master.