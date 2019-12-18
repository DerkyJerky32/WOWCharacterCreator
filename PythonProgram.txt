# Derrick Demers
# 7/14/2019
# World of Warcraft Character Generator Quiz
# A programmed designed to give new World of Warcraft players a helping hand in deciding what race
# and class to play as (final version)

def TryAgain(): #This class is where the end of every quiz portion goes to ask if the user would like to run the program again
    Again = input("\nWould you like to run the program again? (Y/N)\n"
                  "Choice: ")
    if Again.lower() == 'y':
        print("Starting program again...\n")
        Faction_Choice()
    elif Again.lower() == 'n':
        print("Thank you for using the programming, farewell adventurer...")
        return 0
    else:
        print("Invalid input...\n")
        TryAgain()


################################## Alliance Questions #######################################

# CHOOSING A ROLE --ALLIANCE--
def Alliance_Class_Questions():
    print("\nWelcome to the Alliance, new player. It is now time for you to choose a role in which you will play as.\n")
    Alliance_Role_Choice = input("\nRoles to choose from: Tank, DPS (Damage), Healer...\n"
                                 "(a) Tank: Tanks are players that are designed to take as much damage as possible.\n"
                                 "Catch the attention of the enemy and leave the damage roles to take care of the\n"
                                 "enemy/enemies.\n"
                                 "(b) DPS: With the Tanks acting as the shields, the dps are the sword of the group.\n"
                                 "DPS roles are designed to inflict as much damage as possible.\n"
                                 "(c) Healers: Healers need to make sure everyone is alive and well. There are \n"
                                 "healers that can heal in multiple ways whether it be directly or indirectly.\n"
                                 "What will you choose? Role: ")
    if Alliance_Role_Choice.lower() == 'a':
        Alliance_Tank()
    elif Alliance_Role_Choice.lower() == 'b':
        Alliance_DPS()
    elif Alliance_Role_Choice.lower() == 'c':
        Alliance_Healer()
    else:
        print("\nInvalid input. Please try again") 
        Alliance_Class_Questions() #If the user enters an invalid answer, they are transported back to the beginning of 
                                   #a class. This pattern repeats throughout the program


# THE ALLIANCE TANK ROLE
def Alliance_Tank():
    Pandaren_Monk = 0
    Worgen_Warrior = 0 #the values for the results are set to 0

    print("\nYou have chosen the Tank role for the Alliance.")
    YesOrNo = input("Is this what you wanted? (Y/N) ") #asks the user if this is the correct role
    if YesOrNo.lower() == 'y':
        print("Let's continue...\n")
    elif YesOrNo.lower() == 'n':
        print("Understood. Going back to the role choice...\n") 
        Alliance_Class_Questions() #user is transported back to role choice
    else:
        print("Invalid input...\n")
        Alliance_Tank()

        # Question 1 #
    question1_AllianceTank = input("Question 1: \n"
                                   "When fighting an opponent one on one, you prefer to...\n"
                                   "(a) Use status effects to give yourself an advantage\n"
                                   "(b) Overpower the enemy with speed and brute force\n"
                                   "Choice: ")
    if question1_AllianceTank.lower() == 'a':
        Pandaren_Monk += 1 #values get added to the choices after each question is answered 
    elif question1_AllianceTank.lower() == 'b':
        Worgen_Warrior += 1
    else:
        print("\nInvalid input, going back a step...\n")
        Pandaren_Monk = 0
        Worgen_Warrior = 0
        Alliance_Tank()

        # Question 2 #
    question2_AllianceTank = input("\nQuestion 2: \n"
                                   "Do you prefer taking down...\n"
                                   "(a) multiple enemies at once\n"
                                   "(b) one enemy at a time \n"
                                   "Choice: ")
    if question2_AllianceTank.lower() == 'a':
        Pandaren_Monk += 1
    elif question2_AllianceTank.lower() == 'b':
        Worgen_Warrior += 1
    else:
        print("\nInvalid input, going back a step...\n...")
        Pandaren_Monk = 0
        Worgen_Warrior = 0
        Alliance_Tank()

        # Question 3 #
    question3_AllianceTank = input("\nQuestion 3: \n"
                                   "Are you one to prioritize speed?\n"
                                   "(a) No\n"
                                   "(b) Yes\n"
                                   "Choice: ")
    if question3_AllianceTank.lower() == 'a':
        Pandaren_Monk += 1
    elif question3_AllianceTank.lower() == 'b':
        Worgen_Warrior += 1
    else:
        print("\nInvalid input, going back a step...\n...")
        Pandaren_Monk = 0
        Worgen_Warrior = 0
        Alliance_Tank()

        # Add results # Choices are added up and results are printed acoringly
    if Pandaren_Monk > Worgen_Warrior: #checks to see which is the greatest choice chosen
        print("You should play as a PANDAREN MONK.\n"
              "Pandaren Monks are a tough combination of healer and tank that is able to use buffs and debuffs\n"
              "to give themselves or their allies an edge in battle.\n ")
        TryAgain()

    elif Worgen_Warrior > Pandaren_Monk:
        print("You should play as a WORGEN WARRIOR.\n"
              "Worgen Warriors are able to not only to soak a large amount of damage, but are also able to deliver \n"
              "a great amount of damage in a quick amount of time as well.\n")
        TryAgain()

    else:
        print("\nInconclusive amount of data. Going back a step...\n")
        Pandaren_Monk = 0
        Worgen_Warrior = 0 #resets the values back to 0 before continuing to retry
        Alliance_Tank() 


