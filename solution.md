grep CLUE ./crimescene: 
the local coffee shop person said that.. a women left right before they heard the shots. The name on her latte was Annabel, 
she had blond spiky hair and a New Zealand accent.

grep Annabel ./people
Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M	40	Haley Street, line 176

clue 5: 
interviews $ cat interview-699607
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, 
that she ran away as soon as the shots were fired.
However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that
starts with "L337" and ends with "9"

grep L337* ./vehicles 
 
License Plate L337ZR9
License Plate L337P89
License Plate L337GX9
License Plate L337QE9
License Plate L337GB9
License Plate L337OI9
License Plate L337X19
License Plate L337539
License Plate L3373U9
License Plate L337369
License Plate L337DV9
License Plate L3375A9
License Plate L337WR9

clue 6: vi vehicles
:/license plate number

License Plate L337QE9
Make: Honda
Color: Blue
Owner: Erika Owens
Height: 6'5"
Weight: 220 lbs

License Plate L337539
Make: Honda
Color: Blue
Owner: Aron Pilhofer
Height: 5'3"
Weight: 198 lbs

License Plate L337369
Make: Honda
Color: Blue
Owner: Heather Billings
Height: 5'2"
Weight: 244 lbs

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

License Plate L337WR9
Make: Honda
Color: Blue
Owner: Jacqui Maher
Height: 6'2"
Weight: 130 lbs

clue 7:

egrep '((Erika Owens)|(Aron Pilhofer)|(Heather Billings)|(Joe Germuska)|(Jeremy Bowers)|(Jacqui Maher))' ./people | grep '\tM\t' | cut -f1

Joe Germuska
Jeremy Bowers
Aron Pilhofer

egrep -R '((Joe Germuska)|(Jeremy Bowers)|(Aron Pilhofer))' ./memberships

may be Jeremy Bowers or aron pilhofer


