
import random

def juego(characters):
    list_characters=[]
    character=""
    
    while len(list_characters) != characters:
        character=input("Introduce un personaje:")
        list_characters.append(character)

    def days(number):
        print("Día"+str(number))
    
    def death(count):
        if count != 1:
            death_character=random.choice(list_characters)
            print(f"{random.choice(list_characters)} ha visto un animal")
            print(f"{random.choice(list_characters)} ha encontrando algo")
            print(f"{death_character} ha muerto")
            list_characters.remove(death_character)
            print(f"jugadores restantes:{len(list_characters)}")
            return list_characters,death_character
    
    day=0
    
    while len(list_characters) != 1:
        day+=1
        days(day)
        death(len(list_characters))
        
    if len(list_characters) == 1:
        print("El ganador es {}".format(list_characters))

   
juego(int(input("Cuantos participantes deseas?")))
