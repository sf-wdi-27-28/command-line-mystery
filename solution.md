#hint1: head -n 20 people shows first 20 people
#hint2: grep “CLUE” crimescene
#hint3: use ‘head’ on files people and vehicles to see where witness Annabel lives
#hint4: grep Annabel people
#hint5: head -n 173 streets/Mattapan_Street | tail -n 1
#hint6: grep "Honda" vehicles grep "Blue" vehicles grep "L337" vehicles - use ‘head’ on the file
#hint7: grep -A 5 "L337" mystery/vehicles (-A will show 5 lines after L337)
#hint8: cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith" (cat Fitness_Galaxy AAA United_MileagePlus | grep -c "John Smith”) cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith" | wc -l

#cd wdi
#cd command-line-mystery/
	#cheatsheet.md hint1-8 instructions mystery read.md solution.md
#cd mystery
	#grep CLUE crimescene
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.#Suspect 6’, Male, AAA, Delta SkyMiles, Museum of Bash History
#Witness Annabel, Female, blond, New Zealand accent

grep Annabel ./people

#Annabel Sun F 26 Hart Place, line 40
#Annabel Church F 38 Buckingham Place, line 179

#hint5 says: SEE INTERVIEW #9437737
less interview/interview-9437737 #Doesn't appear to be the witness from the cafe, who is female.

#search people for Annabel Church:Interviews with Ms. Church: less interviews/interview-699607
#Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"#People who are Male, over 6’ with a Blue Honda in vehicles
#Hint7 use grep to find L337
#Over 6’
#Memberships:
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

#Al: drives a red car
#Joe: drives a pink car
#Jeremy: drives a blue honda plate L3375a9 so he is the shooter!
#John: drives an orange car
#Matt: drives a blue toyota
