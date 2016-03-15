hint1
head -n 20 people
NAME	GENDER	AGE	ADDRESS
Alicia Fuentes	F	48	Walton Street, line 433
Jo-Ting Losev	F	46	Hemenway Street, line 390
Elena Edmonds	F	58	Elmwood Avenue, line 123
Naydene Cabral	F	46	Winthrop Street, line 454
Dato Rosengren	M	22	Mystic Street, line 477
Fernanda Serrano	F	37	Redlands Road, line 392
Emiliano Wenk	M	90	Paulding Street, line 490
Larry Lapin	M	71	Atwill Road, line 298
Jakub Gondos	M	61	Mitchell Street, line 187
Derek Kazanin	M	55	Tennis Road, line 440
Jens Tuimalealiifano	M	83	Rockwood Street, line 205
Nikola Kadhi	M	75	Glenville Avenue, line 226

grep
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

//hint3
Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M

//hint5
SEE INTERVIEW #47246024
SEE INTERVIEW #699607

// hint6
To find a matching license plate, or a matching car, you can use grep on the 'vehicles' file:
grep "Honda" vehicles

	grep "Blue" vehicles

	grep "L337" vehicles

  //hint7
  In order to actually get information about vehicles that might match our description,
we need to get multiple lines AROUND each match.  We can use the -A, -B, or -C option with grep:

	grep -A 5 "L337" mystery/vehicles

This will match the license plates that contain "L337" and, for each match, show us the five lines AFTER it.

//hint8
To see who was a member of several different groups, you can combine their membership lists into one and search against that.

	cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith"

If you only want to see the number of matches, you can use grep's -c option (the c must be lowercase):

	cat Fitness_Galaxy AAA United_MileagePlus | grep -c "John Smith"

Or you can pipe the result to 'wc -l':

	cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith" | wc

  //interview files
  Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.Admins-MacBook-Pro-2:interviews Admin$ cat interview-699607
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"


License Plate L337P89
Make: Honda
Color: Teal
Owner: Mike Bostock
Height: 6'4"
Weight: 173 lbs
-

License Plate L337DV9
Make: Honda
Color: Blue
Owner: Joe Germuska
Height: 6'2"
Weight: 164 lbs
-
License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs
-
