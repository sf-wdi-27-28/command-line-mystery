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
