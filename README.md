# user-Saranya.github.io
class Car1:
    num_pass1 = 0

    def __int__(self, name):
        self.name = name

    def seat_allotment(self):
        if self.num_pass1 < 5:
            print("Allotted seat in car. Car ID is 1.")
            self.num_pass1 += 1


class Car2:
    num_pass2 = 0

    def __int__(self, name):
        self.name = name

    def seat_allotment(self):
        if self.num_pass2 < 5:
           print("Allotted seat in car. Car ID is 2.")
           self.num_pass2 += 1


class Bus:
    num_pass3 = 0
    num_pass4 = 0
    def __int__(self, name):
        self.name = name
    def seating_allotment(self):
        if self.num_pass3 < 25:
            print("Allotted a sitting seat in bus.")
            self.num_pass3 += 1
        elif (self.num_pass3 == 25) and (self.num_pass4 < 15):
            print("Allotted a standing seat in bus.")
            self.num_pass4 += 1


char = input("Which character do you want? ")
if char == "A" :
    if Car1.num_pass1 < 5:
        Car1.seat_allotment()
    elif (Car1.num_pass1 == 5) and (Car2.num_pass2 < 5):
        Car2.seat_allotment()

elif char == "B" :
    Bus.seating_allotment()

elif char == "C" :
    import random
    val = random.random()
    if val <= 0.6:
         if Bus.num_pass4 > 0:
             Bus.num_pass4 -= 1
             print("A passenger was removed from Bus.")
         elif (Bus.num_pass4 == 0) and (Bus.num_pass3 > 0):
             Bus.num_pass3 -= 1
             print("A passenger was removed from Bus.")
         elif (Bus.num_pass4 == 0) and (Bus.num_pass3 == 0):
             print("No passenger was removed.")

    elif val <= 0.8:
         if Car1.num_pass1 > 0:
             Car1.num_pass1 -= 1
             print("A passenger is removed from Car with ID 1.")
         else:
             print("No passenger was removed.")

    else:
         if Car2.num_pass2 > 0:
             Car2.num_pass2 -= 1
             print("A passenger is removed from Car with ID 2.")
         else:
             print("No passenger was removed.")

else:quit()
