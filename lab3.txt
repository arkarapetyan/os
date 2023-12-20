#Խնդիր 1

ls /etc/ | grep .[[:digit:]].

#Խնդիր 2

cat > file.txt 
grep -E .{3}lo$ file.txt


#Խնդիր 3

cat >  dirlist-bin.txt
cat > dirlist-sbin.txt


grep -h '[A-Z]' dirlist*.txt #գտնում է բոլոր այն տողերը, որոնցում կա մեծատառ
grep -h '[-AZ]' dirlist*.txt ??
grep -h '^[A-Z]' dirlist*.txt #գտնում է բոլոր մեծատառերով սկսվող տողերը
grep -h '[^A-Z]' dirlist*.txt ??

#Խնդիր 4

grep -h -E '^bz|zip' dirlist*.txt

#Խնդիր 5

grep -Eh '^(bz|gz|zip)' dirlist*.txt #գտնում է բոլոր bz,gz կամ zip–ով սկսվող տողերը՝ դրանք խմբավորելով
grep -Eh '^bz|gz|zip' dirlist*.txt #կատարում է նույնը՝ առանց խմբավորման

#Խնդիր 6

echo "test@test.com" | grep -E '^([[:alnum:]_+%-]+)@([[:alnum:].-]+)\.([[:alpha:]]{2,})$'

#Խնդիր 7

echo "192.168.0.1" | grep -E '^((2[0-5][0-5]|1[0-9][0-9]|[1-9][0-9]|[0-9])\.){3}(2[0-5][0-5]|1[0-9][0-9]|[1-9][0-9]|[0-9])$'

#Խնդիր 8

??

#Խնդիր 9

echo "01/02/1970" | sed -E "s/([0-9]{2})\/([0-9]{2})\/([0-9]{4})/\3-\2-\1/"

#Խնդիր 10

echo "0xx 12-34-56" | sed -E "s/(0[0-9x][0-9x]) ([0-9][0-9])-([0-9])([0-9])-([0-9][0-9])/\1 \2\3-\4\5/"
