<div dir=rtl>بنام خدا</div>

##### top

- [Layout](layout)


### Layout
I summarized [this](http://learnlayout.com/no-layout.html) article.
if there is no layout, every things come consective(line long as much as it can)
- display:
  1. every object has itself display.
     1. __block__ as default for _div,p,form,header,footer,section_ .Start  On New line and stratches from left to right.
        - set _width_ to Number and _margine_ to auto make it centeral and prevent of streches.
        - in above set _max-width_ will beter handle small window.
        - _-webkit-box-sizing,-moz-box-sizing,box-sizing: border-box;_ make object no longer than its width.
     2. __inline__ as default for _span,a_ can wrap things inside a object like _p_ wihtout disrupting it.
     3. __none__ as default for __script__, that wouldn't come on page rendereing
  2. position:
     1. __static__ is default Position and object would't reposition any change of window or scroll
     2. __relative__ means realtive to _top,left,right,bottom_ properties those you define, without __relative__ you wouldn't give response from those properties
    ![Alt RelativeImg](Img/Relative01.png)
     3. __fixed__ , fix Object from scroll in viewport, it need position properties
     4. __absolute__ same as _fixed_ but inside the its parent Object
  ![Alt RelativeImg](Img/Position01.png)
  3. float: useful for wrap text around a image: <p ...> <img style="float:right" ...> Text ...</p>
  ![Alt RelativeImg](Img/Float01.png)
  4. clear: useful to prevent overlapping of floating Objects.
  ![Alt RelativeImg](Img/Clear01.png)
  ![Alt RelativeImg](Img/Clear02.png)
  
