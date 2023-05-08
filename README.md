Download Link: https://assignmentchef.com/product/solved-stat823-homework-5-probability-distributions
<br>



<h1>Directions</h1>

Use the attached RMarkdown Probability Distributions.Rmd to create a <strong>pdf </strong>report summarizing the common distributions discussed in this lesson. In addition, I have done the first few to show you my expectations for your report, and have given you some <strong>leading questions to complete</strong>. Partial R-code for the following distributions have been given for you.

<ol>

 <li>Bernoulli</li>

 <li>Binomial</li>

 <li>Hypergeometric: Qn 1</li>

 <li>Poisson: Qn 2</li>

 <li>Geometric: Qn 3</li>

 <li>Negative Binomial: Qn 4</li>

 <li>Normal: Qn 5</li>

 <li>Exponential: Qn 6</li>

 <li>Chi-square: Qn 7</li>

 <li>Student’s t: Qn 8</li>

 <li>F: Qn 9 Optional Beta Optional</li>

 <li>Logistic Optional</li>

</ol>

<strong>All R-code and output must be clearly shown</strong>. Late submission will attract a penalty of 10 points per day after the due date.

If you have any questions, please post them on the lesson discussion board.

<h1>1          Discrete Distributions</h1>

<h2>1.1       Bernoulli</h2>

The <strong>Bernoulli distribution</strong>, named for Jacob Bernoulli, assigns probability to the outcomes of a single Bernoulli experiment—one where the only possible outcomes can be thought of as a “success” or a “failure”

(e.g., a coin toss). Here, the random variable <em><sub>x </sub></em>can take on the values 1 (success) with probability <em><sub>p</sub></em>, or 0

(failure) with probability <em>q </em>= 1<em>≠ p</em>. The plot below contains the pmf of two Bernoulli distributions. The first<em><sub>p </sub></em>= 0<em><sub>.</sub></em>2 and the second (in black) has a probability of success <em><sub>p </sub></em>= 0<em><sub>.</sub></em>5.

(in gray) has a probability of success

<table width="632">

 <tbody>

  <tr>

   <td width="632">x &lt;- 0<strong>:</strong>1<strong>plot</strong>(x, <strong>dbinom</strong>(x, 1, 0.2), type = “h”, ylab = “f(x)”, ylim = <strong>c</strong>(0, 1), lwd = 8, col = “darkgray”, main = “Bernoulli(0.2)”)<strong>lines</strong>(x, <strong>dbinom</strong>(x, 1, 0.5), type = “h”, lwd = 2, col = “black”)<strong>legend</strong>(0.7, 1, <strong>c</strong>(“Bernoulli(0.2)”, “Bernoulli(0.5)”), col = <strong>c</strong>(“darkgray”, “black”), lwd = <strong>c</strong>(8, 2))</td>

  </tr>

 </tbody>

</table>

<h2>Bernoulli(0.2)</h2>

x

The Bernoulli experiment forms the foundation for many of the next discrete distributions.

<h3>1.2       Binomial</h3>

The <strong>binomial distribution </strong>applies when we perform <em><sub>n </sub></em>Bernoulli experiments and are interested in the

total number of “successes” observed. The outcome here, <em><sub>y </sub></em>= <em><sub>x </sub></em>, where <em><sub>P</sub></em>(<em><sub>x </sub></em>= 1) = <em><sub>p </sub></em>and <em><sub>p </sub></em>= 0<em><sub>.</sub></em>5; in blue,

<em>P</em>gray,(<em>x<sub>i </sub></em>= 0) = 1<em>≠ p</em>. The plot below displays three binomial distributions, all for<em><sub>p </sub></em>= 0<em><sub>.</sub></em>1; and in green, <em><sub>p </sub></em>= 0<em><sub>.</sub></em>9.          q <em><sub>i                      i</sub>n </em>= 10 Bernoulli trials: in

<table width="632">

 <tbody>

  <tr>

   <td width="632">x &lt;- <strong>seq</strong>(0, 10, 1)<strong>plot</strong>(x, <strong>dbinom</strong>(x, 10, 0.5), type = “h”, ylab = “f(x)”, lwd = 8, col = “dark gray”, ylim = <strong>c</strong>(0,0.5), main = “Binomial(10, 0.5) pmf”) <strong>lines</strong>(x, <strong>dbinom</strong>(x, 10, 0.1), type = “h”, lwd = 2, col = “blue”)<strong>lines</strong>(x, <strong>dbinom</strong>(x, 10, 0.9), type = “h”, lwd = 2, col = “green”)<strong>legend</strong>(3, 0.5, <strong>c</strong>(“Binomial(10,0.1)”, “Binomial(10,0.5)”,</td>

  </tr>

 </tbody>

</table>

“Binomial(10,0.9)”), col = <strong>c</strong>(“blue”,

“dark gray”, “green”), lwd = <strong>c</strong>(2, 8,

2))

<h2>Binomial(10, 0.5) pmf</h2>

x

