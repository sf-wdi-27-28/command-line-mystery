man grep
git clone https://github.com/seanvsville/command-line-mystery.git
cd command-line-mystery
touch solution.md
cat instructions
cat hint2
cat hint3
cat hint4
cat hint5
cat hint6
cat hint7
cat hint8
ls -a
cd mystery
grep --context=5 "CLUE" crimescene
grep --context=5 "Annabel" people
cd memberships
grep --context=5 "Annabel" AAA
grep --context=5 "Annabel" Delta_SkyMiles
grep --context=5 "Annabel" Museum_of_Bash_History
grep --context-5 "Annabel" Terminal_City_Library
cd ..
head -n 179 streets/Buckingham_Place | tail -n 1
cd interviews
cat interview-699607
cd ..
grep --context=5 "L337" vehicles
cd memberships
grep --context=5 "Bowers" AAA
grep --context=5 "Bowers" Delta_SkyMiles
grep --context=5 "Bowers" Museum_of_Bash_History
grep --context-5 "Bowers" Terminal_City_Library"
cd ..
grep --context=5 "Bowers" people
head -n 284 streets/Dunstable_Road | tail -n 1
cd interviews
cat interview-9620713
cd ..
grep --context=5 "Germuska" people
cat interview-29741223
grep --context=5 "Germuska" AAA
grep --context=5 "Germuska" Delta_SkyMiles
grep --context=5 "Germuska" Museum_of_Bash_History
grep --context-5 "Germuska" Terminal_City_Library"

The culprit of the crime is Jim Bowers, his height matches, his vehicle matches, and his 4 card membership matches. Joe Germuska fits the physical description and vehicle description, however, has no SkyMiles membership, no AAA membership and has never been a member of the Museum_of_Bash_History.
