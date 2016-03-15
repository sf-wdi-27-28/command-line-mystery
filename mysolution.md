1. clone repo: git clone https://github.com/hilava/command-line-mystery.git

2. open the instructions: cat instructions

3. navigate to the mystery folder: cd mystery

4. search for CLUE in the crimescene file: grep CLUE crimescene

5. search for Annabel in the people file: grep Annabel people

6. check 2 Female Annabel in the streets folder:
head -n 40 streets/Hart_Place | tail -n 1 --> SEE INTERVIEW #47246024
head -n 179 streets/Buckingham_Place | tail -n 1 --> SEE INTERVIEW #699607

7. check the two interviews in the interviews folder:
cat interview-699607 --> Annabel Church is the witness. described a blue Honda, with a license plate that starts with "L337" and ends with "9" that fled the scene

8. check the vehicles file for the car that Annabel described:
grep -A 5 "L337" mystery/vehicles --> Joe Germuska | Jeremy Bowers

9. search for the name and memberships found in the wallet in the memberships folder and check which person had all 4 memberships:
cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History  | grep -c "Joe Germuska"
cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History  | grep -c "Jeremy Bowers"
cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History  | grep -c "Jacqui Maher"
