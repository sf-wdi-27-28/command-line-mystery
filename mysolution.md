# change to mystery subdirectory
cd mystery

# read crimescene reports
cat crimescene

# search for keyword "CLUE"
grep "CLUE" crimescene --context=2

# found following
Crime Scene Report #912464709392
********
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.


--
--
Crime Scene Report #028615332953
********
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.


--
--
Crime Scene Report #575776622208
********
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

# look for Annabel in people
$ grep Annabel people

# found following
Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M	40	Haley Street, line 176


# look under streets, for Hart_Place, line 40
$ head -n 40 Hart_Place

# found
SEE INTERVIEW #47246024

# looked into interview #47246024
$ cat interview-47246024

# found
Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe


# look under streets, for Buckingham_Place, line 179
  $ head -n 179 Buckingham_Place

# found
SEE INTERVIEW #699607


# looked into interview #699607
$ cat interview-699607

#found following
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

# looked in vehicles for L337
grep -A 5 "L337" vehicles

# found License Plate L337ZR9
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


# for the people who are male, with blue Honda, and taller than 6' - look to see who has all 4 memberships
$ cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library | grep "Jeremy Bowers"
$ cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library | grep "Joe Germuska"
$ cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library | grep "Jacqui Maher"


# found that Jacqui Maher and Jeremy Bowers are the only ones with all 4 memberships

# looked in people to confirm sex of Jacqui
 $ grep Jacqui people

#confirmed Jacqui is female - therefore Jeremy Bowers is the one!
