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

#Phillberts-MacBook-Pro:mystery PJC$ pwd
#Phillberts-MacBook-Pro:mystery PJC$ grep CLUE ./crimescene
#Phillberts-MacBook-Pro:mystery PJC$ grep Annabel ./people
#Phillberts-MacBook-Pro:command-line-mystery PJC$ cat hint4
#Phillberts-MacBook-Pro:mystery PJC$ head -n 173 streets/Mattapan_Street | tail -n 1
#Phillberts-MacBook-Pro:interviews PJC$ cat interview-9437737
#Phillberts-MacBook-Pro:mystery PJC$ head -n 179 streets/Buckingham_Place
#Phillberts-MacBook-Pro:interviews PJC$ cat interview-699607
#Phillberts-MacBook-Pro:interviews PJC$ ls
#Phillberts-MacBook-Pro:mystery PJC$ cat vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep L337 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep Honda ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep L337 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -l L337 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -l L337ZR9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep L337ZR9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ head vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337ZR9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337P89 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337GX9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337QE9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337GB9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337OI9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337X19 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337539 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L3373U9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337369 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337DV9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L3375A9 ./vehicles
#Phillberts-MacBook-Pro:mystery PJC$ grep -A 5 L337WR9 ./vehicles
#Phillberts-MacBook-Pro:memberships PJC$ cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library | grep "Jacqui Maher"
#Phillberts-MacBook-Pro:memberships PJC$ cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library | grep "Erika Owens"
#Phillberts-MacBook-Pro:memberships PJC$ cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library | grep "Joe Germuska"
#Phillberts-MacBook-Pro:memberships PJC$ cat AAA Delta_SkyMiles Museum_of_Bash_History Terminal_City_Library | grep "Jeremy Bowers"
#Phillberts-MacBook-Pro:mystery PJC$ grep "Jacqui Maher" ./people
#Phillberts-MacBook-Pro:mystery PJC$ grep "Jeremy Bowers" ./people



# The killer is Jeremy Bowers, I thought it was Jacqui Maher, until i found out she was a she.
