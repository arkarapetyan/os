#Խնդիր 1

mkdir lab1
touch ./lab1/file.txt
touch ./lab1/file1.txt
touch ./lab1/file2.txt
touch ./lab1/file3.txt
mkdir ./lab1/dir1
mkdir ./lab1/dir2

#Խնդիր 2

cd lab1
ls *.txt #տպում է դիրեկտորիայի բոլոր տեքստային ֆայլերը
ls * .txt #տպում է բոլոր ֆայլերը դիրեկտորիայում և տալիս սխալ ls: cannot access '.txt': No such file or directory

#Խնդիր 3

ls f???.txt

#Խնդիր 4

ls file[[:digit:]].txt

#Խնդիր 5

ls *[[:lower:]12].txt

#Խնդիր 6

cp /etc/passwd ./

#Խնդիր 7

mv passwd new
mv new ./dir1
mv ./dir1/new ./dir2

#Խնդիր 8

mv dir2 dir3
mv dir3 ./dir1

#Խնդիր 9

mv dir1/dir3/new ./

#Խնդիր 10

cd ../
rm -r lab1

