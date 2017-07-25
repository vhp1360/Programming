<div dir=rtl>بنام خدا</div>

###### top
- [Using Structure](#using-structure)
- [Syntax](#syntax)


[Top](#top)
### Using Structure
1- mustache <YAML> <FILE>

2- mustache --compile <FILE>

3- mustache --tokens <FILE>

- Example:
```vim
  cat data.yml
```
    ---
     names: [ {name: chris}, {name: mark}, {name: scott} ]
    ---
```vim
  cat template.mustache
```
    {{#names} 
      Hi {{name}}!
    {{/names}}
```vim
  cat data.yml template.mustache | mustache
```
    Hi chris!
    Hi mark!
    Hi scott!

[Top](#top)

### Syntax
1. logic less : it means no cluase and no loop.
  - with below hash:
    ```js
      {
      "name": "Chris",
      "value": 10000,
      "taxed_value": 10000 - (10000 * 0.4),
      "in_ca": true
    }
  ```
  - for below HTML code:
  ```js
    Hello {{name}}
    You have just won {{value}} dollars!
    {{#in_ca}}
    Well, {{taxed_value}} dollars, after taxes.
    {{/in_ca}}
  ```
  - we will have:
  ```js
    Hello Chris
    You have just won 10000 dollars!
    Well, 6000.0 dollars, after taxes.
  ```
2. Variables.
  - with below hash:
  ```js
    {
      "name": "Chris",
      "company": "<b>GitHub</b>"
    }
  ```
  - and below HTML Code:
  ```js
    * {{name}}
    * {{age}}
    * {{company}}
    * {{{company}}}
  ```
  - we will have below output:
  ```js
    * Chris
    *
    * &lt;b&gt;GitHub&lt;/b&gt;
    * <b>GitHub</b>
  ```
3. Section.
  - with this hash:
  ```js
    {
      "person": false
    }
  ```
  - and this HTML Code:
  ```js
    Shown.
    {{#person}}
      Never shown!
    {{/person}}
  ```
  - we will have:
  ```js
    Shwon
  ```
4. Loop: if a vasriable with Pound, has more than one Item,it recursively repeat
  - with this hash:
  ```js
    {
      "repo": [
        { "name": "resque" },
        { "name": "hub" },
        { "name": "rip" }
      ]
    }
  ```
  - and this HTML Code:
  ```js
    {{#repo}}
      <b>{{name}}</b>
    {{/repo}}
  ```
  - output will be:
  ```js
    <b>resque</b>
    <b>hub</b>
    <b>rip</b>
  ```
  - or:
  ```js
    {{#list}}
      {{property}} // item.property
      or
      {{.}} // item
    {{/list}}
  ```
5. Lambdas: in this case, {{tag}} pass as Plain Text to itself block and would have meaning in itself Block.
  - whit:
  ```js
    {
      "name": "Willy",
      "wrapped": function() {
        return function(text, render) {
          return "<b>" + render(text) + "</b>"
        }
      }
    }

  ```
  - and HTML Code:
  ```js
    {{#wrapped}}
      {{name}} is awesome.
    {{/wrapped}}

  ```
  - the output will:
  ```js
    <b>Willy is awesome.</b>
  ```
6. Inverted Section.
  - with:
  ```js
    {
      repo: []
    }
  ```
  - and:
  ```js
    {{#repo}}
      <b>{{name}}</b>
    {{^repo}}
      nothing :-)
    {{/repo}}
  ```
  - we will have:
  ```js
  
  ```
7. Comment.
```js
  {{ ! Comment }}
```
8. Partials:rendred at runtime,

9. Set Delimiter: change sign to any thing. use = to do it:
```js
  {{default_sign}}
  {{! define a new Sign}} {{=<% %>=}} 
  <% New_sign %>
  <% ={{ }}= %>
  {{ returnback_to_default_sign }}
```
10. 
  
  
  
  
  
  
  


