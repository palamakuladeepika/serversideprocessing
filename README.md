# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Create a Django project.


### Step 2:
Create an App named mathapp.


### Step 3:
In mathapp create a folder named template.In template folder create an anoter folder named mathapp.


### Step 4:
Create a html document in the mathapp.


### Step 5:
In the html document design the page as required for getting the input values for doing mathematical calculation.


### Step 6:
Add the formula in views.py.


### Step 7:
Link the html document to urls.py.


## PROGRAM :
## HTML Code:
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Area</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <style>
        body{
            text-align: center;
            background-color: pink;
        }
        .maindiv{
            margin-left:400px;
              text-align: center;
            border-style: dashed;
            width: 550px;
            height: 300px;
            background-color: blurywood;
        }
        h1{
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>Server Side processing</h1>
    
    <div class="maindiv">
        <h1>Area of Rectangle</h1>
        <form method="POST">
            {% csrf_token %}
            Length = <input type="text" name="length" value="{{l}}"> meters <br/>
            <br/>
            width = <input type="text" name="width" value="{{w}}"> meters<br/>
            <br/>
            <input type="submit" value="Calculate"><br/>
            <br>
            Area = <input type="text" name="area" value="{{area}}"> meter<sup>2 </sup><br/>
        </form>
        <br>
        <br>
        <footer>
            Developed by:P.Deepika.
        </footer>
    </div>
</body>
</html>
```
## View.py:
```
from django.shortcuts import render

def areacalculation(request):
    context = {}
    context["area"] = "0"
    context["l"] = "0"
    context["w"] = "0"
    if request.method == "POST":
        b = request.POST.get("length","0")
        h = request.POST.get("width","0")
        area = (int(l) * int(hw)
        context["area"] = area
        context["l"] = l
        context["w"] = w
    return render(request,"mathapp/area.html",context)
```
## URLs.py:
```
from django.contrib import admin
from django.urls import path
from mathapp import views

urlpatterns = [
   path('admin/', admin.site.urls),
   path("areaofrectangle/",views.areacalculation,name="areaofrectangle"),
   path("",views.areacalculation,name="areaofrectangleroot")
]
```

## OUTPUT:
![Deepu](https://user-images.githubusercontent.com/94154679/154816020-cfbe95d9-641f-40ed-bf49-84c9aa09bd57.jpeg)

## Result:
Therefor the above codes are successfully executed to run server side programming and mathematical calcualtions.

