#Խնդիր 1

cat > file1 #կարդում է STDIN–ում տվյալները և վերահասցեավորում է այն file1 ֆայլի մեջ
cat file1 #կարդում և արտածում է file1 ֆայլի պարունակությունը
cat < file1 #կարդում է file1 ֆայլի պարունակությունը և այն վերահասցեավորում STDOUT-ում

#Խնդիր 2

cat > file1.txt #մուտքագրվում է "Hello, World!"
cat > file2.txt #մուտքագրվում է "Hello, file2!"
cat > file3.txt #մուտքագրվում է "Hello, file3!"
cat file1.txt file2.txt file3.txt > final.txt
cat < final.txt 
#արտածվում է 
Hello, World! 
Hello, file2! 
Hello, file3!

#Խնդիր 3

ls -1 *.txt | wc -l

#Խնդիր 4
 
sort file1.txt file2.txt file3.txt > s.txt

#Խնդիր 5

ls -lS | head -n 15

#Խնդիր 6

ls -l > ls.txt

#Խնդիր 7

echo "secret text" | tr 'A-Za-z' 'N-ZA-Mn-za-m' 
echo "secret text" | tr 'A-Za-z' 'N-ZA-Mn-za-m' | tr 'N-ZA-Mn-za-m' 'A-Za-z' #գաղտնագրում և վերծանում

#Խնդիր 8

echo "Student's home directory is {home_dir}." | cat > home.txt  
sed 's/{home_dir}/\/home\/student/' home.txt > home_m.txt #կատարել փոփոխությունը
mv home_m.txt home.txt #պահել փոփոխությունը օրիգինալ ֆայլում

#Խնդիր 9

cat > file4.txt 
#ներմուծվում է
This is the first row
This is the second row
This is the third row
This is the fourth row
This is the fifth row
sed -n '2,4p' file4.txt
#արտածվում է
This is the second row
This is the third row
This is the fourth row

#Խնդիր 10

sed -n '2,4d' file4.txt > file4_m.txt
mv file4_m.txt file4.txt #Փոփոխությունը պահել օրիգինալ ֆայլում

