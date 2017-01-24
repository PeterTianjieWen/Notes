
# Crash Introduction to Java and PHP

# Java: Basics

* Java is a class-based Object Oriented Programming language
* Translation: everything in Java is a class or belongs to a class
* Classes must be declared in source files with the same name
* Building in an IDE like Eclipse makes creating and executing code transparent
* Classes are organized in packages

```java
package unl.cse;

public class HelloWorld {

  public static void main(String args[]) {
    System.out.println("Hello World");
  }

}
```

* C-style syntax
* No memory management, Java provides automated garbage collection
* Portable: write once, compile once, run on "any" Java Virtual Machine
* Comments: C-style

```java
//single line comments

/*
 multi line comments
 */

/**
 * Java-doc style comment
 */
public static void main(String args[]) {

}
```

## Variables

* Java is statically typed: you must declare a variable and its type before you use it

```java

int a = 10;//integer variable
double pi = 3.14;
//side note: BigInteger BigDecimal
char c = 'C';  //single unicode (ascii) character
//also: byte, short, long, float
boolean b = true;
b = false;

int x = true;  //compiler error
int y = 10.5;  //compiler error (no implicit type casting)

double z = 10.5;
y = (int) z; //there is explicit type casting
```

## Strings

* In Java, the `String` class is a built-in string class
* You can declare and assign string values without any memory allocation, nor any null terminating characters
* Static strings are denoted with double quotes
* The plus operator `+` is the concatenation operator
* You can mix strings and other types to concatenate

```java
String firstName = "Chris";
String lastName = "Bourke";
String name = lastName + ", " + firstName;

int a = 10;
double pi = 3.14159;
String message = "The value of a is " + a;
String msg = "Pi is " + pi;


```

## Operators

* Basic arithmetic operators: `+ - * /`
* Integer division: `%`
* Logical Operators: `! && ||` (there is short circuiting)
* Inequality operators: `< <= > >= == !=`

## Output

* You can do output to the standard output (console or terminal in Eclipse) using `System.out`
    * `System.out.print()` - prints the content to the standard output
    * `System.out.println()` - prints the content and a new endline character `\n`
    * `System.out.printf()` - prints using printf-style format placeholders

```java
double pi = 3.14159265;
System.out.printf("%f", pi);  //3.141593
System.out.printf("%.2f", pi); //3.14
System.out.printf("%.50f", pi); //

```

# PHP Basics

* PHP is an interpretted language (not compiled)
* PHP is dynamically typed: variables are not declared, variables do not have a fixed type
* A variable's type is whatever you assign to it
* Internally, PHP supports integers, doubles, strings, booleans, arrays, objects

```php
$a = 10;
$a = 3.14;
$a = "ten";
```

* Every variable name *must* begin with dollar sign
* Similar naming rules and conventions: in general use `$lowerCamelCasing`
* Variables are case sensitive!
* You can define (global) constants using the `define()` function

```php
define("PI", 3.14159);

$radius = 3;
$area = $radius * $radius * PI;

//
$area = pow($radius, 2) * PI;

define("PI", 4.0);
```

## Operators

* Arithmetic operators: `+ - * / %`
* NOte: the plus `+` is ONLY ever defined as addition
* String concatenation operator: `.`

### Type Mixing and Juggling

* What is the result of the following code?

```php
$a = 10;
$b = "hello";
$c = $a + $b;
print $c;
```

* PHP attempts to parse the string as a number (and quits at the first non-numerically parsable character)
* It is best not to rely on type juggling, instead be explicit

```php
$a = intval("10");
$b = doubleval("3.14");
```

* You can also test for whether a string contains a number or a "pure" number:

```php
is_numeric("10"); //true, "10" is a pure number
is_numeric("10foo"); //false, it is not a pure number

$a = 10;
$b = "10";
$c = "ten";

is_int($a); //true
is_int($b); //false
is_int($c); //false

//you also have is_float()
```

## Comparison operators

* `< <= > >=` careful: when used with numbers or numbers + strings: numerical comparisons, when used with two strings, lexicographical comparison
* `== !=` careful: these are "loose" comparisons, compare after any type juggling
* `=== !==` strict comparisons: the types AND values have to match

## Null

* There is a `null` keyword (case insensitive)
* You can test for null using `is_null($a)` which returns true only if `$a` is null or has not yet been set
* null values when used in expressions take on a zero value, or an empty value (string), or a "falsy" value (boolean)

# Strings

## Java

* Java has a built-in `String` class
* Strings are *immutable*: once created they cannot be changed
* Basic string methods:
    * `toUpper`

## PHP

* Strings are a built-in type
* May be treated as a character array, but it is *not* null terminated
* Basic string functions:

# Conditionals

* Both languages support standard `if`, `if-else` and `if-else-if` statements
* Both languages support `switch` statements (in general, should be avoided) for integers and strings
* Java: must be boolean expressions

# Loops

* Both languages support standard `for`, `while` and `do-while` loops

# Arrays

## Java

* Java supports static arrays of any type of element
* The `new` keyword can be used to create new arrays
* 0-indexed

