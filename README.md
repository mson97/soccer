# soccer program
n = 1
roster = {} # creates empty dictionary called roster
for i in range (0, 5): # lets user input 5 pairs of numbers
    jersey_number = int(input("Enter player %d's jersey number:\n" % n))
    rating = int(input("Enter player %d's rating:\n" % n))
    print('') 
    roster[jersey_number] = rating # adds key:value pairs-jersey_number:rating
    n = n + 1
print("ROSTER")
for jersey_number, rating in sorted(roster.items()): # sorts jersey numbers in order of low-high
    print("Jersey number: %d, Rating: %d" % (jersey_number, rating))

option = ''
menu =  "\nMENU\na - Add player\nd - Remove player\nu - Update player rating\nr - Output players above a rating\no - Output roster\nq - Quit\n"
while option != 'q': # quits
    print(menu)
    option = input("Choose an option:\n")
    if option == 'o': # outputs roster
        print("ROSTER")
        for jersey_number, rating in sorted(roster.items()):          
            print("Jersey number: %d, Rating: %d" % (jersey_number, rating))
    elif option == 'a': # adds player
        jersey_number = int(input("Enter a new player's jersey number:\n"))
        rating = int(input("Enter the player's rating:\n"))
        roster[jersey_number] = rating
    elif option == 'd': # removes player
        jersey_number = int(input("Enter a jersey number:\n"))
        del roster[jersey_number]
    elif option == 'u': # updates player's rating
        jersey_number = int(input("Enter a jersey number:\n"))
        rating = int(input("Enter a new rating for player:\n"))
        roster[jersey_number] = rating
    elif option == 'r': # outputs all players above inputted rating
        number = int(input("Enter a rating:\n"))
        print("ABOVE", number)
        ratings_list = list(roster.values()) # creates a list from extracted values from dict
        for jersey_number, rating in sorted(roster.items()):
            if rating in ratings_list and rating > number:
                print("Jersey number: %d, Rating: %d" % (jersey_number, rating))
    else:
        print(end='')
