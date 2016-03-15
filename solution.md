
# Clone the initial repository
git clone git@github.com:scoobaroo/command-line-mystery.git
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
grep "CLUE" crimescene
grep Annabel ./people
less ./streets/Mattapan_Street
less ./interviews/interview-9437737
less ./streets/Hart_Place
less ./interviews/interview-47246024
less ./streets/Buckingham_Place
less ./interviews/interview-699607
# However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"
grep "L337..9" vehicles
cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library
egrep -R '((Joe Germuska)|(Brian Boyer)|(Mike Bostock)|(Jeremy Bowers)|(John Keefe)|(Al Shaw)|(Matt Waite))' ./memberships
grep "Bowers" AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library
grep Bowers people
head -n 284 streets/Dunstable_Road | tail -n 1
less interviews/interview-9620713
grep Waite people
less interviews/interview-862173
head -n 79 streets/Alpine_Street | tail -n 1
grep Boyer people
head -n 183 streets/Harbor_Point_Boulevard | tail -n 1
less interviews/interview-628618
grep Bostock people
head -n 287 streets/Senders_Court | tail -n 1
less interviews/interview-290346
# Ruled out other suspects, Jeremy Bowers is murderer
