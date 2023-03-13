# Lab Report 5
Nitya Pillai | CSE 15L Thursday 10 am B270

## the ```grep``` command 

### 1. grep -i \<pattern> \<file>
[Source Link](https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html)

This command returns a list of all the lines in the listed files that contain the given pattern, ignoring the case. It could be useful if we wanted to know which lines contained a patten but we didn't care about whether uppercase or lowercase was preserved.

#### Example #1

The command below returns a list of all lines in the ch2.txt that contain the phrase "general stores", ignoring case. It can be seen that because of using the -i option the command returned lines with "General Stores" capitalized as well as lines with "general stores. "

Command: ``` grep -i "general stores"  non-fiction/OUP/Abernathy/ch2.txt```

Output: 
```
Retail: From General Stores to Mass Retailers
Until the emergence of mass retail, the wholesaler-jobber dominated the distribution of consumer dry goods to general stores: clothing, upholstered furnishings, hardware, drugs, tobacco, furniture, china, and glassware. Unlike traveling peddlers of the past, who carried everything with them, these salesmen could ride the rails into town with no more than a trunk of samples and catalogs. The new infrastructure created by the railroads and telegraph contributed to the growth of wholesale houses. Retailers no longer needed to carry such large inventories, the risk of losing shipments was reduced, and delivery was more certain on a specified schedule. Increased volume cut unit costs and enhanced cash flow, reducing credit needs. Moreover, these salesmen provided a flow of information to their headquarters on changing demand in -various localities as well as the credit ratings of local storekeepers and merchants.
Wholesaler-jobber enterprises of the time, such as Field, Leiter and Company in Chicago (which later became Marshall Field and Company), required both a purchasing organization and an extensive traveling sales force to sell to the scattered general stores in smaller cities and country towns. These buyers and their assistants each handled a major product line like hardware or dry goods. They typically determined the specifications of the goods purchased, the volume purchased, and the price to be charged to customers at retail. These buyers became the most important managers in wholesaler-jobber companies, foreshadowing the key status of the buyer in later retail organizations.
```
#### Example #2

The command below returns a list of all lines in ch8.txt that contain the name "JOSEPH GERBER", but ignoring case. It can be seen that even though there were no matches for "JOSEPH GERBER", the command still returned lines containing "Joseph Gerber."

Command: ```grep -i "JOSEPH GERBER"  non-fiction/OUP/Abernathy/ch8.txt```

Output: 
```
The late Joseph Gerber, founder of Gerber Garment Technology Company in Tolland, Connecticut, invented automated fabric cutting and introduced it to the market in 1969. This innovative company went on to create a new industry in automatic-cutting equipment. By the late 1970s, Gerber Garment Technology was supplying the automotive and apparel industries with its GERBERcutter, allowing firms to cut cloth and nonwoven material more effectively. The Gerber system first made it possible for a computer to guide the cutting knife anywhere on the cutting table. Gerber’s automatic-cutting equipment, as well as that of several other international competitors, has continued to improve; cloth from a single ply to layers up to six inches thick can now be cut quickly and accurately.
Joseph Gerber solved the major problem in cutting—how to hold the cloth while the knife cuts through the material—by putting the entire lay on a vacuum table. The fabric lay with the marker on top is covered with a thin sheet of clear plastic. When the vacuum pump comes on, five pounds of force per square foot push down on the fabric. The thin plastic sheet effectively cuts off the flow of room air through the fabric. The vacuum holds the cloth firmly and compresses the thickness of the lay, typically by half.
```

### 2. grep -n \<pattern> \<file>

[Source Link](https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html)

This command adds the line number to the standard output of the grep command. Essentially, it returns the contents of the lines where the given pattern was found in the file, but it also includes their line numbers as part of the output. This would be helpful if you wanted to know the exact location in a file that a word or phrase was rather than just where it was used in terms of content. 

#### Example #1

