# Game
1) In each turn, a player must take a certain number of stones from the heap. 2) The number of stones a player can take is determined by finding the greatest common divisor (GCD) of their fixed number and the number of stones left in the heap. 3) If a player cannot take the required number of stones , they lose the game. 

from math import gcd

def game_winner(a, b, n):
    while n > 0:
        tia_stones = gcd(a, n)
        n -= tia_stones
        if n == 0:
            return 0  

        raj_stones = gcd(b, n)
        n -= raj_stones
        if n == 0:
            return 1 

a, b, n = map(int, input().split())

result = game_winner(a, b, n)
print(result)
