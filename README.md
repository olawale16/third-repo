# CGPA Calculator with text reader
import pyttsx3

player= pyttsx3.init()



grade = {"A": 5, "B": 4, "C": 3, "D": 2, "E": 1, "F": 0}
courseName = ""
Tot = int(input("Enter Total Course Unit:"))
score = 0
total = 0
cgpa = 0
units = 0

print(f"{units} units {score} scores")


while True:
    
    print(Tot)
    unit = int(input("Enter course credit: "))
    name = input("Enter course grade: ").upper()
    if name in grade:
        m = unit * grade[name]
        units += unit
        score += m
        total = score/Tot
        print(f"{units} units {score} scores")
        print(total)

    if units == Tot:
        cgpa = total
        print(f"{units} units {score} scores")
        print("Your CGPA for this session: ", cgpa)
        player.say(f"Your CGPA for this session: {cgpa}")
        if cgpa >= 4.5:
            print("First Class")
            player.say("First Class")
            break
        elif cgpa <= 4.9 and cgpa >= 3.5:
            print("Second Class Upper")
            player.say("Second Class Upper")
            break
            
        elif cgpa >= 2.40 and cgpa <= 3.49:
            print("Second Class Lower")
            player.say("Second Class Lower")
            break
        elif cgpa >= 1.50 and cgpa <= 2.39:
            print("Third Class")
            player.say("Third Class")
            break
            
        else:
            print("Kindly meet your HOD")
            player.say("Kindly meet your Head Of Department")
            break
                                      

player.runAndWait()
