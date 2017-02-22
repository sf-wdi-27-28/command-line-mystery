#Navigate to main directory
cd dev/hw/command-line-mystery
#Load instructions
cat instructions
#Navigate to Mystery
cd mystery
#search crimescene for instances of "CLUE"
grep "CLUE" crimescene
#Three clues found. 
##CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
##CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
##CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.
#Find who Annabel is, search in people
grep "Anabel" people
##Annabel Sun	F	26	Hart Place, line 40
##Oluwasegun Annabel	M	37	Mattapan Street, line 173
##Annabel Church	F	38	Buckingham Place, line 179
##Annabel Fuglsang	M	40	Haley Street, line 176
#Only two are women, search for addresses
head -n 40 streets/Hart_Place | tail -n 1
>SEE INTERVIEW #47246024
head -n 179 streets/Buckingham_Place | tail -n 1
>SEE INTERVIEW #699607
#Change dir to interviews
cd interviews
#view interviews
cat interview-47246024
cat interview-699607
#Annabel Chuch was the witness, saw the car, a blue honda with plate L337*-*9
#Return to previous directory
cd ..
#Search vehicles
grep "L337" vehicles
#Not too useful, check head for structure of file
head vehicles
#Now get enough lines after tag to get make, gender and height
grep -A 4 "L337" vehicles
##Possibilities: Joe Germuska, Jeremy Bowers. 
#Time to check those membership cards, go to memberships dir
cd memberships
#Read membership files together
cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History | grep -c "Joe Germuska"
cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History | grep -c "Jeremy Bowers"
#Jeremy has all four cards
#Move back to check people
cd ..
#Lets check in on Jeremy, where's he live?
grep "Jeremy Bowers" people
#Knock Knock
head -n 284 streets/Dunstable_Road | tail -n 1
#Looks like he's done a runner, that Jeremy Bowers!
cat interviews/interview-9620713






