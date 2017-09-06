<div dir=rtl>بنام خدا</div>

###### top
- [Description](#description)
- [Syntax](#syntax)
- [Special Functions](#special-functions)
- [Indicators](#indicators)



[top](#top)
# Description
the syntax like C Language,

[top](#top)
# Syntax
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
8. Variables:
  - Scope of Variables:
    1. Locale
    2. Global
  - Extern Variable: Define with _extern_ Keyword and Users could modify it.
  ```mql4
    extern DataaType VariableName=DefaultValue
  ```
9. Preprocessors: are the instructions you give to the compiler to carry them out before starting your app.
  - Define: used to define Constant:
  ```mql4
    #define ConstantName Value;
  ```
  - Property: are the properties of your App.
  ```mql4
    #property Name Value;
  ```
    - Table of All Propertis:
    
    Constant|Type|Description
    ---|---|---
    link|string|a link to the company website
    copyright|string|the company name
    stacksize|int|Stack Size
    indicator_chart_window|void|Show the indicator in chart Window
    indicator_separate_window|void|Show the indicator in separate Window
    indicator_buffers|int|the Number of buffers for calculations,up to 8
    indicator_minimum|int|bottum border for Chart
    indicator_maximum|int|Top border for the Chart
    indicator_colorN|color|the Color for displaying line N,up to 8
    indicator_levelN|double|predefined Level N for separate window custom Indicator,up to 8
    show_confirm|void|Show confirmation Message appear before run script
    show_inputs|void|appears property sheet before run script
    
10.

[top](#top)

#Indicators

[top](#top)

# Special Functions
- Program Bodies:
  1. Init:
  ```mql4
    int init(){
    
    }
  ```
  2. DeInit():
  ```mql4
    int deinit(){
    
    }
  ```
  3. Start:
  ```mql4
    start(){
    
    }
  ```
  
[top](#top)
#
[top](#top)
#
[top](#top)
#
