My Solutions


cd mystery
// changed to the mystery directory


cat instructions
// opened the instructions file.


grep CLUE ./crimescene
// searched the crimescene file for everything marked as CLUE
// got the below
// CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.


ls
// see what's in the mystery folder


grep Annabel ./people
// trying to find the latte owner and got the below
// Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M	40	Haley Street, line 176


head -n 173 streets/Mattapan_Street | tail -n 1
// got SEE INTERVIEW #9437737


less interviews/interview-9437737
// Doesn't appear to be the witness from the cafe, who is female.


head -n 179 streets/Buckingham_Place | tail -n 1
// see interview 699607


less interviews/interview-699607
//Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"


grep -A 5 "L337..9" vehicles
//pulled up all license plates with L337..9 and their corresponding info

cd memberships
// go into the memberships to see who has which memberships

cat Fitness_Galaxy AAA United_MileagePlus | grep "Jeremy Bowers"
//Jeremy has all the aforementioned memberships

Jeremy Bowers did it.