The command below returns all lines and line numbers in ch8.txt that contain "Joseph Gerber". Letter case is taken into account. It can be seen in the output that unlike previous examples, the line number is also included in what is returned. "Joseph Gerber"w was found on lines 5 and 46. 

Command: ```grep -n "Joseph Gerber"  non-fiction/OUP/Abernathy/ch8.txt ```

Output:
```
5:The late Joseph Gerber, founder of Gerber Garment Technology Company in Tolland, Connecticut, invented automated fabric cutting and introduced it to the market in 1969. This innovative company went on to create a new industry in automatic-cutting equipment. By the late 1970s, Gerber Garment Technology was supplying the automotive and apparel industries with its GERBERcutter, allowing firms to cut cloth and nonwoven material more effectively. The Gerber system first made it possible for a computer to guide the cutting knife anywhere on the cutting table. Gerber’s automatic-cutting equipment, as well as that of several other international competitors, has continued to improve; cloth from a single ply to layers up to six inches thick can now be cut quickly and accurately.
46:Joseph Gerber solved the major problem in cutting—how to hold the cloth while the knife cuts through the material—by putting the entire lay on a vacuum table. The fabric lay with the marker on top is covered with a thin sheet of clear plastic. When the vacuum pump comes on, five pounds of force per square foot push down on the fabric. The thin plastic sheet effectively cuts off the flow of room air through the fabric. The vacuum holds the cloth firmly and compresses the thickness of the lay, typically by half.

```
#### Example #2

The command below returns all lines and line numbers in all text files in the Berk directory that contain "decades". Letter case is taken into account. Since this command involves searching multiple files, the line number and file name are included included in what is returned. "decades" was found in lines 5, 22, 76, 91, and 157 of ch1.txt and line 121 of ch2.txt.

Command: ```grep -n "decades"  non-fiction/OUP/Berk/*.txt```

Output:
```
non-fiction/OUP/Berk/ch1.txt:5:In my three decades of teaching university courses in child development, I have come to know thousands of students, many of whom were parents or who became parents soon after completing my class. I also served on boards of directors and advisory committees for child-care centers, preschools, elementary schools, and parent organizations. And my research continually drew me into classrooms, where for countless hours I observed and recorded preschool and school-age children’s activities, social interactions, and solitary behaviors, in hopes of answering central questions about how they learn.
non-fiction/OUP/Berk/ch1.txt:22:Over the past three decades, external forces impinging on the family have transformed parents’ and, therefore, children’s lives. Overall, parents complain that they have less free time to spend with their children.1 Witness a 1995 survey of a large, representative sample of American workers, nearly 25 percent of whom expressed the feeling that the demands of their jobs left them with “no time for family.”2 Compounding their worries, employed parents must, out of necessity, turn over many hours of child rearing to other adults. Yet once their children are beyond their grasp, they are hardly o the hook! Conscientious parents face an added responsibility: monitoring their child’s whereabouts and activities, verifying from a distance that their youngster is physically safe, emotionally contented, and constructively engaged. 
non-fiction/OUP/Berk/ch1.txt:76:The past three decades have seen a continuation of this dichotomy of extremes in parenting advice and educational practice. In the 1970s, titles appeared that blew the whistle on permissiveness and child-centeredness, such as Don’t Be Afraid of Your Child and Power to the Parents. As part of this rebound, Thomas Gordon’s Parent Effectiveness Training 41 oered to rescue parents who had allowed their child to ride roughshod over them. In the realm of children’s learning, books in the behaviorist tradition, advocating intensive, early academic training, resurfaced. A prominent example, Siegfried and Therese Engelmann’s blueprint for raising a brighter preschooler, Give Your Child a Superior Mind, appealed to parents bent on boosting their child’s IQ or—even better—producing a genius. In spelling out the theory, the Engelmanns dismissed the legitimacy of biological readiness and proclaimed,
non-fiction/OUP/Berk/ch1.txt:91:After decades of theoretical division and debate, a new, more complex view of child development is coalescing in the ﬁeld, supported by rapidly accumulating research evidence. The fragmented, polarized theories of the past are giving way to more equitable theories emphasizing that the child and the social environment interact and that the contributions of each to development cannot be separated and weighted in a simplistic, one-sided manner.48
non-fiction/OUP/Berk/ch1.txt:157:Although Harris is correct that children often evoke behaviors from parents and others that strengthen their genetic tendencies, research clearly shows that parents can, and often do, uncouple these child-to-parent eects. Indeed, the substantial malleability of temperament in infancy and early childhood is explained, in large measure, by the fact that many parents and other adults are successful in guiding children with maladaptive tendencies toward more eective functioning. Moreover, decades of research on intelligence show that IQ, although not inﬁnitely pliant, varies greatly with the stimulating quality of children’s experiences.75
non-fiction/OUP/Berk/ch2.txt:121:In a study of parenting in 180 societies, anthropologists Ronald and Evelyn Rohner found that warmth combined with at least moderate expectations for mature behavior and accomplishment is the most common child-rearing style around the world.48 Why do so many cultures mingle concern and aection with guidance and control—a blend known as authoritative parenting in the child-rearing literature? Certainly because they sense its eectiveness, borne out by decades of research. 
```

