Download Link: https://assignmentchef.com/product/solved-2110215prog-midterm-3
<br>



<ol>

 <li>Instructions

  <ul>

   <li>Create Java Project named <strong>“2110215_Midterm_Q3”</strong> in your workspace.</li>

   <li>Copy all folders in <strong>“Q3.zip”</strong> to your project directory src folder.</li>

   <li>You are to implement the following classes (details for each class are given in section 4.)

    <ol>

     <li>Penguin                     (package penguin)</li>

     <li>FighterPenguin           (package penguin)</li>

     <li>ElementalPenguin (package penguin)</li>

    </ol></li>

   <li>You also need to create a UML Diagram including the classes Penguin, FighterPenguin, and ElementalPenguin from the package penguin. (This is worth 2 points.) Save it as picture in the folder of package penguin.</li>

   <li>JUnit for testing is in package test.</li>

   <li><strong>To submit: </strong>

    <ol>

     <li><strong>go to src folder that you actually do the coding for this question. </strong></li>

     <li><strong>Zip this question’s src folder. Name it YOUR-ID_Q3.zip (for example, </strong></li>

    </ol></li>

  </ul></li>

</ol>

<strong>6332112121_Q3.zip) </strong>

<ol>

 <li><strong>Submit the zipped file as an assignment on MyCourseville.</strong></li>

</ol>

<ol start="2">

 <li>Problem Statement: Penguin Impact</li>

</ol>




You are hired by MemeHoyo to finish the code for the game Penguin Impact after the previous programmer was fired for hacking Penguin Gems into his own account. Your task is to create new Penguin classes that supports PvP combat, including the elemental system.

The characters in this game are Penguins. There are NPC Penguins that has no ability to fight, Fighter Penguins who has a power level and can attack other Penguins, and Elemental Penguins who has elemental advantage and disadvantages over other Penguins with elements.




There are three elements in this game. Fire, Water, and Snow. Refer to the chart above for elemental advantage information. Fire beats Snow, Snow beats Water, and Water beats Fire. Elemental advantage allows a Penguin to deal double damage, while elemental disadvantage gives them a half damage penalty. Elemental Penguins do not gain advantage or disadvantage over non-elemental Penguins or Elemental Penguins of the same type.

<ol start="3">

 <li>Implementation Details</li>

</ol>

The class packages are summarized below. Note that only important methods that you either need to write and methods that you need to complete this question are listed below.

<strong>4.1 package penguin </strong>

4.1.1. <strong>public class PenguinUtil</strong> <strong>/*ALREADY PROVIDED*/</strong>

This class contains useful functions for creating your program.

<ul>

 <li>Variables</li>

</ul>

None.

<ul>

 <li>Methods</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Method </strong></td>

   <td width="312"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="312"><u>+ String getTypeString(ElementalPenguin</u> <u>penguin)</u></td>

   <td width="312">Static method. Returns a shorthand String of the input Penguin’s element. Used for ElementalPenguin’s toString.</td>

  </tr>

  <tr>

   <td width="312"><u>+ String makeToString(Penguin p)</u></td>

   <td width="312">Static method. Returns a Penguin formatted as string. Used for Penguin’s toString, FighterPenguin’s toString, and ElementalPenguin’s toString.</td>

  </tr>

  <tr>

   <td width="312"><u>+ String makeSpeech(Penguin p)</u></td>

   <td width="312">Static method. Returns a formatted speech string. Used for Penguin’s getSpeech.</td>

  </tr>

 </tbody>

</table>




4.1.2. <strong>public enum PenguinType </strong><strong>/*ALREADY PROVIDED*/</strong>

This enum contains the values that can be used to initialize ElementalPenguin. There are three enum types here: PenguinType.FIRE, PenguinType.SNOW, PenguinType.WATER.        4.1.3. <strong>public class Penguin</strong> <strong>/* You must implement this class from scratch*/</strong>

This class represents a Penguin in the game world. This class will be used for noncombatant NPCs.

