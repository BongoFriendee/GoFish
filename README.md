# gofish
A game of gofish in python. Work in progress.
```python 
#!/usr/bin/python3                           
# a game of go fish                          
import sys                                   
import random                                

class Card:                                  
    def __init__(self, rank, suit):          
        self.rank = rank                     
        self.suit = suit                     
    suit = ['hearts', 'spades', 'clubs', 'diamonds']                                      
    rank = ['ace', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'jack', 'queen', 'king']                                                                                     

    def i__str__(self):                      

        return '%s of %s' % (Card.rank[self.rank], Card.suit[self.suit])                  
testcard = Card(2, 3)                        
players = ''                                 
while players is not int:                    
    try:                                     
        players = int(input('How many players?: '))                                       
        break                                
    except ValueError:                       
        print('Please enter a real number of players: ')                                  

if players <= 1:                             
    print("Not possible. You can't play alone.")                                          
    sys.exit()                               

elif players == 2:                           
    hand_size = 7                            

elif 2 < players < 6:                        
    hand_size = 5                            

else:                                        
    print("Too many players. Enter a number between 2 and 6")                             
    sys.exit()                               

print("Each player will be dealt",hand_size,"Cards.")                                     
ready = input('Ready?: [y/n]')               
if not ready == 'y':                         
    print('Bye then')                        
    sys.exit()                               

#to do                                       
#define size each players hand accoring to hand_size                                      
#deal hands to each playre.                  
#turn mechanism.  prompt player with a list of options on their respective turns          

