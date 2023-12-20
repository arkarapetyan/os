#Խնդիր 1

str="Hi"
echo $str2 #կտպի դատարկ տող, քանի որ չկա str2 անունով փոփոխական
echo ${str}2 #կտպի Hi2
 
#Խնդիր 2

echo $(((5**2)*4/10))

#Խնդիր 3

echo "The balance for user $USER is: $5.00" #կտպի The balance for user Student is: .00 քանի որ $ նշանից առաջ դրված չեր \
echo "The balance for user $USER is: \$5.00" #կտպի The balance for user Student is: $5.00

#Խնդիր 4

echo '$USER $((2 + 2)) $(ls)' #կտպի $USER $((2 + 2)) $(ls) ինչը սխալ է
echo "$USER $((2 + 2)) $(ls)" #կտպի Student 4 և դիրեկտորիայի պարունակությունը

#Խնդիր 5

#!/bin/bash
cat << EOF
${PWD}
$(ls -1 *.txt | wc -l)
EOF

#Խնդիր 6

#!/bin/bash
sum()
{
    echo $(($1 + $2))
}
sum 6 4

#Խնդիր 7

#!/bin/bash

dir_count()
{
	echo $(ls $1 -1 | wc -l)
}

dir_count ${PWD}

#Խնդիր 8

#!/bin/bash

touch a.txt

get_file_permission()
{
	p=$(($(stat -c %a $1) / 100)) 

	if [ $p -eq 0 ];
	then
		echo "No permissions";
	elif [ $p -eq 1 ];
	then
		echo "Only Execute Permission";
	elif [ $p -eq 2 ];
	then
		echo "Only Write Permission";
	elif [ $p -eq 3 ];
	then
		echo "Execute And Write Permission";
	elif [ $p -eq 4 ];
	then
		echo "Only Read Permission";
	elif [ $p -eq 5 ];
	then
		echo "Execute and Read Permission";
	elif [ $p -eq 6 ];
	then
		echo "Write And Read Permission";
	elif [ $p -eq 7 ];
	then
		echo "Execute, Write And Read Permission";
	fi

}

get_file_permission $"a.txt"

#Խնդիր 9

#!/bin/bash

IsEven()
{
	if [ $(($1 % 2)) -eq 0 ];
	then
		echo "$1 is even";
	else
		echo "$1 is odd";
	fi
}

IsEven 7
IsEven 4

#Խնդիր 10

#!/bin/bash

IsEven()
{
	if [ $(($1 % 2)) -eq 0 ];
	then
		echo "$1 is even";
	else
		echo "$1 is odd";
	fi
}

IsEven 7
IsEven 4