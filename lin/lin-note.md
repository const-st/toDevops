create 10 numeric file
touch file{1..10}.txt 
in cicle
for i in {1..10}; do touch "file$i.txt"; done
del
rm file{1..5}.txt
for i in {6..10}; do rm "file$i.txt"; done


