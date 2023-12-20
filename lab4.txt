#խնդիր 1

touch file.txt
chmod 744 file.txt

#Խնդիր 2

chmod a+x file.txt

#Խնդիր 3

chmod go-x file.txt

#Խնդիր 4

chmod a-rwx  file.txt #սիմվոլային
chmod u+rw file.txt

chmod 600 file.txt #8-ական

#Խնդիր 5

mkdir dir
chmod 666 dir
touch dir/file.txt

#Խնդիր 6

touch dir/file1.txt
touch dir/file2.txt
chmod -R 766 dir

#Խնդիր 7

umask 0026

#Խնդիր 8

umask 0066
umask 0022

#Խնդիր 9

#ls_file.sh սկրիպտը
#!/bin/bash
ls -p | grep -v '/'

#
chmod 344 ls_file.sh
chmod u+rwx ls_file.sh

#Խնդիր 10

mkdir bin
mv ls_file.sh ~/bin/
export PATH=~/bin:"$PATH"