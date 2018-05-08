# HTML5_MATH_GAME

RANDOM MATH SHOOTER

Introduction: This is a random math shooter game where bomb are falling to the airship with a random number and airship try to shoot the bomb. This game was designed by using HTML5 with basic css and javascript technology.

Game Description: This game mainly containing 3 main characters.
1)	Airship: It can move left to right and shoot the bomb
2)	Bomb: Actually there will be  a random number of bomb which is containing a random number with random speed from top to ground direction on the Airship
3)	Bullet: Airship actually through bullet to bomb

And The full game influence by a random math. There is a random math like 3+4=? , so the bomb is more important which is containing value 7 instead of others bomb. So when bullet is touching the bomb then bomb is blasting and game user is getting score. Random valued bomb blasting score is higher than the other bomb blasting score. But if any bomb fall on the airship the crash the airship and game is over.

 


Game Instructions: 
1)	Keyboard let, right arrow key for moving Airship from left to right
2)	Spacebar used to through the bullet
3)	Right top corner showing a random math
4)	Math value bomb blast score +50
5)	Any other value bomb blast score +10
6)	Always try to save the airship from fallen bomb
7)	Single life, so game will over if any bomb fall on the airship
8)	Total score showing to the left top corner.

Requirement: 
1)	Any modern pc


Technology Used:
1)	HTML5
2)	Javascript
3)	CSS

Development Requirement:
1)	PC
2)	Webpage development editor like sublime text, notpad ++ etc.


Development Description:

This game body mainly simple HTML5, but little elaboration between game view name with technical name.

#hero: Airship
#laser: Bullet
#enemy: Bomb

<div id="background"></div>
<div id="hero"></div>
<div id="blust"></div>
<div id="laser"></div>
<div id="score"></div>
<div id="mathvalue"></div>
<div id="gameover">GAME OVER</div>
<div id="instructions">
  <H3>Instructions</H3>
  <ul>
    <li>Letf and Right arrow key used to move the fighter</li>
    <li>Space key used to throw the bullet</li>
    <li>Any bomb blust without math value will increase scroe +10</li>
    <li>Math value bomb blust score +50</li>
    <li>If any bomb hit the ship then game over</li>
  </ul>
</div>

So every div maintained and designed by css

#hero {
  width: 35px;
  height: 62px;
  background-image: url(images/hero.png);
  position: absolute;
}
#blust {
  width: 157px;
  height: 90px;
  background-image: url(images/blust.png);
  position: absolute;
}
#background {
  background: #000000;
  width: 840px;
  height: 600px;
  position: absolute;
  left: 0px;
  top: 0px;
}
#laser {
  width: 10px;
  height: 38px;
  position: absolute;
  background-image: url(images/bulet.png);
}
.enemy {
  width: 50px;
  height: 69px;
  color: blue;
  vertical-align: middle;
  display: table-cell;
  font-weight: bold;
  font-size:25px;
  position: absolute;
  -moz-border-radius: 25px / 25px;
	-webkit-border-radius: 25px / 25px;
	border-radius: 25px / 25px;
	text-align: center;
	display: table-cell;
  background-image: url(images/bomb.png);
}

Initially 3 main object created, and it will be controlled in the rest of the game

var hero = createSprite('hero', 420, 580, 35, 62);
var laser = createSprite('laser', 0, -120, 10, 38);
var blust =  createSprite('blust', 380, 500, 157, 90);


loop() is the initial method and it is calling itself periodically. The loop method mainly call 3 others method periodically.

updatePositions();
handleControls();
checkCollisions();
addEnemy();
showSprites();


UpdatePositions() Method:  this method help the bomb to move from game screen top to bottom.
HandleControls() Method:  Actually this method handling the keyboard event like left, right arrow key and space bar to move airship and through the bullet accordingly.

CheckCollisions() Method: This method actually checking always the collision between bullet and bomb as well as bomb and airship.

AddEnemy() Method:  This method help to add new enemy to the screen with random value.

ShowSprit() Method: This method just help to show airship, bullet and bomb to specific position for each loop.


So when bullet is throwing and hitting a bomb then below block execute and score is updating.

if(element.innerHTML.substring(4).trim()==(mathvalue1+mathvalue2)){
        score += 50; 
      }else{
        score += 10;
      }
     
And when bomb is hitting on airship, then game over method calling


