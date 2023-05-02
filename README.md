Download Link: https://assignmentchef.com/product/solved-cot5930-homework5-indexedseq
<br>
<strong>Problem 1. </strong>

Write the solution in a file called p1.scala, in an object called p1.

<table width="80">

 <tbody>

  <tr>

   <td width="80"> <em>isSorted </em>tha</td>

  </tr>

 </tbody>

</table>

<ol>

 <li>Write a functiont checks that an <em>IndexedSeq </em>object is in sorted order using a function argument <em>less: (A,A) =&gt; Boolean</em>.</li>

 <li>Consider the <em>quicksort </em>function you wrote for Homework 4. Define a set of properties for the quicksort function, including checking for ascending order using the <em>isSorted </em>function from part a). Address all cases: empty vectors, vectors of one element, and vectors of more than one element. Also, compare results with the standard library <em>sorted</em></li>

</ol>

Write a program that tests those properties using the Prop/Gen classes from the <a href="http://wisenet.fau.edu/class/scala/notes/book-code/fpinscala-dir/answers/src/main/scala/fpinscala/testing/Gen.scala">Gen.scala</a> file. The solution is graded also on the correct definition of properties.

(Hint: Gen.listOf generates lists and quicksort works with IndexedSeq. One could define a Gen and a sized generator for Vector or just convert back and forth between List and Vector.)

<strong>Problem 2. </strong>

Write the solution in a file called p2.scala, in an object called p2. Click for file <a href="http://wisenet.fau.edu/class/scala/notes/book-code/fpinscala-dir/answers/src/main/scala/fpinscala/monoids/Monoid.scala">Monoid.scala</a><a href="http://wisenet.fau.edu/class/scala/notes/book-code/fpinscala-dir/answers/src/main/scala/fpinscala/monoids/Monoid.scala">. </a>a) Write a function with this signature:

<strong>def</strong> getMinMax[<strong>A</strong>](v<strong>:</strong> <strong>IndexedSeq</strong>[<strong>A</strong>])(less<strong>:</strong> (<strong>A</strong>,<strong>A</strong>) <strong>=&gt;</strong> <strong>Boolean</strong>)<strong>:</strong> <strong>MinMax</strong>[<strong>A</strong>]

getMinMax returns the minimum and the maximum values of an object <strong>IndexedSeq</strong>[<strong>A</strong>] wrapped in a

<strong>MinMax</strong>[<strong>A</strong>] object defined like this: <strong>  case</strong> <strong>class</strong> <strong>MinMax</strong>[<strong>A</strong>](min<strong>:</strong><strong>Option</strong>[<strong>A</strong>], max<strong>:</strong><strong>Option</strong>[<strong>A</strong>])

If the sequence is empty, then the result is <strong>MinMax</strong>[<strong>A</strong>](<strong>None</strong>,<strong>None</strong>).

If the sequence has one element <em>x</em>, then the result is <strong>MinMax</strong>[<strong>A</strong>](<strong>Some</strong>(x),<strong>Some</strong>(x)).

Example: getMinMax for Vector(1, -3, 0, 5, 2, 4) using less = _ &lt; _ returns

<strong>MinMax</strong>[<strong>A</strong>](<strong>Some</strong>(-3),<strong>Some</strong>(5)).




To get any credit your solution must do the following:

<ul>

 <li>define a <strong>monoid </strong>for the <strong>MinMax</strong>[<strong>A</strong>] type, using the less<strong>:</strong> (<strong>A</strong>,<strong>A</strong>) <strong>=&gt;</strong> <strong>Boolean</strong>) function given as argument to getMinMax.</li>

 <li>Use the foldMapV function described in the tetbook/notes to compute the <strong>MinMax</strong>[<strong>A</strong>] object with the minimum and maximum values of the <em>v</em></li>

</ul>

Write a <em>main</em> method that demonstrates how the getMinMax function is used.

Hint: get inspiration from function ordered(ints: IndexedSeq[Int]): Boolean from the textbook/notes. b) Prove formally that the <strong>MinMax</strong>[<strong>A</strong>] monoid follows the two monoid laws.

<h1>Problem 3. Extra Credit  10 points</h1>

A company selling used phones on eBay keeps its inventory information in a CSV file that looks like this:

<table width="517">

 <tbody>

  <tr>

   <td width="73">Product ID</td>

   <td width="152">Name</td>

   <td width="102">Unit cost $</td>

   <td width="107">Sell price $</td>

   <td width="44">Stock</td>

   <td width="39">Sold</td>

  </tr>

  <tr>

   <td width="73">2324</td>

   <td width="152">Apple iPhone 6s</td>

   <td width="102">189</td>

   <td width="107">210</td>

   <td width="44">5</td>

   <td width="39">2</td>

  </tr>

  <tr>

   <td width="73">9842</td>

   <td width="152">Motorola G6</td>

   <td width="102">146</td>

   <td width="107">155</td>

   <td width="44">10</td>

   <td width="39">7</td>

  </tr>

  <tr>

   <td width="73">4471</td>

   <td width="152">Samsung Galaxy S7</td>

   <td width="102">190</td>

   <td width="107">199</td>

   <td width="44">3</td>

   <td width="39">5</td>

  </tr>

 </tbody>

</table>

The Canvas homework page includes a link to this file.

Write a program with <strong>the IO monad code from the textbook</strong> (following the principles from  Chapter 13) that reads from the terminal the name of a file with this format and then computes and displays the total cost, revenue, and profit from items sold across the inventory.

Feel free to interpret what these terms mean and to select the output format.

Make sure you comment your code.