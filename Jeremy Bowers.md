```zsh
# Clone the initial repository
git clone git@github.com:eerwitt/command-line-mystery.git
cd command-line-mystery

# Check the status to see if anything is already marked as new (shouldn't be)
git status

# Edit my solution file
subl solution.md

# Commit initial solution
git add solution.md
git commit -a

# Start reading the instructions
less instructions

# Check for clues in the mystery
cd mystery
grep CLUE ./crimescene

Joanne-Abads-MacBook-Pro:mystery abadjoanne$ grep "CLUE" crimescene
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

# Search for person with the Latte
grep Annabel ./people

Joanne-Abads-MacBook-Pro:mystery abadjoanne$ grep -c "Annabell" *
crimescene:0
grep: interviews: Is a directory
grep: memberships: Is a directory
people:0
grep: streets: Is a directory
vehicles:0

# Knock on her door
less streets/Mattapan_Street
# Goto line in file using less: http://stackoverflow.com/questions/8586648/going-to-a-specific-line-number-using-less-in-unix
# in less type 173g
# Try different interviews
less interviews/interview-47246024
less interviews/interview-699607

Joanne-Abads-MacBook-Pro:mystery abadjoanne$ head -n 173 streets/Mattapan_Street | tail -n 1
SEE INTERVIEW #9437737
Joanne-Abads-MacBook-Pro:mystery abadjoanne$ ls
crimescene	interviews	memberships	people		streets		vehicles
Joanne-Abads-MacBook-Pro:mystery abadjoanne$ open interviews
interview-47246024
Doesn't appear to be the witness from the cafe, who is female.
interview-699607
Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"


# Checking for vehicle
less vehicles
# Search in less for vehicles starting with L337 and ending in 9
# in less /L337..9
# Check which are over 6'
# Katie Park
# Mike Bostock
# John Keefe
# Erika Owens
# Matt Waite
# Brian Boyer
# Al Shaw
# Miranda Mulligan
# Joe Germuska
# Jeremy Bowers
# Jacqui Maher

Joanne-Abads-MacBook-Pro:mystery abadjoanne$ grep -r "L337" vehicles
vehicles:License Plate L337ZR9
vehicles:License Plate L337P89
vehicles:License Plate L337GX9
vehicles:License Plate L337QE9
vehicles:License Plate L337GB9
vehicles:License Plate L337OI9
vehicles:License Plate L337X19
vehicles:License Plate L337539
vehicles:License Plate L3373U9
vehicles:License Plate L337369
vehicles:License Plate L337DV9
vehicles:License Plate L3375A9
vehicles:License Plate L337WR9

Joanne-Abads-MacBook-Pro:mystery abadjoanne$ grep -A 5 "L337" vehicles
License Plate L337ZR9
Make: Honda
Color: Red
Owner: Katie Park
Height: 6'2"
Weight: 189 lbs
--
License Plate L337P89
Make: Honda
Color: Teal
Owner: Mike Bostock
Height: 6'4"
Weight: 173 lbs
--
License Plate L337GX9
Make: Mazda
Color: Orange
Owner: John Keefe
Height: 6'4"
Weight: 185 lbs
--
License Plate L337QE9
Make: Honda
Color: Blue
Owner: Erika Owens
Height: 6'5"
Weight: 220 lbs
--
License Plate L337GB9
Make: Toyota
Color: Blue
Owner: Matt Waite
Height: 6'1"
Weight: 190 lbs
--
License Plate L337OI9
Make: Jaguar
Color: Blue
Owner: Brian Boyer
Height: 6'6"
Weight: 201 lbs
--
License Plate L337X19
Make: Fiat
Color: Blue
Owner: Al Shaw
Height: 6'5"
Weight: 240 lbs
--
License Plate L337539
Make: Honda
Color: Blue
Owner: Aron Pilhofer
Height: 5'3"
Weight: 198 lbs
--
License Plate L3373U9
Make: Ford
Color: Blue
Owner: Miranda Mulligan
Height: 6'6"
Weight: 156 lbs
--
License Plate L337369
Make: Honda
Color: Blue
Owner: Heather Billings
Height: 5'2"
Weight: 244 lbs
--
License Plate L337DV9
Make: Honda
Color: Blue
Owner: Joe Germuska
Height: 6'2"
Weight: 164 lbs
--
License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs
--
License Plate L337WR9
Make: Honda
Color: Blue
Owner: Jacqui Maher
Height: 6'2"
Weight: 130 lbs

# Check which is male/female and get their names
egrep '((Katie Park)|(Mike Bostock)|(John Keefe)|(Erika Owens)|(Matt Waite)|(Brian Boyer)|(Al Shaw)|(Miranda Mulligan)|(Joe Germuska)|(Jeremy Bowers)|(Jacqui Maher))' ./people | grep '\tM\t' | cut -f1

Joanne-Abads-MacBook-Pro:mystery abadjoanne$ egrep '((Katie Park)|(Mike Bostock)|(John Keefe)|(Erika Owens)|(Matt Waite)|(Brian Boyer)|(Al Shaw)|(Miranda Mulligan)|(Joe Germuska)|(Jeremy Bowers)|(Jacqui Maher))' ./people | grep '\tM\t' | cut -f1
Joe Germuska
Brian Boyer
Mike Bostock
Jeremy Bowers
John Keefe
Al Shaw
Matt Waite

# Limit down by membership
egrep -R '((Joe Germuska)|(Brian Boyer)|(Mike Bostock)|(Jeremy Bowers)|(John Keefe)|(Al Shaw)|(Matt Waite))' ./memberships

Joanne-Abads-MacBook-Pro:mystery abadjoanne$ egrep -R '((Joe Germuska)|(Brian Boyer)|(Mike Bostock)|(Jeremy Bowers)|(John Keefe)|(Al Shaw)|(Matt Waite))' ./memberships
./memberships/AAA:Al Shaw
./memberships/AAA:Joe Germuska

./memberships/AAA:Jeremy Bowers

./memberships/AAA:John Keefe
./memberships/AAA:Matt Waite
./memberships/AAA:Brian Boyer
./memberships/AAA:Mike Bostock
./memberships/Delta_SkyMiles:Matt Waite
./memberships/Delta_SkyMiles:Mike Bostock
./memberships/Delta_SkyMiles:Brian Boyer

./memberships/Delta_SkyMiles:Jeremy Bowers

./memberships/Museum_of_Bash_History:Jeremy Bowers

./memberships/Museum_of_Bash_History:Brian Boyer
./memberships/Museum_of_Bash_History:Matt Waite
./memberships/Museum_of_Bash_History:Mike Bostock
./memberships/Terminal_City_Library:Joe Germuska
./memberships/Terminal_City_Library:John Keefe
./memberships/Terminal_City_Library:Matt Waite

./memberships/Terminal_City_Library:Jeremy Bowers

./memberships/Terminal_City_Library:Mike Bostock
./memberships/Terminal_City_Library:Al Shaw
./memberships/Terminal_City_Library:Brian Boyer

# (Jeremy Bowers)|(Brian Boyer)|(Mike Bostock)|(Matt Waite)
# Not MB, wrong car color
# Not MW, wrong car manufacturer
# Not BB, wrong car manufacturer
# JB, it is JB
```
