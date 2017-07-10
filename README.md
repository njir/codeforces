## CodeWars

#### Complete The Pattern #8 - Number Pyramid
- You have to write a function pattern which creates the following Pattern(See Examples) upto n(parameter) number of rows.
- If the Argument is 0 or a Negative Integer then it should return "" i.e. empty string.
- All the lines in the pattern have same length i.e equal to the number of characters in the last line. Range of n is (-∞,100]
- Examples: 
```
pattern(5):

    1    
   121   
  12321  
 1234321 
123454321
```
- [Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/CompleteThePattern.cpp)
  - very clever

#### Count the Digit
- Take an integer n (n >= 0) and a digit d (0 <= d <= 9) as an integer. Square all numbers k (0 <= k <= n) between 0 and n. Count the numbers of digits d used in the writing of all the k**2. Call nb_dig (or nbDig or ...) the function taking n and d as parameters and returning this count.
- Examples:
```
n = 10, d = 1, the k*k are 0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100
We are using the digit 1 in 1, 16, 81, 100. The total count is then 4.

nb_dig(25, 1):
the numbers of interest are
1, 4, 9, 10, 11, 12, 13, 14, 19, 21 which squared are 1, 16, 81, 100, 121, 144, 169, 196, 361, 441
so there are 11 digits `1` for the squares of numbers between 0 and 25.
```
> Note that 121 has twice the digit 1.
- [Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/HelpTheBookseller.cpp)
  - I added someone else's solution instead of my solution since it is clever solution.

#### Help the bookseller.
- A bookseller has lots of books classified in 26 categories labeled A, B, ... Z. Each book has a code c of 3, 4, 5 or more capitals letters. The 1st letter of a code is the capital letter of the book category. In the bookseller's stocklist each code c is followed by a space and by a positive integer n (int n >= 0) which indicates the quantity of books of this code in stock.
- In a given stocklist all codes have the same length and all numbers have their own same length (can be different from the code length).
- For example an extract of one of the stocklists could be:
```
L = {"ABART 20", "CDXEF 50", "BKWRK 25", "BTSQZ 89", "DRTYM 60"}.
```
- In this stocklist all codes have a length of five and all numbers have a length of two. You will be given a stocklist (e.g. : L) and a list of categories in capital letters e.g :
```
  M = {"A", "B", "C", "W"}
```
- and your task is to find all the books of L with codes belonging to each category of M and to sum their quantity according to each category. For the lists L and M of example you have to return the string (in Haskell/Clojure a list of pairs):
```
  (A : 20) - (B : 114) - (C : 50) - (W : 0)
```
- where A, B, C, W are the categories, 20 is the sum of the unique book of category A, 114 the sum corresponding to "BKWRK" and "BTSQZ", 50 corresponding to "CDXEF" and 0 to category 'W' since there are no code beginning with W. If L or M are empty return string is "" (Clojure should return an empty array instead).
- [Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/HelpTheBookseller.cpp)


#### Don't give me five!
- In this kata you get the start number and the end number of a region and should return the count of all numbers except numbers with a 5 in it. The start and the end number are both inclusive!
- The result may contain fives. ;-)
- The start number will always be smaller than the end number. Both numbers can be also negative!
- Examples:
```
1,9 -> 1,2,3,4,6,7,8,9 -> Result 8
4,17 -> 4,6,7,8,9,10,11,12,13,14,16,17 -> Result 12
```
- [My Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/DontGiveMeFive.cpp)
```
// Best Solution I think
bool containsFive(int num) {
  for (; num > 0; num /= 10) {
    if (num%10 == 5) { return true; }
  }
  return false;
}

int dontGiveMeFive(int start, int end) {
  int count = 0;
  for (int i = start; i <= end; ++i) {
    if (!containsFive(abs(i))) { count++; }
  }
  return count;
}
```

#### Bouncing ball
- A child plays with a ball on the nth floor of a big building. The height of this floor is known:
    - (float parameter "h" in meters, h > 0) .
- He lets out the ball. The ball rebounds for example to two-thirds: of its height.
    - (float parameter "bounce", 0 < bounce < 1) 
- His mother looks out of a window that is 1.5 meters from the ground:
    - (float parameters window < h).
- How many times will the mother see the ball either falling or bouncing in front of the window
    - (return a positive integer unless conditions are not fulfilled in which case return -1) ?
- Note: You will admit that the ball can only be seen if the height of the rebouncing ball is stricty greater than the window parameter.
- Example:
```
h = 3, bounce = 0.66, window = 1.5, result is 3
h = 3, bounce = 1, window = 1.5, result is -1
```
- [My Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/BouncingBalls.cpp)


#### Parts of a list
- Write a function partlist that gives all the ways to divide a list (an array) of at least two elements into two non-empty parts.
    - Each two non empty parts will be in a pair (or an array for languages without tuples or a structin C - C: see Examples test Cases - )
    - Each part will be in a string
    - Elements of a pair must be in the same order as in the original array.
- Example:
```
a = ["az", "toto", "picaro", "zone", "kiwi"] --> 
answer: [["az", "toto picaro zone kiwi"], ["az toto", "picaro zone kiwi"], ["az toto picaro", "zone kiwi"], ["az toto picaro zone", "kiwi"]]
```
- [My Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/PartOfaList.cpp)


#### Couting Duplicates
- Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphanumeric characters, including digits, uppercase and lowercase alphabets.
- Example:
```
"abcde" -> 0 # no characters repeats more than once
"aabbcde" -> 2 # 'a' and 'b'
"aabbcdeB" -> 2 # 'a' and 'b'
"indivisibility" -> 1 # 'i'
"Indivisibilities" -> 2 # 'i' and 's'
"aa11" -> 2 # 'a' and '1'
```
- [My Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/CoutingDuplicates.cpp)

#### Averages of numbers
- Write a method, that gets an array of integer-numbers and return an array of the averages of each integer-number and his follower, if there is one.
- Example:
```
Input:  [ 1, 3, 5, 1, -10]
Output:  [ 2, 4, 3, -4.5]
```
- [My Solution](https://github.com/njir/Algorithm-study/tree/master/codewars/AveragesNumbers.cpp)


----

## Codeforces

##### simple c++ code to solve problemset in codeforces.com
- 2015.05.25 solved : 1A, 4A, 71A, 118A, 282A, 158B
- 2015.05.28 solved : 96A, 131A, 266A, 133A, 112A
- 2015.05.29 solved : 339A, 281A
- 2015.06.05 solved : 236A, 110A, 467A
- 2015.10.10 solved : 41A, 61A, 443A
- 2015.10.14 solved : 102B
