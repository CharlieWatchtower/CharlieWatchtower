# CODES
The purpose is to transmit information to the user using a reduced amount of verbosity so that you can save memory at the same time.

## style1
```e-code
error: xxx.xxx
```
you can do like a 3 digit code and a 3 digit count of how many errors? or maybe something else?

Obviously this would be in base10 for the general user.

so this gives you 1000 unique codes?

**Con:** Its very limited to give meaning, i.e. the user needs a booklet thingy with the numbers in descending order.

We can use conventions like 404 when something's missing.

---
## style2
```e-code.oh this isn't visible in the md render...
error: 0x1_111
```
#### The 0x
That will be used to indicated where the error happened, in a very general sense.

I don't think we'll need more than 9, but that's what the "x" is for I guess, and it doubles as a separator.

Nerds will get angry cause they'll think its hex but anyway... I'll change it later.

#### The 1_111
**Con:** the "_" is a waste of memory but its better for readablity

The first 1 can indicate a more specific location or source, and the other 3 codes indicated the error...

**Con:** Doesn't really solve the problem of a code book.

We can make the first number of the error indicate severity in some way?

**Con:** yeah just noticed its 7 chararcters...

## style3
```
0x1_111_X2
```
10 characters is better than 7... 8 or 16 would be easier but whatever.

the "error:" bit is kinda redundant? I think you'd be able to tell this thing is an error code

Anway now we can more or less maintain the previous but the severity and exent of the error can be the domain of the "X2" bit.

could also log it out.
## LOG
Could use a .log file if we needed and make it something like
```
log{
    {0x:blablabla}
    {1_111:tatata}
    {_X2:titititi}
}
```