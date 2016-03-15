# Perpetrator is JEREMY BOWERS

#PROCESS

cd ~
cd wdi/command-line-mystery/
cat instructions
cd mystery
grep CLUE crimescene
# got:
#CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
#CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
#CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

grep Annabel people
# got:
#Annabel Sun	F	26	Hart Place, line 40
#Oluwasegun Annabel	M	37	Mattapan Street, line 173
#Annabel Church	F	38	Buckingham Place, line 179
#Annabel Fuglsang	M	40	Haley Street, line 176

less streets/Hart_Place
# Noticed SEE INTERVIEW marking

grep INTERVIEW streets/Hart_Place
# SEE INTERVIEW #47246024

cd interviews
ls
less interview-47246024
#Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.

cd ..
grep INTERVIEW streets/Mattapan_Street
#SEE INTERVIEW #9437737

less interviews/interview-9437737
#Doesn't appear to be the witness from the cafe, who is female.

grep INTERVIEW streets/Buckingham_Place
#SEE INTERVIEW #699607
#Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.
#However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

grep -A 5 "L337" vehicles
#License Plate L337ZR9
#Make: Honda
#Color: Red
#Owner: Katie Park
#Height: 6'2"
#Weight: 189 lbs
#--
#License Plate L337P89
#Make: Honda
#Color: Teal
#Owner: Mike Bostock
#Height: 6'4"
#Weight: 173 lbs
#--
#License Plate L337GX9
#Make: Mazda
#Color: Orange
#Owner: John Keefe
#Height: 6'4"
#Weight: 185 lbs
#--
#License Plate L337QE9
#Make: Honda
#Color: Blue
#Owner: Erika Owens
#Height: 6'5"
#Weight: 220 lbs
#--
#License Plate L337GB9
#Make: Toyota
#Color: Blue
#Owner: Matt Waite
#Height: 6'1"
#Weight: 190 lbs
#--
#License Plate L337OI9
#Make: Jaguar
#Color: Blue
#Owner: Brian Boyer
#Height: 6'6"
#Weight: 201 lbs
#--
#License Plate L337X19
#Make: Fiat
#Color: Blue
#Owner: Al Shaw
#Height: 6'5"
#Weight: 240 lbs
#--
#License Plate L337539
#Make: Honda
#Color: Blue
#Owner: Aron Pilhofer
#Height: 5'3"
#Weight: 198 lbs
#--
#License Plate L3373U9
#Make: Ford
#Color: Blue
#Owner: Miranda Mulligan
#Height: 6'6"
#Weight: 156 lbs
#--
#License Plate L337369
#Make: Honda
#Color: Blue
#Owner: Heather Billings
#Height: 5'2"
#Weight: 244 lbs
#--
#License Plate L337DV9
#Make: Honda
#Color: Blue
#Owner: Joe Germuska
#Height: 6'2"
#Weight: 164 lbs
#--
#License Plate L3375A9
#Make: Honda
#Color: Blue
#Owner: Jeremy Bowers
#Height: 6'1"
#Weight: 204 lbs
#--
#License Plate L337WR9
#Make: Honda
#Color: Blue
#Owner: Jacqui Maher
#Height: 6'2"
#Weight: 130 lbs

egrep '((Katie Park)|(Mike Bostock)|(John Keefe)|(Erika Owens)|(Matt Waite)|(Brian Boyer)|(Al Shaw)|(Miranda Mulligan)|(Joe Germuska)|(Jeremy Bowers)|(Jacqui Maher))' ./people | grep '\tM\t' | cut -f1
#Joe Germuska
#Brian Boyer
#Mike Bostock
#Jeremy Bowers
#John Keefe
#Al Shaw
#Matt Waite

egrep -R '((Joe Germuska)|(Brian Boyer)|(Mike Bostock)|(Jeremy Bowers)|(John Keefe)|(Al Shaw)|(Matt Waite))' ./memberships
#/memberships/AAA:Al Shaw
#./memberships/AAA:Joe Germuska
#./memberships/AAA:Jeremy Bowers
#./memberships/AAA:John Keefe
#./memberships/AAA:Matt Waite
#./memberships/AAA:Brian Boyer
#./memberships/AAA:Mike Bostock
#./memberships/Delta_SkyMiles:Matt Waite
#./memberships/Delta_SkyMiles:Mike Bostock
#./memberships/Delta_SkyMiles:Brian Boyer
#./memberships/Delta_SkyMiles:Jeremy Bowers
#./memberships/Museum_of_Bash_History:Jeremy Bowers
#./memberships/Museum_of_Bash_History:Brian Boyer
#./memberships/Museum_of_Bash_History:Matt Waite
#./memberships/Museum_of_Bash_History:Mike Bostock
#./memberships/Terminal_City_Library:Joe Germuska
#./memberships/Terminal_City_Library:John Keefe
#./memberships/Terminal_City_Library:Matt Waite
#./memberships/Terminal_City_Library:Jeremy Bowers
#./memberships/Terminal_City_Library:Mike Bostock
#./memberships/Terminal_City_Library:Al Shaw
#./memberships/Terminal_City_Library:Brian Boyer

# JEREMY BOWERS IS ONLY SUSPECT THAT MATCHES ALL MEMBERSHIPS.
