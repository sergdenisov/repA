1) git config --global user.name "Sergey Denisov"
2) git config --global user.email "sergeant.wssa@gmail.com"
3) mkdir git
4) cd git
5) mkdir repA
6) cd repA
7) git init
8) echo > fileA.txt
9) echo > fileB.txt
10) git add .
11) git commit -m "1st commit with some files (file A, file B)"
12) git checkout -b branch1
13) cd ..
14) git clone -b branch1 repA repB
15) cd repB
16) echo > fileC.txt
17) git add fileC.txt
18) git commit -m "2nd commit containing new file (file C)"
19) cd ../repA
20) git checkout master
21) cd ../repB
22) git push origin branch1
23) cd ../repA
24) git checkout branch1
25) open -a TextEdit fileC.txt # (modifying line#1 of file C to "line#1A")
26) git commit -a -m "3rd commit with modified line#1 of file C"
27) cd ../repB
28) open -a TextEdit fileC.txt # (modifying line#1 of file C to "line#1B”)
29) git commit -a -m "4th commit with modified line#1 of file C"
30) git fetch origin
31) git merge origin/branch1
32) git checkout --theirs fileC.txt
33) git add fileC.txt
34) git commit -m "5rd commit with resolving conflict using theirs file"
35) cd ../repA
36) git remote add origin ../repB
37) git fetch origin
38) git merge origin/branch1
39) git remote rm origin
40) git remote add origin git@github.com:sergdenisov/repA.git
41) git push --all origin
42) cd ../repB
43) git remote rm origin
44) git remote add origin git@github.com:sergdenisov/repB.git
45) git push --all origin
