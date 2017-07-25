<div dir=rtl>بنام خدا</div>
###### Top

- [Syntax](#syntax)
  - [Variables](#variables)
  - [Function](#function)
  - [Conditional](#conditional)
  - [Arrays](#arrays)
  - [Objects](#objects)
  - [Operators](#operators)
  - [Chaining](#chaining)
  
- [](#)
- [](#)

[the good article](#https://www.discovermeteor.com/blog/javascript-for-meteor/) regarding Meteor

### Syntax
- [Variables](#variables)

  1- Local
  ```js
    var Var;
    var Var=Value;
  ```
  2- Global:
  ```js
    Var=Value;
  ```
- [Function](#function): definition and usage
  1.Regular definition:
  ```js
    var MyFunction=function(Args){
      //Some things to do
    };
    MyFunction(MyArgs);
  ```
    - :bell:  _Functions_ in **JS** is a variable it means you could use function like below:
  ```js
    var Myf=function(f,a){ return f(a) };
    var square=function(a){return a*a};
    Myf(square,10);
  ```
  2. Anonymouse Function:
  ```js
    Myf(function(a){ a+3;},10}); //100  
  ```
- [Conditional](#conditional)
```js
  if (p) {
    return q;
  }
  else if (r){
    return s
  };
  if (p)
    return q;
  p ? q:s;
```
- [Arrays](#arrays)
```js
  a = [123, 456, 789];
  a[0]; //123
```
- [Objects](#objects)
```js
  myProfile = {
    name: "John Smith",
    email: "johnsmith@gmail.com",
    city: "San Francisco",
    points: 1234,
    isInvited: true,
    friends: [
      {
        name: "John Doe",
        email: "johndoe@gmail.com"
      },
      {
        name: "Jane Doe",
        email: "janedoe@gmail.com"
      }
    ]
  };
  myProfile.name; // John Smith
  myProfile.friends[1].name; // Jane Doe
```
- [Operators](#operators)
```js
  a="12";  -> assigh 12 to a
  a==12 // true -> check only value of variable
  a===12 //false -> check both value and type
  !a //false
```



- [Chaining](#chaining)
```js
  var myArray = [123, 456];
  myArray.push(789) // 123, 456, 789
  var myString = "abcdef";
  myString.replace("a", "z"); // "zbcdef"
  n = 5;
  n.double().square(); //100
```


  
  
