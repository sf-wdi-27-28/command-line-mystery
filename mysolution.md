# 1. Go into 'mystery' sub-directory
cd mystery

# 2. Search for keyword 'CLUE' in 'crimescene' file
grep CLUE crimescene
returns:
  CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
  CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
  CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

# 3. Search keyword 'Annabel' in 'people' file
grep Annabel people
returns:
  Annabel Sun	F	26	Hart Place, line 40
  Oluwasegun Annabel	M	37	Mattapan Street, line 173
  Annabel Church	F	38	Buckingham Place, line 179
  Annabel Fuglsang	M	40	Haley Street, line 176

# 4. Read the instructions for 'people' file
head people
returns:
  To go to the street someone lives on, use the file
  for that street name in the 'streets' subdirectory.
  To knock on their door and investigate, read the line number
  they live on from the file.  If a line looks like gibberish, you're at the wrong house.

# 5. Searched for the line number in the street file for each address from 3 above
head -n 40 streets/Hart_Place | tail -n 1
returns:
  SEE INTERVIEW #47246024

head -n 173 streets/Mattapan_Street | tail -n 1
returns:
  SEE INTERVIEW #9437737

head -n 179 streets/Buckingham_Place | tail -n 1
returns:
  SEE INTERVIEW #699607

head -n 176 streets/Haley_Street | tail -n 1
returns:
  SEE INTERVIEW #871877

# 6. Go into 'interview' subdirectory and opened interview file with the corresponding number
cd interview
cat interview-47246024
returns:
  Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.

cat interview-9437737
returns:
  Doesn't appear to be the witness from the cafe, who is female.

cat interview-699607
returns:
  Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.
  However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

cat interview-871877
returns:
  Mr. Fuglsang is male and has brown hair.  Not the witness from the cafe.

# 7. In 'mystery' subdirectory, search for vehicles with license plate that starts with 'L337'
grep -A 5 L337 vehicles
returns about 13 results, which I manually narrowed down by removing results that wasn't a Honda, blue or height of at least 6':

  License Plate L337QE9
  Make: Honda
  Color: Blue
  Owner: Erika Owens
  Height: 6'5"

  License Plate L337DV9
  Make: Honda
  Color: Blue
  Owner: Joe Germuska
  Height: 6'2"

  License Plate L3375A9
  Make: Honda
  Color: Blue
  Owner: Jeremy Bowers
  Height: 6'1"

  License Plate L337WR9
  Make: Honda
  Color: Blue
  Owner: Jacqui Maher
  Height: 6'2"

# 8. Go into 'memberships' subdirectory and search for each name in the above for the following memberships: AAA, Delta Skymiles, Terminal City Library, and Museum of Bash History
cat AAA Delta_Skymiles Terminal_City_Library Museum_of_Bash_History | grep "Erika Owens"
returns:
    nothing

cat AAA Delta_Skymiles Terminal_City_Library Museum_of_Bash_History | grep "Joe Germuska"
returns:
  Joe Germuska
  Joe Germuska
cat AAA Delta_Skymiles Terminal_City_Library Museum_of_Bash_History | grep "Jeremy Bowers"
returns:
  Jeremy Bowers
  Jeremy Bowers
  Jeremy Bowers
  Jeremy Bowers
cat AAA Delta_Skymiles Terminal_City_Library Museum_of_Bash_History | grep "Jacqui Maher"
returns:
  Jacqui Maher
  Jacqui Maher
  Jacqui Maher
  Jacqui Maher

By process of elimination, it's either Jeremy Bowers or Jacqui Maher since they have memberships for all four cards.

# 9. In 'mystery' subdirectory search for the last two suspects
grep "Jacqui Maher" people
returns:
  Jacqui Maher	F	40	Andover Road, line 224
grep "Jeremy Bowers" people
returns:
  Jeremy Bowers	M	34	Dunstable Road, line 284

# 10. By process of elimination, since we know that the suspect is male the killer must be Jeremy Bowers.
