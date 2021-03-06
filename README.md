# Getting-Dressed-Permutations-in-Python
Getting Dressed: Permutations in Python

The challenge:


You have to get dressed in the morning before going to work. Unfortunately, you only accept a space separated list of numbers to indicate article of clothing to don.

    1 = hat
    2 = pants
    3 = shirt
    4 = shoes
    5 = socks

How many different number of ways can you successfully get dressed, following the rules below?

Rules:

    You must put your socks on before your shoes.
    You must put your pants on before your shoes.
    You must put your shirt on before your hat.
    A hat is optional but all other articles of clothing are required.
    You must leave the house when receiving the number 6. You must leave the house after getting dressed.
    Any violation should output "fail" and stop immediately.

Examples:

    Input: 5 1
    Output: socks, fail
    Input: 5 2 3 4 6
    Output: socks, pants, shirt, shoes, leave
    
    
Solution:
The python scripts in this repo were made as a solution to the challenge above. To run, first download the repository and run the following command in the terminal to create a csv (space_separated_permutations.csv) of permutations:

python create_inputs.py

The resulting csv will be a list of all possible permutations for 5 things ("1", "2", "3, "4, "5") taken 1, 2, 3, 4, or 5 at a time. According to the permutation equation below, we will have 325 permutations when summing across r=1 to 5.
	Number of permutations of n things taken r at a time:
	
	=(n!)/(n-r)!
	=(5!)/(4!)
		+ (5!)/(3!) 
		+ (5!)/(2!) 
		+ (5!)/(1!)
		+ (5!)/(0!)
		= 5 + 20 + 60 + 120 + 120
		=325

This means that there are 325 different ways to put on your attire, regardless of whether it's acceptable by the rules or not.

Appended to each of these permutations is the number "6", which indicates "leave" as explained above. The program run_program.py reads in the permutations (space_separated_permutations.csv) and prints the successful ways to get dressed after filtering out ways that the rules don't allow (which are defined as functions in getting_dressed.py). Running this program is straightforward:

python run_program.py

This program will print the successful ways to get dressed. Of the 325 possible ways, only 28 were ways to successfully get dressed with respect to the rules defined. They are listed below:

1) 2 3 5 4 6 is ['pants', 'shirt', 'socks', 'shoes', 'leave']
2) 5 2 3 1 4 6 is ['socks', 'pants', 'shirt', 'hat', 'shoes', 'leave']
3) 2 5 4 3 1 6 is ['pants', 'socks', 'shoes', 'shirt', 'hat', 'leave']
4) 2 3 5 1 4 6 is ['pants', 'shirt', 'socks', 'hat', 'shoes', 'leave']
5) 5 3 2 4 1 6 is ['socks', 'shirt', 'pants', 'shoes', 'hat', 'leave']
6) 5 2 4 3 1 6 is ['socks', 'pants', 'shoes', 'shirt', 'hat', 'leave']
7) 5 3 2 1 4 6 is ['socks', 'shirt', 'pants', 'hat', 'shoes', 'leave']
8) 2 5 4 3 6 is ['pants', 'socks', 'shoes', 'shirt', 'leave']
9) 5 2 3 4 1 6 is ['socks', 'pants', 'shirt', 'shoes', 'hat', 'leave']
10) 5 3 2 4 6 is ['socks', 'shirt', 'pants', 'shoes', 'leave']
11) 3 5 2 1 4 6 is ['shirt', 'socks', 'pants', 'hat', 'shoes', 'leave']
12) 3 2 5 4 1 6 is ['shirt', 'pants', 'socks', 'shoes', 'hat', 'leave']
13) 2 3 1 5 4 6 is ['pants', 'shirt', 'hat', 'socks', 'shoes', 'leave']
14) 3 5 2 4 6 is ['shirt', 'socks', 'pants', 'shoes', 'leave']
15) 3 2 1 5 4 6 is ['shirt', 'pants', 'hat', 'socks', 'shoes', 'leave']
16) 3 1 2 5 4 6 is ['shirt', 'hat', 'pants', 'socks', 'shoes', 'leave']
16) 2 5 3 4 6 is ['pants', 'socks', 'shirt', 'shoes', 'leave']
18) 3 5 1 2 4 6 is ['shirt', 'socks', 'hat', 'pants', 'shoes', 'leave']
19) 5 3 1 2 4 6 is ['socks', 'shirt', 'hat', 'pants', 'shoes', 'leave']
20) 3 1 5 2 4 6 is ['shirt', 'hat', 'socks', 'pants', 'shoes', 'leave']
21) 2 5 3 4 1 6 is ['pants', 'socks', 'shirt', 'shoes', 'hat', 'leave']
22) 3 2 5 4 6 is ['shirt', 'pants', 'socks', 'shoes', 'leave']
23) 5 2 4 3 6 is ['socks', 'pants', 'shoes', 'shirt', 'leave']
24) 3 5 2 4 1 6 is ['shirt', 'socks', 'pants', 'shoes', 'hat', 'leave']
25) 3 2 5 1 4 6 is ['shirt', 'pants', 'socks', 'hat', 'shoes', 'leave']
26) 2 3 5 4 1 6 is ['pants', 'shirt', 'socks', 'shoes', 'hat', 'leave']
27) 2 5 3 1 4 6 is ['pants', 'socks', 'shirt', 'hat', 'shoes', 'leave']
28) 5 2 3 4 6 is ['socks', 'pants', 'shirt', 'shoes', 'leave']
