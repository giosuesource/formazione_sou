In questo script inizialmente mi sposto nella cartella /var/log, che è la cartella contenente i log di sistema. Successivamente elimino il contenuto dei files "messages" e "wtmp" sfruttando la directory /dev/null, infatti viene redirezionato il suo contenuto in entrambi i files, permettendo di effettuare una "pulizia". Infine viene effettuata una stampa a video con il comando "Echo", così da avvertire l' utente dell' avvenuta operazione.