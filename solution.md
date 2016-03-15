List of commands used to solve "Command Line Mystery" (please note that I was part of a group that worked cooperatively, so the list is not entirely exhaustive):
cat hint8
cat hint7
cat hint6
cat hint5
cat hint4
cat hint3
cat hint2
cat hint1
head -n 284 streets/Dunstable_Road | tail -n 1
grep "Jeremy" people
grep "Jeremy" AAA
grep "Jeremy" Delta_SkyMiles
grep "Joel” Delta_SkyMiles
cd memberships
grep "Delta" memberships
pwd
ls mystery
grep "Annabel" people
grep "Jeremy" people
cat vehicles
head vehicles
cat interviews
head n-40 people
head -n30 people
grep "CLUE" crimescene
cat cheatsheet.md
cat readme.md
cd command-line-mystery/
cd wdi
grep man

JEREMY BOWERS

(Everything that follows was included in the file when I opened it.)


```zsh
# Clone the initial repository
git clone git@github.com:eerwitt/command-line-mystery.git
cd command-line-mystery

# Check the status to see if anything is already marked as new (shouldn't be)
git status

# Edit my solution file
subl solution.md

# Commit initial solution
git add solution.md
git commit -a

# Start reading the instructions
less instructions

# Check for clues in the mystery
cd mystery
grep CLUE ./crimescene

# Search for person with the Latte
grep Annabel ./people

# Knock on her door
less streets/Mattapan_Street
# Goto line in file using less: http://stackoverflow.com/questions/8586648/going-to-a-specific-line-number-using-less-in-unix
# in less type 173g
# Try different interviews
less interviews/interview-47246024

less interviews/interview-699607

# Checking for vehicle
less vehicles
# Search in less for vehicles starting with L337 and ending in 9
# in less /L337..9
# Check which are over 6'
# Katie Park
# Mike Bostock
# John Keefe
# Erika Owens
# Matt Waite
# Brian Boyer
# Al Shaw
# Miranda Mulligan
# Joe Germuska
# Jeremy Bowers
# Jacqui Maher

# Check which is male/female and get their names
egrep '((Katie Park)|(Mike Bostock)|(John Keefe)|(Erika Owens)|(Matt Waite)|(Brian Boyer)|(Al Shaw)|(Miranda Mulligan)|(Joe Germuska)|(Jeremy Bowers)|(Jacqui Maher))' ./people | grep '\tM\t' | cut -f1

# Limit down by membership
egrep -R '((Joe Germuska)|(Brian Boyer)|(Mike Bostock)|(Jeremy Bowers)|(John Keefe)|(Al Shaw)|(Matt Waite))' ./memberships

# (Jeremy Bowers)|(Brian Boyer)|(Mike Bostock)|(Matt Waite)
# Not MB, wrong car color
# Not MW, wrong car manufacturer
# Not BB, wrong car manufacturer
# JB, it is JB
```
