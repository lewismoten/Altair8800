# Light Switch
Program by Lewis Moten, May 21, 2018

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

# Video
[![Altair 8800: Light Switch Video](http://img.youtube.com/vi/7E5G5GA2zdI/0.jpg)](http://www.youtube.com/watch?v=7E5G5GA2zdI)

# Code Table
| Mnumonic      | Data          | Tags  | Binary | Line | Dump |
| ------------- | ------------- | ----- | ---    | ---- | ---- |
| MVI | D = 0x80 | 00-(r=010=D)-110 | 00-010-110 | 000 | 026 |
| | 200 ||10-000-000|001|200|
|LDAX|D&E->A|00-0(rp=1=DE)1-010|00-011-010|**002**|032|
|LDAX|D&E->A|00-0(rp=1=DE)1-010|00-011-010|003|032|
|LDAX|D&E->A|00-0(rp=1=DE)1-010|00-011-010|004|032|
|LDAX|D&E->A|00-0(rp=1=DE)1-010|00-011-010|005|032|
|IN|Sense Switches -> A||11-011-011|006|333|
||Device 255||11-111-111|007|377|
|MOV|A->D|01-(rp=101=D)-(rp=111=A)|01-010-111|010|127|
|JMP|0x0002||11-000-011|011|303|
||2||00-000-010|012|**002**|
||0||00-000-000|013|000|


