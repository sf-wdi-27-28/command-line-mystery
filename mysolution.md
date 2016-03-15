## My Investigation
Go to mystery directory to get started
```
cd mystery
ls
```

Peak inside crimescene file
`head -n 20 crimescene`

Search for CLUEs within the crimescene file
`grep CLUE crimescene -- C`


Based on clues, I need to find info about Annabel in people file
```
head -n 20 people
grep Annabel people -- C
	people:Annabel Sun	F	26	Hart Place, line 40
	people:Oluwasegun Annabel	M	37	Mattapan Street, line 173
	people:Annabel Church	F	38	Buckingham Place, line 179
	people:Annabel Fuglsang	M	40	Haley Street, line 176
```

Found two possibilities that live on Hart Place and Buckingham Place. Need to investigate Hart Place and the corresponding line number (40)
`head -n 40 streets/Hart_Place | tail -n 1`

Got this response: SEE INTERVIEW 47246024. Need to search interviews directory for more clues.
```
cd interviews
cat interview-47246024
	//Ms. Sun has brown hair and is not from New Zealand.  Not the witness from the cafe.
```

No dice! Need to backtrack and investigate Buckingham Place
```
cd ..
head -n 179 streets/Buckingham_Place | tail -n 1
```

Got this response: SEE INTERVIEW 699607. Need to search interviews directory.
```
cd interviews
cat interview-699607
```

Apparently, the killer owns a blue Honda, with a license plate that starts with "L337" and ends with "9". Need to search vehicles for an owner that matches the witness description
```
cd ..
grep -A 5 "L337" vehicles
```

Based on the owner info there are two possibilities: Joe Germuska and Jeremy Bowers (both are males and taller than 6'). Need to check if these two males have all the memberships specified in the initial clues.
```
cd memberships
ls
cat Delta_SkyMiles AAA Terminal_City_Library Museum_of_Bash_History | grep -c "Joe Germuska"
```

Joe Germuska only has two of these memberships. He is not the culprit.
`cat Delta_SkyMiles AAA Terminal_City_Library Museum_of_Bash_History | grep -c "Jeremy Bowers"`

Jeremy Bowers has all the memberships. He is the culprit.
