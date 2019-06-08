-------------------------------------------------------------------------------
                            PHP CHEAT SHEET
-------------------------------------------------------------------------------
## PHP FILES
PHP file using any one of these four functions:
- include : This will try to find and include the specified file each time it is
invoked. If the file is not found, PHP will throw a warning, but will continue
with the execution.
-	 require : This will do the same as include , but PHP will throw an error
instead of a warning if the file is not found.
-	 include_once : This function will do what include does, but it will include
the file only the first time that it is invoked. Subsequent calls will be ignored.
-	 require_once : This works the same as require , but it will include the file
only the first time that it is invoked. Subsequent calls will be ignored.

-------------------------------------------------------------------------------
## TYPE OF COMMENT
example :
```
<?php
/*
* multiple line comment
*
*/
// let's print a message from php (single line comment)
echo 'hello world';
// and then include the rest of html
require 'index.html'; (it will include html page otherwise through error message)
?>
```

##  VARIABLE
PHP variable start with $ sign.
```
<?php
$a = 1; // it will assign value 1 to variable a
?>
```

## DATA TYPES
We can assign more than numbers to variables.
•	 Booleans: These take just true or false values
•	 Integers: These are numeric values without a decimal point, for example,
2 or 5
•	 Floating point numbers or floats: These are numbers with a decimal point,
for example, 2.3
•	 Strings: These are concatenations of characters which are surrounded by
either single or double quotes, like 'this' or "that"

example code:
```
<?php
$number = 123;
var_dump($number);  // it will ouput the variable type with assigned value
$number = 'abc';
var_dump($number);  // php never mind to type juggling
?>
```

## DIFFERENCE BETWEEN ADD AND CONCAT
```
$a = 1;
$b = 2;
var_dump($a + $b); // 3 it will add two values.
var_dump($a . $b); // 12  // . will concat two values.
```

## OPERATOR
Operators are elements that take some expressions—operands—and perform actions on them to get a result.
Types  of OPERATORS are :

### ARITHMETIC OPERATORS
see the example :
```
<?php
$a = 10;
$b = 3;
var_dump($a + $b); // 13
var_dump($a - $b); // 7
var_dump($a * $b); // 30
var_dump($a / $b); // 3.333333...
var_dump($a % $b); // 1
var_dump($a ** $b); // 1000
var_dump(-$a); // -10
?>
```
### ASSIGNEMENT OPERATORS
```
<?php
$a = 3 + 4 + 5 - 2;
var_dump($a); // 10

$a = 13;
$a += 14; // same as $a = $a + 14;
var_dump($a);

$a -= 2; // same as $a = $a - 2;
var_dump($a);

$a *= 4; // same as $a = $a * 4;
var_dump($a);
?>
```

### COMPARISION OPERATORS
```
<?php
var_dump(2 < 3); // true
var_dump(3 < 3); // false
var_dump(3 <= 3); // true
var_dump(4 <= 3); // false
var_dump(2 > 3); // false
var_dump(3 >= 3); // true
var_dump(3 > 3); // false
var_dump(1 <=> 2); // int less than 0
var_dump(1 <=> 1); // 0
var_dump(3 <=> 2); // int greater than 0

// SOME EXAMPLE OF TYPE juggling
$a = 3;
$b = '3';
$c = 5;
var_dump($a == $b); // true
var_dump($a === $b); // false
var_dump($a != $b); // false
var_dump($a !== $b); // true
var_dump($a == $c); // false
var_dump($a <> $c); // true
```
### INCREMENT AND DECREMENT OPERATOR
It used to increment/decrement variable value by 1.
example :
```
$a = 3;
$b = $a++; // $b is 3, $a is 4
var_dump($a, $b);
$b = ++$a; // $a and $b are 5
var_dump($a, $b);
```
------------------------------------------------------------------------------
## WORKING WITH STRINGS
learn by example :
```
$text = 'How can a clam cram in a clean cream can? ';
echo strlen($text); // return the string lenght 45

$text = trim($text);
echo $text; // How can a clam cram in a clean cream can? "BASICALLY IT RETURN STRING WITHOUT BLANK TO THE LEFT AND RIGHT"

echo strtoupper($text); // HOW CAN A CLAM CRAM IN A CLEAN CREAM CAN? (upper case transformation)

echo strtolower($text); // how can a clam cram in a clean cream can? (lower case transformation)

$text = str_replace('can', 'could', $text);
echo $text; // How could a clam cram in a clean cream could? ( can is replaced by could string)

echo substr($text, 2, 6); // w coul (return the string from char position 2 to 6)

var_dump(strpos($text, 'can')); // false (return the string position in the text.. here it return false since world is not in string)

var_dump(strpos($text, 'could')); // 4 ('could' position is 4 in text)
```
------------------------------------------------------------------------------

## ARRAYS
Array can be defined as a data structure that can store multiple values of same data types.
#### <strong>Typle of Initialization of Array</strong>
example:
```
$empty1 = [];   // empty array
$empty2 = array();  // empty array (same as first)
$names1 = ['Harry', 'Ron', 'Hermione'];   
$names2 = array('Harry', 'Ron', 'Hermione');

//
// it is kind of map which is implement using array in php
// here 'name' is key and 'James Potter ' is value.
$status1 = [
'name' => 'James Potter',
'status' => 'dead'
];
$status2 = array(
'name' => 'James Potter',
'status' => 'dead'
);
```
#### INSERTING INTO ARRAY
example :
```
$names = ['Harry', 'Ron', 'Hermione'];
$status = [
'name' => 'James Potter',
'status' => 'dead'
];

$names[] = 'Slowestwind'; // here 'Slowestwind' will be added into name at last position
$status['age'] = 32; // in status key age and value 32 will be added at last.
print_r($names, $status);  // it will show the result
```

