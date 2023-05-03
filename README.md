Download Link: https://assignmentchef.com/product/solved-cs224-lab-2-creating-and-running-simple-mips-assembly-language-programs
<br>



<strong>Purpose</strong>: 1. Understanding preliminary principles of using stack for saving $s registers, passing arguments to and receiving results from subprograms, dynamic storage allocation and array processing.

You are obliged to read this document word by word and are responsible for the mistakes you make by not following the rules. Your programs should be reasonably documented and must have a neat syntax in terms of variable names and spacing. In all labs if it is not specified assume that inputs are always correct.




<strong>Important Notes</strong>. In this lab in the implementation of subprograms you are not allowed to use  $t registers: use $s registers to get used to the MIPS software development principles. When you enter to a subprogram save $s registers you use in the subprogram to the stack etc. Remember and use the rules of passing parameters to subprograms and results to caller.




If you use $t registers in subprograms (once or more) in Part 1 (Preliminary Work) you will lose 10 points. If you use $t registers in subprograms (once or more) in Part 2 (Lab Work) you will lose another 10 points.




As stated earlier in all lab works if it is not explicitly stated you may assume that program inputs are correct.




<strong>Summary </strong>

<strong>Preliminary Report/Preliminary Design Report</strong>

<strong>Part 1</strong> (30 points): Preliminary Report/Preliminary Design Report: Learning the principles of writing subprograms. Bit manipulation. Dynamic storage allocation.




<strong>Lab Work:</strong>

<strong>Part 2</strong>  (70 points): More on learning principles of writing subprograms. Involves dynamic storage allocation and arrays.

<strong>Lab: (Note try and study lab part at home before coming to the lab. Make sure that you show the lab work to your TA before uploading in the lab.)</strong>

<strong>DUE DATE OF PART 1 (PRELIMINARY WORK): SAME FOR ALL SECTIONS</strong>: <strong>No late submission will be accepted</strong>.

<ol start="2020">

 <li>Please bring and drop your hardcopy (printed copy) of the preliminary work into the box(es) provided in the lab by 13:30 on Monday March 2, 2020.</li>

 <li>Please <strong>upload your programs of Part 1 (PRELIMINARY WORK)</strong> to the Unilica by 13:30 on Monday March 2. Use filename <strong>StudentID_FirstName_LastName_SecNo_PRELIM_LabNo.txt</strong> <u>Upload only the programs. Only a NOTEPAD FILE (txt file) is accepted. </u>Your paper submission for preliminary work must match MOSS submission. <u>Any format other than txt gets 0 points.</u></li>

 <li>For preliminary work grading you have to complete both section a (preliminary work paper submission) and b (Unilica file upload) as defined above. If one of them is missing you get 0 (zero) from the preliminary part. This is valid for all labs.</li>

</ol>




<strong>DUE DATE PART 2 (LAB WORK): (different for each section) YOUR LAB DAY</strong>

<ol>

 <li>You have to demonstrate your lab work to the TA for grade by <strong>12:15</strong> in the morning lab and by <strong>17:15</strong> in the afternoon lab. Your TAs may give further instructions on this. If you wait idly and show your work last minute, 20 points will be taken off from your grade.</li>

</ol>




<ol>

 <li>At the conclusion of the demo for getting your grade, you will <strong>upload your entire program work</strong> <strong>including Part 1 (Preliminary Work)</strong> to the Unilica Assignment, for similarity testing by MOSS. See Part 3 below for details.</li>

</ol>




<strong>If we suspect that there is cheating, we will send the work with the names of the students to the university disciplinary committee. </strong>




<strong>Part 1. Preliminary Work / Preliminary Design Report (30 points)</strong>

You have to provide a neat presentation prepared by <u>Word or a word processor with similar output quality such as Latex as you were asked in Lab 1</u>. At the top of the paper on left provide the following information and staple all papers. In this part provide the program listings with proper identification like Part no. and program number/name in that part (please make sure that this info is there for proper grading of your work, otherwise some points will be taken off).




