<div dir=rtl>بنام خدا</div>

- [Type](#type)
  - [String literal](#string-literal)
    - [Substitution](#substitution)
    - [Itration](#itration)
    - [Regular Experssion](#regular-experssion)



# Type
## String literal
### Substitution
```rb
  puts "strings.....".sub("SomeThings","SomeThingsElse")
```
### Itration
```rb
  "Strings.....".scan(/../) do |q| puts q  //puts 2 characters each time
```
### Regular Experssion
- Fisrt Table:

Character | Meaning
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
*     | Match zero or more occurrences of the preceding character, and match as many as possible.
+     | Match one or more occurrences of the preceding character, and match as many as possible.
*?    | Match zero or more occurrences of the preceding character, and match as few as possible.
+?    | Match one or more occurrences of the preceding character, and match as few as possible.
?     | Match either one or none of the preceding character.
{x}   | Match x occurrences of the preceding character.
{x,y} | Match at least x occurrences and at most y occurrences.

