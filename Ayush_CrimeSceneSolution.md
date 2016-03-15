// Fork repo & clone (command-line-mystery) in WDI.//
$ cd ~/WDI/
$ git clone https://github.com/sf-wdi-27-28/command-line-mystery.git

// Change directory to "command-line-mystery". //
$ cd command-line-mystery

// Create new file "Ayush_CrimeSceneSolution.md". //
$ touch Ayush_CrimeSceneSolution.md

// Check git status. //
$ git status
"Untracked files: Ayush_CrimeSceneSolution.md".

// Search for term "CLUE" in ~/mystery/crimescene file. //
$ grep "CLUE" crimescene

result
------
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.

// Probable witness pointed by barista: Annabel, blonde spiky hair & a NZ accent //
// Look for Annabel in the people file //

$ grep "Annabel" people

result
------
Annabel Sun	F	26	Hart Place, line 40
Oluwasegun Annabel	M	37	Mattapan Street, line 173
Annabel Church	F	38	Buckingham Place, line 179
Annabel Fuglsang	M	40	Haley Street, line 176


head -n 173 streets/Mattapan_Street | tail -n 1         SEE INTERVIEW #9437737
head -n 40 streets/Hart_Street | tail -n 1              No such file or directory
head -n 179 streets/Buckingham_Place | tail -n 1        SEE INTERVIEW #699607
head -n 176 streets/Haley Street | tail -n 1            No such file or directory



// Search for License plate
$ grep "L337" mystery/vehicles

result
------
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
