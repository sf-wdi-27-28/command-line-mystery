touch my-solution.md

atom my-solution.md

cd mystery

grep "CLUE" ./crimescene
#Finds clues
*******
Crime Scene Report #912464709392
********
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
*******
Crime Scene Report #028615332953
********
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
*******
Crime Scene Report #575776622208
********
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.


head people
#look inside file of people to see what is listed

grep "Annabel" ./people
#Find witness "Annabel"
results:
Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M	40	Haley Street, line 176

head -40 ./streets/Hart_Place
# Annabel Sun's address; bottom line is the identified line
SEE INTERVIEW #47246024
less ./interviews/interview-47246024
# Annabel Sun's interview
Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.


head -173 ./streets/Mattapan_Street
# Oluwasegun Annabel's address; bottom line is the identified line
SEE INTERVIEW #9437737
less ./interviews/interview-9437737
# Oluwasegun Annabel's interview
Doesn't appear to be the witness from the cafe, who is female.

head -179 ./streets/Buckingham_Place
# Annabel Church's address; bottom line is the identified line
SEE INTERVIEW #699607
less ./interviews/interview-699607
# Annabel Church's interview
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"
# Annabel Church was the Witness

head -176 ./streets/Haley_Street
# Annabel Fuglsang's address; bottom line is the identified line
SEE INTERVIEW #871877
less ./interviews/interview-871877
# Annabel Fuglsang's interview
Mr. Fuglsang is male and has brown hair.  Not the witness from the cafe.

head -20 ./vehicles
# peak inside vehicle file

grep -A 5 -i "L337..9" ./vehicles
# list vehicles from Annabel's description, pulling five lines after each plate number for information on the make, model, and owner (only pasted blue hondas, and people matching height)
License Plate L337QE9
Make: Honda
Color: Blue
Owner: Erika Owens
Height: 6'5"
Weight: 220 lbs
grep "Erika" ./people
#Check gender-Female not her

License Plate L337DV9
Make: Honda
Color: Blue
Owner: Joe Germuska
Height: 6'2"
Weight: 164 lbs
grep "Germuska" ./people
#Check gender-male
grep -r "Germuska" ./memberships
# View Germuska Memeberships
./memberships/AAA:Joe Germuska
./memberships/Terminal_City_Library:Joe Germuska
vehicles:Owner: Joe Germuska


License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs
#Check gender-male
grep -r "Bowers" ./memberships
# View Bowers Memeberships
./memberships/AAA:Jeremy Bowers
./memberships/Delta_SkyMiles:Jeremy Bowers
./memberships/Museum_of_Bash_History:Jeremy Bowers
./memberships/Terminal_City_Library:Jeremy Bowers
#Bowers memberships match up, suspected killer

--
License Plate L337WR9
Make: Honda
Color: Blue
Owner: Jacqui Maher
Height: 6'2"
Weight: 130 lbs
grep "Jacqui" ./people
#Check gender-Female

Suspected killer is Jeremy Bowers
