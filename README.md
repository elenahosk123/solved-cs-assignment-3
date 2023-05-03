Download Link: https://assignmentchef.com/product/solved-cs-assignment-3
<br>
You will create a simple class hierarchy as the basis for a fantasy combat game.  Your ‘universe’ contains the creatures in the table.  Each will have characteristics for attack, defense, armor, and strength points.




<table width="591">

 <tbody>

  <tr>

   <td width="118">Type</td>

   <td width="118">Attack</td>

   <td width="118">Defense</td>

   <td width="118">Armor</td>

   <td width="118">Strength Points</td>

  </tr>

  <tr>

   <td width="118">Medusa<sup>4</sup></td>

   <td width="118">2d6 *Glare</td>

   <td width="118">1d6</td>

   <td width="118">3</td>

   <td width="118">8</td>

  </tr>

  <tr>

   <td width="118">Barbarian<sup>2</sup></td>

   <td width="118">2d6</td>

   <td width="118">2d6</td>

   <td width="118">0</td>

   <td width="118">12</td>

  </tr>

  <tr>

   <td width="118">Baba Yaga<sup>1</sup></td>

   <td width="118">2d6 *Soul</td>

   <td width="118">1d10</td>

   <td width="118">3</td>

   <td width="118">12</td>

  </tr>

  <tr>

   <td width="118">Blue Men<sup>3</sup></td>

   <td width="118">2d10</td>

   <td width="118">3d6*</td>

   <td width="118">3</td>

   <td width="118">12 *Mob</td>

  </tr>

  <tr>

   <td width="118">Harry Potter<sup>5</sup></td>

   <td width="118">2d6</td>

   <td width="118">2d6</td>

   <td width="118">0</td>

   <td width="118">10/20*Hogwarts</td>

  </tr>

 </tbody>

</table>




3d6 is rolling three 6-sided dice.  2d10 is rolling two 10-sided dice.




*Glare- If a Medusa rolls a 12 in attack then the target has looked her in the eyes and is turned to stone.  The Medusa wins!




*Soul- Baba Yaga feeds on the pain and suffering of others.  <span style="text-decoration: line-through">When she makes a successful attack her attack</span> <span style="text-decoration: line-through">roll is applied to her opponent, but she gains points equal to the points lost by her opponent.  For example,</span> <span style="text-decoration: line-through">she makes an attack and 3 points of damage are inflicted.  She increases her strength points by 3 also.</span>  When she attacks she receives 1/3<sup>rd</sup> of the damage points inflicted by her attack, rounded down.  Her total can exceed 12.  She wears no physical armor but has many spells and enchantments to protect her.




*Mob- The Blue Men are actually a swarm of small individuals.  For every 4 points of damage (round down) they lose one defense die.  For example, when they reach strength of 8 they only have 2d6 for defense.




*Hogwarts- If Harry dies (i.e. strength &gt;=0) he immediately recovers.  His total strength becomes 20.  If he were to die again then he’s dead.




HINT:  None of these abilities requires their own function!  None of them change the data going in or out of the attack and defend functions.  For example consider the Medusa Glare.  How can you modify the result of the attack function to guarantee ANY opponent loses the fight?




To resolve an attack you will generate 2 dice rolls.  The attacker rolls the appropriate number and type of dice under Attack.  The defender rolls the appropriate number and type of dice under Defense.  You subtract the Defense roll from the Attack roll.  Then subtract the armor, if any.  That is the damage.  Example function prototypes:  int attack()          void defend(int)




Each class only has its own information or data.  When O1 is fighting O2 your program should call O1’s attack function.  It will return the damage inflicted.  Then O2’s defense function will take the damage inflicted, then roll the specified dice and subtract the points for the defense.   To apply the damage you subtract the Armor value.  The result is then subtracted from the Strength Points.  That value becomes the new Strength Points for the next round.  If Strength Points goes to 0 or less then the character is out of the combat.  If it receives 8 points of damage and rolls 3 for it’s defense and has an armor of 3 it would take 8 subtract 3 and then 3 for the armor to receive 2 points of damage.




You need to create a Creature class.  Then you will have a subclass for each of these characters.  Note that the Creature class will be an abstract class.  You will never instantiate one.  Since each starts with the same data elements you will only need one constructor.  Each Creature will have an attack and defend function.  Since they differ they will be pure virtual functions in the Creature base class.  Each class will be in a separate source file with its own header file.




This is the first stage in what will be a larger project.  Please do not add any creatures of your own.




You must complete your design document.  In that document and in your reflections you can discuss how the original design may have changed as you worked through the problems.  You must also submit a test plan.  The test plan should cover all logic paths.  So you should have each character type have combat with all character types (including another of its own).  Remember to submit these documents as PDF files.




It is not hard, just a lot to think about. The TAs will be asked to grade your project against your design so please do not just throw together some random stuff so you have a file to submit.  No, you are not required to implement only the design you submit.  BUT, your reflections will need to explain the difference.  So the old adage garbage in, garbage out will not apply here.  If you give us a random design you will need to explain each step in how you got to the code submitted.  In other words, that will make it much more difficult.  So, learn a good habit and think about it before you start coding. JJ




HINT:  This program has a random element.  You will need to address that in your test plan.  It will also affect debugging.  Your design should address this (potential) problem.  It is not hard but you need to think about it.