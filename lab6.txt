#Խնդիր 1

#!/bin/bash

echo -n "Enter Number: "
read N

if [[ "$N" =~ ^-?[0-9]+$ ]];
then
        if [[ $N -gt  0 ]]; #կամ (( $N > 0 ));
        then
                echo "The Number is positive";
        elif [[ $N -lt 0 ]]; #կամ (( $N < 0 ));
        then
                echo "The Number is negative";
        else
                echo "The Number is zero";
        fi
else
        echo "Invalid Input. Not a Number: $N"
        exit 1
fi

#Խնդիր 2

Նայել վերևի լուծման մեկնաբանությունները

#Խնդիր 3

#!/bin/bash

echo -n "Enter Number: "
read N

if [[ "$N" =~ ^-?[0-9]+$ ]];
then
        if (( ($N%2==0)&&(N%3==0)&&(N%5==0) ))
        then
                echo "Is Multiple";
        else
                echo "Is Not Multiple";
        fi
else
        echo "Invalid Input. Not a Number: $N"
        exit 1
fi

#Խնդիր 4

#!/bin/bash

echo -n "Enter Number: "
read N

if [[ "$N" =~ ^-?[0-9]+$ ]];
then
        if (( ($N%2==0)&&((N%3==0)||(N%5==0)) ))
        then
                echo "Is Multiple";
        else
                echo "Is Not Multiple";
        fi
else
        echo "Invalid Input. Not a Number: $N"
        exit 1
fi

#Խնդիր 5

touch file | chmod u+x file
#կամ
touch file && chmod u+x file

#Խնդիր 6

[ -d dir ] || mkdir dir.

#Խնդիր 7

#!/bin/bash

invalid_input () 
{
 echo "Invalid input: $N" >&2
 exit 1
}

echo -n "Enter Number: "
read N

[[ -z $N ]] && invalid_input
[[ !("$N" =~ ^-?[0-9]+$) ]] && invalid_input


if (( ($N >= 0) && ($N <= 100) ));
then
        echo "In Range";
else
        echo "Not in Range";
fi


#Խնդիր 8

echo -n "Enter Word: "
read -s word

if [[ "$word" == "Secret" ]];
then
      echo -e "\nThe word is Secret";
else
      echo -e "\nThe word is not Secret";  
fi

#Խնդիր 9

#!/bin/bash

invalid_input () 
{
 echo "Invalid input: $N" >&2
 exit 1
}

echo -n "Enter File Name: "
read filename

[[ -z $filename ]] && invalid_input
[[ !("$filename" =~ ^[A-Za-z0-9._-]+$) ]] && invalid_input


if [[ -e $filename ]];
then
        echo "File Exists";
else
        echo "Flie Does not Exist. Creating File: $filename ";
        touch $filename;
fi

#Խնդիր 10

#!/bin/bash

invalid_input () 
{
 echo "Invalid input: $1" >&2
 exit 1
}

echo -n "Enter Number1 Operator Number2: "
read m o n

([[ -z $m ]] || [[ -z $n ]] || [[ -z $o ]] ) && (echo "Too Few Arguments, Expected 3" | exit 1)
[[ "$n" == *[[:blank:]]* ]] && (echo "Too Much Arguments, Expected 3" | exit 1)
[[ "$m" =~ ^-?[0-9]+$ ]] || invalid_input $m
[[ "$n" =~ ^-?[0-9]+$ ]] || invalid_input $n

if [[ $o == "+" ]];
then
        echo $(( $m + $n ));
elif [[ $o == "*" ]];
then
        echo $(( $m * $n ));
elif [[ $o == "/" ]];
then
        echo $(( $m / $n ));
elif [[ $o == "**" ]];
then
        echo $(( $m ** $n ));
else
        invalid_input $o 
        exit 1
fi