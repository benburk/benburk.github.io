+++
title = "Designing an alternative keyboard layout"
date = 2022-03-03
+++

Hello


## TLDR

I designed a keyboard layout for myself based on a handful of metrics.

![image](/images/bold_layout.png)

I consider it combination of the best features of dvorak and colemak.

I also remapped caps lock to be a layer key, which provides the following keys:





## Introduction


I never learned how to type "properly" using all my fingers. During the summer of 2016, I figured since I type so much, it would be worthwhile to learn correct techniqued. As I embarked on the task, I learned about "alternative keyboard layouts" such as Dvorak and Colemak. Snce I was already relearning how to type, I thought I should learn a new layout at well.


## Evaluating a keyboard layout

I used a handful of different metrics for evaluating how much I might like a keyboard layout.
- Hand alternation: the odds you will type the next key with the opposite hand
- Same finger repetition: the odds you will type two keys in a row with the same finger
- rolls: The percentage of keys typed with the same hand 
- inward/outward roll ratio
- Seesaw motions: Percentage 
- Row jumps
- Finger heatmap

Maximize hand alternation (bigrams typed with both hands)
Maximize inward rolls ("rolling" your fingers towards the center of the keyboard when typing)
Minimize same finger repetition (bigrams typed with the same finger)
Minimize seesaw motions (trigrams that consist of one inward and outward motion)
Minimize row jumps

Balancing these characteristics is a bit of an art and certainly more subjective. 

## Corpus


- vim, english, bigram/trigram frequency


Colemak has a 50/50 


I wrote

## Result

I wrote a program to calculate all this. I tweaked a handful of heuristics to ultimately end up with the following layout

![image](/images/bold_layout.png)



## Implementing in software




I tried learning Dvorak, and then colemak, getting up to 50wpm in each. (inb4 "you shoulda stuck it out longer before realizing the true benefits")


If I was going through all the trouble of learning to type properly, I thought I might use a new keyboard layout.






A lot of people think about speed when considering a different keyboard layout. I think the more interesting value proposition is comfort, and speed follows from that.