# THE ALLIANCE DPS ROLE
def Alliance_DPS():
    Pandaren_DeathKnight = 0
    NightElf_Rogue = 0
    NightElf_DemonHunter = 0
    Worgen_Warrior = 0
    Dwarf_Hunter = 0

    print("\nYou have chosen the DPS role for the Alliance.")
    YesOrNo = input("Is this what you wanted? (Y/N) ")
    if YesOrNo.lower() == 'y':
        print("Let's continue...\n")
    elif YesOrNo.lower() == 'n':
        print("Understood. Going back to role choice...\n")
        Alliance_Class_Questions()
    else:
        print("Invalid input...\n")
        Alliance_DPS()

        # Question 1 #
    question1_AllianceDPS = input("\nQuestion 1:\n"
                                  "What is your basic method of attacking?\n"
                                  "(a) Close and brutal\n"
                                  "(b) Silent but deadly\n"
                                  "(c) Close and life stealing\n "
                                  "(d) Close and quick\n"
                                  "(e) At a distance\n"
                                  "Choice: ")
    if question1_AllianceDPS.lower() == 'a':
        Pandaren_DeathKnight += 1
    elif question1_AllianceDPS.lower() == 'b':
        NightElf_Rogue += 1
    elif question1_AllianceDPS.lower() == 'c':
        NightElf_DemonHunter += 1
    elif question1_AllianceDPS.lower() == 'd':
        Worgen_Warrior += 1
    elif question1_AllianceDPS.lower() == 'e':
        Dwarf_Hunter += 1
    else:
        print("\nInvalid entry. Going back a step...\n")
        Pandaren_DeathKnight = 0
        NightElf_Rogue = 0
        NightElf_DemonHunter = 0
        Worgen_Warrior = 0
        Dwarf_Hunter = 0
        Alliance_DPS()

        # Question 2 #
    question2_AllianceDPS = input("\nQuestion 2:\n"
                                  "What skills do you like to implement to your attack patterns?\n"
                                  "(a) Debuffs to enemies and buffs to myself\n"
                                  "(b) Poisons to the enemy and potions to myself\n"
                                  "(c) Speed boosts and life/mana stealing\n "
                                  "(d) Speed boosts and stuns\n"
                                  "(e) Animal companions and long range stuns\n"
                                  "Choice: ")
    if question2_AllianceDPS.lower() == 'a':
        Pandaren_DeathKnight += 1
    elif question2_AllianceDPS.lower() == 'b':
        NightElf_Rogue += 1
    elif question2_AllianceDPS.lower() == 'c':
        NightElf_DemonHunter += 1
    elif question2_AllianceDPS.lower() == 'd':
        Worgen_Warrior += 1
    elif question2_AllianceDPS.lower() == 'e':
        Dwarf_Hunter += 1
    else:
        print("\nInvalid entry. Going back a step...\n")
        Pandaren_DeathKnight = 0
        NightElf_Rogue = 0
        NightElf_DemonHunter = 0
        Worgen_Warrior = 0
        Dwarf_Hunter = 0
        Alliance_DPS()

        # Question 3 #
    question3_AllianceDPS = input("\nQuestion 3:\n"
                                  "Are you more comfortable in a group or alone?\n"
                                  "(a) Alone\n"
                                  "(b) With a group if I'm the only one of my class\n"
                                  "(c) I prefer a group\n "
                                  "(d) Either/Or\n"
                                  "(e) In a group\n"
                                  "Choice: ")
    if question3_AllianceDPS.lower() == 'a':
        Pandaren_DeathKnight += 1
    elif question3_AllianceDPS.lower() == 'b':
        NightElf_Rogue += 1
    elif question3_AllianceDPS.lower() == 'c':
        NightElf_DemonHunter += 1
    elif question3_AllianceDPS.lower() == 'd':
        Worgen_Warrior += 1
    elif question3_AllianceDPS.lower() == 'e':
        Dwarf_Hunter += 1
    else:
        print("\nInvalid input. Going back a step...\n")
        Pandaren_DeathKnight = 0
        NightElf_Rogue = 0
        NightElf_DemonHunter = 0
        Worgen_Warrior = 0
        Dwarf_Hunter = 0
        Alliance_DPS()

        # Results #
    if Pandaren_DeathKnight > NightElf_Rogue & NightElf_DemonHunter & Worgen_Warrior & Dwarf_Hunter:
        print("\nYou should play as a PANDAREN DEATH KNIGHT\n"
              "The Death Knight damage output combined with the buffs and other abilities from the\n"
              "Pandaren race are sure to make the Pandaren Death Knight a force to be reckoned with\n"
              "on the battlefield.\n")
        TryAgain()

    elif NightElf_Rogue > Pandaren_DeathKnight & NightElf_DemonHunter & Worgen_Warrior & Dwarf_Hunter:
        print("\nYou should play as a NIGHT ELF ROGUE.\n"
              "Night elves are able to slip into the shadows easier making them the perfect race\n"
              "for those that love dealing damage from the shadows.\n")
        TryAgain()

    elif NightElf_DemonHunter > Pandaren_DeathKnight & NightElf_Rogue & Worgen_Warrior & Dwarf_Hunter:
        print("\nYou should play as a NIGHT ELF DEMON HUNTER\n"
              "Night Elf Demon Hunters are able to get an addional critical hit boost as well as leech\n"
              "health from their enemies making. This combined with their increased attack speed abilities\n"
              "make them ideal for most raids.\n")
        TryAgain()

    elif Worgen_Warrior > Pandaren_DeathKnight & NightElf_Rogue & NightElf_DemonHunter & Dwarf_Hunter:
        print("\nYou should play as WORGEN WARRIOR.\n"
              "As a Worgen Warrior you are more resistant to nature and shadow damage which helps out\n"
              "against fighting mages and warlocks. They're bonus movement speed makes moving from target\n"
              "to target much easier as well.\n")
        TryAgain()

    elif Dwarf_Hunter > Pandaren_DeathKnight & NightElf_Rogue & NightElf_DemonHunter & Worgen_Warrior:
        print("\nYou should play as a DWARF HUNTER.\n"
              "Dwarf Hunters are very skilled in trickling down enemies from afar. With their pets able\n"
              "to even tank damage, skilled hunters can flank and take down the largest of foes from afar.\n")
        TryAgain()

    else:
        print("\nInconclusive amount of data. Going back a step...\n")
        Pandaren_DeathKnight = 0
        NightElf_Rogue = 0
        NightElf_DemonHunter = 0
        Worgen_Warrior = 0
        Dwarf_Hunter = 0
        Alliance_DPS()


