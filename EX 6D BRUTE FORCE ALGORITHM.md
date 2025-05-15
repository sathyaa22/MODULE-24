# EX 6D BRUTE FORCE ALGORITHM

## DATE: 13.05.2025

## AIM:
To write a python program using brute force method of searching for the given substring in the main string.


## Algorithm

1. Start the program.
2. Take the main string and the substring to be searched as input.
3. Iterate over each index in the main string where the substring could start (from 0 to len(main) - len(substring)).
4. For each starting index, compare characters of the substring with the corresponding characters in the main string one by one.
5. If all characters match for the substring length, record or print the current starting index as a match.
6. If any character does not match, move to the next starting index in the main string.
7. Repeat this process until all possible starting positions have been checked.
8. Return or output all indices where the substring was found in the main string.
9. End the program.


## Program:

```
To implement the program using brute force method of searching for the given substring in the main string.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
import re 
def match(str1,str2):
    pattern = re.compile(str2)
    r = pattern.search(str1)
    while r:
        print("Found at index {}".format(r.start()))
        r = pattern.search(str1,r.start() + 1)
str1=input()
str2=input()
```


## Output:

![image](https://github.com/user-attachments/assets/83ae83b3-2b3d-4cad-90ae-9f9dfef1f8f2)


## Result:
Thus the above program was executed successfully for searching the substring at respective index.
