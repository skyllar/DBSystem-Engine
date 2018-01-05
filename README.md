# DBSystem-Engine

The project puts up a Database System with following components:
1. Resolve SQL queries with various possible ops like: >, <, !, =, LIKE, NOT, EXISTS, etc as well rule out the invalid queries from user.
2. All combinations of above queries.
3. Builds multi-level index structure (3-level Index) for faster retrieval of records from table.
4. Implementation includes B+ tree, External Merge Sort to support above features.
5. Parser Used : gsp

Extra Features:
 1. Where clause can include nesting, can include any combination of 'And'/'OR' operators with brackets.
 2. Associativity of the operators (including brackets) taken into account.
 3. Handled Join between two relations.

Usage:

	bash run.sh <Path to Config File> <Path to Input File>

Short Overview of the Approach Used:

	1. Index is initially created for all the columns of the table.
	2. For each query:
		 a. Validation is checked.
		 b. Conditions are checked and corresponding line numbers are stored in set.
		 c. Records from the file are fetched only for these line numbers. 
		 d. Records are obtained from LRU everytime. So Better page size and Page count will improve the performance.
		