# THE ALLIANCE HEALER ROLE
def Alliance_Healer():
    Draenei_Paladin = 0
    Human_Priest = 0

    print("\nYou have chosen the healer role for the Alliance.")
    YesOrNo = input("Is this what you wanted? (Y/N) ")
    if YesOrNo.lower() == 'y':
        print("Let's continue...\n")
    elif YesOrNo.lower() == 'n':
        print("Understood. Going back to role choice...\n")
        Alliance_Class_Questions()
    else:
        print("Invalid input...\n")
        Alliance_Healer()

        # Question 1 #
    question1_AllianceHealer = input("\nQuestion 1:"
                                     "\nWhat is your preferred method of healing?\n"
                                     "(a) Area of Effect buffs and healing\n"
                                     "(b) Constant/Regular healing\n"
                                     "Choice: ")
    if question1_AllianceHealer.lower() == 'a':
        Draenei_Paladin += 1
    elif question1_AllianceHealer.lower() == 'b':
        Human_Priest += 1
    else:
        print("\nInvalid entry. Going back a step...\n")
        Draenei_Paladin = 0
        Human_Priest = 0
        Alliance_Healer()

        # Question 2 #
    question2_AllianceHealer = input("\nQuestion 2:"
                                     "\nDo you prefer buffs or strictly healing?\n"
                                     "(a) Buffs\n"
                                     "(b) Strictly healing\n"
                                     "Choice: ")
    if question2_AllianceHealer.lower() == 'a':
        Draenei_Paladin += 1
    elif question2_AllianceHealer.lower() == 'b':
        Human_Priest += 1
    else:
        print("\nInvalid entry. Going back a step...\n")
        Draenei_Paladin = 0
        Human_Priest = 0
        Alliance_Healer()

        # Question 3 #
    question3_AllianceHealer = input("\nQuestion 3:\n"
                                     "Which of these sounds more appealing to your style of play?\n"
                                     "(a) Shields and giving damage when taking damage\n"
                                     "(b) Removing lethal magic in an area and boosting the"
                                     " abilities of other healers\n"
                                     "Choice: ")
    if question3_AllianceHealer.lower() == 'a':
        Draenei_Paladin += 1
    elif question3_AllianceHealer.lower() == 'b':
        Human_Priest += 1
    else:
        print("\nInvalid entry. Going back a step...\n")
        Draenei_Paladin = 0
        Human_Priest = 0
        Alliance_Healer()

        # Results #
    if Draenei_Paladin > Human_Priest:
        print("\nYou should play as a DRAENEI PALADIN.\n"
              "Draenei have the ability to heal themselves and others over time. Add the Paladin\n"
              "abilities to give buffs and they can be an asset to raids and maybe even PVP.\n")
        TryAgain()

    elif Human_Priest > Draenei_Paladin:
        print("\nYou should play as a HUMAN PRIEST.\n"
              "Humans have the natural ability to break out of stuns. Added with a Paladin's ability to heal\n"
              "at a steady rate and Human Paladins will be a huge asset in raids.\n")
        TryAgain()

    else:
        print("\nInconclusive amount of data. Going back a step...\n")
        Draenei_Paladin = 0
        Human_Priest = 0
        Alliance_Healer()


