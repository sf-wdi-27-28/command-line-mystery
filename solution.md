# read instructions
cat instructions

# go to mystery subdirectory
cd mystery

# all clues are marked with "CLUE" so use a grep command to search each directory in the mystery directory
grep "CLUE" crimescene

# suspect is Male; over 6'; membership cards for "AAA", "Delta_SkyMiles", "Library", and "Museum_of_Bash_History"

# first real witness is Annabel, a female, search people for that name
grep "Annabel" people

#only two of the four were female. Searched adresses in streets
cd streets
cat Hart_Place
cat Buckingham_Place

# also gave me line numbers to search, assuming in streets
# line 40 for Hart and 179 for Buckingham

# used hint5 to find out how to search for specific line numbers in a file
head -n 40 streets/Hart_Place | tail -n 1
head -n 179 streets/Buckingham_Place | tail -n 1

# these returned interview numbers
# search interviews for the first from Hart_Place
cat interview-47246024

# first is not the witness from the cafe
#search interviews for the second form Buckingham_Place
cat interview-699607

# AHA the witness. Saw a BLUE HONDA, with LISCENSE PLATE that starts with "L337" and ends with "9"

# time to grep vehcles for "L337"
grep "L337" vehicles

# didnt help, only showed 9 liscense numbers
# hint7 said to use the "A" option with grep
grep -A 5 "L337" mystery/vehicles

# decided to try and ad a pipe after that to filter out "Blue" cars
grep -A 5 "L337" mystery/vehicles | grep -A 7 "Blue"

# seemed to work, scrolled through and wrote down all the male names
# Jeremy Bowers
# Joe Germuska
# Aron Pilhofer 
# Al Shaw
# Brian Boyer
# Matt Waite

# Then looked at the car makes since we know its a honda
# only 3 had hondas
# Jeremy Bowers - Honda
# Joe Germuska - Honda
# Aron Pilhofer - Honda

# looked at their heights, only two are over 6' like the culprit
# Jeremy Bowers
# Joe Germuska

# now use the names to search for memberships
# going to cat each of the memberships together and pipe it into a grep for the persons name. the person who is a member of all 4 is the culrpit
cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History | grep "persons name"

# Jeremy Bowers is a member of all 4 therefore is the culprit.















