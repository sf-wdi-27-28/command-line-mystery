```zsh
# Clone the initial repository
git clone git@github.com:eerwitt/command-line-mystery.git
cd command-line-mystery

# Start reading the instructions
cat instructions

# Check for clues in the mystery
cd mystery
grep CLUE crimescene

# Search for person with the Latte
grep Annabel people

# Find the right Annabel
open Hart_Place
open Buckingham_Place

# Read Interviews 
cd ..
cd interviews 
ls
open interview-47246024
open interview-699607


# Checking for vehicle
cd ..
grep -A5 "L337" vehicles

# Check which have Blue Honda's
# Eliminate Katie, Mike, John, Matt, Brian, Al, and Miranda
# Eliminate clear female names Erika and Heather
# Check which are over 6'
# Eliminate Aaron
cd ..

# Check for memberships using command that searches all subdirectories and their files for key words (currently in Mystery directory)

# Joe Germuska
grep -nr \w*Germaska\w* .
# Eliminate Joe because he is only a member of AAA

# Jeremy Bowers
grep -nr \w*Bowers\w* .

# Jacqui Maher
grep -nr \w*Jacqui\w* .

# We found their adresses, go there and see what they have to say
cd streets
open Andover_Road
open Dunstable_Road
cd..

# Read their interviews files
cd interviews 
open interview-904020
open interview-9620713

# Eliminate Jacqui, Female and wasnt in town

# Jeremy Bowers, He is the only male over 6ft with a blue Honda that match the lisence plates; and he is a member at to all the places the  memeberships cards found belong to. 
```