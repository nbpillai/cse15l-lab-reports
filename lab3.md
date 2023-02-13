# Lab Report 3
Nitya Pillai | CSE 15L Thursday 10 am B270

## the ```find``` command 

[Source Link](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)

### 1. find -newer file
This command returns a list of all the files that were created or edited after the specified file. It could be useful if we wanted to know files that were recently edited or created with reference to a specific file.

#### Example #1

The command below finds all files in the berlitz1 directory that were created or modified before WhatToDublin.txt. 

Command: ``` find written_2/travel_guides/berlitz1 -newer written_2/travel_guides/berlitz1/WhatToDublin.txt```

Output: 
```
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz1/WhatToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhatToIbiza.txt
written_2/travel_guides/berlitz1/WhatToHawaii.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhatToMadeira.txt
written_2/travel_guides/berlitz1/WhatToFWI.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhatToFrance.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
written_2/travel_guides/berlitz1/WhatToIsrael.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToDublin.txt
written_2/travel_guides/berlitz1/WhereToMallorca.txt
written_2/travel_guides/berlitz1/WhatToMallorca.txt
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
written_2/travel_guides/berlitz1/WhatToGreek.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
written_2/travel_guides/berlitz1/WhatToIndia.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz1/WhatToItaly.txt
written_2/travel_guides/berlitz1/WhereToMadrid.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhatToJapan.txt
written_2/travel_guides/berlitz1/WhatToJamaica.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhatToEgypt.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToFWI.txt
written_2/travel_guides/berlitz1/WhatToIstanbul.txt
written_2/travel_guides/berlitz1/WhereToIstanbul.txt
written_2/travel_guides/berlitz1/WhatToLasVegas.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
```
#### Example #2

The command below finds all the files in the berlitz1 directory that were created or modified before WhereToGreek.txt.

Command: ```find written_2/travel_guides/berlitz1 -newer written_2/travel_guides/berlitz1/WhereToGreek.txt```

Output: 
```
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToMallorca.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz1/WhereToMadrid.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToIstanbul.txt
```

### 2. find -type

[Source Link](https://www.redhat.com/sysadmin/linux-find-command)

This command outputs only things that match the specified type. For example, -type f only outputs files and -type d only ouputs directories within the path. This would be useful if you want to find only files and not have the command return the directory names too or if you wanted to only find directory names; by default the find command returns directories and files. 

#### Example #1

The command below returns all files in the written_2/non-fiction/OUP directory. It can be seen in the output none of the subdirectories are included. 

Command: ```find written_2/non-fiction/OUP -type f ```

Output:
```
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/non-fiction/OUP/Rybczynski/ch3.txt
written_2/non-fiction/OUP/Rybczynski/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch3.txt
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch4.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch7.txt
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/non-fiction/OUP/Kauffman/ch9.txt
written_2/non-fiction/OUP/Kauffman/ch10.txt
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
written_2/non-fiction/OUP/Castro/chR.txt
written_2/non-fiction/OUP/Castro/chP.txt
written_2/non-fiction/OUP/Castro/chQ.txt
written_2/non-fiction/OUP/Castro/chB.txt
written_2/non-fiction/OUP/Castro/chC.txt
written_2/non-fiction/OUP/Castro/chA.txt
written_2/non-fiction/OUP/Castro/chV.txt
written_2/non-fiction/OUP/Castro/chW.txt
written_2/non-fiction/OUP/Castro/chM.txt
written_2/non-fiction/OUP/Castro/chZ.txt
written_2/non-fiction/OUP/Castro/chL.txt
written_2/non-fiction/OUP/Castro/chN.txt
written_2/non-fiction/OUP/Castro/chY.txt
written_2/non-fiction/OUP/Castro/chO.txt
```
#### Example #2

The command below returns all directories in the written_2/non-fiction/OUP directory. It can be seen in the output none of the file names are included. 

Command: ```find written_2/non-fiction/OUP -type d```

Output:
```
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
```

### 3. find -size

[Source Link](https://man7.org/linux/man-pages/man1/find.1.html)

This command allows you to return files that are greater than, less than, or equal to a specified file size. The command is as follows ```find [path] -size [+/-][c/w/b/k/M/G]``` The first argument determines whether we are checking greater than or less than the specifed file size and the second argument specifes the unit of file size measurement. This could be useful if you are trying to keep track of the largest/smallest files in a directory to ensure ample memory space is allocated.

#### Example #1

The command below returns all files in the Abernath directory that have a size greater than 42 KB. The + indicates we are looking for files greater than the specified file size and the k indicates the unit of file size KB.

Command: ```find written_2/non-fiction/OUP/Abernathy -size +42k```

Output:
```
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
```

#### Example #2

The command below returns all files in the Berk directory that have a size less than 92 KB. The - indicates we are looking for files equal to the specified file size and the k indicates the unit of file size KB. 

Command: ```find written_2/non-fiction/OUP/Berk -size -92k```

Output:
```
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/ch7.txt
```

### 4. find -iname

[Source Link](https://www.binarytides.com/linux-find-command-examples/)

This commmand works similarly to ```-name``` but allows you to find files or directories with a specific name, ignoring whether it is uppercase or lowercase. This could be useful if you want to find files with the same name but they have inconsistent cases.

#### Example #1

The command below finds all files in the Berk directory that start with ch, regardless of whether they are uppercase or lowercase. Thus, it returns ch1.txt, ch2.txt, CH4.txt, and ch7.txt rather than just ch1.txt, ch2.txt, and ch7.txt.

Command: ```find written_2/non-fiction/OUP/Berk -iname "ch*.txt"```

Output:
```
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
```

#### Example #2

The command below finds all files in the Berk directory that start with CH, regardless of whether they are uppercase or lowercase. Thus, it returns ch1.txt, ch2.txt, CH4.txt, and ch7.txt rather than just CH4.txt. It can be seen that, unlike the ```-name``` option, ```-iname``` removes case sensitivity. Thus, this command example has the same output as the previous example. 

Command: ```find written_2/non-fiction/OUP/Berk -iname "CH*.txt"```

Output:
```
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
```