################################## Horde Questions #######################################

# CHOOSING A ROLE --HORDE--
def Horde_Class_Questions():
    print("\nWelcome to the Horde, new player. It is now time for you to choose a role in which you will play as.\n")
    Horde_Role_Choice = input("\nRoles to choose from: Tank, DPS (Damage), Healer...\n"
                              "(a) Tank: Tanks are players that are designed to take as much damage as possible.\n"
                              "Catch the attention of the enemy and leave the damage roles to take care of the\n"
                              "enemy/enemies.\n"
                              "(b) DPS: With the Tanks acting as the shields, the dps are the sword of the group.\n"
                              "DPS roles are designed to inflict as much damage as possible.\n"
                              "(c) Healers: Healers need to make sure everyone is alive and well. There are \n"
                              "healers that can heal in multiple ways whether it be directly or indirectly.\n"
                              "What will you choose? Role: ")
    if Horde_Role_Choice.lower() == 'a':
        Horde_Tank()
    elif Horde_Role_Choice.lower() == 'b':
        Horde_DPS()
    elif Horde_Role_Choice.lower() == 'c':
        Horde_Healer()
    else:
        print("\nNot enough data, taking you back a step")
        Horde_Class_Questions()



# THE HORDE TANK ROLE
def Horde_Tank():
    Orc_Warrior = 0
    Pandaren_Monk = 0

    print("\nYou have chosen the Tank role for the Horde.")
    YesOrNo = input("Is this what you wanted?  (Y/N)  ")
    if YesOrNo.lower() == 'y':
        print("Let's continue...\n")
    elif YesOrNo.lower() == 'n':
        print("Understood. Taking you back to role choice...\n")
        Horde_Class_Questions()
    else:
        print("Invalid input...\n")
        Horde_Tank()

        # Question 1 #
    question1_HordeTank = input("\nQuestion 1:\n"
                                "Which of these choices defines your tanking style best?\n"
                                "(a) Soak damage AND attack each enemy one at a time\n"
                                "(b) Soak damage AND apply status effects to groups of enemies\n"
                                "Choice: ")
    if question1_HordeTank.lower() == 'a':
        Orc_Warrior += 1
    elif question1_HordeTank.lower() == 'b':
        Pandaren_Monk += 1
    else:
        print("\nInvalid input, going back a step\n")
        Orc_Warrior = 0
        Pandaren_Monk = 0
        Horde_Tank()

        # Question 2 #
    question2_HordeTank = input("Question 2: \n"
                                "Do you prefer to...\n"
                                "(a) Have damage focused on you as you both you and your team attacks a common foe\n"
                                "(b) Have damage focused on you as you weaken your enemy and buff your allies\n"
                                "Choice: ")
    if question2_HordeTank.lower() == 'a':
        Orc_Warrior += 1
    elif question2_HordeTank.lower() == 'b':
        Pandaren_Monk += 1
    else:
        print("\nInvalid input, going back a step...\n")
        Orc_Warrior = 0
        Pandaren_Monk = 0
        Horde_Tank()

        # Question 3 #
    question3_HordeTank = input("Question 3: \n"
                                "Do you prefer gaining experience at an increased or regular rate when resting?\n"
                                "(a) Regular rate\n"
                                "(b) Increased rate\n"
                                "Choice: ")
    if question3_HordeTank.lower() == 'a':
        Orc_Warrior += 1
    elif question3_HordeTank.lower() == 'b':
        Pandaren_Monk += 1
    else:
        print("\nInvalid input, going back a step...\n")
        Orc_Warrior = 0
        Pandaren_Monk = 0
        Horde_Tank()

        # Results #
    if Orc_Warrior > Pandaren_Monk:
        print("\nYou should play as an ORC WARRIOR\n"
              "Orc warriors are capable of withstanding massive amounts of damage as well as\n"
              "stunning and breaking enemy defenses making them suitable for soaking and giving damage.\n")
        TryAgain()

    elif Pandaren_Monk > Orc_Warrior:
        print("\nYou should play as a PANDAREN MONK\n"
              "Pandaren Monks are a tough combination of healer and tank that are able to use buffs and debuffs\n"
              "to give themselves or their allies an edge in battle.\n")
        TryAgain()

    else:
        print("\nInconclusive amount of data. Going back a step...\n")
        Orc_Warrior = 0
        Pandaren_Monk = 0
        Horde_Tank()


