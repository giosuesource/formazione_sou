Lo script 32.7 parte inizializzando a 1 la variabile che indica un intervallo di tempo breve e a 10 la variabile che indica un intervallo di tempo lungo. Successivamente inizia un ciclo che permette di scrivere sulla stessa riga (-n) una serie di “.” finché non viene inviato un segnale SIGUSR1. Ad ogni “.” Viene eseguito un intervallo del valore specificato nella variabile inizializzata (in questo caso 1 ), per cui l’ output verrà stampato con cadenza 1 secondo. 
Dopo il ciclo viene inizializzata la variabile PID con il valore del PID dell’ ultimo processo eseguito in background ($!). Viene poi effettuato un “trap” che permette di stampare il PID dell’ ultimo processo, di mandare un segnale di kill e di fare un comando wait utilizzando il valore del $PID.
Per ultimo, viene eseguito un comando di sleep utilizzando come parametro la variabile “long_interval” inizializzata all’ inizio e  viene poi killato il processo utilizzando un segnale USR1