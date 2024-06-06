## Lab Report 5
Patrick Fong, A14080869\

# Part 1: Debugging Scenario
**Original student post with a screenshot showing a symptom and a guess as to what the bug might be:**\
\
&emsp; I'm trying to write a Java program that reads a list of numbers from a text file, then calculates and outputs the mean of the numbers.\
&emsp; The Java file is called ```MeanCalc.java```. The text file to be read is in a different directory called ```data```.\
&emsp; However, the program only outputs “Average: 0.0” regardless of what is written in the text file that provides the input.\
\
&emsp; Here is a screenshot of the directory structure:\
&emsp; ![Image](lab5ss1.png)\
&emsp; Here is the code in ```labfive/src/MeanCalc.java```:\
&emsp; ![Image](lab5ss2.png)\
&emsp; Here are the contents of ```labfive/data/numbers.txt```:\
&emsp; ![Image](lab5ss3.png)\
&emsp; Here is a screenshot of the failure-inducing input and symptom:\
&emsp; ![Image](lab5ss4.png)\
\
&emsp; The output should be ```Average: 2.0```.\
&emsp; I'm not sure whether my program is calculating the average incorrectly or reading input from the wrong file. Any ideas?\
\
\
**A reponse from a TA asking a leading question or suggesting a command to try (To be clear, I'm mimicking a TA here):**\
\
&emsp; Are you sure the main method in MeanCalc.java is reading input from the correct file?\
&emsp; Using JDB, can you think of a way to check the value assigned to a field at a given line to determine the input is being correctly read?\
&emsp; What are the values in the numbers.txt file in the src directory?\
\
\
