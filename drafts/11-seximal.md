+++
title = "Seximal"
date = 2022-03-04
+++

- Also called hex, heximal, base-6
- https://www.seximal.net/
- https://xanthir.com/hex/
- http://shacktoms.org/base-six/base-six.htm
- `0,1,2,3,4,5`

## Bases are arbitrary
Why do we use base-10, then? The obvious answer is that we have 10 fingers. Counting off each finger gives us one "unit" of 10 things, and that unit-size carried over until we invented positional notation, where it froze into the base-10 we know today.

If we invented positional notation earlier, then our hands could have supplied a better base - each hand can count off the values 0, 1, 2, 3, 4, and 5, which are exactly the digits of base-6. Two hands, then, lets you track two base-6 digits, counting up to 35

## Finger counting
One hand for 10s, other hand for units.
- https://www.seximal.net/finger-counting#

## Math
| Fraction | Base 6          | Base 8             | Base 10         | Base 12            | Base 16 |
| -------- | --------------- | ------------------ | --------------- | ------------------ | ------- |
| $1/2$    | $.3$            |                    |                 |                    |         |
| $1/3$    | $.2$            | $.\overline{25}$   |                 |                    |         |
| $1/4$    |                 |                    |                 |                    |         |
| $1/5$    | $.\overline{1}$ |                    |                 |                    |         |
| $1/6$    | $.1$            | $.\overline{1463}$ | $.\overline{2}$ | $.\overline{2497}$ |         |
|          |                 |                    |                 |                    |         |

**Multiplication**
- Table is smaller

## Primality and divisibility rules
In base-6, all primes end in 1 or 5

Divisibility:
- 2 and 3: Check last digit
- 5: Add all the digits

## Time
- Each day is $100_6$ hours (24 hours)
- Each hour is $100_6$ minutes (40 minutes)
- Each minute is $100_6$ seconds (1.1 minutes)
- Each second is $100_6$ milliseconds ()
If a movie is $142_6$ minutes long, we know its $1_6$ hour and $42_6$ minutes

- https://www.xanthir.com/b54c0


## Calendar
Base 6 calendar.
- Each week is $10_6$ (6) days long
- Each month is $10_6$ (6) weeks long or $100_6$ (36) days long
- You can tell what day of the week it is by the last digit

There are $14_6$ (10) months total so the last month has an extra seventh week consisting of 5 days, and 6 on leap years.

Culturally you can have a four-day work week

$6x6=100_6$ days per month

- https://www.xanthir.com/hex/calendar/
- https://calendars.wikia.org/wiki/Symmetry454_Calendar
- [Leap Years: we can do better](https://www.youtube.com/watch?v=qkt_wmRKYNQ)

## Currency
Currencies come out quite a bit nicer in smaller bases. Don't need 10 of an item to round up.
$1 = $1
$10 = $6
$100 = $36
$1000 = $216


## Sequences and constants in base-6
- Primes: 2, 3, 5 ,11, 15, 21, 25, 31, 35, 45, 51, 101, 105, 111 (they all end in 1 or 5)
- Powers of two: 1, 2, 4, 12, 24, 52, 144, 332, 1104, 2212, 4424, 13252
- $\tau = 10.141100143234252214513232150255042205002433324012$ 
- $\pi = 3.050330051415124105234414053125321102301214442004$
- $e = 2.415052053524243123125404352354404354235032444$
- $\sqrt2 = 1.2252453142055233214322324304424$
- $\Phi = 1.34125455435343145134223514015012$