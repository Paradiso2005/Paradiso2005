10 REM This is a simple video game for a CASIO fx-9750G111 calculator
20 REM The player controls a spaceship and must avoid incoming asteroids
30 GRAPHICS 0
40 DIM x(30), y(30), s(30)
50 FOR i = 1 TO 30
60   x(i) = INT(RND*128)
70   y(i) = INT(RND*64)
80   s(i) = INT(RND*3)+1
90 NEXT i
100 SHIPX = 64
110 SHIPY = 32
120 PRINT "Press the left and right keys to move the spaceship"
130 PRINT "Avoid the incoming asteroids!"
140 DO
150   FOR i = 1 TO 30
160     PSET (x(i), y(i))
170     x(i) = x(i) - s(i)
180     IF x(i) < 0 THEN x(i) = 128
190   NEXT i
200   LINE (SHIPX-2, SHIPY-2)-(SHIPX+2, SHIPY+2)
210   LINE (SHIPX-2, SHIPY+2)-(SHIPX+2, SHIPY-2)
220   IF INKEY(26) = 1 THEN SHIPX = SHIPX - 1
230   IF INKEY(27) = 1 THEN SHIPX = SHIPX + 1
240   LOCATE 1, 1: PRINT "SCORE:"; SCORE
250 LOOP UNTIL SCORE = 10
260 PRINT "You win!"
270 END
