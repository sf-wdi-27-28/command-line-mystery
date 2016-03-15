
# Fork repo and clone it to wdi folder
git clone git@github.com:hermchan/command-line-mystery.git
cd command-line-mystery

# Checked what other files are in command-line-mystery
ls

# Created a new file called mysolution.md
touch mysolution.md

# Opened instructions
less instructions

# Opened up cheatsheet.md
less cheatsheet.md

# Opened up hint1 hint8
less hint

# Check for clues
grep "CLUE" crimescene
# potential clue, barista noticed woman, name on latte was Annabel
# Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.

# Search for a female by the name of Annabel
grep "Annabel" people

# Search the address for each Annabel to look for clues
head -40 ./streets/Hart_Place
SEE INTERVIEW #47246024

head -173 ./streets/Mattapan_Street
SEE INTERVIEW #9437737

head -179 ./streets/Buckingham_Place
SEE INTERVIEW #699607

head -176 ./streets/Haley_Street
SEE INTERVIEW #871877

# Goto inteviews directory
cd /users/book/wdi/command-line-mystery/mystery/interviews/
ls

# Open interview-47246024
less interview-47246024
#"Ms. Sun has brown hair and is not from New Zealand. Not the witness from the cafe."

# Open interview-9437737
less interview-9437737
#Doesn't appear to be the witness from the cafe, who is female.

# Open interview-699607
less interview-699607
#"Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.
#However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9""

# Check each license plate with L337 vehicles
less vehicles
grep -i L33 vehicles
#License Plate L337ZR9
#License Plate L337P89
#License Plate L337GX9
#License Plate L337QE9
#License Plate L337GB9
#License Plate L337OI9
#License Plate L337X19
#License Plate L337539
#License Plate L3373U9
#License Plate L337369
#License Plate L337DV9
#License Plate L3375A9
#License Plate L337WR9

# Searching for vehicles where owner is taller than 6' and blue Honda

grep -A 5 "L337ZR9" vehicles
#License Plate L337ZR9
#Make: Honda
#Color: Red
#Owner: Katie Park
#Height: 6'2"
#Weight: 189 lbs

grep -A 5 "L337P89" vehicles
#License Plate L337P89
#Make: Honda
#Color: Teal
#Owner: Mike Bostock
#Height: 6'4"
#Weight: 173 lbs

grep -A 5 "L337GX9" vehicles
#License Plate L337GX9
#Make: Mazda
#Color: Orange
#Owner: John Keefe
#Height: 6'4"
#Weight: 185 lbs

grep -A 5 "L337QE9" vehicles
#License Plate L337QE9
#Make: Honda
#Color: Blue
#Owner: Erika Owens
#Height: 6'5"
#Weight: 220 lbs

grep -A 5 "L337GB9" vehicles
#License Plate L337GB9
#Make: Toyota
#Color: Blue
#Owner: Matt Waite
#Height: 6'1"
#Weight: 190 lbs

grep -A 5 "L337OI9" vehicles
#License Plate L337OI9
#Make: Jaguar
#Color: Blue
#Owner: Brian Boyer
#Height: 6'6"
#Weight: 201 lbs

grep -A 5 "L337X19" vehicles
#License Plate L337X19
#Make: Fiat
#Color: Blue
#Owner: Al Shaw
#Height: 6'5"
#Weight: 240 lbs

grep -A 5 "L337539" vehicles
#License Plate L337539
#Make: Honda
#Color: Blue
#Owner: Aron Pilhofer
#Height: 5'3"
#Weight: 198 lbs

grep -A 5 "L3373U9" vehicles
#License Plate L3373U9
#Make: Ford
#Color: Blue
#Owner: Miranda Mulligan
#Height: 6'6"
#Weight: 156 lbs

grep -A 5 "L337369" vehicles
#License Plate L337369
#Make: Honda
#Color: Blue
#Owner: Heather Billings
#Height: 5'2"
#Weight: 244 lbs

grep -A 5 "L337DV9" vehicles
#License Plate L337DV9
#Make: Honda
#Color: Blue
#Owner: Joe Germuska
#Height: 6'2"
#Weight: 164 lbs

grep -A 5 "L3375A9" vehicles
#License Plate L3375A9
#Make: Honda
#Color: Blue
#Owner: Jeremy Bowers
#Height: 6'1"
#Weight: 204 lbs

grep -A 5 "L337WR9" vehicles
#License Plate L337WR9
#Make: Honda
#Color: Blue
#Owner: Jacqui Maher
#Height: 6'2"
#Weight: 130 lbs

# Caneled out those who are not taller than 6' and does not drive a Blue Honda
# Check membership and entire directory based on potential suspects (Maher, Bowers, Germuska, Owens)
grep -r "Owens" *
# Owens is not a suspect and does not have suspects membership cards

grep -r "Maher" *
# Maher is not a suspect

grep -r "Germuska" *
# Germuska is not a suspect and does not have suspects membership cards

grep -r "Bowers" *
# Jermey Bowers is the suspect
