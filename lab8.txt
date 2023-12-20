#Խնդիր 1

#!/bin/bash 

while true;
do
    echo "Please Select [1-3] or 0 to Quit"
    read -p "Enter selection [0-3] > "
    case $REPLY in
        0)
            echo "Program terminated."
            exit

            ;;
        1)
            ls -1
            ;;
        2)
            ls -1 *.txt | wc -l
            ;;
        3)
            pwd
            ;;
        *)
            echo "Invalid Input" >&2
            ;;
    esac
done

#Խնդիր 2

read -p "Enter Month: "

case "$REPLY" in
    "January" | "March" | "May" | "July" | "August" | "October" | "December")
        echo "31"
        ;;
    "April" | "June" | "September" | "November")
        echo "30"
        ;;
    "February")
	    echo "28 or 29"
	    ;;
    *)
        echo "Invalid Input" >&2
        exit 1
        ;;
esac


#Խնդիր 3

#!/bin/bash

invalid_input () 
{
    echo "Invalid input: $1" >&2
    exit 1
}

while true; do
	echo -n "Enter Number1 Operator Number2: "
    read m o n

    ([[ -z $m ]] || [[ -z $n ]] || [[ -z $o ]] ) && (echo "Too Few Arguments, Expected 3" | exit 1)
    [[ "$n" == *[[:blank:]]* ]] && (echo "Too Much Arguments, Expected 3" | exit 1)
    [[ "$m" =~ ^-?[0-9]+$ ]] || invalid_input $m
    [[ "$n" =~ ^-?[0-9]+$ ]] || invalid_input $n

	case $o in
	"+")
		result=$(( $m + $n ))
		;;
	"-")
		result=$(( $m - $n ))
		;;
	"*")
		result=$(( $m * $n ))
		;;
	"/")
		result=$(( $m / $n ))
		;;
	"**")
		result=$(( $m ** $n ))
		;;
	*)
		invalid_input $o 
		;;
	esac

done

#Խնդիր 4

#!/bin/bash

file = "$1"

if [[ -e $file ]]; 
    then
        echo "File Exists"
        if [[ -r $file ]];
        then
            echo "File has read permission";
        else
            echo "File does not have read permission";
        fi
        done
    else
        echo "File doe not Exist.";
fi

#Խնդիր 5

#!/bin/bash

[ -e $1 ] || (echo "File $1 does not exist" | exit 1)
[ -r $1 ] || (echo "No read permission on file $1" | exit 1)

cat "$1" >"$2"

#Խնդիր 6

#!/bin/bash

invalid_input () 
{
 echo "Invalid input: $1" >&2
 exit 1
}

[[ -z $1 ]] && invalid_input $1
[[ "$1" =~ ^-?[0-9]+$ ]] || invalid_input $1

[[ -z $2 ]] && invalid_input $2
[[ "$2" =~ ^-?[0-9]+$ ]] || invalid_input $2

echo $(( $1 + $2 ))

#Խնդիր 7

#!/bin/bash

while [[ $# -gt 0 ]]; 
do
    echo $1
    shift
done

#Խնդիր 8

#!/bin/bash

for a in "$@";
do
    echo "$a"
done

#Խնդիր 9

#!/bin/bash

invalid_input () 
{
 echo "Invalid input: $1" >&2
 exit 1
}

sum=0

while [[ $# -gt 0 ]]; 
do
    [[ -z $1 ]] && invalid_input $1
    [[ "$1" =~ ^-?[0-9]+$ ]] || invalid_input $1

    sum=$(( $sum + $1 ))
    shift
done

echo $sum

#Խնդիր 10

#!/bin/bash

invalid_input () 
{
 echo "Invalid input: $1" >&2
 exit 1
}

count=0

while [[ $# -gt 0 ]]; 
do
    [[ -z $1 ]] && invalid_input $1
    [[ "$1" =~ ^-?[0-9]+$ ]] || invalid_input $1
    
    if [ $(( $1 % 2 )) -eq 0 ]; 
    then
        count=$(( $count + 1 ))
    fi

    shift
done

echo $count