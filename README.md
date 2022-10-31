# unicode
Unicode is a command-line utility for querying the [Unicode Character Database](https://unicode.org/ucd/).

## Installation
It is not recommended to install from GitHub directly - Use the following, instead:

```
go install robpike.io/cmd/unicode@latest
```

## Examples/Usage
```
% unicode
usage: unicode { [-t] hex hex ... | hexmin-hexmax ... | [-n] char ... }
% # Print the character corresponding to code point U+0037
% unicode -c 0037
7
% # Above is also the default behavior - That is, it will assume hex if no flags are provided
% unicode 0037
7
% # Print the code point assigned to the character '%'
% unicode -n %
0025
% # Use the -t flag to print plain characters, without a newline separating them
% # for example, compare:
% unicode 0022 0037 00aa
"
7
ª
% # to:
% unicode -t 0022 0037 00aa
"7ª% 
% Print all characters, with their code point, within the given range
% unicode 20-7e
0020  	0021 !	0022 "	0023 #	0024 $	0025 %	0026 &	0027 '
0028 (	0029 )	002a *	002b +	002c ,	002d -	002e .	002f /
0030 0	0031 1	0032 2	0033 3	0034 4	0035 5	0036 6	0037 7
0038 8	0039 9	003a :	003b ;	003c <	003d =	003e >	003f ?
0040 @	0041 A	0042 B	0043 C	0044 D	0045 E	0046 F	0047 G
0048 H	0049 I	004a J	004b K	004c L	004d M	004e N	004f O
0050 P	0051 Q	0052 R	0053 S	0054 T	0055 U	0056 V	0057 W
0058 X	0059 Y	005a Z	005b [	005c \	005d ]	005e ^	005f _
0060 `	0061 a	0062 b	0063 c	0064 d	0065 e	0066 f	0067 g
0068 h	0069 i	006a j	006b k	006c l	006d m	006e n	006f o
0070 p	0071 q	0072 r	0073 s	0074 t	0075 u	0076 v	0077 w
0078 x	0079 y	007a z	007b {	007c |	007d }	007e ~
```