### 3. grep -c \<pattern> \<file>

[Source Link](https://www.howtogeek.com/devops/how-to-count-all-matches-of-a-string-with-grep-for-linux/#:~:text=The%20grep%20command%20has%20the,%2C%20endpoint%2C%20or%20other%20identifier.&text=However%2C%20grep%20is%20able%20to%20match%20multiple%20times%20per%20line.)

This command allows you to return count of the number of lines that contain the given pattern. However, it's important to remember this command only returns the number of lines, so it won't increase count if the word is found multiple times within the same line. This command would be useful if you didn't need to know about the contents or location of the pattern/word but you just needed to know how many lines contained it. 

#### Example #1

The command below returns the number of lines that contain "decades" in each of the text files in the Berk directory. It can be seen that rather than displaying the contents of the files like previous commands, it just displays a count of numebr of occurences of the pattern in each file. 

Command: ```grep -c "decades"  non-fiction/OUP/Berk/*.txt```

Output:
```
non-fiction/OUP/Berk/CH4.txt:0
non-fiction/OUP/Berk/ch1.txt:5
non-fiction/OUP/Berk/ch2.txt:1
non-fiction/OUP/Berk/ch7.txt:0
```

#### Example #2

The command below returns the number of lines that contain "parent" in ch1.txt. It can be seen that rather than displaying the contents of the files like previous commands, it just displays a count of numebr of occurences of the pattern in the given file. Unlike example 1, it doesn't display the name of the file since we are only searching one file. 

Command: ```grep -c "parent"  non-fiction/OUP/Berk/ch1.txt```

Output:
```
78
```

### 4. grep -l \<pattern> \<file>

[Source Link](https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html)

This commmand returns only the names of the files that contain the pattern. It would work well if you were trying to search through multiple text files in a large directory and just wanted to know which files contained the pattern rather than what the context or content with the pattern in the file was. 

#### Example #1

The command below outputs the names of the files that contain the pattern "decadeds" out of all the text files in the Berk directory. From previous examples, we know this pattern was only found in ch1.txt and ch2.txt which is why these file names and their paths were outputted. 

Command: ```grep -l "decades"  non-fiction/OUP/Berk/*.txt```

Output:
```
non-fiction/OUP/Berk/ch1.txt
non-fiction/OUP/Berk/ch2.txt
```

#### Example #2

The command below can be used to check whether "decades" is in the specified file, in this case ch1.txt. Because the name and path of ch1.txt is outputted, this means the pattern was found. However, if nothing was outputted, this would mean that the pattern was not contained within the given file. 

Command: ```grep -l "decades"  non-fiction/OUP/Berk/ch1.txt ```

Output:
```
non-fiction/OUP/Berk/ch1.txt
```