I found a german program called for analyzing keyboard layouts [ADNW](http://www.adnw.de/)



Dvorak has high hand alternation



## Recreate the environment

```bash
g++ -std=c++11 -O2 -DNDEBUG -DENGLISH -DTASTENZAHL=33 opt.cc -o opt
```


```javascript
QWERTY          443.611 total effort   184.951 positional effort    left right
                  6.800 same finger rp   5.990 shift same finger top 28.0 20.2
qwertyuiop       52.758 hand alternat.  41.713 shift hand alter. mid 22.1  9.6
asdfghjkl;        1.073 inward/outward  37.864 inward or outward bot  6.8 13.3
zxcvbnm,./       21.605 adjacent        11.942 shift adjacent    sum 56.9 43.1
                  25.289 no hand altern. 27.150 two hand altern.
                  13.192 seesaw           5.655 indir same finger
                9.1  8.4 18.5 20.9 --.- --.- 18.4  8.9 12.1  3.7 Sh  1.1  1.7
same fing/fi.  0.04 0.07 2.96 1.59           1.16 0.22 0.75 0.01 Sh 5.60 0.39
" " jump >= 2  0.00 0.00 1.03 0.21           0.87 0.01 0.02 0.00 Sh 0.00 0.38
adjacent/fin.pair 1.82 3.19 8.74                4.79 2.22 0.84   Sh 0.6411.30
" " row jump >=2  0.00 0.22 2.21                3.48 0.03 0.03   Sh 0.06 7.98


COLEMAK         241.001 total effort   104.325 positional effort    left right
                  1.358 same finger rp  13.653 shift same finger top  7.8  8.3
qwfpgjluy;       58.113 hand alternat.  40.206 shift hand alter. mid 32.7 37.3
arstdhneio        1.034 inward/outward  37.951 inward or outward bot  6.8  7.3
zxcvbkm,./       17.487 adjacent         8.548 shift adjacent    sum 47.2 52.8
                  16.768 no hand altern. 30.773 two hand altern.
                  10.561 seesaw           5.575 indir same finger
                9.1  7.8 11.6 18.7 --.- --.- 18.8 15.4  9.8  8.8 Sh  1.1  1.7
same fing/fi.  0.04 0.04 0.17 0.18           0.39 0.37 0.16 0.01 Sh 5.06 8.59
" " jump >= 2  0.00 0.00 0.00 0.00           0.07 0.00 0.11 0.00 Sh 0.05 0.01
adjacent/fin.pair 2.30 1.03 2.47                9.34 1.35 0.99   Sh 3.09 5.46
" " row jump >=2  0.00 0.00 0.00                0.27 0.16 0.00   Sh 0.07 0.51


DVORAK          260.778 total effort   125.364 positional effort    left right
                  2.679 same finger rp  12.404 shift same finger top  6.0 16.8
/,.pyfgcrl       70.460 hand alternat.  34.504 shift hand alter. mid 36.1 30.4
aoeuidhtns        1.598 inward/outward  24.282 inward or outward bot  3.0  7.6
;qjkxbmwvz       11.122 adjacent        19.795 shift adjacent    sum 45.1 54.9
                  5.501 no hand altern. 44.775 two hand altern.
                  2.971 seesaw           5.847 indir same finger
                9.7  8.3 13.0 14.1 --.- --.- 16.5 13.3 13.7 11.4 Sh  1.8  0.9
same fing/fi.  0.02 0.03 0.22 0.97           0.43 0.48 0.31 0.23 Sh 9.46 2.95
" " jump >= 2  0.00 0.00 0.00 0.09           0.01 0.00 0.05 0.01 Sh 0.01 1.68
adjacent/fin.pair 0.10 0.44 2.45                4.50 2.51 1.12   Sh11.93 7.87
" " row jump >=2  0.00 0.00 0.02                0.01 0.04 0.03   Sh 0.16 2.12


BOLD            228.752 total effort   108.234 positional effort    left right
                  1.409 same finger rp  15.611 shift same finger top 12.9 10.6
bldfw/,oyk       70.374 hand alternat.  27.617 shift hand alter. mid 30.3 33.9
rnstmuaeih        3.648 inward/outward  25.638 inward or outward bot  7.2  5.2
zxcvg;.qjp       11.186 adjacent        12.905 shift adjacent    sum 50.4 49.6
                  5.504 no hand altern. 43.392 two hand altern.
                  2.889 seesaw           6.209 indir same finger
                8.5 10.9 13.3 17.7 --.- --.- 12.8 18.8  8.8  9.2 Sh  1.1  1.7
same fing/fi.  0.14 0.07 0.31 0.25           0.33 0.13 0.05 0.12 Sh 2.3913.22
" " jump >= 2  0.00 0.00 0.00 0.00           0.02 0.00 0.00 0.00 Sh 0.23 0.02
adjacent/fin.pair 0.52 2.80 2.28                2.48 1.88 1.24   Sh 7.40 5.51
" " row jump >=2  0.01 0.15 0.05                0.02 0.05 0.02   Sh 1.68 0.64
```



## Can you still type in qwerty?

Yes. Because I never did learn how to properly type in qwerty, the muscle memory doesn't overlap much and I can still type ~80wpm



## Inspiration

- https://xsznix.wordpress.com/2016/05/16/introducing-the-rsthd-layout/
- https://www.jonashietala.se/blog/2021/06/03/the-t-34-keyboard-layout/
- https://www.reddit.com/r/Norman/wiki/index#

keybr to learn the layout


- https://mdickens.me/typing/theory-of-letter-frequency.html
- https://geekhack.org/index.php?topic=67604.0
- http://www.adnw.de

Servers
This server - https://discord.gg/2qq8qmDtFf
This server on matrix - https://matrix.to/#/!iZdsjIZXWPXnohYGdD:matrix.org
Dvorak - https://discord.com/invite/JXpsSR2
Colemak - https://discord.gg/3VsHDG86hM
ColemaQ - https://discord.gg/Csra5jK2R6
Monkeytype - https://discord.gg/FcjrA7pBpG
Babymak (not a joke) - https://discord.gg/frtQHGrNwm

Resources
Keyboard Layouts Doc - Many known layouts compiled in one place, sorted by SFB rate | https://bit.ly/keyboard-layouts-doc
Dreymar's Big Bag - A collection of modifications and other useful tricks | https://dreymar.colemak.org/
SteveP Analyzer - A good fork of the patorjk layout analyzer | https://stevep99.github.io/keyboard-layout-analyzer/#/main
Mod DH Analyzer - A detailed and configurable layout analyzer | https://colemakmods.github.io/mod-dh/analyze.html 
CarpalX - The original layout analyzer and generator | http://mkweb.bcgsc.ca/carpalx/ 
gfruit's Words Filter - A simple yet incredibly useful tool for finding words with certain bigrams, characters, and fingers | https://gfruit.github.io/typing/words-filter.html
Octa's Keymap Creator- A tool for creating and sharing layout fingermaps | https://keymap-creator--octatypes.repl.co/ 
Monkeytype Fingermap - Same as above, made by the creator of MonkeyType | https://fingermap.monkeytype.com/
genkey - Layout analyzer and generator CLI | https://semilin.github.io/genkey
a200 - A spreadsheet-like layout analyzer | https://github.com/ClemenPine/200-analyzer