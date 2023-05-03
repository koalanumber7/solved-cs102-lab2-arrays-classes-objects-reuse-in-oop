Download Link: https://assignmentchef.com/product/solved-cs102-lab2-arrays-classes-objects-reuse-in-oop
<br>
<strong>Lab Objectives: </strong>Arrays, Classes &amp; Objects, reuse in OOP​

For all labs in CS 102, your solutions must conform to these <a href="http://www.cs.bilkent.edu.tr/~adayanik/cs101/practicalwork/styleguidelines.htm">CS101/102 style guideline</a>​ <a href="http://www.cs.bilkent.edu.tr/~adayanik/cs101/practicalwork/styleguidelines.htm">s</a>.​

<strong>Question </strong>In​ this lab, you will use the <strong>Polynomial</strong>​ class​ that you implemented in the first lab assignment.

Implement the following operations for

<ul>

 <li><strong>add( Polynomial p2 ):</strong>​ Sums this polynomial (polynomial for which the method​ is called) and polynomial p2, and returns the result as a new polynomial.</li>

 <li><strong>sub( Polynomial p2 ):</strong>​ Subtracts polynomial p2 from this polynomial for which​ the method is called on, and returns the result as a new polynomial.</li>

 <li><strong>mul( Polynomial p2 ):</strong>​ Multiplies this polynomial (polynomial for which the​ method is called), and polynomial p2 and returns the result as a new polynomial.</li>

</ul>

For polynomials P(x) and Q(x), the results of addition, subtraction and multiplication operations are:

P(x) = 3 + 4x + 5x​<sup>2</sup><sup>​</sup> + 2x<sup>3</sup>​

Q(x) = 2 + 4x + 1x<sup>2</sup>​

P(x) + Q(x) = 5 + 8x + 6x​<sup>2</sup><sup>​</sup> + 2x<sup>3</sup>​

P(x) – Q(x) = 1 + 4x​<sup>2</sup><sup>​</sup> + 2x<sup>3</sup>​

P(x) * Q(x) = 6 + 20x + 29x​<sup>2</sup><sup>​</sup> + 28x<sup>3</sup>​ <sup>​</sup> + 13x​<sup>4</sup><sup>​</sup> + 2x<sup>5</sup>​

<ol start="2">

 <li>Implement compose and div methods. You can use add, sub, mul methods you already implemented to simplify compose and div methods.</li>

</ol>

<ul>

 <li><strong>compose( Polynomial p2 ):</strong>​ Returns the composition of this polynomial with p2.​</li>

</ul>

For polynomials P(x) and Q(x), the result of composition (P(Q(x))) is:

P(x) = 3 + 4x + 1x<sup>2</sup>​

Q(x) = 2 + 1x




P(Q(x)) = 3 + 4 (2 + 1x) + 1 (2 + 1x)<sup>2</sup>​

P(Q(x)) = 15 + 8x + 1x<sup>2</sup>​




<ul>

 <li><strong>div( Polynomial p2 ):</strong>​ Divides this polynomial with p2 and returns the quotient.​</li>

</ul>




P(x) = 3 + 4x + 1x​<sup>2</sup><sup>​</sup> + 3x​<sup>3</sup><sup>​</sup> + 2x<sup>5</sup>​

Q(x) = 2 + 1x




For polynomials P(x) and Q(x), the result of the division operation, P(x) / Q(x), is found as follows:




<ul>

 <li>Find the leading term (non zero term with highest degree) of the P(x) and Q(x).</li>

</ul>




lead(P(x)) = 2x<sup>5</sup>​ lead(Q(x)) = x




<ul>

 <li>Find polynomial T(x) such that:</li>

</ul>




T(x) = lead(P(x)) / lead(Q(x)) = 2x<sup>4</sup>​

<ul>

 <li>Subtract T(x) * Q(x) from P(x) and assign the result to P(x).</li>

</ul>

P(x) – Q(x) * T(x) = 3 + 4x + 1x​<sup>2</sup><sup>​</sup> + 3x​<sup>3</sup><sup>​</sup> + -x​<sup>4 </sup>

<ul>

 <li>Add T(x) to the result and repeat this process until the degree of P(x) is higher than the degree of Q(x).</li>

</ul>




Dividend (P(x))                                 T(x) = lead(P(x)) / lead(Q(x))

3 + 4x + 1x​<sup>2</sup><sup>​</sup> + 3x​<sup>3</sup><sup>​</sup> + 2x​<sup>5                                           </sup>2x<sup>4</sup>​

3 + 4x + 1x​<sup>2</sup><sup>​</sup> + 3x​<sup>3</sup><sup>​</sup> – 4x​<sup>4                                             </sup>-4x<sup>3</sup>​

3 + 4x + 1x​<sup>2</sup><sup>​</sup> + 11x​<sup>3                                                         </sup>11x<sup>2</sup>​

3 + 4x – 21x​<sup>2                                                                            </sup>-21x

3 + 46x                                              46

-89




Result of P(x) / Q(x) is 46 – 21x + 11x​<sup>2</sup><sup>​</sup> – 4x​<sup>3</sup><sup>​</sup> + 2x​<sup>4</sup><sup>​</sup>. Note that remainder is ignored.




<ol start="3">

 <li>Modify the <strong>PolynomialTester</strong>​ class from the first assignment to test your Polynomial​ class for the above operations.</li>

</ol>

<strong>IMPORTANT NOTES: </strong>

<ol>

 <li>Please reuse the available methods as much as you can instead of repeating the same code in different methods. For example, instead of calculating the degree of the polynomial for addition, you must use the method defined for this purpose. You can implement subtraction by calling polynomial addition and multiplication methods instead of repeating the code of the add method. For the compose method, you must call the multiplication method repeatedly.</li>

</ol>

<strong> </strong>