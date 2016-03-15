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

cd wdi
cd command-line-mystery
//first 20 people in line
head -n 20 people

//CLUEs tall male 6ft, small change in wallet with memberships at AAA Delta etc.
//witness name Annabel from NZ
grep CLUE crimescene --context=4

//tracking down Annabel
head Annabel people
head Annabel vehicles

//finding Annabel's address
grep "Annabel" people

//changing to interviews
cd interviews

//interview two people
head -n 173 streets/Mattapan_Street | tail -n 1

//open interview
cat interview-9437737
cd ..
cd vehicles

//finding matching vehicles
head grep "Honda" vehicles
head grep "Blue" vehicles
head grep "L337" vehicles
cd ..

//matching informations
grep -A 5 "L337" mystery/vehicles

//finding membership from various groups
cd mystery
cd memberships
cat AAA Delta_SkyMiles Museum_of_Bash_History | grep "Joe Germuska"
Joe Germuska
AAA Delta_SkyMiles Museum_of_Bash_History | grep "Jeremy Bowers"
Jeremy Bowers
Jeremy Bowers
Jeremy Bowers

The solution is Jeremy Bowers
