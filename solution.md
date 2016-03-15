Morgan Sharif
WDI 28
Command Line Mystery

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

>> save/stage/commit/push solution
$ git add solution.md
$ git commit -m "Leads on possible witness"
$ git push origin master

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

