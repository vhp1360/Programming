<div dir='rtl'>بنام خدا</div>
<div dir='rtl'>خلاصه ای بر سرور فسک</div>

```python
  from flask import Flask
  app=Flask(__name__)
  @app.route('/')
  def index():
    # this is home page and complete it

  app.route('/NewPage')
  def NewPage():
    <h1>this id new page</h1>

  app.route('/dynamoPage/<Variable>')
  def dynamoPage(Variable):
    return "variable passed , was %s" % Variable

  from flsk import request
  app.route('/PageRequest')
  def PageRequest():
    if request.method=='GET':
      return "your request type is GET"
    else if request.method=='POST':
      return "your request type is POST"

  from flask import renden_template
  app.route("/Profile/<UserName>")
  def Profile(UserName):
    return render_template("profile.html",name=UserName) # in profile.html to calling variable should use {{}} into html tags
          # also we could call flask function in this way in html tags
          # like <link rel="stylesheet" type="text/css" href="{{url_for('static'),filename='style.css'}}">
  # so we could pass Variable to main page
  @app.route('/<UserName>')
  def index(UserName=None):
    return render_template("MainPage.html", name=UserName)





  if __name__== "__main__":
    app.run(debug==True)
  ```

<div dir='rtl'>نمونه کدهای استفاده از فسک در صفحات اچ-تی-ام-ال</div><br\>
Sample using flask in Html pages<br/>
{% if UserName %}
  Html tags
{% elif ... %}
  ...
{% endif %}

{% for .... %}

{% endif %}
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>
<div dir='rtl'></div>

