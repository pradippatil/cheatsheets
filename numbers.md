
### Numbers representations

Decimal|Binary|Hexadecimal|Octal
---|---|---|---
0|0000 |0|0
1|0001 |1|1
2|0010 |2|2
3|0011 |3|3
4|0100 |4|4
5|0101 |5|5
6|0110 |6|6
7|0111 |7|7
8|1000 |8|-
9|1001 |9|-
10|1010 |A|-
11|1011 |B|-
12|1100 |C|-
13|1101 |D|-
14|1110 |E|-
15|1111 |F|-

### Internal Numeric representations
In general, with an n-bit string you can represent up to 2n different values


Bit string| Size in Bits|Number of Possible Combinations (2^n)
:----------|:------------------------------|:-------------------------
nibble|4| 16
byte|8| 256
word|16| 65,536
double word|32|4,294,967,296
quad word|64|18,446,744,073,709,551,616
long word|128|340,282,366,920,938,463,463,374,607,431,768,211,456

---
### GCM (Greatest Common Divisor)
Using Euclidean algorithm: https://en.wikipedia.org/wiki/Euclidean_algorithm

_Implementations_:

    function gcd(a, b)
        while b ≠ 0
        t := b; 
        b := a mod b; 
        a := t; 
        return a;
    
or Using recursion

    function gcd(a, b)
        if b = 0
        return a; 
        else
        return gcd(b, a mod b);


### LCM (Least Common Multiple)

The least common multiple of a and b is the product divided by the greatest common divisor. I.e. lcm(a, b) = ab/gcd(a, b). So the question becomes how to find the gcd. The Euclidean algorithm mentioned above is generally how the gcd is computed. 
http://stackoverflow.com/a/3154503/3781709

*Important comment*:
>LCM using GCD is fast and easy to code. One small but important detail: in order to avoid overflows, calculate the final result like this: lcm = a / gcd * b instead of lcm = a * b / gcd



### Finding GCD / LCM of multiple Numbers
GCD and LCMD is associative, GCD(a,b,c,d) is the same as GCD(GCD(GCD(a,b),c),d)