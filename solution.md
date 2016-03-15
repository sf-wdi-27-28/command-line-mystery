# Entered homework directory
cd ~/wdi/command-line-mystery/

# Opened "readme"
atom readme.md

# Added "solution" file
touch solution.md

# Renamed "solution" file to keep as a reference if needed
mv solution.md answer.md

# Added new "solution" file
touch solution.md

# Opened "instructions"
cat instructions

# Opened "cheat sheet"
atom cheatsheet.md

# Entered "mystery" sub-directory
cd mystery
ls

# Searched for "CLUE"
grep CLUE ./crimescene

# Opened Hint1
cd -
cat hint1

# Cross-referenced memberships found in killer's wallet with the name "Annabel" found on cup
cd -
ls
cd memberships
grep Annabel ./AAA
grep Annabel ./Delta_Skymiles
grep Annabel ./Terminal_City_Library
grep Annabel ./Museum_of_Bash_History

# Found "Annabel Church" multiple times

# Searched for "Annabel Church" in "people" sub-directory
cd -
grep Annabel ./people

# Found Annabel Church's information

# Opened hints
cd ~/wdi/command-line-mystery/
cat hint2
cat hint3
cat hint4
cat hint5

# "Interviewed" Annabel Church
cd mystery
head -n 179 streets/Buckingham_Place | tail -n 1
cd interviews
ls
cat interview-699607

# Filtered out vehicles using description of Getaway Car
cd -
grep -A 5 "L337" ./vehicles | grep -A 4 "Honda" | grep -A 3 "Blue"

# Remaining suspects that fit description of male, at least 6' tall:
  #Joe Germuska
  #Jeremy Bowers

# Cross referenced names with membership cards
cd memberships
grep Joe ./AAA
grep Joe ./Delta_SkyMiles (Joe not found)
grep Jeremy ./AAA
grep Jeremy ./Delta_SkyMiles
grep Jeremy ./Terminal_City_Library
grep Jeremy ./Museum_of_Bash_History

#Jeremy belongs to all. Therefore...
murderer === Jeremy Bowers