#### REMOVE FROM ARRAY
example :
```
$status = [
'name' => 'James Potter',
'status' => 'dead'
];
unset($status['status']);  // it will remove the status key and it's value.
print_r ($status);
```
The new $status array contains the key name only.

#### ACCESSING ELEMENTS OF ARRAY
example :
```
<?php
$names = ['Harry', 'Ron', 'Hermione'];
$names['badguy'] = 'Voldemort';
$names[8] = 'Snape';
$names[] = 'McGonagall';
print_r($names);
```
it will print
Array
(
[0] => Harry
[1] => Ron
[2] => Hermione
[badguy] => Voldemort
[8] => Snape
[9] => McGonagall
)

#### EMPTY AND ISSET FUNTIONS
example :
```
$string = '';
$array = [];
$names = ['Harry', 'Ron', 'Hermione'];
var_dump(empty($string)); // true   (check array it is empty or not)
var_dump(empty($array)); // true
var_dump(empty($names)); // false

var_dump(isset($names[2])); // true (check if position contains the value then return true or false)
var_dump(isset($names[3])); // false
```
#### SEARCHING FOR ELEMENTS IN ARRAY
example :
```
$names = ['Harry', 'Ron', 'Hermione'];

$containsHermione = in_array('Hermione', $names);
var_dump($containsHermione); // true in_array check the name in array if it is available then return true or false

$containsSnape = in_array('Snape', $names);
var_dump($containsSnape); // false

$wheresRon = array_search('Ron', $names);
var_dump($wheresRon); // 1 array_search is check the name in array if it is available then it returns position(key) or false.

$wheresVoldemort = array_search('Voldemort', $names);
var_dump($wheresVoldemort); // false
```
---------------------------------------------------------------------------
## CONTROL STRUCTURES
---------------------------------------------------------------------------
Control structure are used to alter the control flow using some conditions
<strong>Types of Control Structures are:</strong>

### CONDITIONAL CONTROL STRUCTURES
#### IF-ELSE
if the condition is true than statement1 is execute else statements2 is executed.

```
/////////////////////////////
// if condition syntax example:
echo "Before the conditional.";
if (4 > 3) {
  echo "Inside the conditional.";
}

if (3 > 4) {
  echo "This will not be printed.";
}
echo "After the conditional.";

/////////////////////////////
// if else syntax example:
if (2 > 3) {
  echo "Inside the conditional.";
} else {
  echo "Inside the else.";
}

//////////////////////////////
// if else ladder example :
if (4 > 5) {
  echo "Not printed";
} elseif (4 > 4) {
  echo "Not printed";
} elseif (4 == 4) {
  echo "Printed.";
} elseif (4 > 2) {
  echo "Not evaluated.";
} else {
  echo "Not evaluated.";
}
if (4 == 4) {
  echo "Printed";
}
```

#### SWITCH CASE
It first evaluate one condition and than match the result with each case
if it is matched than it execute the related statements.
syntax example:
```
switch ($title) {
  case 'Harry Potter':
    echo "Nice story, a bit too long.";
    break;
  case 'Lord of the Rings':
    echo "A classic!";
    break;
  default:
    echo "Dunno that one.";
    break;
```
### LOOPS
Loops are control structure that execute some statement several times.

#### WHILE LOOP
It executes a block of code until the
expression to evaluate returns false . Let's see one example:
```
<?php
$i = 1;
while ($i < 4) {
  echo $i . " ";
  $i++;
}
```
#### DO WHILE LOOP
It is same as the while loop and if the expression is
false from the very beginning, the loop will be executed at least once.
Let's see one example:
```
echo "with while: ";
$i = 1;
while ($i < 0) {
  echo $i . " ";
  $i++;
}
echo "with do-while: ";
$i = 1;
do {
  echo $i . " ";
  $i++;
} while ($i < 0);
```

#### FOR LOOP
The for loop is the most complex of the four loops. It defines an initialization
expression, an exit condition, and the end of an iteration expression. Let's see one example:
```
for ($i = 1; $i < 10; $i++) {
  echo $i . " ";
}
```
#### FOREACH LOOP
This loop is exclusive for arrays, and
it allows you to iterate an array entirely, even if you do not know its keys. There are
two options for the syntax, as you can see in the following examples:
```
$names = ['Harry', 'Ron', 'Hermione'];
foreach ($names as $name) {
  echo $name . " ";
}
foreach ($names as $key => $name) {
  echo $key . " -> " . $name . " ";
}
```
--------------------------------------------------------------------------------
##                           FUNCTIONS
--------------------------------------------------------------------------------
<strong>NOTE :
PHP does not support overloaded functions.
</strong>

Let's see a simple example:
```
function addNumbers($a, $b) {
  $sum = $a + $b;
  return $sum;
}
$result = addNumbers(2, 3);
```
<strong>
- CALL BY VALUE FUNCTION
</strong>
```
function modify($a) {
  $a = 3;
}
$a = 2;
modify($a);
var_dump($a); // prints 2
```
<strong>
- CALL BY REFERENCE FUNCTION
</strong>
```
function modify(&$a) {
  $a = 3;
}
$a=2;
modify($a);
var_dump($a); // print always 3
```

### RETURN STATEMENT
You can have as many return statements as you want inside your function, but
PHP will exit the function as soon as it finds one.
```
function loginMessage() {
  if (isset($_COOKIE['username'])) {
    return "You are " . $_COOKIE['username'];
    } else {
      return "You are not authenticated.";
    }
}
```