```java
int n = 10;

//integer array of size n (10)
int a[] = new int[n];
a[0] = 42;
a[9] = 101;
a[10] = 12;
if(i < a.length) {
  a[i] = 42;
}

double b[] = new double[20];
b[0] = 3.13;

String names[] = new String[5];
names[0] = "Joe";
names[1] = "Jane";

```

### Dynamic Data Structures

* Java supports `List`, a dynamic array, 0-indexed, grows/shrinks as you use it

```java
List<Integer> numbers = new ArrayList<Integer>();
numbers.add(10);
numbers.add(20);
numbers.add(30);

//retrieve elements:
int x = numbers.get(0); //first index

int n = numbers.size(); //gives the size of the list
numbers.add(10); //list allows duplicates, at this point 10, 20, 30, 10

```

* Java also supports a `Set` data structure
* Key difference: it is NOT ordered, it does NOT allow duplicates

```java
Set<Intger> ids = new HashSet<Integer>();

ids.add(10);
ids.add(20);
ids.add(30);

int n = ids.size();

ids.add(30); //no effect

//enhanced for loop (can be used on any collection):
for(Integer x : ids) {
  System.out.println(x);
}
```

* Java also supports a `Map` data structure, allows you to map a key to a value

```java
//m maps integers to string values
Map<Integer, String> m = new HashMap<Integer, String>();

//put stuff into the map:
m.put(10, "ten");
m.put(20, "twenty");

//retrieve:
String s = m.get(10); //n now holds the value "ten"
String t = m.get(50); //t has the value null

Set<Integer> keys = m.keySet();

for(Integer k : keys) {
  String value = m.get(k);
  System.out.println(k + " maps to " + value);
}

```

## PHP

* PHP actually has what are called "associative arrays"
* You can map either integers OR strings to values in the array
* Arrays can hold mixed types: one array could hold integers AND strings AND objects, etc.
* Array indices need not be contiguous

```php
//create an array:

$arr = array();
$arr[0] = 10;
$arr[1] = "forty two";
$arr[5] = "dog";
$arr[10] = 101;
$arr[3.5] = "test"; //truncation
$arr["10"] = "cat";  //overwrites 101
$arr["3.5"] = "mouse";

$arr["foo"] = "bar";

print_r($arr);

for($i=0; $i<count($arr); $i++) {
  print $arr[$i] . "\n";
}

foreach($arr as $key => $value) {
  print $key . " maps to " . $value . "\n";
}

//alternative syntax:
$arr = array(10, 20, 30);
//add elements to the next smallest available index:
$arr[] = 42;

$arr = array(
  0 => "hello",
  10 => "bye",
  "foo" => "bar"
  );


```

#Input/Output

* Standard output:
    * Java supports `System.out.`printf()`
    * PHP supports `printf()`
    * Placeholdser: `%d %f %s` (integers, doubles, strings respectively)
    * Escape characters: `\n, \r, \t, \\`

* Command Line Inputs
    * Java: `String args[]`
    * The first argument is NOT the class name
    * Conversion: `Integer.parseInt()`, `Double.parseDouble()`
    * PHP: `$argv`,  `$argc`
    * In PHP `$argv[0]` is the script file's name
    * `intval()` `doubleval()`

## File I/O

### Java

* File output: look at the notes
* File input: the "easiest" way to do it is with a `Scanner`

```java
//open a file in a scanner

String fileName = "input.txt";
Scanner s = null;
try {
  s = new Scanner(new File(fileName));
} catch(Exception e) {
  throw new RuntimeException(e);
}
//read the file line by line
while(s.hasNext()) {
  String line = s.nextLine();  //throw away the endline character
  System.out.println(line);
}
s.close();
```

### PHP

* File output: look at the notes
* File input: open the file, process it, close it

```php
//h is a file "handle"
$h = fopen("input.txt", "r");
//read line by line
while( !feof($h) ) {
  $line = fgets($h); //this preserves the endline character
  $line = trim($line); //removes leading/trailing whitespace
  printf("%s\n", $line);
}
fclose($h);

//you can read an entire file as one big string:
file_get_contents("input.txt");

```

# Strings

## PHP

* You can treat a string as an indexed array
* Strings in PHP are mutable (can be changed)

```php
$str = "hello World!";
$str[0] = "H";
```

* `strlen($s)` gives the length of the string
* `explode($delimiter, $s)` allows you to split a string along some delimiter
* `preg_split($pattern, $s)` allows you to split a string using  a regular expression

## Java

* Spilt in Java:

```java
String s = "hello WOrld how are you?";
String token[] = s.split(" ");  //you can also use regular expressions here
```

* Strings in Java are immutable, if you want a string you can change, use a `StringBuilder`

```java
StringBuilder sb = new StringBuilder();
sb.append("hello");
sb.append(" ");
sb.append("World");

sb.setCharAt(0, 'H');

String s = sb.toString(); //s is now an immutable string containing "Hello World"
```

# Functions/Methods

# Error Handling

# Searching/Sorting


```












```
