# big-data-hadoop-lab

Exercise 1
Q1. How many files are there?
7 files in total in the directory- 6 partition files and 1 "SUCCESS" status file.

Q2. Did the number of mappers change?
No, the number of mappers stayed 9.

Q3. Did the number of reducers change?
Yes, the number of reducers changed from 3 to 6.

Q4. Did the number of output files change? Why?
Yes, the number of output files increased from 3 to 6 because each reducer writes its own separate output partition file.

Q5. What does the value of 'Merged Map outputs' represent, and how is it calculated?
Merged Map outputs represents the total number of intermediate map output partitions fetched and merged across all reducers during the shuffle/sort phase, calculated as: Launched map tasks X Launched reduce tasks (9X6=54).


Exercise 2
Q1. Is your change in the mapper or in the reducer?
In the mapper. Converting words to lowercase and stripping trailing commas and periods must happen before the shuffle and sort phase so that variations like "The", "the,", and "the." produce the exact same key ("the") and get grouped together for the reducer.

Q2. Please provide your code on GitHub



Exercise 3
Q1. Is your change in the mapper or in the reducer?

Q2. Please provide your code on GitHub
______________________________

Q3. Print the output of the MapReduce and put in your GitHub as an image
Note: you should not use external pipes, sort, or filters. All should be done inside the
MapReduce Python code
I want to see in the screenshot after you type the command:
$ > hadoop fs -ls /user/hduser/gutenberg-output
