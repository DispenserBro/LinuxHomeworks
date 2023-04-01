```shell
 disbro@Dis-Bro  ~  mkdir students mentors; touch students/students_list.txt mentors/mentors_list.txt
 disbro@Dis-Bro  ~  vim students/students_list.txt
 disbro@Dis-Bro  ~  # Изменения в mentors/mentors_list.txt внес через вторую вкладку vim
 disbro@Dis-Bro  ~  tree -L 2
.
├── Downloads
├── main
│   ├── env
│   ├── newfile.txt
│   ├── new.py
│   └── sqrt_example.py
├── mentors
│   └── mentors_list.txt
└── students
    └── students_list.txt

5 directories, 5 files
 disbro@Dis-Bro  ~  mv mentors/mentors_list.txt students/
 disbro@Dis-Bro  ~  tree -L 2
.
├── Downloads
├── main
│   ├── env
│   ├── newfile.txt
│   ├── new.py
│   └── sqrt_example.py
├── mentors
└── students
    ├── mentors_list.txt
    └── students_list.txt

5 directories, 5 files
 disbro@Dis-Bro  ~  rm -r mentors/
 disbro@Dis-Bro  ~  mv students/ students_and_mentors/
 disbro@Dis-Bro  ~  tree -L 2
.
├── Downloads
├── main
│   ├── env
│   ├── newfile.txt
│   ├── new.py
│   └── sqrt_example.py
└── students_and_mentors
    ├── mentors_list.txt
    └── students_list.txt

4 directories, 5 files
 disbro@Dis-Bro  ~  rm -r students_and_mentors/
 disbro@Dis-Bro  ~  tree -L 2
.
├── Downloads
└── main
    ├── env
    ├── newfile.txt
    ├── new.py
    └── sqrt_example.py

3 directories, 3 files
```
Доп. задания:

```shell
 disbro@Dis-Bro  ~  tree -L 2
.
├── Downloads
└── main
    ├── env
    ├── newfile.txt
    ├── new.py
    └── sqrt_example.py

3 directories, 3 files
 disbro@Dis-Bro  ~  vim file1
 disbro@Dis-Bro  ~  cp file1 file2
 disbro@Dis-Bro  ~  ln -s file1 file3
 disbro@Dis-Bro  ~  ln file1 file4
total 20
46409 drwxr-xr-x 2 disbro disbro 4096 мар 26 21:43 Downloads
39595 -rw-r--r-- 2 disbro disbro   24 апр  1 23:15 file1
40061 -rw-r--r-- 1 disbro disbro   24 апр  1 23:16 file2
50595 lrwxrwxrwx 1 disbro disbro    5 апр  1 23:16 file3 -> file1
39595 -rw-r--r-- 2 disbro disbro   24 апр  1 23:15 file4
 1819 drwxr-xr-x 3 disbro disbro 4096 мар 31 16:56 main
 disbro@Dis-Bro  ~  rm file1
 disbro@Dis-Bro  ~  ls -li
total 16
46409 drwxr-xr-x 2 disbro disbro 4096 мар 26 21:43 Downloads
40061 -rw-r--r-- 1 disbro disbro   24 апр  1 23:16 file2
50595 lrwxrwxrwx 1 disbro disbro    5 апр  1 23:16 file3 -> file1
39595 -rw-r--r-- 1 disbro disbro   24 апр  1 23:15 file4
 1819 drwxr-xr-x 3 disbro disbro 4096 мар 31 16:56 main
 disbro@Dis-Bro  ~  cat file*
some comtent in file...
cat: file3: No such file or directory
some comtent in file...
 ✘  disbro@Dis-Bro  ~  # был вывод содержимого из 2, 3 и 4 файлов по порядку
 ✘  disbro@Dis-Bro  ~  mv file2 text2
 disbro@Dis-Bro  ~  mv file3 test
 disbro@Dis-Bro  ~  mv file4 text4
 disbro@Dis-Bro  ~  ls -li
total 16
46409 drwxr-xr-x 2 disbro disbro 4096 мар 26 21:43 Downloads
 1819 drwxr-xr-x 3 disbro disbro 4096 мар 31 16:56 main
50595 lrwxrwxrwx 1 disbro disbro    5 апр  1 23:16 test -> file1
40061 -rw-r--r-- 1 disbro disbro   24 апр  1 23:16 text2
39595 -rw-r--r-- 1 disbro disbro   24 апр  1 23:15 text4
 disbro@Dis-Bro  ~  mv text? main/; mv test main/
 disbro@Dis-Bro  ~  tree -L 2
.
├── Downloads
└── main
    ├── env
    ├── newfile.txt
    ├── new.py
    ├── sqrt_example.py
    ├── test -> file1
    ├── text2
    └── text4

3 directories, 6 files
```