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

console log:
  less hint1
  less



////////////////////\\\\\\\\\\\\\\\\\\\\\\\\\
+6 foot tall male
membership cards:
  AAA
  Delta
  Library
  Musium of bash history
Annabel Church
    Lives at 38	Buckingham Place, line 179
    Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired. However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"
  spikey hair
  new zealand accent
Joe Germuska
  Has AAA and Library
Jeremy Bowers
  has Library and AAA
  less interview-9620713
    Home appears to be empty, no answer at the door. After questioning neighbors, appears that the occupant may have left for a trip recently. Considered a suspect until proven otherwise, but would have to eliminate other suspects to confirm.
    interview-9620713 (END)"


  IT WAS JEREMY BOWERS!!!
