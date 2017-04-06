# The-Camel-Game
import random
print("Welcome, this is the CAMEL GAME")
print("You have just stolen a camel from the village and the villagers are angry")
print("You have to reach the end of the desert to escape them, the desert is 200 miles long")
print("Good Luck!")
    
miles_traveled = 0
villagers_position = -30
thirst = 10
camel_fatigue = 15
oasis = 0

done = False
while done == False:
    full_speed = random.randint(10, 16)
    moderate_speed = random.randint(5, 9)
    a_thirst = random.randint(2, 3)
    a_fatigue = random.randint(3, 4)
    b_thirst = random.randint(1, 2)
    b_fatigue = random.randint(1, 3)
    natives_behind = miles_traveled - villagers_position
    villagers = random.randint(1, 15)
    
    print("A. Go ahead at full speed")
    print("B. Advance at moderate speed")
    print("C. Stop and rest")
    print("D. Drink 1 bottle of water")
    print("E. Status check")
    print("Q. Quit Game")

    response = input("What do you want to do ? :")
    if response == "A" or response == "a":
        if camel_fatigue < 4:
            print("Your camel is tired")
        elif thirst < 4:
            print("Your thirsty")
        miles_traveled = miles_traveled + full_speed
        thirst = thirst - a_thirst
        camel_fatigue = camel_fatigue - a_fatigue
        villagers_position = villagers_position + villagers
        print("You traveled ", miles_traveled ," miles")

    elif response == "B" or response == "b":
        if camel_fatigue < 4:
            print("Your camel is tired")
        elif thirst < 4:
            print("Your thirsty")
        miles_traveled = miles_traveled + moderate_speed
        thirst = thirst - b_thirst
        camel_fatigue = camel_fatigue - b_fatigue
        villagers_position = villagers_position + villagers
        print("You traveled ", miles_traveled ," miles")
        print(thirst)

    elif response == "C" or response == "c":
         camel_fatigue= 15
         villagers_position = villagers_position + villagers
         print("Your camel is no longer thirsty")

    elif response == "D" or response == "d":
         thirst= 15
         villagers_position = villagers_position + villagers
         print("You are no longer thirsty")

    elif response == "E" or response == "e":
        print("You traveled ", miles_traveled ," miles")
        print("Hydration: ", thirst)
        print("Energy: ", camel_fatigue)
