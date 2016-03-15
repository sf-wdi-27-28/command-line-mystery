cd mystery
grep "CLUE" crimescene
grep "Annabel" people
head -n 40 streets/Hart_Place | tail -n 1
head -n 179 streets/Buckingham_Place | tail -n 1
cd interviews
less interview-47246024
q
less interview-699607
q
cd ..

#wasn't sure how to do this more elegantly (ended up just reading through the list to find the two tall male owners of a blue Honda)
grep --context=4 'L337..9' vehicles

cd memberships

#ditto
grep "Germuska" AAA
grep "Germuska" Delta_SkyMiles
grep "Bowers" AAA
grep "Bowers" Delta_SkyMiles
grep "Bowers" Museum_of_Bash_History
grep "Bowers" Terminal_City_Library

cd ..
grep "Bowers" people
grep "Germuska" people
head -n 284 streets/Dunstable_Road | tail -n 1
head -n 275 streets/Plainfield_Street | tail -n 1
cd interviews
less interview-9620713
q
less interview-29741223

#Only remaining suspect is Jeremy Bowers
