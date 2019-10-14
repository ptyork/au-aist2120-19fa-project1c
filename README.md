# Project 1c: Email Address Parser 

Often times, you may be given a list of raw email addresses and be asked to generate meaningful information from such a list. This project involves parsing such a list and generating names and summary information from that list. 

The script, `emailparser.py`, should: 

1. Ask the user for a file name 
2. Open the requested file 
3. Iterate over each line in the file (each line will be a separate email address) 
4. Print (to the screen) a line that "interprets" the email address as described below 
5. When finished, display the total number of email addresses and a count unique domain names 

Each email address will either be in the form "first.last@domain.ext" OR "ilast@domain.ext", where "first" and "last" are the first and last names of the person respectively, and "i" is the first initial. Each "line" (step 4) should contain the email address itself, the name (either "Last, First" or "Last, I." where "I" is the first initial, and the domain name of th email address. The name components should be in "title case" (capitalize first letter of all words/initials). So for example, the following two email addresses in the input file: 
```
doe.deer@re.mi 
irobot@sneaker.net 
```
should result in the following printed to the screen: 
```
doe.deer@re.mi                Deer, Doe                re.mi 
irobot@sneaker.net            Robot, I.                sneaker.net 
```
Allow 30 characters for the email address, 25 characters for the full name and 25 characters for the domain name for a total of 80 characters wide per line of output. All fields should be left aligned (that's the default for strings). 

## REQUIRED IMPLEMENTATION NOTES 

1. You MUST abstract your most useful logic by creating a function named `parsemail` that takes an email address as a parameter and prints the line formatted as described above. This function should be "called" as your step 4 above, which will make the main script much cleaner. So to reiterate, the following function MUST be in your code: 
``` 
        def parsemail(email): 
            ...
``` 
2. You MUST use either the format() function or an f-string to format your lines of text.

3. You MUST modify emails.txt, and add your own email address at the bottom as first.last@augusta.edu. 

4. You MUST run your script against the file `emails.txt` and redirect the output to `parsed-emails.txt`. In other words, you should run `python emailparser.py > parsed-emails.txt` and select `emails.txt` when prompted. Include this file in your final submission. 

## LOGISTICS 

Same basic deal as with the homeworks. 

1. From your AIST2120 folder, run `git clone [URL]` to make a local copy of this assignment. 
2. DO THE WORK (create and complete any and all needed files)
3. TEST YOUR WORK A WHOLE LOT 
4. TEST IT SOME MORE LIKE YOU MEAN IT THIS TIME 
5. When done, run `git add .` 
6. Then run `git commit –m "type a clever message here"` 
7. Finally run `git push` to push your changes back up to GitHub 
8. Breathe a sigh of relief 

## OPTIONAL CHALLENGES 

1. Create a second version of the script, emailparser2.py. This version should import the parsemail function from emailparser (`from emailparser import parsemail`). Instead of asking for a file name and reading the text from the file, instead read in the text line-by-line from `sys.stdin`. This should allow you to run it interactively AND to pipe in text from another command (e.g., `type emails.txt | python emailparser2.py`). 

2. Improve the "logic" for `parsemail` to remove any numbers (digits) from the name before running your "rules." So for instance, `dcunningham12@rasa.net` would parse to a name of "Cunningham, D." (dropping the "12").

3. Improve the logic of `parsemail` to ALSO capitalize the third letter of any name that starts with `Mc`. So for instance `Mcshady` whould become `McShady`.
