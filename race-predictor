'''
Use this python code to predict future race times when given a past race time. It uses the formula found on the NYRR website: https://www.nyrr.org/new-race-procedures/calculated-pace-and-corral-updates
'''


# Create race menus and initialize variables
race_menu = ["Marathon","Half Marathon","10K","5K","Mile","Other"]
race_distance_menu = [42195, 21097.5,10000,5000,1609.34]
distance = 6
target_distance = 6
printable_time = []

# Ask for original race distance
while distance > 5:
  distance = int(input("What is the most recent race that you've run?\nSelect from the following options: \n [0] Marathon\n [1] Half Marathon\n [2] 10K\n [3] 5K\n [4] Mile\n [5] Other\n Your Choice: "))
  if distance > 5:
    print("Your selection was invalid; please try again.")

# If non-standard race, get distance and ask for time
if distance == 5:
  d1 = int(input("You have selected other.\nPlease input your race distance in meters: "))

  print("\nWhat was your most recent time for the " + str(d1) + "-meter race?")
  hours = int(input("Hours: "))
  minutes = int(input("Minutes: "))
  seconds = int(input("Seconds: "))

# If standard race, get distance and ask for time
else:
  d1 = race_distance_menu[distance]
  # Ask for time
  print("\nWhat was your most recent time for the " + race_menu[distance] + "?")
  hours = int(input("Hours: "))
  minutes = int(input("Minutes: "))
  seconds = int(input("Seconds: "))

# Calculate original time in seconds
t1 = hours*3600 + minutes*60 + seconds

# Ask for target race
while target_distance > 5:
  target_distance = int(input("What race are you planning to run?\nSelect from the following options: \n [0] Marathon\n [1] Half Marathon\n [2] 10K\n [3] 5K\n [4] Mile\n [5] Other\n Your Choice: "))
  if target_distance >5:
    print("Your selection was invalid; please try again.")

# Get target distance if it's not a pre-populated option, otherwise, grab the pre-populated distance in meters
if target_distance == 5:
  d2 = int(input("You have selected other.\nPlease input your target race distance in meters: "))
else:
  d2 = race_distance_menu[target_distance]
  
# Make prediction
t2 = t1 * (d2/d1) ** 1.06

# Get hours, minutes, and seconds of prediction
target_hours = divmod(t2,3600)
target_minutes = divmod(target_hours[1],60)
target_seconds = target_minutes[1]

# Reset target times to whole numbers
target_hours = round(target_hours[0])
target_minutes = round(target_minutes[0])
target_seconds = round(target_seconds)

# Give target time to user
print("Your target time in the " + race_menu[target_distance] + " is " + str(target_hours) + ":" + str(target_minutes) + ":" + str(target_seconds) + ". Good luck!")