<ul>

 <li>Variables</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Variable </strong></td>

   <td width="312"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="312">-String name</td>

   <td width="312">The name of this Penguin.</td>

  </tr>

  <tr>

   <td width="312">-int hp</td>

   <td width="312">The HP of this Penguin. If it reaches 0, it is defeated.</td>

  </tr>

  <tr>

   <td width="312">-int maxHp</td>

   <td width="312">The max HP of this Penguin.</td>

  </tr>

  <tr>

   <td width="312">-String catchphrase</td>

   <td width="312">This Penguin’s catchphrase that it will say in combat.</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>Methods</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Method </strong></td>

   <td width="312"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="312">+ Penguin(String name, int hp, String catchphrase)</td>

   <td width="312">Constructor. Set variables to the given parameter values. maxHp is set to the value of hp. (The ordering of these parameter is important!)</td>

  </tr>

  <tr>

   <td width="312">Public getter/setter for everything</td>

   <td width="312">For setMaxHp and setHp, if the input is less than 0, set the value to 0. For setHp, if the input is greater than maxHp, set the value to maxHp.</td>

  </tr>

  <tr>

   <td width="312">+ String toString()</td>

   <td width="312">Returns this character’s status.              UsePenguinUtil’s makeToString for this. </td>

  </tr>

  <tr>

   <td width="312">+ String getSpeech()</td>

   <td width="312">Returns this character’s catchphrase. Use PenguinUtil’s makeSpeech for this.</td>

  </tr>

 </tbody>

</table>

<sup> </sup><strong><u>Important:</u></strong> There are 3 methods in PenguinTest (package test) that cannot be tested until other classes are finished. They are originally commented out. Please uncomment them to test them when you finish other classes.




<sup>  </sup>4.1.4. <strong>public class FighterPenguin</strong> <strong>/* You must implement this class from scratch*/</strong>

This class represents an extension of the base Penguin class that can attack. This class will be used for player characters and enemies.

<ul>

 <li>Variables</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Variable </strong></td>

   <td width="312"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="312">-int pow</td>

   <td width="312">The power level of this Penguin.</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>Methods</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Method </strong></td>

   <td width="312"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="312">+ FighterPenguin(String name, int hp, int pow,String catchphrase)</td>

   <td width="312">Constructor. Use the super constructor to set other values, and set the pow to pow.</td>

  </tr>

  <tr>

   <td width="312">Public getter/setter for pow.</td>

   <td width="312">For setPow, if the input is less than 0, set the value to 0.</td>

  </tr>

  <tr>

   <td width="312">+ int attack(Penguin target)</td>

   <td width="312">Deals damage to the target. Reduce the target Penguin’s health by this Penguin’s pow, then return the damage dealt.</td>

  </tr>

  <tr>

   <td width="312">+ String toString()</td>

   <td width="312">Returns this character’s status. UsePenguinUtil’s makeToString for this. </td>

  </tr>

 </tbody>

</table>

<strong><u>Important:</u></strong> There are 2 methods in FighterPenguinTest (package test) that cannot be tested until other classes are finished. They are originally commented out. Please uncomment them to test them when you finish other classes.




4.1.4. <strong>public class ElementalPenguin</strong> <strong>/* You must implement this class from scratch*/</strong>

This class represents an extension of the base FighterPenguin class whose attacks have an elemental attribute.

<ul>

 <li>Variables</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Variable </strong></td>

   <td width="312"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="312">-PenguinType type</td>

   <td width="312">The elemental type of this Penguin. See the enum PenguinType for more information.</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>Methods</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Method </strong></td>

   <td width="312"><strong>Description </strong></td>

  </tr>

  <tr>

   <td width="312">+ ElementalPenguin(String name, int hp, int pow, PenguinType type, String catchphrase)</td>

   <td width="312">Constructor. Use the super constructor to set other values, and set the type to type.</td>

  </tr>

  <tr>

   <td width="312">Public getter/setter for type.</td>

   <td width="312"></td>

  </tr>

  <tr>

   <td width="312">+ int getElementalAdvantage(Penguin target)</td>

   <td width="312">Returns 0 if this Penguin has no advantage or disadvantage over target Penguin. Returns 1 if this Penguin has elemental <strong>advantage</strong> over target Penguin. Returns -1 if this Penguin has elemental <strong>disadvantage</strong> over target Penguin. (Elemental advantage is explained in ProblemStatement, but to recap: Fire beats Snow, Snow beats Water, and Water beats Fire. If the target has no element or is the same element, there is no advantage or disadvantage.)</td>

  </tr>

 </tbody>

