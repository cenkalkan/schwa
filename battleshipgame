import numpy as np
import random

shipboard = np.array([['a','b','c'],['d','e','f'],['g','h','i']])

shipboard2 = np.array([[random.randint(0,1),random.randint(0,1),random.randint(0,1)],[random.randint(0,1),random.randint(0,1),random.randint(0,1)],[random.randint(0,1),random.randint(0,1),random.randint(0,1)]])

print(shipboard2)

ships = np.where(shipboard2 == 1)

coordinates_of_ships= list(zip(ships[0], ships[1]))

game_wins = 0

game_losses = 0

playing = True

while playing == True:
    print("Your options are:", shipboard)
    selection = input("Where would you like to fire your missile? ")
    where_is_this_coordinate = np.where(shipboard == selection)
    coords = list(zip(where_is_this_coordinate[0], where_is_this_coordinate[1]))
    misses = 0

    for coord in coords:
        print(coord)

    for coord in coords:

        if coord in coordinates_of_ships:
            for value in np.nditer(shipboard, op_flags=['readwrite']):
                if value == selection:
                    print("You hit one!")
                    value[...] = 'o'

        else:
            for value in np.nditer(shipboard, op_flags=['readwrite']):
                if value == selection:
                    print("No boat!")
                    value[...] = 'x'
                    misses += 1

        list_of_os = np.where(shipboard == 'o')
        coords_of_os = list(zip(list_of_os[0],list_of_os[1]))

        if coordinates_of_ships == coords_of_os:
            print("All ships have been sunk!!")
            game_wins += 1
            playing = False


        if misses == 5: #supposes to check for if you've missed a certain amount of times, doesn't work, can't figure out why
            print("You lost, your fleet has been destroyed!")
            game_losses += 1
            playing = False

def statistics ():
    '''Finds statistics about the player's journey'''
    print("wins: ", game_wins)
    print("losses: ", game_losses)
def clear_stats():
    '''Resets a player's statistics to 0'''
    global game_wins
    global game_losses
    game_wins = 0
    game_losses = 0
statistics()
clear_stats()