# THE HORDE DPS ROLE
def Horde_DPS():
    Orc_Warrior = 0
    Goblin_Rogue = 0
    Pandaren_DeathKnight = 0
    Orc_Shaman = 0
    BloodElf_Mage = 0

    print("\nYou have chosen the DPS role for the Horde.")
    YesOrNo = input("Is this what you wanted? (Y/N)")
    if YesOrNo.lower() == "y":
        print("Let's continue...\n")
    elif YesOrNo.lower() == 'n':
        print("Understood. Going back to role choice...\n")
        Horde_Class_Questions()
    else:
        print("Invalid input...\n")
        Horde_DPS()

        # Question 1 #
    question1_HordeDPS = input("\nQuestion 1: \n"
                               "How would you describe your preferred method of attack?\n"
                               "(a) Heavy and all out\n"
                               "(b) Quick and quiet\n"
                               "(c) Through status effects\n"
                               "(d) Ranged and debuff enemies\n"
                               "(e) Ranged focusing on critical strikes\n"
                               "Choice: ")
    if question1_HordeDPS.lower() == 'a':
        Orc_Warrior += 1
    elif question1_HordeDPS.lower() == 'b':
        Goblin_Rogue += 1
    elif question1_HordeDPS.lower() == 'c':
        Pandaren_DeathKnight += 1
    elif question1_HordeDPS.lower() == 'd':
        Orc_Shaman += 1
    elif question1_HordeDPS.lower() == 'e':
        BloodElf_Mage += 1
    else:
        print("\nInvalid input, going back a step\n")
        Orc_Warrior = 0
        Goblin_Rogue = 0
        Pandaren_DeathKnight = 0
        Orc_Shaman = 0
        BloodElf_Mage = 0
        Horde_DPS()

        # Question 2 #
    question2_HordeDPS = input("\nQuestion 2: \n"
                               "What skills would you implement in your attack patterns?\n"
                               "(a) Stunning enemies and hitting them with heavy strikes\n"
                               "(b) Swiftly close in on a target and attack them unseen\n"
                               "(c) Put an enemy to sleep then strike them with heavy attacks\n"
                               "(d) Stay at a distance and focus on weakening your enemy\n"
                               "(e) Drain energy from your enemy and cast spells at a distance\n"
                               "Choice: ")
    if question2_HordeDPS.lower() == 'a':
        Orc_Warrior += 1
    elif question2_HordeDPS.lower() == 'b':
        Goblin_Rogue += 1
    elif question2_HordeDPS.lower() == 'c':
        Pandaren_DeathKnight += 1
    elif question2_HordeDPS.lower() == 'd':
        Orc_Shaman += 1
    elif question2_HordeDPS.lower() == 'e':
        BloodElf_Mage += 1
    else:
        print("\nInvalid input, going back a step\n")
        Orc_Warrior = 0
        Goblin_Rogue = 0
        Pandaren_DeathKnight = 0
        Orc_Shaman = 0
        BloodElf_Mage = 0
        Horde_DPS()

        # Question 3 #
    question3_HordeDPS = input("\nQuestion 3: \n"
                               "Where would your position be in a battle/raid?\n"
                               "(a) Front lines, tanking damage and striking first\n"
                               "(b) Away from the rest of the group, striking enemies silently\n"
                               "(c) Front lines casting status effects and using melee attacks\n"
                               "(d) Middle of the group, debuffing enemies and using ranged attacks\n"
                               "(e) In the middle, sapping enemies of their mana and using long ranged attacks\n"
                               "Choice: ")
    if question3_HordeDPS.lower() == 'a':
        Orc_Warrior += 1
    elif question3_HordeDPS.lower() == 'b':
        Goblin_Rogue += 1
    elif question3_HordeDPS.lower() == 'c':
        Pandaren_DeathKnight += 1
    elif question3_HordeDPS.lower() == 'd':
        Orc_Shaman += 1
    elif question3_HordeDPS.lower() == 'e':
        BloodElf_Mage += 1
    else:
        print("\nInvalid input, going back a step\n")
        Orc_Warrior = 0
        Goblin_Rogue = 0
        Pandaren_DeathKnight = 0
        Orc_Shaman = 0
        BloodElf_Mage = 0
        Horde_DPS()

        # Question 3 #
    if Orc_Warrior > Goblin_Rogue & Pandaren_DeathKnight & Orc_Shaman & BloodElf_Mage:
        print("\nYou should play as an ORC WARRIOR\n"
              "Orc warriors are capable of withstanding massive amounts of damage as well as\n"
              "stunning and breaking enemy defenses making them suitable for soaking and giving damage.\n")
        TryAgain()

    elif Goblin_Rogue > Orc_Warrior & Pandaren_DeathKnight & Orc_Shaman & BloodElf_Mage:
        print("\nYou should play as a GOBLIN ROGUE\n"
              "Goblin's ability to jump far distances makes for great swift damage classes.\n"
              "Combined with a rogue's high damage output, a goblin rogue makes for a fantastic dps.\n")
        TryAgain()

    elif Pandaren_DeathKnight > Orc_Warrior & Goblin_Rogue & Orc_Shaman & BloodElf_Mage:
        print("\nYou should play as a PANDAREN DEATH KNIGHT\n"
              "The Death Knight damage output combined with the buffs and other abilities from the\n"
              "Pandaren race are sure to make the Pandaren Death Knight a force to be reckoned with\n"
              "on the battlefield.\n")
        TryAgain()

    elif Orc_Shaman > Orc_Warrior & Goblin_Rogue & Pandaren_DeathKnight & BloodElf_Mage:
        print("\nYou should play as an ORC SHAMAN\n"
              "An Orc Shaman's ability to disable enemies as well as enchant weaponry and allies\n"
              "makes them a crucial part to any raid or PvP group considering their abilities of sabotage.\n")
        TryAgain()

    elif BloodElf_Mage > Orc_Warrior & Goblin_Rogue & Pandaren_DeathKnight & Orc_Shaman:
        print("\nYou should play as a BLOOD ELF MAGE\n"
              "Blood Elf Mages are caable of quickly restoring mana to themselves for quicker and longer-lasting\n"
              "damage from a distance, making Blood Elf Mages a good long range DPS character.\n")
        TryAgain()

    else:
        print("\nInconclusive amount of data. Going back a step...\n")
        Orc_Warrior = 0
        Goblin_Rogue = 0
        Pandaren_DeathKnight = 0
        Orc_Shaman = 0
        BloodElf_Mage = 0
        Horde_DPS()


