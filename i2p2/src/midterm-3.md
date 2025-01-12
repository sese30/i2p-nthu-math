## Midterm-3: Enhanced Big Positive Real Number Calculator (20%)

* Inputs:
  1. Input a big positive real number in decimal point format, one line for one number.
     1. digits before and after the decimal point are at most 9 digits, separated by a point character `.`.
  2. Input a operator, one line for one operator:
     1. `+`: add
     2. `*`: multiply
  3. The input is interleaved, one line for one number and one line for one operator after the number.
  4. Input <kbd>Ctrl</kbd>+<kbd>D</kbd> to finish the input.
     * Windows: <kbd>Ctrl</kbd>+<kbd>Z</kbd> (will show `^Z` on the screen) then <kbd>Enter</kbd> (`⏎` in Format) to finish the input.
  5. The input is any valid `string` type.
* Outputs: 
  1. The calculation result
     1. The result is shown in decimal point format, with at most 18 digits before the decimal point, and 9 digits after the decimal point ([rounding toward zero, truncate](https://en.wikipedia.org/wiki/Rounding#Round_half_toward_zero)).
     2. If the input is an operator, the program should print the current result in the following line. The format please refer to the [Example](#example) section.
     3. If the input operand or operator is invalid, the program should print the error message `Error: Invalid input` and terminate the program.
* File name: `midterm-3_<student_id>.cpp` (e.g. `midterm-3_106062802.cpp`)

* The program will not have any user prompts, only print the result.
* The program only need to handle invalid inputs, i.e., invalid operand or operator. Other errors will be ingored.
* Please based on `main` and `BigReal_Calc::set_input` that provided in the pseudo code to handle the input and output.
* The program should be finished within 10 seconds. Any test cases will garuntee the program is finished within 10 seconds.

## Format

``` text
<before dec 1>.<after dec 1>⏎
<result 1>
<op 1>⏎
<result 1>
<before dec 2>.<after dec 2>⏎
<result 2>
<op 2>⏎
<result 2>
...
<before dec n-1>.<after dec n-1>⏎
<result n-1>
<op n-1>⏎
<result n-1>
<before dec n>.<after dec n>⏎
<result n>
^Z⏎
```

## Example

### Normal

```console
$ ./a.out
1.0⏎
1.000000000
^Z⏎
$ ./a.out
0.2⏎
0.200000000
^Z⏎
$ ./a.out
000000000.000000000⏎
0.000000000
^Z⏎
$ ./a.out
1.0⏎
1.000000000
+⏎
1.000000000
2.0⏎
3.000000000
+⏎
3.000000000
3.0⏎
6.000000000
*⏎
6.000000000
4.3⏎
25.800000000
^Z⏎
$ ./a.out
1.000000001⏎
1.000000001
+⏎
1.000000001
2.000000002⏎
3.000000003
^Z⏎
$ ./a.out
123456789.123456789⏎
123456789.123456789
+⏎
123456789.123456789
987654321.987654321⏎
1111111111.111111110
^Z⏎
$ ./a.out
1.000000001⏎
1.000000001
*⏎
1.000000001
2.000000002⏎
2.000000004
^Z⏎
$ ./a.out
123456789.123456789⏎
123456789.123456789
*⏎
123456789.123456789
987654321.987654321⏎
121932631356500531.347203169
^Z⏎
```

### Exception Handling
```console
$ ./a.out
+⏎
Error: Invalid input
$
$ ./a.out
1.0⏎
1.000000000
1.0⏎
Error: Invalid input
$
$ ./a.out
1.0⏎
1.000000000
+⏎
1.000000000
+⏎
Error: Invalid input
$
$ ./a.out
1.0 2.0⏎
Error: Invalid input
$
$ ./a.out
1234567890.0⏎
Error: Invalid input
$
$ ./a.out
0000000000.0⏎
Error: Invalid input
$
$ ./a.out
123456789.1234567890⏎
Error: Invalid input
$
$ ./a.out
 123456789.0⏎
Error: Invalid input
$
$ ./a.out
1.0⏎
1.000000000
sdafsdagret⏎
Error: Invalid input
$
$ ./a.out
sdoifjwepoirjpwoie⏎
Error: Invalid input
$
```

## Reference
* [Big Number Calculator](https://www.calculator.net/big-number-calculator.html)

## Pseudo Code

```c++
{{#include midterm-3_pseudo.cpp}}
```