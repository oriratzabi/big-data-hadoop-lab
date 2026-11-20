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

Q2. Please provide your code on GitHub.
See [`exercise2_mapper.py`](./exercise2_mapper.py) in this repository.


Exercise 3
Q1. Is your change in the mapper or in the reducer?
n the reducer. Because Hadoop automatically groups all occurrences of each key together before sending them to the reducer, only the reducer knows the complete aggregated count for each word. Collecting the pairs inside reducer.py, sorting them in descending order by count, and emitting only the top 3 items performs the filtering and sorting directly inside the MapReduce job.

Q2. Please provide your code on GitHub.
See [`exercise3_reducer.py`](./exercise3_reducer.py) in this repository.

Q3.Print the output of the MapReduce and put in your GitHub as an image
<img width="1690" height="355" alt="image" src="https://github.com/user-attachments/assets/65947eb6-f326-45d3-b5b4-eb3c996660c9" />
