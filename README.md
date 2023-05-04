Download Link: https://assignmentchef.com/product/solved-csci2500-homework-3-matrix-multiplication-this-time-using-mips
<br>
For this individual homework assignment, you will again implement matrix multiplication, this time using MIPS. More specifically, you will read in two matrices from the user and multiply them together. As with Homework 1, if you need a refresher in how matrix multiplication works, look in a math textbook or check out Wikipedia!

The first matrix is an <em>n</em>×<em>k </em>matrix, while the second matrix is a <em>k</em>×<em>m </em>matrix. Therefore, the result will be an <em>n</em>×<em>m </em>matrix. Use the read_int system call (syscall) to read in <em>n</em>, <em>k</em>, and <em>m</em>, as well as each unsigned integer matrix value.

One approach you could take is to store these important values in your .data section as follows (with sample hard-coded values shown):

.data

n:            .word 4 k:            .word 3 m:                .word 4

Once you have your matrix sizes defined, dynamically allocate memory to store the actual matrices. This would be equivalent to calling malloc() or calloc() in C to allocate memory on the heap. And remember that each integer is one word (or four bytes) in size.

<h2>Example Program Execution</h2>

On the next page is an example MIPS program execution that you can use to better understand how your program should work, how you can test your code, and what output formatting to use for Submitty. Also use test cases from Homework 1 to test your MIPS code.

Note that you must input each value on a separate line in MIPS. And you can assume that the input given to your program is valid.

When displaying a matrix, each line must start with ‘[’ and end with ‘]’ (as with Homework 1), but in this assignment, left justify the columns by using TAB (‘t’) characters as follows:

[12t34t5567t]

[8t9t123t]

[45t67t8t]

[9t10t11t]

This will display this 4 × 3 matrix as follows:

<table width="0">

 <tbody>

  <tr>

   <td width="53">[12</td>

   <td width="53">34</td>

   <td width="53">5567</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="53">[8</td>

   <td width="53">9</td>

   <td width="53">123</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="53">[45</td>

   <td width="53">67</td>

   <td width="53">8</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="53">[9</td>

   <td width="53">10</td>

   <td width="53">11</td>

   <td width="8">]</td>

  </tr>

 </tbody>

</table>







(spim) load “hw3.s”

(spim) run

Please enter values for n, k, and m:

4

3

4

Please enter values for the first matrix (4×3):

10

20

30

40

50

60

70

80

90

100

110

120

Please enter values for the second matrix (3×4):

0

10

0

20

30

0

40

0

0

50

0

60

<table width="0">

 <tbody>

  <tr>

   <td width="160">[10            20             30</td>

   <td width="53">]</td>

   <td width="8"> </td>

  </tr>

  <tr>

   <td width="160">[40            50             60</td>

   <td width="53">]</td>

   <td width="8"> </td>

  </tr>

  <tr>

   <td width="160">[70            80             90</td>

   <td width="53">]</td>

   <td width="8"> </td>

  </tr>

  <tr>

   <td width="160">[100          110           120multiplied by</td>

   <td width="53">]</td>

   <td width="8"> </td>

  </tr>

  <tr>

   <td width="160">[0              10             0</td>

   <td width="53">20</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="160">[30            0                40</td>

   <td width="53">0</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="160">[0              50             0equals</td>

   <td width="53">60</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="160">[600          1600        800</td>

   <td width="53">2000</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="160">[1500 3400               2000</td>

   <td width="53">4400</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="160">[2400 5200               3200</td>

   <td width="53">6800</td>

   <td width="8">]</td>

  </tr>

  <tr>

   <td width="160">[3300 7000               4400(spim)</td>

   <td width="53">9200</td>

   <td width="8">]</td>

  </tr>

 </tbody>

</table>

<h1>Error Checking</h1>

Given the complexity of this assignment, you can assume that all input values are valid unsigned integers. You can also assume that the correct number of values is given for each matrix. In other words, you do not need to validate the user input