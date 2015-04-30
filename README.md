Part a
======
on opencl1, using Cypress and group size of 16 I got:
290   Mpixels/s
2.32  Gbit/s
14    GFlops/s  
on opencl1, using Cypress and group size of 8 I  got:
211  Mpix/s
1.69  Gbit/s
10.25 GFlop/s
On opencl1 using Cypress and group size of 20 and 32 I got an abort (core dumped)
message.
On cuda3 using Tesla T10 I got:
321 Mpix/s
2.56 GBit/s
15 GFlops/s

All theses were averaged using 10,000 repetitions.


Thus, increasing the group size doesn't seem to be a good idea (of course, there
might be an optimum between 16 and 20 but I did not check). Reducing the group 
size doesn't seem to help either. 

I don't add the blurred picture and the original since all of the files everyone
sends will look the same. I add the results of the second part instead.


part b
======
The implementation is online. Just one comment - the original code left a thin
black frame around the original picture. When blurring, this black frame takes 
over all of the image. I fixed this problem by setting both the origin and 
the target arrays to the right greyscale value. 


How to run
==========
To run the program, type "make" in command line.

