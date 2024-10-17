In questo script si è semplicemente verificato che nella variabile “$” durante l’ esecuzione di un comando viene inserito un numero, che varia in base alla riuscita nell’ esecuzione del comando. Nel primo caso il comando va a buon fine e alla variabile “$” viene sostituito il numero precedente con il numero 0. 
Nel secondo caso viene scritta una serie di caratteri che non corrispondono a nessun comando (Command not found), per cui viene inserito il numero 127. 
Infine nell ultimo caso, dopo il comando exit verrà inserito il numero 113.