# THE HORDE HEALER ROLE
def Horde_Healer():
    Undead_Warlock = 0
    Troll_Shamman = 0

    print("You have chosen the Healer role for the Horde.\n")
    YesOrNo = input("Is this what you wanted? (Y/N)\n"
                    "Choice: ")
    if YesOrNo == 'y':
        print("Let's continue...\n")
    elif YesOrNo == 'n':
        print("Understood. Going back to role choice...\n")
        Horde_Class_Questions
    else:
        print("Invalid input...\n")
        Horde_Healer

        # Question 1 #
    question1_HordeHealer = input("\nQuestion 1:\n"
                                  "How would you describe your healing style?\n"
                                  "(a) Direct healing\n"
                                  "(b) Indirect healing through area of effect\n"
                                  "Choice: ")
    if question1_HordeHealer.lower() == 'a':
        Undead_Warlock += 1
    elif question1_HordeHealer.lower() == 'b':
        Troll_Shamman += 1
    else:
        print("\nInvalid input, going back a step\n")
        Undead_Warlock = 0
        Troll_Shamman = 0
        Horde_Healer()

        # Question 2 #
    question2_HordeHealer = input("\nQuestion 2:\n"
                                  "You would prefer to...\n"
                                  "(a) Using the environment around me to create oppertunities and advantages\n"
                                  "(b) Use my own items/abilities to crate oppertunities and advantages for me\n"
                                  "Choice: ")
    if question2_HordeHealer.lower() == 'a':
        Undead_Warlock += 1
    elif question2_HordeHealer.lower() == 'b':
        Troll_Shamman += 1
    else:
        print("\nInvalid input, going back a step\n")
        Undead_Warlock = 0
        Troll_Shamman = 0
        Horde_Healer()

        # Question 3 #
    question3_HordeHealer = input("\nQuestion 3:\n"
                                  "How would you describe your attacking style?\n"
                                  "(a) From a distance\n"
                                  "(b) Up close witht the help of buffs and debuffs\n"
                                  "Choice: ")
    if question3_HordeHealer.lower() == 'a':
        Undead_Warlock += 1
    elif question3_HordeHealer.lower() == 'b':
        Troll_Shamman += 1
    else:
        print("\nInvalid input, going back a step\n")
        Undead_Warlock = 0
        Troll_Shamman = 0
        Horde_Healer()

    if Undead_Warlock > Troll_Shamman:
        print("\nYou should play as an UNDEAD WARLOCK\n"
              "Undead Warlocks have the ability to suck the health and mana out of dead bodies\n"
              "around them, making them great healers for large raids with smaller/weaker mobs.\n")
        TryAgain()

    elif Troll_Shamman > Undead_Warlock:
        print("\nYou should play as TROLL SHAMAN\n"
              "Troll Shamans can heal party members over large distances with the uses of healing\n"
              "totems they can summon. Thi smakes them ideal for both raids and PvP quests.")
        TryAgain()

    else:
        print("\nInconclusive amount of data. Going back a step...\n")
        Undead_Warlock = 0
        Troll_Shamman = 0
        Horde_Healer()


