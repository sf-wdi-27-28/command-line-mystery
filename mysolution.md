cd mystery
ls
cat crimescene
grep CLUE crimescene -- C
	crimescene:CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
	crimescene:CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
	crimescene:CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.
cat people
grep Annabel people -- C
	people:Annabel Sun	F	26	Hart Place, line 40
	people:Oluwasegun Annabel	M	37	Mattapan Street, line 173
	people:Annabel Church	F	38	Buckingham Place, line 179
	people:Annabel Fuglsang	M	40	Haley Street, line 176
cd streets
ls
	//shows what's inside streets
cd ..
head -n 40 streets/Hart_Place | tail -n 1
	//SEE INTERVIEW #47246024
cd interviews
ls
cat interview-47246024
	//Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.
cd ..
head -n 179 streets/Buckingham_Place | tail -n 1
	//SEE INTERVIEW #699607

cd interviews
cat interview-699607
	Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

	However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

cd ..
grep -A 5 "L337" vehicles
	Possibilities:
	License Plate L337DV9
Make: Honda
Color: Blue
Owner: Joe Germuska
Height: 6'2"
Weight: 164 lbs

License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs

cd memberships
ls
cat Delta_SkyMiles AAA Terminal_City_Library Museum_of_Bash_History | grep -c "Jeremy Bowers"
Answer: 4

Culprit: Jeremy Bowers





