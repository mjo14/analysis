Design Description
=======
CLASSES: 
Weapon{
--Some Attritubes(maybe power, strength...)
updateAttributes();
}

WeaponsManager{
--List of Weapons
--Weapon Relationships
public int marginOfVictory(Weapon, Weapon) 
public Weapon initializeWeapon(attributes)
public void createWeaponRelationship(List Weapon)
public Weapon addNewWeapon(attributes)
public void updateWeaponRelationship(Weapon)
}

FileReader class{
//reads file to determine rules for game
}

Player class{
--Score of Player
--List of weapons used
chooseWeapon();
mostRecentWeapon();
updateScore();
}

Human extends Player{
}
AI extends Player{
overrides chooseWeapon();
}

Game Class{
--List of all the WeaponManager objects created
newGame();
newTurnPickWeapons();
battlePlayers();
saveGame();
}





User Stories
=======

###Win the round
Each player calls chooseWeapon
Game class looks at all pairs of players and calls compare weapons
game class calls update score on each player
###New Choice
The FileReader creates the new file of weapons and passes it to the WeaponManager
WeaponManager calls createWeaponRelationship and creates the relationships
###New Game
WeaponManager stores the relationships between weapons. So creating a new game is passing in a new file with
different attributes for the weapons

###Choose Game
Each WeaponManager is basically a game (since it contains all the weapons and the relations)
So choosing a WeaponManager instance is choosing a game