CS224




<ol>

 <li><strong>a</strong>. <strong>(15 points)</strong> <strong>Circular Shifts</strong>:</li>

</ol>

<strong>Shift Left Circular (SLC)</strong>: Implement a method (subprogram) called shiftLeftCircular that shifts the contents of a register and works as demonstrated below:

# input  8 hex digits (shift left amount) ==&gt; output 8 hex digits

0XAA 00 00 BB (SLC   4) ==&gt; 0XA0 00 0B BA

0XAA 00 00 BB (SLC  8) ==&gt;  0X00 00 BB AA

As shown above the bits falling down from left comes to right in the order they drop.




<strong>Shift Right Circular (SRC)</strong>: Implement a method (subprogram) called shiftRightCircular. It works like SLC but this time the bits falling down from right comes to left in the order they drop.




Write two separate subprograms for these circular shift operations. Provide the necessary interface for testing  your code in the main (top level) program. Ask the user to enter the decimal integer number to be shifted and a number that indicates the amount of shift. Display the number to be shifted, the shift amount and direction, and the shifted number in hexadecimal on the console.




You must pass the number to be shifted and the shift amount in $a0, and $a1 respectively and return the result in $v0 (as required by the rules of MIPS software development).




How to display an integer in hexadecimal: See Mars help menu on syscalls.




Make sure that you have an efficient implementation.




<ol>

 <li><strong>b</strong>. <strong>(15 points)</strong> <strong>Array Processing</strong>: The main program invokes two subprograms: <strong>createArray</strong> and <strong>arrayOperations</strong>.</li>

</ol>




<strong>createArray</strong>: Asks the user the array size and  initializes the array elements with interaction on the console. It returns to the main program the array beginning address and size respectively in  $v0 and $v1.




<strong>arrayOperations</strong>: Receives array address and array size from the main program respectively in $a0 in $a1 and invokes <strong>min, max, sum,  palindrome</strong> subprograms to perform the following. After each it displays a console message.

<ul>

 <li><strong>min</strong>: returns the minimum value stored in the array.</li>

 <li><strong>max</strong>: returns the maximum value stored in the array..</li>

 <li><strong>sum</strong>: returns the summation of array elements.</li>

 <li><strong>palindrome</strong>: Checks if array contents defines a palindrome. An array that contains for example 1, 4, 4, 1 is a palindrome. An array with zero or one element is a palindrome by definition. The method returns 1 in $v0 if it is a palindrome, otherwise it returns 0.</li>

</ul>




<strong>Part 2. <u>Lab Work</u>: Writing MIPS assembly language programs (70 points)</strong>

<ol>

 <li><strong> (20 points)</strong> <strong>initializeArray:</strong> Main program invokes a subprogram (<strong>initializeArray</strong>) and initializes an array of integer numbers with random numbers within the range of 1 to 100,000. See Syscalls help menu item of Mars for random number generation. The subprogram gets the array size from the user.</li>

</ol>




<ol start="2">

 <li><strong>2</strong>. <strong>(25 points)</strong> <strong>bubbleSort</strong>: Main program invokes a subprogram (<strong>bubbleSort</strong>) that sorts the array in ascending order using the bubble sort algorithm. The array size can be 0 or more.</li>

</ol>




<ol start="3">

 <li><strong>3</strong>. <strong>(25 points)</strong> <strong>processArray:</strong> Main program invokes another subprogram and passes the sorted array. This subprogram (<strong>processArray</strong>) displays the sorted array by providing array index position, array element value, summation of the digits of the element (using a method called <strong>sumDigits</strong>), and indicates if the element is a prime number or not (using a method called <strong>checkPrime</strong>). Therefore, for each array element it generates one line with four items. For example, if the array position 5 contains 25 it displays</li>

</ol>

5          25        7          No





