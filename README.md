# Ex.05 Design a Website for Server Side Processing
# Date:17.10.24
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
math.html

<!DOCTYPE html>
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title> Power </title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color: rgb(233, 250, 230);
}
.edge {
    width: 100%;
    padding-top: 250px;
    text-align: center;
}
.box {
    display: inline-block;
    border: thick dashed rgb(117, 6, 243);
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: pink(167, 240, 9);
}
.formelt {
    color: sky blue;
    text-align: center;
    margin-top: 7px;
    margin-bottom: 6px;
}
h1 {
    color: violet;
    padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1> Power </h1>
        <h3>Saranya (24900574) </h3>
        <form method="POST">
            {% csrf_token %}
            <div class="formelt">
                Intensity: <input type="text" name="intensity" value="{{i}}">m<br/>
            </div>
            <div class="formelt">
                Resistance: <input type="text" name="resistance" value="{{r}}">m<br/>
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"><br/>
            </div>
            <div class="formelt">
                Power: <input type="text" name="power" value="{{power}}">m<sup>2</sup><br/>
            </div>
        </form>
    </div>
</div>
</body>
</html>


views.py

from django.shortcuts import render 
def power(request): 
    context={} 
    context['power'] = "0" 
    context['i'] = "0" 
    context['r'] = "0" 
    if request.method == 'POST': 
        print("POST method is used")
        i = request.POST.get('intensity','0')
        r = request.POST.get('resistance','0')
        print('request=',request) 
        print('Intensity=',i) 
        print('Resistance=',r) 
        power = int(i) * int(i) *int(r)
        context['power'] = power 
        context['i'] = i
        context['r'] = r 
        print('Power=',power) 
    return render(request,'mathapp/math.html',context)


urls.py

from django.contrib import admin 
from django.urls import path 
from mathapp import views 
urlpatterns = [ 
    path('admin/', admin.site.urls), 
    path('power/',views.power,name="power"),
    path('',views.power,name="power"
    
]
```

# SERVER SIDE PROCESSING: 


![Screenshot 2024-12-11 180735](https://github.com/user-attachments/assets/b736797d-9867-4fd4-9cb6-5ad0b86af517)


# HOMEPAGE:

![Screenshot 2024-12-11 180519](https://github.com/user-attachments/assets/8445fdcd-a7fc-47d1-beff-5d339bdef62a)


# RESULT:
The program for performing server side processing is completed successfully.
