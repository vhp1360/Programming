<div dir=rtl>بنام خدا</div>

- [Type](#type)
  - [String literal](#string-literal)
    - [Substitution](#substitution)
    - [Itration](#itration)
    - [Regular Experssion](#regular-experssion)
    - [Matches](#matches)
    - [Array](#array)
    - [Hashes](#hashes)
- [Flow Controls and Conditions](#flow-controls-and-conditions)
  - [Code Blocks](#code-blocks)
  - [Functions](#functions)
  - [Procedures](#procedures)
  - [Lambda](#lambda)
    

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
*     | Match zero or more occurrences of the preceding character, and match as many as possible.
+     | Match one or more occurrences of the preceding character, and match as many as possible.
*?    | Match zero or more occurrences of the preceding character, and match as few as possible.
+?    | Match one or more occurrences of the preceding character, and match as few as possible.
?     | Match either one or none of the preceding character.
{x}   | Match x occurrences of the preceding character.
{x,y} | Match at least x occurrences and at most y occurrences.


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
```

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

[top](#top)

[top](#top)

[top](#top)

[top](#top)

[top](#top)

[top](#top)

[top](#top)

[top](#top)
