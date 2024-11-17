
# Descrizione dello Script 37.5
 
declare -A address
 
address[Charles]="414 W. 10th Ave., Baltimore, MD 21236"
address[John]="202 E. 3rd St., New York, NY 10009"
address[Wilma]="1854 Vermont Ave, Los Angeles, CA 90023"
 
 
echo "Charles's address is ${address[Charles]}."

echo "Wilma's address is ${address[Wilma]}."

echo "John's address is ${address[John]}."

 
echo
 
echo "${!address[*]}"   # The array indices ...
