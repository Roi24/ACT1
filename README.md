#sample text-based game with simple conditional statement
character_health = 100
monster_health = 100
item = ""
import random   

name = input("Enter your name: ")
print("Hello " + name)

while character_health > 0:
    if character_health != 100 and item == "Fish":
        n = input("You have taken some damage to heal select [1 to heal/ 0 to ignore]")
        if n == "1":
            character_health += 10
            print("Your character's health is back to " + str(character_health))
        else :
             print("Your character's health is back to " + str(character_health))

    v = int(input("Choose 1 if you want to cross the river\nChoose 2 if you want to jump on the ravine\nChoose 3 if you want to fight monster in the dungeon \nInput: "))

    #Start of Journey
    if v == 1: 
        choice = input("If you want to go fishing select [1 for yes/ 0 for no]")
        if choice == "1":
            #Fishing minigame
            print("You have chosen Fishing! ")
            chance = random.randint(0,9)
            if chance > 6:
                item = "Fish"
                print("You have catch a Fish!")
            else:
                print("There is no fish to catch")

        elif choice == "0":
            print("You have crossed the river")


    elif v == 2:
        #damages the player
        print("You have jumped into the ravine")
        print("Your character has taken 10pt of damage")
        character_health = character_health - 10

    elif v == 3:
        #damages the player
        print("You have enter the dungeon")
        #monster attack
        chance = random.randint(0,9)
        if chance > 6:
            item = "Monster"
            print ("Monster appeared !!!")
            choice = input("Do you want to fight the monster? \n \t [1 to fight and 0 to run]") 
            if choice == "1":
                monster_health = 100
                m = int(input("chance to attack \n [choose!!!] \n 0 to punch\t 2 to uppercut \n 1 to kick"))
                if m == "0":
                    monster_health -= 15
                    print ("The monster is slowing" + str(monster_health))
                if m == "1":
                    monster_health -= 20
                    print ("You make him hurt" + str(monster_health))
                if m == "2":
                    monster_health -= 35
                    print ("he can't breath" + str(monster_health))     
                
                else:
                    print ("you defeated the monster but you have taken damages")
                character_health -= 25
                
            elif choice == "0":

                print ("you escaped")



        

    else:
        print("Invalid input")

    print("Your character's Health: " + str(character_health))

print("Your Character is dead!")
