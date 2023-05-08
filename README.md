Download Link: https://assignmentchef.com/product/solved-programming-problem2-logic-programming-using-prolog
<br>
<h1>Problem 1: Message Decoding</h1>

Alok sent a message to Boman containing letters from A-Z which is encoded to numbers using the following rules : ‘A’ -&gt; 1

‘B’ -&gt; 2

…

‘Z’ -&gt;26

Write a PROLOG program to determine the number of possible message(s) Boman could get after decoding the message from Alok. Define the following predicate Decode (String)

E.g. ?-Decode(“7”) 1 (“G”)

?-Decode(“25”)

2 (either “BE” (2,5) or “Y” (25))







<h1>Problem 2: Diwali Dinner</h1>

As a part of Diwali celebration, a special dinner is arranged in your hostel. The menu of the same is prepared along with their nutrient values as shown below

<table width="639">

 <tbody>

  <tr>

   <td width="213">Starter</td>

   <td width="213">Main Dish</td>

   <td width="213">Desert</td>

  </tr>

  <tr>

   <td width="213">Corn Tikki (30)Tomato Soup (20)Chilli Paneer (40)Crispy chicken (40)Papdi Chaat (20)Cold Drink (20)</td>

   <td width="213">Kadhai Paneer with Butter / Plain Naan (50)Veg Korma with Butter / Plain Naan (40)Murgh Lababdar with Butter / Plain Naan (50)Veg Dum Biryani with Dal Tadka (50)Steam Rice with Dal Tadka (40)</td>

   <td width="213">Ice-cream (20)Malai Sandwich (30)Rasmalai (10) </td>

  </tr>

 </tbody>

</table>




Consider the following

<ol>

 <li>You are allowed to choose items from the menu in the following manner

  <ol>

   <li>One item from each category (Starter, Main Dish and Desert) if you choose from all categories</li>

   <li>If you want to skip one or more categories, you can choose any number of items from your selected category(s) but with a limit in the nutrient value of 80</li>

  </ol></li>

 <li>You may be very hungry, not so hungry or on a diet</li>

 <li>If you are very hungry, you select one item each from Starter, Main dishes and Desert</li>

 <li>If you are not so hungry (or have placement test tomorrow), you might want to only have a Starter and a Main dish or a Desert and a Main dish</li>

 <li>If you are currently on a diet, you are concerned about the nutrient content of each food item. You would select only a single category and take food not exceeding nutrient value of 40.</li>

</ol>

Write a program in PROLOG which should be able to find menus/ items for you depending on whether you are hungry, not so hungry or on a diet.

<ol>

 <li>Define <em>menu(Status,X,Y,Z)</em> which will either find if a selected menu category choice is valid or not.</li>

</ol>

<em>    Status</em> is &lt;<em>hungry,not so hungry, diet&gt;</em> and <em>X, Y, Z</em> are a starter, a main dish, and a desert, respectively.  Value <em>X, Y, Z </em>can be either 0 or 1 (0 means not selected and 1 means selected) Eg. ?- menu(diet, 1,0,0)

True

?- menu (hungry,X,Y,Z)

X=1

Y=1

Z=1




<ol>

 <li>Also define find_items (status,X,Y,Z) to find out the possible combination of items from the selected categories</li>

</ol>

Eg. ?- find_items (not_so_hungry, 1,1,1)

False

?- find_items (diet, 0,1,0)

Items: Veg Korma with Butter / Plain Naan

Items:  Steam Rice with Dal tadka







<h1>Problem 3: Prisoner Escape Problem</h1>

There is a jail in a hilly area with a steep mountain on one side and a river with crocodiles on another side. The prisoners are kept inside core unit of the jail for their entire life. To get rid of the sufferings, sometimes the prisoners try to escape from this place. The map of the jail is shown below. The prisoners do not have the idea about the map.

On the New Year celebration, all the security personnel were busy in other tasks. So, in the meantime the prisoners made plans to escape from the jail.

The core unit has 4 gates (G1, G2, G3, G4) which open towards corridor1 (C1). C1 has two outward gates

(G5, G6) which open towards corridor2 (C2). C2 has four outward gates (G7, G8, G10 and G11). It is not possible to escape from the jail through G7 or G9 because of the steep mountain and the river with crocodiles. But the prisoner may try those two gates.

There are two bounded land outwards of gate G10 and G12 and one tunnel which is connected to G11, G13 and G15. The tunnel is directly connected to the core unit of the jail. There is a blocked road ahead of G18. G17 is a gate which is open towards outside. The prisoner may return to his previous position if required.




The distance between each pair of gated which can be directly visited are as follows:

G1àG5 = 4ft, G2àG5=6ft, G3àG5=8ft, G4àG5=9ft, G1àG6=10ft, G2àG6=9ft, G3àG6=3ft,

G4àG6=5ft, G5àG7=3ft, G5àG10=4ft, G5àG11=6ft, G5àG12=7ft, G5àG6=7ft, G5àG8=9ft, G6àG8=2ft, G6àG12=3ft, G6àG11=5ft, G6àG10=9ft, G6àG7=10ft, G7àG10=2ft, G7àG11=5ft, G7àG12=7ft, G7àG8=10ft, G8àG9=3ft, G8àG12=3ft, G8àG11=4ft, G8àG10=8ft, G10àG15=5ft, G10àG11=2ft, G10àG12=5ft, G11àG15=4ft, G11àG13=5ft, G11àG12=4ft, G12àG13=7ft, G12àG14=8ft, G15àG13=3ft, G13àG14=4ft, G14àG17=5ft, G14àG18=4ft, G17àG18=8ft.

When the distance is given between a pair of gates, it means the prisoner can move between the pair of gates in any order. For example, distance between G1àG5=4ft means the prisoner can move from G1 to G5 and vice-versa.

For the above scenario:

<ol>

 <li>Write a PROLOG program to find all possible paths for a prisoner to escape from the jail.</li>

 <li>Find the optimal path for the prisoner to escape. Optimal path is a path in which the prison has to cover minimum distance to escape from the jail.</li>

 <li>Given a path, your program should be able to find if it is valid or invalid in terms of escaping the jail.</li>

</ol>




Sample Input/Output:

Input:

Optimal(X)




Output:

G3àG6àG12àG14àG17

Input:

Valid ([G1, G6, G8, G9, G8, G7, G10, G15, G13, G14, G18, G17])                      [The argument is a list] Output: True





