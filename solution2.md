*TERMINAL COMMMANDS*
-cd command-line-mystery
-ls
-touch solution2.md

// created a file called "solution2.md"

-cat instructions
-cd mystery
-ls
-grep "CLUE" crimescene

// the word "Clue" gets us the clues of the invistigation. We find out that the killer is a male who's at least 6'. He is also a member to many organizations but the cards have no name and are untracable. We also recieve news that there was a witness named Annabel with blonde spikey hair and a New Zealand Aceent

// also learned from the hints to use the command "head" to look for the witness

-grep "annabel" people

// 2 possible matches(females)

-cd streets
-ls
-cat buckingham_palace
-cat hart_place 

// looking through the addresses, we are given a interview number for both witnesses

-cd ..
-ls
-cat interview-699607
-cat interview-47246024

// from the interviews, we find out who the rght witness was and also a decritption of the shooters car and partial license plate number

//with that info and the help of the hints, I go through the vehicles file

-grep -A 5 "L3337" vehicles
 // list of potential killers show up

 //through the process of elimination, I narrow the search to a few people who are male and at least 6'

 -cat AAA Delta_skyMiles Terminal_City_Library Museum_of_Bash_History | grep "Jeremy Bowers"
// hint helps me to properly look for the killer. Two names register. Jacqui Maher and Jeremy Bowers. I go through the "people" file to see if Jacqui is female. She is so it means Jeremy Bower is the killer.

 



Killer: Jeremy Bowers
