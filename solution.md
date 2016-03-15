
sobolewa$ cd ~/wdi/command-line-mystery/

sobolewa$ mv solution.md solution_original.md //rename file

sobolewa$ touch solution.md //create new solution file

sobolewa$ cd mystery/

sobolewa$ grep "CLUE" crimescene

    CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
    CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
    CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

sobolewa$ grep "Annabel" people

    Annabel Sun	F	26	Hart Place, line 40
    Oluwasegun Annabel	M	37	Mattapan Street, line 173
    Annabel Church	F	38	Buckingham Place, line 179
    Annabel Fuglsang	M	40	Haley Street, line 176

sobolewa$ cd ..

sobolewa$ cat hint1
    Try poking around what's in a file by using the 'head' command:

      head -n 20 people

    This will show you the first 20 lines of the 'people' file.

sobolewa$ head -n 20 people
    ***************
    To go to the street someone lives on, use the file
    for that street name in the 'streets' subdirectory.
    To knock on their door and investigate, read the line number
    they live on from the file.  If a line looks like gibberish, you're at the wrong house.
    ***************

sobolewa$ cd streets/

sobolewa$ sed -n '40'p Hart_Place
  SEE INTERVIEW #47246024

sobolewa$ cd ../interviews/

sobolewa$ cat interview-47246024
    Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.

sobolewa$ cd ../streets/

sobolewa$ sed -n '173'p Mattapan_Street
  SEE INTERVIEW #9437737

sobolewa$ cd ../interviews/

sobolewa$ cat interview-9437737
  Doesn't appear to be the witness from the cafe, who is female.

sobolewa$ cd ../streets/

sobolewa$ sed -n '179'p Buckingham_Place
  SEE INTERVIEW #699607

sobolewa$ cd ../interviews/

sobolewa$ cat interview-699607
    Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

    However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

sobolewa$ cd ..

sobolewa$ grep "L337" vehicles
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

sobolewa$ less vehicles

grep -A 5 "L337" vehicles
    License Plate L337QE9
    Make: Honda
    Color: Blue
    Owner: Erika Owens
    Height: 6'5"
    Weight: 220 lbs

    License Plate L337539     //NOT over 6'
    Make: Honda
    Color: Blue
    Owner: Aron Pilhofer
    Height: 5'3"
    Weight: 198 lbs

    License Plate L337369     //NOT over 6'
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