</table>




<table width="624">

 <tbody>

  <tr>

   <td width="312">+ int attack(Penguin target)</td>

   <td width="312">First, check for elemental advantage against the target. If there is elemental <strong>advantage</strong>, reduce the target Penguin’s health by this Penguin’s pow multiplied by 2. If there is elemental <strong>disadvantage</strong>, reduce the target Penguin’s health by this Penguin’s pow divided by 2 (rounded down). If there is no advantage or disadvantage, deal damage to target normally. Finally, return the damage dealt.</td>

  </tr>

  <tr>

   <td width="312">+ String toString()</td>

   <td width="312">Returns this character’s status. UsePenguinUtil’s makeToString for this. </td>

  </tr>

 </tbody>

</table>




<strong>4.2 package game </strong>

<ul>

 <li><strong>public class Test </strong><strong>/*ALREADY PROVIDED*/</strong></li>

</ul>

This class is for testing the objects you wrote. You can use this class to do whatever you want; it will not be checked.

<ul>

 <li><strong>public class GameApp </strong><strong>/*ALREADY PROVIDED*/</strong></li>

</ul>

This class contains a simulation of the PvP system that you can use to test the objects you wrote.




<ol start="4">

 <li>Scoring Criteria</li>

</ol>

The scoring criteria is listed below. There are 3 JUnit files to test for the 3 files in the penguin package. The total score of this section is 38, which will be factored to a net score of 5. <strong>Note that some tests start off commented, and will have to be uncommented to be properly tested.</strong>

5.1 PenguinTest (Total: 12)

<ul>

 <li>testConstructor (2)</li>

</ul>

<ol>

 <li>testSetName (1)</li>

 <li>testSetHp (1)</li>

 <li>testSetMaxHp (1)</li>

</ol>

<ul>

 <li>testSetCatchphrase (1)</li>

</ul>

<ol>

 <li>testToString (uncomment after finishing ElementalPenguin) (1)</li>

</ol>

<ul>

 <li>testGetSpeech (1)</li>

</ul>

<ol>

 <li>testNotFighter (uncomment after finishing FighterPenguin) (2)</li>

 <li>testNotElemental (uncomment after finishing ElementalPenguin) (2) 5.2 FighterPenguinTest (Total: 10)</li>

</ol>

<ul>

 <li>testConstructor (2)</li>

</ul>

<ol>

 <li>testSetPow (1)</li>

 <li>testAttack (2)</li>

 <li>testToString (uncomment after finishing ElementalPenguin) (1)</li>

</ol>

<ul>

 <li>testNotElemental (uncomment after finishing ElementalPenguin) (2)</li>

</ul>

<ol>

 <li>testInheritance (2)</li>

</ol>

5.3 ElementalPenguinTest (Total: 14)

<ul>

 <li>testConstructor (2)</li>

</ul>

<ol>

 <li>testSetType (1)</li>

 <li>testGetElementalAdvantageFire (1)</li>

 <li>testGetElementalAdvantageSnow (1)</li>

</ol>

<ul>

 <li>testGetElementalAdvantageWater (1)</li>

</ul>

<ol>

 <li>testGetElementalAdvantageElementless (1)</li>

</ol>

<ul>

 <li>testGetElementalAdvantageSameElement (1)</li>

</ul>

<ol>

 <li>testAttackFire (1)</li>

 <li>testAttackSnow (1)</li>

 <li>testAttackWater (1)</li>

 <li>testToString (1)</li>

 <li>testInheritance (2)</li>

</ol>

5.4 UML Diagram of Penguin, FighterPenguin, and ElementalPenguin. Save the UML Diagram as png or jpg in the folder penguin. (2)