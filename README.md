# configs


cpu2

#!/bin/sh

grep 'cpu ' /proc/stat | awk '{usage=($2+$4)*100/($2+$4+$5)} END {print usage}' | cut -c 1,2,3 | awk '{print $1"%"}'


temperature2

#!/bin/sh

sensors | awk '/temp1/ {print $2}' | cut -c 2,3 | awk '{print $0"°C"}'


fan

#!/bin/sh

sensors | awk '/fan/ {print $2}' 
