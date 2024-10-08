# Practicing Piping

## Redirecting Output

run **echo PWN > COLLEGE** as instructed

## Redirecting more output

run **/challenge/run > myflag** as instructed. the flag is stored in myflag, so do **cat myflag** to get the flag.

## Appending output

run **/challenge/run > /home/hacker/the-flag** as instructed. this will write the first half of the flag to the-flag. i was confused what to do next, but then just figured out appending will write the 2nd half to the file by running **/challenge/run >> /home/hacker/the-flag**

## Redirecting Errors

just like the example given above, run **/challenge/run > myflag 2> instructions** as instructed.

## Redirecting input

write COLLEGE to PWN with **echo COLLEGE > PWN**, then input PWN into the run file with **/challenge/run < PWN** to get the flag.

## Grepping stored results

output the flag to /tmp/data.txt with **/challenge/run > /tmp/data.txt**, then since every flag starts with pwn.college, we can search for it with **grep pwn.college /tmp/data.txt** to get the flag.

## Grepping live output

run challenge/run, then the output gets piped into grep with | as taught. **/challenge/run | grep pwn.college**

## Grepping errors  

Redirect the errors of the program into the standard output by using the >& operator. Since the errors are in 2 and stdout in 1, 2>&1 is used. then pipe the result into grep: **/challenge/run 2>& 1 | grep pwn.college** gives us the flag.

## Duplicating piped data with tee

We first have to pipe the error message into another file to see what the issue is. we do this by doing **/challenge/pwn | tee output1 | /challenge/college**, where the output is added to output 1. after this we can do cat output1. it tells us to use the --secret flag with a given secret key. **/challenge/pwn --secret A6C249ip | /challenge/college** then gives us the flag.

## Writing to multiple programs