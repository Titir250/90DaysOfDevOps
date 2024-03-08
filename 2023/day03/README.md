Day 3 Task: Basic Linux Commands

Task: What is the linux command to

1. To view what's written in a file.-->cat <file_name>
2. To change the access permissions of files.-->chmod
3. To check which commands you have run till now.-->history
4. To remove a directory/ Folder.--> rm -rf need to use -r recursive option for directories.
5. To create a fruits.txt file and to view the content.-->

touch fruits.txt
cat fruits.txt

7. Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.

Open vi editor press i then esc+:wq

9. To Show only top three fruits from the file.

cat fruits.txt | head -3

10. To Show only bottom three fruits from the file.

cat fruits.txt | tail -3

12. To create another file Colors.txt and to view the content.

touch Colors.txt

14. Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.

Open vi editor press i then esc+:wq

16. To find the difference between fruits.txt and Colors.txt file.

diff fruits.txt Colors.txt

Reference: https://www.linkedin.com/pulse/linux-commands-devops-used-day-to-day-activit-chetan-/

[← Previous Day](../day02/README.md) | [Next Day →](../day04/README.md)
