# Lab 5 Using find command

**Option 1: '-type'**
---
This option is used to specify the type of files to search for.
>
(f = regular files, d = directories, l = symbolic links)
>
Example 1: -type d
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
 **Option 2: 'mtime' option**
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
>
This option is used to search for files and directories that match a specific name.
>
Example 1:
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
 
