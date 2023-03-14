# Ruben A Gonzalez 
# Lab 5 Using *find* command (from lab 3 report)

**Option 1: '-type'**
---
This option is used to specify the type of files to search for.
>
(f = regular files, d = directories, l = symbolic links)
>
Example 1: -type d
>
For this example I typed the command < find ./written_2/ -type d > which
allowed me to find the directories in the written_2 directory.
```
[cs15lwi23agr@ieng6-203]:docsearch:510$ find ./written_2/ -type d
./written_2/
./written_2/non-fiction
./written_2/non-fiction/OUP
./written_2/non-fiction/OUP/Abernathy
./written_2/non-fiction/OUP/Berk
./written_2/non-fiction/OUP/Castro
./written_2/non-fiction/OUP/Fletcher
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Rybczynski
./written_2/travel_guides
./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz2
```
 Example 2: -type f
 >
 For this example I typed out < find written_2/ -type f > to find all
 the regular files in the directory written_2/
 ```
 [cs15lwi23agr@ieng6-203]:docsearch:516$ find written_2/ -type f
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch7.txt
 ```
 ---
 **Option 2: '-mtime' option**
 ---
 This option is used to search for files that were modified in the last (x) days.
 >
 Example 1: -mtime -7
 >
 ```
 [cs15lwi23agr@ieng6-203]:docsearch:518$ find -mtime -7
.
./.git
./.git/info
./.git/info/exclude
./.git/hooks
./.git/hooks/commit-msg.sample
./.git/hooks/prepare-commit-msg.sample
./.git/hooks/update.sample
 ```

Example 2: -mtime +30
>
For this example I used the command < find > on a old file I used a while back
called StringServer and typed out the command < find ./StringServer -type f -mtime +30 >
To get all the files that were updated 30 days out. You can do (+) any amount of days.
```[cs15lwi23agr@ieng6-203]:~:583$ find ./StringServer -type f -mtime +30
./StringServer/wavelet/.git/info/exclude
./StringServer/wavelet/.git/hooks/commit-msg.sample
./StringServer/wavelet/.git/hooks/prepare-commit-msg.sample
./StringServer/wavelet/.git/hooks/update.sample
./StringServer/wavelet/.git/hooks/pre-rebase.sample
./StringServer/wavelet/.git/hooks/pre-merge-commit.sample
./StringServer/wavelet/.git/hooks/push-to-checkout.sample
./StringServer/wavelet/.git/hooks/pre-push.sample
```
---
**Option 3: '-name'**
---
This option is used to search for files and directories that match a specific name.
Example 1:
>
For this example I typed out < find ./written_2/ -name '*.txt' >* which printed
all the files with the name ".txt"
```
[cs15lwi23agr@ieng6-203]:docsearch:533$ find ./written_2 -name '*.txt'
./written_2/non-fiction/OUP/Abernathy/ch1.txt
./written_2/non-fiction/OUP/Abernathy/ch14.txt
./written_2/non-fiction/OUP/Abernathy/ch15.txt
./written_2/non-fiction/OUP/Abernathy/ch2.txt
./written_2/non-fiction/OUP/Abernathy/ch3.txt
./written_2/non-fiction/OUP/Abernathy/ch6.txt
./written_2/non-fiction/OUP/Abernathy/ch7.txt
./written_2/non-fiction/OUP/Abernathy/ch8.txt
./written_2/non-fiction/OUP/Abernathy/ch9.txt
```
Example 2:
```
[cs15lwi23agr@ieng6-203]:docsearch:595$ find ./written_2 -name "*" -type d
./written_2
./written_2/non-fiction
./written_2/non-fiction/OUP
./written_2/non-fiction/OUP/Abernathy
./written_2/non-fiction/OUP/Berk
./written_2/non-fiction/OUP/Castro
./written_2/non-fiction/OUP/Fletcher
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Rybczynski
./written_2/travel_guides
./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz2
```
---
**Option 4: '/tmp'**
---
This option finds all the hidden files.
```
[cs15lwi23agr@ieng6-203]:docsearch:656$ find /tmp -type f -name ".*"
find: '/tmp/cs15lwi23aom-pulse': Permission denied
find: '/tmp/ee15wi23ij-pulse': Permission denied
find: '/tmp/cs15lwi23ta14-pulse': Permission denied
```
**Option 5: '-iname'**
---
This command searches for all files in the searched directory of the "docsearch" repository that start with the letters "file".
>
---
**Example 1:**
---
```
[cs15lwi23agr@ieng6-203]:docsearch:525$ find written_2/ -iname *.TXT
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
```
>
Example 2:
---
With '-iname'
```
[cs15lwi23agr@ieng6-203]:StringServer:532$ find wavelet/ -iname *.java
wavelet/NumberServer.java
wavelet/Server.java
```
Without '-iname'
```[cs15lwi23agr@ieng6-203]:StringServer:537$ find wavelet/ *.java
wavelet/
wavelet/.git
wavelet/.git/info
wavelet/.git/info/exclude
wavelet/.git/hooks
wavelet/.git/hooks/commit-msg.sample
...
```
---
Sources: 
1. ChatGPT for examples
2. [find command in Linux with examples](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)
 
