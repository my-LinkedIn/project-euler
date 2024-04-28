# A glimpse of Factor or solving problem almost with oneliner code

[Factor](https://factorcode.org) is a concatenative, stack-based programming language with high-level features.

I just used [Online Factor Compiler](https://www.tutorialspoint.com/execute_factor_online.php) to harness them. Feel free to do the same... just by `Copy and Paste` and basta.

I begin now to have a good grasp of what is the [Forth](https://www.tutorialspoint.com/execute_factor_online.php) language is like... I just remember it was cited among others outstanding ones in our Computer Science primer course years ago.

## Problem #1

```factor
! Multiples of 3 or 5
! https://projecteuler.net/problem=1

USING: kernel math prettyprint sequences ;
1000 <iota> [ [ 5 mod ] [ 3 mod ] bi [ 0 = ] either? ] filter sum .
```

## Problem #2

```factor
! Even Fibonacci Numbers
! https://projecteuler.net/problem=2

USING: kernel math prettyprint sequences ;
4,000,000 [ 1 0 ] dip '[ [ + ] 2keep dup _ < ] [ ] produce 3nip [ even? ] filter sum .
```

## Problem #3

```factor
! Largest Prime Factor
! https://projecteuler.net/problem=3

USING: math.primes.factors prettyprint sequences ;
600851475143 factors last .
```

## Problem #5

```factor
! Smallest Multiple
! https://projecteuler.net/problem=5

USING: math.functions ranges sequences ;
20 [1..b] 1 [ lcm ] reduce
```

## Problem #6

```factor
! Sum Square Difference
! https://projecteuler.net/problem=6

USING: kernel math ranges sequences ;
100 [1..b] [ 0 [ sq + ] reduce ] [ sum sq ] bi - abs
```

## Problem #7

```factor
! 10001st Prime
! https://projecteuler.net/problem=7

USING: lists math.primes.lists prettyprint ;
10001 lprimes lnth .
```

## Problem #10

```factor
! Summation of Primes
! https://projecteuler.net/problem=10

USING: math.primes prettyprint sequences ;
2000000 primes-upto sum .
```

## Problem #15

```factor
! Lattice Paths
! https://projecteuler.net/problem=15

USING: kernel math math.combinatorics prettyprint ;
20 dup 2 * swap nCk .
```

## Problem #16

```factor
! Power Digit Sum
! https://projecteuler.net/problem=16

USING: math.functions math.parser prettyprint sequences ;
2 1000 ^ number>string string>digits sum .
```

## Problem #17

```factor
! Number Letter Counts
! https://projecteuler.net/problem=17

USING: ascii kernel math.text.english prettyprint ranges sequences ;
1000 [1..b] SBUF" " clone [ number>text append! ] reduce [ Letter? ] count .
```

## Problem #19

```factor
! Counting Sundays
! https://projecteuler.net/problem=19

USING: calendar kernel prettyprint ranges sequences ;
1901 2000 [a..b] [ 12 [1..b] [ 1 (day-of-week) ] with map ] map concat [ 0 = ] count .
```

## Problem #20

```factor
! Factorial Digit Sum
! https://projecteuler.net/problem=20

USING: kernel math math.factorials math.parser prettyprint sequences ;    
100 factorial number>string string>digits sum .
```
