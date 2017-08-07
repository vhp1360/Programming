<div dir=rtl>بنام خدا</div>

###### top
- [Description](#description)
- [Syntax](#syntax)
- [Indicators](#indicators)
- [Special Functions](#special-functions)



[top](#top)
# Description
the syntax like C Language,

[top](#top)
#Syntax
1. Comment:
  - Single Comment:
  ```mql4
    // One Line Comment
  ```
  - Multiple Line:
  ```mql4
    /*
      these
      are
      Multiline
      Comments
    */
  ```
2. Datatypes:
  - int --> Integer from  -2147483648 to 2147483647 .
  ```mql4
    int intInteger = 0;
    int intAnotherIntger = -100;
    int intHexIntger=0x12;
  ```
  - bool --> Boolean .
  ```mql4
    bool I = true;
    bool bFlag = 1;
    bool bBool= FALSE;
  ```
  - char --> Character.
  ```mql4
    int chrA = 'A';
    int chrB = '$';
    int chrA = '\\'; //slash character
    int chrB = '\n'; //new line
  ```
    - This is the list of Escape Sequence characters used in MQL4.
CharName|CharSymbol
---|---
carriage return|\\r
new line|\\n
horizontal tab|\\t
reverse slash|\\\\
single quote|\\'
double quote|\\"
hexadecimal ASCII-code|\\xhh

  - string --> String.
  ```mql4
    string str2 = "Copy right © 2005, \"Forex -tsdforum\".";
  ```
  - double --> Floating Point Number.
  ```mql4
    double dblNumber1 = 1000000000000000;
    double dblNumber3 = 1/4;
    double dblNumber3 = 5.75;
  ```
  - color --> Color.
  ```mql4
    colorclr1= Red;
    colorclr1= C'128,128,128';
    colorclr1= 32768;
  ```
  - datetime --> DateTime.
  ```mql4
    datetime D1=D'2004.01.01 00:00' //New Year
    datetime D1=D'1980.07.19 12:30:27'
    datetime D1=D'19.07.1980 12:30:27'
    datetime D1=D'19.07.1980 12' //equalto 
    datetime D1=D'1980.07.19 12:00:00'
    datetime D1=D'01.01.2004' //equal to D'01.01.2004 00:00:00'
  ```
3. Arithmetical operators: \+,\-,\/,\%,\*,\+\+,\-\-,\+\=,\-\=,...,\>\>\=,\&\=,\|\=,\^\=
4. Relational operators:  \=\=,\>,\!\=,\&\&,\|\|,\!,\&,\^,\~
5. Loops:
  - For:
  ```mql4
    int i;
    for(i=0;i<100;i++)
    for(;;)
  ```
  - While:
  ```mql4
    int i=0;
    while(i<15){
    ...
    i++}
  ```
6. Conditions:
  - if Cluase:
  ```mql4
    if (Condition1){
      ...
    }
    if (Condition2){
      ...
    }
    ...
    else {
      ...
    }
  ```
  - switch:
  ```mql4
    switch(a)
      {
      case Case1:
        ...
        break;
      case Case2:
        ...
        break;
      ...
      default:
        ...
        break;
      }
  ```
7. Function:
```mql4
  [void || or any datatype] function(Param1 Datatype,...){
    Bodies
    ...
    return ...
  }
```


[top](#top)

#Indicators

[top](#top)

#Special Functions
1. Program Bodies:
  1/1. Init:
  ```mql4
    init(){
    
    }
  ```
[top](#top)
#
[top](#top)
#
[top](#top)
#