We can see the shifting of probability from low values for <em><sub>p </sub></em>= 0<em><sub>.</sub></em>1 to high values for <em><sub>p </sub></em>= 0<em><sub>.</sub></em>9. This makes sense, as it becomes more likely with <em><sub>p </sub></em>= 0<em><sub>.</sub></em>9 to observe a success for an individual trial. Thus, in 10 trials, more successes (e.g., 8, 9, or 10) are likely. For <em><sub>p </sub></em>= 0<em><sub>.</sub></em>5, the number of successes are likely to be around 5 (e.g., half of the 10 trials).

<h3>1.3       Hypergeometric</h3>

In the example I have below, I have set the number of balls in the urn to 10, 5 of which are white and 5 of which are black. I have also fixed the number of balls drawn from the urn to 5. Play around with the parameters and describe what you see.

<table width="632">

 <tbody>

  <tr>

   <td width="632">x &lt;- <strong>seq</strong>(0, 10, 1)<strong>plot</strong>(x, <strong>dhyper</strong>(x, 5, 5, 5), type = “h”, ylab = “f(x)”,lwd = 2, main = “Hypergeometric(5,10,5) pmf”5 , 5 ,5          )</td>

  </tr>

 </tbody>

</table>




<h2>Hypergeometric(5,10,5) pmf5, 5, 5</h2>

x

<h3>1.4      Poisson</h3>

What happens if you increase <em><sub>⁄</sub></em>? To 2? To 3?

x &lt;- <strong>seq</strong>(0, 5, 1)

<strong>plot</strong>(x, <strong>dpois</strong>(x, 1), type = “h”, ylab = “f(x)”, main = “Poisson(1) pmf”, lwd = 2)

<h2>Poisson(1) pmf</h2>

x

<h3>1.5       Geometric</h3>

What happens to the geometric distrbution if you vary <em><sub>p</sub></em>? Show me a few plots and explain.

x &lt;- <strong>seq</strong>(0, 20, 1)

<strong>plot</strong>(x, <strong>dgeom</strong>(x, 0.2), type = “h”, ylab = “f(x)”, lwd = 2, main = “Geometric(0.2) pmf”)

<h2>Geometric(0.2) pmf</h2>

x

<h3>1.6        Negative Binomial</h3>

The negative binomial I have below has set <em><sub>r </sub></em>= 1, so it’s identical to the geometric above. Play around with <em>r </em>and see how it changes.

x &lt;- <strong>seq</strong>(0, 20, 1)

<strong>plot</strong>(x, <strong>dnbinom</strong>(x, 1, 0.2), type = “h”, ylab = “f(x)”, lwd = 2, main = “Negative Binomial(0.2) pmf”)




<h2>Negative Binomial(0.2) pmf</h2>

x

<h1>2          Continuous Distributions</h1>

<h2>2.1       Exponential</h2>

Vary <em><sub>⁄ </sub></em>and describe.

x &lt;- <strong>seq</strong>(0, 10, 0.01)

<strong>plot</strong>(x, <strong>dexp</strong>(x, 1), type = “l”, ylab = “f(x)”, lwd = 2, main = “Exponential(1) pdf”)

<h2>Exponential(1) pdf</h2>

x

<h3>2.2      Normal</h3>

Vary <em><sub>‡ </sub></em>and see how the distribution changes. If you make it too big, you may need to adjust the <em>x</em>-axis by

making the sequence span a wider range thanthe proper limits for x for a given <em>≠</em>5 to 5. You can use a trial-and-error approach to determing <em><sub>‡</sub></em>.

x &lt;- <strong>seq</strong>(<strong>–</strong>5, 5, 0.01)

<strong>plot</strong>(x, <strong>dnorm</strong>(x, 0, 1), type = “l”, ylab = “f(x)”, main = “Normal(0, 1) pdf”)

<h2>Normal(0, 1) pdf</h2>

x

<h3>2.3       Chisquare</h3>

How do the degrees of freedom change the shape? Plot a few and explain.

x &lt;- <strong>seq</strong>(0, 20, 0.01)

<strong>plot</strong>(x, <strong>dchisq</strong>(x, 6), type = “l”, ylab = “f(x)”, main = “Chi-square(6) pdf”)




<h2>Chi−square(6) pdf</h2>

x

<h3>2.4       Students t</h3>

How do the degrees of freedom change the shape? Plot a few and explain.

x &lt;- <strong>seq</strong>(<strong>–</strong>5, 5, 0.01)

<strong>plot</strong>(x, <strong>dt</strong>(x, 6), type = “l”, ylab = “f(x)”, main = “Student s t(6) pdf”)

<h2>Student’s t(6) pdf</h2>

x

<h3>2.5      F</h3>

How do the degrees of freedom (numerator and/or denominator) change the shape? Plot a few and explain.

<table width="632">

 <tbody>

  <tr>

   <td width="632">x &lt;- <strong>seq</strong>(0, 6, 0.01)<strong>plot</strong>(x, <strong>df</strong>(x, 12, 15), type = “l”, ylab = “f(x)”,main = “F(2, 5) pdf”<sub>F(12, 15)  pdf </sub>)</td>

  </tr>

 </tbody>

</table>

<h3>F(12, 15) pdfF(2, 5) pdf</h3>

x