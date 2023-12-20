#Խնդիր 1

#!/bin/bash

count=0

while [ $count -le 20 ];
do
    if [ $(( $count % 2 )) -eq 0 ]; 
    then
        echo $count
    fi

    count=$(( $count + 1))
done

#Խնդիր 2

#!/bin/bash

count=0

until [ $count -gt 20 ];
do
    if [ $(( $count % 2 )) -eq 0 ]; 
    then
        echo $count
    fi

    count=$(( $count + 1))
done


#Խնդիր 3

#!/bin/bash

count=0

while true;
do
    sq=$(( $count ** 2 ))
    if [[ sq -le 1000 ]]; 
    then
        echo $sq
    else
        break
    fi

    count=$(( $count + 1 ))
done

#Խնդիր 4

#!/bin/bash

for (( i=0; i<=20; i=i+1 )); 
do 
    if [ $(( $i % 2 )) -eq 0 ]; 
    then
        echo $i
    fi
done

#Խնդիր 5

#!/bin/bash

while true;
do
    echo "Enter an integer number, or enter q to quit: "
    read n
 
    if [[ "$n" =~ ^-?[0-9]+$ ]]; 
    then
        echo $(( $n * 2 ));
    elif [[ "$n" == "q" ]]; 
    then 
        exit 1;
    else
        echo "Invalid Input: $n "
    fi

done

#Խնդիր 6

#!/bin/bash

ls -1 *.txt > t_files.txt

count=0

for file in $( ls -1 *.txt );
do
    echo "$count $file";
    count=$(( $count + 1 ))
done

#Խնդիր 7

#!/bin/bash

for (( i=0; i<=30; i=i+1 )); 
do 
    if [ $(( $i % 3 )) -eq 0 ]; 
    then
        echo $i
    fi
done

#Խնդիր 8

#!/bin/bash

for file in $( ls *.txt ); 
do 
    echo $file
done

#Խնդիր 9

#!/bin/bash

for i; 
do
    if [[ -r $i ]]; 
    then
        min_len=0
        for j in $(strings $i); 
        do
            len=$(echo $j | wc -c)
            if (( len < max_len )); 
            then
            min_len=$len
            fi
        done
    echo "$i: ($min_len characters)"
    fi
done


#Խնդիր 10

#!/bin/bash

for i; 
do
    if [[ -e $i ]]; 
    then
        echo "File Exists"
        if [[ -r $i ]];
        then
            echo "File has read permission";
        else
            echo "File does not have read permission";
        fi
        done
    else
        echo "File doe not Exist.";
    fi
done