<div dir=rtl>بنام خدا</div>

- [Type](#type)
  - [String literal](#string-literal)
    - [Substitution](#substitution)
    - [Itration](#itration)
    - [Regular Experssion](#regular-experssion)
    - [Matches](#matches)
    - [Array](#array)
    - [Hashes](#hashes)
    - [Time](#time)
    - [Ranges](#ranges)
    
    
- [Flow Controls and Conditions](#flow-controls-and-conditions)
  - [if](#if)
  - [unless](#unless)
  - [case](#case)
  - [while](#while)
  - [until](#until)
- [CodeBlocks,Functions,Procedures,Lambdas](#odeblocksfunctionsprocedureslambdas)
  - [Code Blocks](#code-blocks)
  - [Functions](#functions)
  - [Procedures](#procedures)
  - [Lambda](#lambda)
- [Class](#class)   
  - [Inheritance](#inheritance)
  - [Nested Class](#nested-class)
- [Namespaces, Modules and Mix-Ins](#namespaces-modules-and-mix-ins)

# Type
## String literal
### Substitution
```rb
  puts "strings.....".sub("SomeThings","SomeThingsElse")
```

[top](#top)
### Itration
```rb
  "Strings.....".scan(/../) do |q| puts q  //puts 2 characters each time
```

[top](#top)
### Regular Experssion
- Fisrt Table:

Character | Meaning
---|---
^  | Anchor for the beginning of a line
$  | Anchor for the end of a line
\A | Anchor for the start of a string
\z | Anchor for the end of a string
.  | Any character
\w | Any letter, digit, or underscore
\W | Anything that \w doesn’t match
\d | Any digit
\D | Anything that \d doesn’t match (non-digits)
\s | Whitespace (spaces, tabs, newlines, and so on)
\S | Non-whitespace (any visible character)

- Second Table:

Modifier | Description
---|---
\*     | Match zero or more occurrences of the preceding character, and match as many as possible.
\+     | Match one or more occurrences of the preceding character, and match as many as possible.
\?     | Match either one or none of the preceding character.
\*\?   | Match zero or more occurrences of the preceding character, and match as few as possible.
\+\?   | Match one or more occurrences of the preceding character, and match as few as possible.
\{x\}  | Match x occurrences of the preceding character.
\{x,y\}| Match at least x occurrences and at most y occurrences.


[top](#top)
### Matches
```rb
  puts "there is not any digit in this sentence" unless "sample Sentence" =~ /[0-9]/
  # another way as always
  puts "there is not any digit in this sentence" unless "sample Sentence".match(/[0-9]/)
```
  - be care like below:
  ```rb
    x = "This is a test".match(/(\w+) (\w+) (\w+)/)
    => #<MatchData "This is a" 1:"This" 2:"is" 3:"a">
    x.length
    => 4
    x = "This is a test".match(/\w+ \w+ \w+/)
    => #<MatchData "This is a">
    x.length
    => 1
  ```
  
[top](#top)
### Array
- is [...] and accept every type in one array.
- string to array:
```rb
  p "Strings.....".split(/\./){.inspect}   # _inspect_ is optional
```
- deal with array:
```rb
  [...].each {|elem| ....}
  [...].collect{|elem| ....}   #result is a array
  %w{word1 word2 word3 ...}.select{|word| !%w{elem1 elem2 ...}.include?(word)} # return an array that not include in clause
  %w{word1 word2 word3 ...}.reject{|word| !%w{elem1 elem2 ...}.include?(word)} # return an array that include in clause
  String.split(/.../)  #return an array, default seperator is Space
  Array.join('...') # return a string, default joinner is Space
```
* to define a string array as simple way: `a=%w{word1 word2 word3 ...}`

[top](#top)
### Hashes
- hash inside hash:
```rb
  people = {'Frist' => {'name' => 'Mohammad','age' => 63,'gender' => 'male',
            'favorite painters' => ['Monet', 'Constable', 'Da Vinci']},
            'Second' => {'name' => 'Ali','age' => 55,'gender' => 'female'}}
  puts people['Frist']['age']
  puts people['Second']['gender']
  p people['Second']
```

[top](#top)
### Time
- time in Ruby store ms from 1/1/97, it means you could do calculation on it.
```rb
  Time.now + 10 # be care _10_ here means __10 Second not milisecond__
```
  - some developer extend ___Fixnum___ class to below:
  ```rb
    class Fixnum
      def minutes
        self*60
      end
      def hours
        self * 60 * 60
      end  
      def days
        self * 60 * 60 * 24
      end  
    end
  ```
  then we could use command like:
   ```rb
     Time.now + 19.hours
   ```
  - _Time.local_ , _Time.gm_ , _Time.utc_ are local time, greendwich and Universal time respectively:
  ```rb
    Time.local(yAER,mONTH,dAY,hOUR,mINUTE,sECOND,mILISECOND) # all are numbers
  ```
  - Find Time element from number:
  ```rb
    Time.at(1431431418).year
    # => 2015
  ```
- Time Object Methods Used to Access Date/Time Attributes:
Method | Returns
---|---
hour | A number representing the hour in 24-hour format ( 21 for 9 p.m., for example).
min | The number of minutes past the hour.
sec | The number of seconds past the minute.
usec | The number of microseconds past the second (there are 1,000,000 microseconds per second).
day | The number of the day in the month.
mday | Synonym for the day method, considered to be “month” day.
wday | The number of the day in terms of the week (Sunday is 0 , Saturday is 6 ).
yday | The number of the day in terms of the year.
month | The number of the month of the date ( 11 for November, for example).
year | The year associated with the date.
zone | Returns the name of the time zone associated with the time.
utc? | Returns true or false depending on if the time/date is in the UTC/GMT time zone or not.
gmt? | Synonym for the utc ? method for those who prefer to use the term GMT.
  for example:
  ```rb
    irb(main):027:0> Time.at(1431431418).wday
    # => 2
  ```
### Ranges
its simple:
```rb
  ('a'..'z')
```
  - it has some methodes:
    1. convert to aray: `('a'..'z').to_a`
    2. `each` methode like as always.
    3. member test: `('a'..'z').include?('S') `
### Symbols
- in a simple explanation: like string, but same _Symbole_ use one place of memory. we used it in _hash_ definition.
```rb
  sYmbole= :Name
```
- it has `to_s` methode to convert _Symbole_ to _String_

# Flow Controls and Conditions
### if
```rb
  if Condition Clause
    result
  elsif ...
    ...
  else
    ...
  end
  Variable= Condition Clause? TrueResult:FalseResult
```
### unless

[top](#top)
### case
```rb
  case Param 
    when FirstCondition
    Variable=Result1
    when SecondCondition
    Variable=Result2
    ...
    else
    ...
    end
  # another Way
  Variable=case Param
    when FirstCondition
    Result1
    ...
    end
```
    
    
[top](#top)
### while

[top](#top)
### until
```rb
  i = 1
  i = i * 2 until i > 1000
  puts i
```

[top](#top)
# CodeBlocks,Functions,Procedures,Lambdas
### Code Blocks
- definition:
```rb
  {puts "Hello"}
  do
    puts "Hello"
  end
  1.upto(10).each {|n| puts n*19}
```
- we could use _Lambda_ to store _code block_ and then call it:
```rb
  lAMBDA= lambda {|q| q.each {|q| puts q}}
  lAMBDA.call(1.upto(10))
```

[top](#top)
### Functions
- definition
```rb

```
- Block as Input parameter:
```rb
  def func1(a,&codeBlock)
    a.each{|a| codeBlock.call(a)} 
  end
  func1(%w{1,2,3,4,5}) {|a| put a}  # as you see its very fun lang, we use _a_ in all block without confusing :-)
```

[top](#top)
### Procedures
- definition
```rb
  Proc.new { puts "Hello"}
  Proc.new do
    puts "Hello"
  end
  proc {puts "Hello"}
  test= proc {puts "Hello"}
  test.call()
```

[top](#top)
### Lambdas
```rb
  lambda {puts "Hello"}
  lambda do
    puts "Hello"
  end
  -> {puts "Hello"}
  -> (arg) {puts arg}
  -> { |arg| puts arg}
  test= ->{1.upto(10).each{|n| n}
  test.yield[0]
```

[top](#top)
# Class
## definition:
```rb
  class ClassName
  attr_accessor :varName1, ...
    def initialize(InputParams)
      @InstanceVariables= assing InputParams
      ...
    end
    if defined?(@@ClassVariable)
      Some thing with @@ClassVariable
    def InstanceMethod(InputParams)
      ...
    end
    def [self|ClassName].ClassMethod(...)
      ...
    end
    private
      def ...
        ...
      end
    
    ...
  end
```
  - you could define all things in class as public and after that, use `private :def_Name :... ` to make them as private.
  - `protect :... ` is last scope of __OOP__ .
  
- What is diffrent between Instance and class variable|Method?
  - Instance Variable is define for each new Object of class but
  - Class Variable is static object in class and is shared between all Objects those creat from class
- what does _attr\_accessor_ do?
  - it creates _Setter_ and _getter_ for all variables defined. if we define `attr_accessor :varName`, 
    it will does like below:
  ```rb
    def varName=(varName)
      @varName=varName
    end
    def varName
      @varName
    end
  ```
## Structure
we could say with a good precision that the __Struct__ure is the same as class:
```rb
  StrucName=Struct.new(:var1,:var2,...)
  class StructName
    attr_accessor :var1,:var2,...
    def initialize(var1,var2,...)
      @var1=var1
      @va2=va2
      ...
    end
  end
  structVar=StructName.new(var1,var2,...)
```

## Inheritence:
```rb
  class ParentName
    def initialize(..)
      ...
    end
    def Test(InputParams)
      ...
    end
    ...
  end
  class ChildName < ParentName
    ...
    def Test
     ... + super   #nice!! you are free of howmany InputParams in ParentClass
  end
```
## Nested Class
Sometimes we need classes but when a main class was defined. for example we need _Pen_ , _Eraser_ , _Line_ when we want 
  _Draw_ and create _Draw_ class:
```rb
  class Draw
    def cREATE_a_Line
      Line.new
    end
    class Line
      def lINE_methode
        p "Hello I'm a line"
      end
    end
  end
```
How to call nesteded class:
```rb
  a=Draw.new
  a.lIne.lINE_methode
  b=Draw::Line.new
  b.lINE_methode
```
- actually we could access all public _class's_ methodes with double _colon_.

[top](#top)
# Namespaces, Modules and Mix-Ins
## Namespaces, Modules
simply you call other _ruby_ files to include their codes in current _ruby file_.
assume we have __File1.rb__ as below:
```rb
  module NAMESPACE1
    class ClassTest
      def classtest
        p "Hello From First NameSpace from ClassTest"
      end
    end
    def self.test
      p "Hello From First NameSpace in Module"
    end  
  end
  def test 
    p "Hello From First NameSpace"
  end
```
and __File2.rb__ like this:
```rb
  module NAMESPACE2
    class ClassTest
      def classtest
        p "Hello From First NameSpace from ClassTest"
      end
    end
    def self.test
      p "Hello From Second NameSpace in Module"
    end  
  end
  def test 
    p "Hello From Second NameSpace"
  end
```
now, in __File3.rb__ we have:
```rb
  {require|require_relative|load} './File1.rb'
  {require|require_relative|load} './File2.rb'
  test    <= this ambigous function calling
  NAMESPACE1.test
  NAMESPACE2.test
  NAMESPACE1::ClassTest.new.classtest
  NAMESPACE2::ClassTest.new.classtest
```
then NameSpace and Module should be clear.
- what are require,require_relative,load?
  - __require__ search for a file in _Rub_Path_ directory, those fine in __$LAOD\_PATH__(or $: in shorthand)
    while __load__ and __require\_relative__ only serach in _current directory_
  - __require__ and __require\_relative__ load file _only one time_ while __load__ load file _each time you call_
  - in __load__ command, _.rb_ postfix _should be mentioned_ while __require__ and __require\_relative__ donot need.
- these three command like other ruby commands. it means you could use them every where:
```rb
  %w{file1 file2 file3 file4 file5}.each { |l| require l }
  require $debug_mode==0? "File1":"File2"
```
- what dows happen in Nested Inclusion:
  - assume in _a.rb_ we include _b.rb_ and in that we include _c.rb_ and in that we include _d.rb_ and in _e.rb_ we 
    include __a.rb__ and __test__ is function in __d.rb__, we simply could call it in __e.rb__.

## Mix-Ins
___ruby___ has not got multi inheritances.
OK! but it has solution called: __Mix-Ins__.
consider below class:
```rb
  class Test
    include Enumerable
    Const= %w {M o h a m a d}
    def each                     <= if we donot include Enumerable, we could not define this
      Const.each {|a| yield a*2}
    end
  end
```
now, we could use each item that has _iterate_ like _collect_,_select_,_detect_,_sort_ for ___Class Instance__:
```rb
  a=Test.new
  a.each{|w| p w}
```

## Modules


[top](#top)

[top](#top)

[top](#top)

[top](#top)

[top](#top)

[top](#top)

[top](#top)
