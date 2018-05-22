# Light Switch
Turn Lights On program by Lewis Moten, May 21, 2018

## Object
Turn lights on above the sense switches.

## Code

```Assembly
0000                 org    0
0000 1680            mvi    d,0x80 ; setup register D
0002 1A         beg: ldax   d      ; display state from register D
0003 1A              ldax   d
0004 1A              ldax   d
0005 1A              ldax   d
0006 DBFF            in     0xFF   ; input sense switches
0008 57              mov    d,a    ; copy switch state to register D
0009 C30200          jmp    beg    ; repeat
000C                 end
```

## Octal

Here is the program in octal for easier entry into the Altair:

```octal
000: 026 200 032 032 032 032 333 377
010: 127 303 002 000
```
