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