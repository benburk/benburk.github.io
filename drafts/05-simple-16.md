+++
title = "Simple-16"
date = 2022-03-05
+++

A 16-bit CPU.


```
; collatz conjecture
r1: starting value

        mov r2 0x01         ; save constant 1


even:   shr r1 r2           ; r1 >>= 1

loop:   sw  r1 r0 TICKER    ; print value
        
        sub r3 r1 r2        ; r3 = r1 - 1
        bfl r3 end          ; quit if value == 1
        and r3 r1 r2
        bfl r3 even       ; a % 2 == 0 => even

        ; r1 is odd, r1 = 2r1 + r1 + 1
        shl r3 r1 r2
        add r1 r1 r3
        adi r1 r1 0x01
        jmp loop

end:
```