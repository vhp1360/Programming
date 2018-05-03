<div dir=rtl>بنام خدا</div>

- [Type](#type)
  - [String literal](#string-literal)
    - [Substitution](#substitution)
    - [Itration](#itration)
    - [Regular Experssion](#regular-experssion)
    - [Matches](#matches)


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













