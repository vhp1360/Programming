<div dir="rtl">بنام خدا</div><br/>
<div dir="rtl">مطالب ارائه  شده خلاصه ای بر کتاب Scala by Example می باشد.</div>
######## top

### Scala By Example

+ [Capter 1](#chapter1)
+ [Capter 3](#chapter3)
+ [Capter 4](#chapter4)

+ [Chapter 2](#chapter2)
+ [Chapter 5](#chapter5)
+ [Chapter 6](#chapter6)
+ [Chapter 7](#chapter7)
+ [Chapter 8](#chapter8)
+ [Chapter 9](#chapter9)
+ [Chapter 10](#chapter10)
+ [Chapter 11](#chapter11)
+ [Chapter 12](#chapter12)

+ [Tips](#tips)

# Chapter1
# Chapter3
# Chapter4

[Top](#top)

# Chapter2

As a first example, here is an implementation of Quicksort in Scala.
```scala
  def sort(xs: Array[Int]) {
    def swap(i: Int, j: Int) {
      val t = xs(i); xs(i) = xs(j); xs(j) = t
    }
    def sort1(l: Int, r: Int) {
      val pivot = xs((l + r) / 2)
      var i = l; var j = r
      while (i <= j) {
        while (xs(i) < pivot) i += 1
        while (xs(j) > pivot) j -= 1
        if (i <= j) {
          swap(i, j)
          i += 1
          j -= 1
        }
      }
      if (l < j) sort1(l, j)
      if (j < r) sort1(i, r)
    }
    sort1(0, xs.length - 1)
  }
```
above example like C, also below is another coding
```scala
  def sort(xs: Array[Int]): Array[Int] = {
    if (xs.length <= 1) xs
    else {
      val pivot = xs(xs.length / 2)
      Array.concat(
      sort(xs filter (pivot >)),
      xs filter (pivot ==),
      sort(xs filter (pivot <)))
    }
  }
```
more nearlr to # _*functional Language Programming*_

_While_ definition in Scala:
```scala
  def While (p: => Boolean) (s: => Unit) {
    if (p) { s ; While(p)(s) }
  }
```
this code `p: => Boolean` has two means:
  1. _p_ is function paramter that return a *boolean*.
  2. _p_ is bollean parameter that would initialize, when expected(not at all).
  


[Top](#top)
# Chapter5
- function definition:
 1. Standard:
 ```scala
   def sumInts(a: Int, b: Int): Int = if (a> b) 0 else a+sumInts(a+1, b)
   def square(a: Int): Int = a*a
 ```
 2. Function as Input Variable
 ```scala
   def sum(f: Int=> Int, a: Int, b: Int): Int= if (a> b) 0 else f(a)+ sum(f, a+1, b)
   def sumSquars(a, b)= sum(square, a, b)
 ```
 3. Anonymouse Function
 ```scala
   (a: Int, b: Int)=> a* b
   //redefine sum function
   def sumSquars(a, b) = sum((e: Int) => e* e, a, b)
 ```
 4. Currying: get rid of extra repetition fixed variables
 ```scala
  def sum(f: Int => Int):(Int,Int) => Int ={
    def sumF(a: Int, b: Int): Int = if (a>b) 0 else f(a)+ sumF(a+1,b)
    sumF
  }
  //redefine previous function
  def sumSquars(a, b) = sum((r: Int) => r* r)) //also we can use val
```
5. in totaly : 
  1. f(args1)(args2) is equivalent to (f(args1))(args2)
  2. T1 => T2 => T3 is equivalent to T1 => (T2 => T3 )
  _then we can redefine *sum* function_
```
  sum(f: Int=> Int)(a: Int, b: Int): Int= if (a> b) 0 else f(a)+ sum(f, a+1, b)
```

[Top](#top)
# Chapter6
1. Class definition:
```scala
  class Rational(n: Int, d: Int) {
    private def gcd(x: Int, y: Int): Int = {
      if (x == 0) y
      else if (x < 0) gcd(-x, y)
      else if (y < 0) -gcd(x, -y)
      else gcd(y % x, x)
    }
    private val g = gcd(n, d)
    val numer: Int = n/g
    val denom: Int = d/g
    def +(that: Rational) = new Rational(numer * that.denom + that.numer * denom, denom * that.denom)
    def -(that: Rational) = new Rational(numer * that.denom - that.numer * denom, denom * that.denom)
    def *(that: Rational) = new Rational(numer * that.numer, denom * that.denom)
    def /(that: Rational) = new Rational(numer * that.denom, denom * that.numer)
  }
```
2. Inheritance and Overriding:
```scala
  class Rational(n: Int, d: Int) extends AnyRef {
    ... // as before
  }
  class Rational(n: Int, d: Int) extends AnyRef {
    ... // as before
    override def toString = "" + numer + "/" + denom
  }
```
3. Parameterless Methods:
```scala
  class Rational(n: Int, d: Int) extends AnyRef {
    ... // as before
    def square = new Rational(numer*numer, denom*denom)
  }
  val r = new Rational(3, 4)
  println(r.square)  // prints‘‘9/16’’*
```
4. Abstract Classes and Traits: _Trait_ like _Abstract_ but could add it to each class definition without worried about inheritance issues.
```scala
  abstract class IntSet {
    def incl(x: Int): IntSet
    def contains(x: Int): Boolean
  }
  trait IntSet {
    def incl(x: Int): IntSet
    def contains(x: Int): Boolean
  }
  //Extend
  class EmptySet extends IntSet {
    def contains(x: Int): Boolean = false
    def incl(x: Int): IntSet = new NonEmptySet(x, new EmptySet, new EmptySet)
  }
  
```


[Top](#top)
# Chapter7

1.  Case Classes and Case Objects: they have two properties
  1. the Constructor function comes implicity with class\object definition.
  2. _toString, equals and hashCode_ methods by default defined with case definition.
  3. by default defining parameter definition for interface's parameters(nullary accessor methodes)
  4. you no longer need 'new' keyboard to use it.
  5. it usable for _Match_\es
2. Pattern Matching: it likes SWITCH command in C.
  - what is pattern: In general, patterns are built from
     - Case class constructors, e.g. Number, Sum, whose arguments are again patterns,
     - pattern variables, e.g. n, e1, e2,
     - the “wildcard” pattern \_,
     -literals, e.g. 1, true, "abc",
     - constant identifiers, e.g. MAXINT, EmptySet.
  - Meaning of Pattern Matching: e match { case p 1 => e1 ... case p n => en }
     - A constructor pattern C (p 1 , . . . , p n ) matches all values that are of type C (or a
     - subtype thereof) and that have been constructed with C-arguments matching patterns p 1, . . . , p n .
     - A variable pattern x matches any value and binds the variable name to that value.
     - The wildcard pattern ‘\_’ matches any value but does not bind a name to that value.
     - A constant pattern C matches a value which is equal (in terms of ==) to C.
  1. Standard definition:
  ```scala
    def eval(e: Expr): Int = e match {
      case Number(n) => n
      case Sum(l, r) => eval(l) + eval(r)
    }
  ``` 
  2. Pattern Matching Anonymous Functions:
  ```scala
    (x => x match { case P1 => E 1 ... case P n => En })
  ```

[Top](#top)
# Chapter8
## Generic Types and Methodes
1. define a function with _Generic_ type:
```scala
  abstract class Stack[A] {
    def push(a: A): Stack[A] = new NonEmptyStack[A](a, this)
    def isEmpty: Boolean
    def top: A
    def pop: Stack[A]
  }
  val Q = new EmptyStack[Int]
  val W = new EmptyStack[String]
```
2. Plain Bound: *_\<:Ordered[A]_* Generic type is useable for ordering types, assume in previous class ypu define
  1. first syntax type
  ```scala
    def incl(b: A): A = if (b < a) print('True')
  ```
    as it appears only ordered class(like Int,float, ...) could used, otherones raise an error,for that we could bound A with this:
  ```scala
    trait Set[A <: Ordered[A]] {
      def incl(x: A): Set[A]
      def contains(x: A): Boolean
    }
  ```
  2. second:
  ```scala
    case class Num(value: Double) extends Ordered[Num] {
      def compare(that: Num): Int =
      if (this.value < that.value) -1
      else if (this.value > that.value) 1
      else 0
    }
  ```
3. View Bound: *_\<%_* is weaker than _Plain Bound_, it means if A is type that can implicity convertable to ordering type,sufficient.
4.  Variance Annotations
  1. _co-variant_ subtyping: if T is a subtype of S then Stack[T] should be subtype of Stack[S].
  2.  generic types have by default non-variant subtyping. for that we need a bit change:
  ```scala
    class Stack[+A]{
  ```

[Top](#top)
# Chapter9


[Top](#top)
# Chapter10


[Top](#top)
# Chapter11


[Top](#top)
# Chapter12


# Tips
. Array types are written Array[T] rather than T[], and array selections are writ-
ten a(i) rather than a[i].
  


```
  def sort(xs: Array[Int]): Array[Int] = {
    if (xs.length <= 1) xs
    else {
      val pivot = xs(xs.length / 2)
      Array.concat(
      sort(xs filter (pivot >)),
      xs filter (pivot ==),
      sort(xs filter (pivot <)))
    }
  }
```
`def filter(p: T => Boolean): Array[T] :  T => Boolean is the type of functions that take an element of type t and return
a Boolean`

- *higher-order functions*: function that take a function as a paramter.

```
def While (p: => Boolean) (s: => Unit) {
if (p) { s ; While(p)(s) }
}
```

- *def*: used to  _Name expression_  and also define a _Function_ .
- *val*: used to define constance value.
- *var*: used to define variable value.
- *calculating of expression*: it start from right but there are some considaration:
    1. (),* / ,+- are respectively.
    2. (a:Int,b:Int)   --> calculate both variables
    3. (a:Int,b:=>Int) --> calculate b if needed
- *if-else*: if Condition Expression else Expression
- !, ||, && are there signs

- *tail-recursive function*: recursive function that need bounded memory space.
- *anonymouse function*: some times we donot want function at whole and need it in short hande, then we define _anonymouse function_, the style is: (Parameters) => Body
- *class*: structure like --> abstract class _ClassName(Input Parameters)_ extends _TopClassName_{.}
    1. if you use *class* with *abstract* you could not create of it, because you first should define it.
    2. you may have new instance of *class* as much you want.

- *object*: structure exactly like *class* exclusive _abstract_ prefix
     1. there is not any seperate distance of *object*, it means all instance of point to same pointer.
     2. for pionting a *object* to new _variable_ , you donot need to use _*new*_ prefix in assignment clause.

- *case _class_ or _object_*: new type of *class* or *object* with 5 property
     1. definition should contain *case* prefix,never *abstract* prefix, should contain _InputParameter(s)_.
     2. _Constructor_ implicitly defined with definition, it means you could use *case class _or_ object* name it program after definition.
     3. _toString_,_equeal_ and _hashcode_ functions, Automaticaly added to these types.
     4. each parameters define seperately with *def* word, it means you may access each of them like _ClassName.ParamName_.
     5. very good object type for using in *match case* clause.

- *Pattern Matching*: in general shows with --> e match { case p 1 => e1 . case p n => e n }
    1. in general patterns are built from:
       - Case Class Constructures.
       - Pattern Variables like n1.
       - literals like "asd".
       - "_" wilcard pattern.
       - Constant Identifier like MAXINT,EmptySet.
       - *becareful* "Pattern Variables" should start with lowercase char and "Constant Identifier" should start with uppercase char.
    2. could be define as standalone function or into abstract class.
    3. Pattern matching AnonyMouse Function, is mod of pattern mathing usable kind --> (x => x match { case P 1 => E 1 . case P n => E n })

[Top](#top)
