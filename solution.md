Morgan Sharif
WDI 28
Command Line Mystery

w01 d01

comfort: 4/5
completeness: 5/5
Had some trouble part-way through with grep commands, but was very satisfied when I was able to run grep against multiple files in one line - making the last cross-referencing part much more straightforward. I would definitely like to learn about more complex and specific expressions to target information.


	Legend:
	>> action summary
	|| mystery notes
	$ command line inputs


>> forked and cloned command-line-mystery to wdi directory
>> change directory to command-line-mystery
$ cd ~/wdi/command-line-mystery/

>> read instructions
$ cat instructions

>> change directory to mystery
$ cd mystery/

>> view crime scene info (then get overwhelmed)
$ cat crimescene

>> show lines with real CLUE within crimescene
$ grep CLUE crimescene

|| Perpetrator identity:
|| 	Gender - Male
|| 	Height - >= 6'0"
|| 	Member of AAA, Delta Skymiles, Local Library, Museum of Bash History

|| Possible witness: Annabel, female, left coffee shop right before gunshots.|| Blond spiky hair and new Zealand accent

>> Search for 'Annabel' in people
$ grep Annabel people

|| Two possible Annabels:
|| 	Annabel Sun, 	F, 	26,	Hart Place,			Line 40
|| 	Annabel Church,	F,	38,	Buckingham Place,	Line 179

>> Interview Annabel Sun in Hart Place
$ head -n 40 streets/Hart_Place | tail -n 1

|| SEE INTERVIEW #47246024

>> Open interview #47246024
$ cat interviews/interview-47246024

|| Not Ms Sun. Annabel Church is likely the witness

>> Interview Annabel Church
$ head -n 179 streets/Buckingham_Place | tail -n 1

|| SEE INTERVIEW #699607

>> Open interview #699607
$ cat interviews/interview-699607

|| Suspect car:
|| 	Blue Honda
||	License plate starts with "L337", ends with "9"

>> view layout of vehicles file
$ head vehicles
|| vehicles files provide: license# make, color, owner, height, and weight (6 items)

>> search for license plate matches to "L337" (license# match + 5 lines of details)
$ grep -A 5 "L337" vehicles

|| 
License Plate L337ZR9
Make: Honda
Color: Red
Owner: Katie Park
Height: 6'2"
Weight: 189 lbs
--
License Plate L337P89
Make: Honda
Color: Teal
Owner: Mike Bostock
Height: 6'4"
Weight: 173 lbs
--
License Plate L337GX9
Make: Mazda
Color: Orange
Owner: John Keefe
Height: 6'4"
Weight: 185 lbs
--
License Plate L337QE9
Make: Honda
Color: Blue
Owner: Erika Owens
Height: 6'5"
Weight: 220 lbs
--
License Plate L337GB9
Make: Toyota
Color: Blue
Owner: Matt Waite
Height: 6'1"
Weight: 190 lbs
--
License Plate L337OI9
Make: Jaguar
Color: Blue
Owner: Brian Boyer
Height: 6'6"
Weight: 201 lbs
--
License Plate L337X19
Make: Fiat
Color: Blue
Owner: Al Shaw
Height: 6'5"
Weight: 240 lbs
--
License Plate L337539
Make: Honda
Color: Blue
Owner: Aron Pilhofer
Height: 5'3"
Weight: 198 lbs
--
License Plate L3373U9
Make: Ford
Color: Blue
Owner: Miranda Mulligan
Height: 6'6"
Weight: 156 lbs
--
License Plate L337369
Make: Honda
Color: Blue
Owner: Heather Billings
Height: 5'2"
Weight: 244 lbs
--
License Plate L337DV9
Make: Honda
Color: Blue
Owner: Joe Germuska
Height: 6'2"
Weight: 164 lbs
--
License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs
--
License Plate L337WR9
Make: Honda
Color: Blue
Owner: Jacqui Maher
Height: 6'2"
Weight: 130 lbs
||

|| Car owners matching description [Blue Honda / >6'0" / Male]:
|| Joe Germuska
|| Jeremy Bowers
|| Jacqui Maher

>> Search against memberships to: AAA, Delta Skymiles, Local Library, and Museum of Bash History
$ cd memberships
$ grep "Joe Germuska" AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History

|| AAA:Joe Germuska
|| Terminal_City_Library:Joe Germuska
|| Incomplete match. Not Joe.

$ grep "Jeremy Bowers" AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History

|| AAA:Jeremy Bowers
|| Delta_SkyMiles:Jeremy Bowers
|| Terminal_City_Library:Jeremy Bowers
|| Museum_of_Bash_History:Jeremy Bowers

|| Jeremy Bowers is a positive match against all descriptions and evidence.