################################## Faction Question #######################################

def Faction_Choice():
    print("\nThe World of Warcraft Character Chooser Quiz\nA Python Program by Derrick Demers")
    faction_question = input("\nIn the World of Warcraft, there are two sides:\n\n"
                             "The Alliance: \n"
                             "The Alliance consists of powerful cultures and peoples that are loyal to the alliance \n"
                             "by their deep commitments to the concepts of justice and nobility.  The races and \n"
                             "members of the Alliance are all courageous and noble and do all they can to preserve \n"
                             "order in the land of Azeroth. The Alliance are led by their king, High King \n "
                             "Anduin Wrynn son of the fallen Varian Wrynn. \n\n"
                             "The Horde: \n"
                             "The Horde is a faction led by a conglomerate of outsiders and survivors of prejudices \n"
                             "who have overcome obstacles by creating bonds with each other, fighting together as \n"
                             "family or comrades, or creating uneasy alliances. The Horde is currently under command \n"
                             "by the current Warchief Slyvanas Windrunner, a Forsaken \n"
                             "(currently undead, previously High Elf).\n\n"
                             "So new player, which faction will you choose?\n"
                             "(a) Alliance\n"
                             "or\n"
                             "(b) Horde\n"
                             "(q) Exit the program\n")

    if faction_question.lower() == 'a':
        Alliance_Class_Questions()

    elif faction_question.lower() == 'b':
        Horde_Class_Questions()

    elif faction_question.lower() == 'q':
        print("\nThank you for using the program\n"
              "Farewell, adventurer...\n")
        return

    else:
        print("\nInvalid input, please try again...")
        Faction_Choice()


################################## Where the program begins #######################################

Faction_Choice()