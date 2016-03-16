grep "CLUE" crimescene

CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

grep "Annabel" people

Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M	40	Haley Street, line 176

head -n 179 Buckingham_Place | tail -n 1

SEE INTERVIEW #699607

cat interview-699607

Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

grep -A 5 "L337" vehicles
//manually went through the list of approx. 15 and weeded out all but three men from the previous clues

Jacqui Mahr
Jeremy Bowers
Joe Germuska

cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History | grep "Joe Germuska"
Joe Germuska
Joe Germuska

cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History | grep "Jeremy Bowers"
Jeremy Bowers
Jeremy Bowers
Jeremy Bowers
Jeremy Bowers

cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History | grep "Jacqui Mahr"
//nothing

//Looks like Jeremy Bowers has som' 'splainin' to do
