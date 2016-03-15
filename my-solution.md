touch my-solution.md

atom my-solution.md

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


less people
#look inside file

grep "Annabel" ./people
#Find witness "Annabel"
results:
Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M	40	Haley Street, line 176

cd interviews

grep -C 4 "Annabel" ./vehicles
License Plate 9R7TTGF
Make: Volkswagen
Color: Yellow
Owner: Oluwasegun Annabel
Height: 5'1"
Weight: 240 lbs

License Plate HSY9IQ3
--
--

License Plate L2E48EF
Make: BMW
Color: Orange
Owner: Annabel Church
Height: 5'5"
Weight: 201 lbs

License Plate 8VE37YH
--
--

License Plate 0O27BTD
Make: Fiat
Color: Yellow
Owner: Annabel Sun
Height: 5'0"
Weight: 232 lbs

License Plate Y2O255D
--
--

License Plate 20VVU2P
Make: Mazda
Color: Pink
Owner: Annabel Fuglsang
Height: 5'11"
Weight: 241 lbs

License Plate RIGMSHY

head people

head -40 ./streets/Hart_Place
SEE INTERVIEW #47246024
less ./interviews/interview-47246024
Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.


head -173 ./streets/Mattapan_Street
SEE INTERVIEW #9437737
less ./interviews/interview-9437737
Doesn't appear to be the witness from the cafe, who is female.


head -179 ./streets/Buckingham_Place
SEE INTERVIEW #699607
less ./interviews/interview-699607
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"
#Witness

head -176 ./streets/Haley_Street
SEE INTERVIEW #871877
less ./interviews/interview-871877
Mr. Fuglsang is male and has brown hair.  Not the witness from the cafe.

head -20 ./vehicles

grep -A 5 -i "L337..9" ./vehicles
License Plate L337QE9
Make: Honda
Color: Blue
Owner: Erika Owens
Height: 6'5"
Weight: 220 lbs
grep "Erika" ./people
#Female not her

License Plate L337DV9
Make: Honda
Color: Blue
Owner: Joe Germuska
Height: 6'2"
Weight: 164 lbs
grep "Germuska" ./people
#male
grep -r "Germuska" ./memberships
./memberships/AAA:Joe Germuska
./memberships/Terminal_City_Library:Joe Germuska
vehicles:Owner: Joe Germuska


License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs
#male
grep -r "Bowers" ./memberships
./memberships/AAA:Jeremy Bowers
./memberships/Delta_SkyMiles:Jeremy Bowers
./memberships/Museum_of_Bash_History:Jeremy Bowers
./memberships/Terminal_City_Library:Jeremy Bowers

--
License Plate L337WR9
Make: Honda
Color: Blue
Owner: Jacqui Maher
Height: 6'2"
Weight: 130 lbs
grep "Jacqui" ./people
#Female
