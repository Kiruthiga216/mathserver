# Ex.05 Design a Website for Server Side Processing
# Name:KIRUTHIGA.B
# Reg.no:212224040160
# Date:11/04/2025
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

<html>
    <head>
        <title> Calculate the power</title>
        <style type="text/css">
        body {
           background-color: pink;
           align-items: center;
        }
        
        h1 {
           color: green;
           padding-top: 20px;
        }
        </style>
        </head>
        <body >
            <h1 align="center">calculating power of a lamp</h1>
            <form action="{% url 'home' %}" method="post" align="center">
                {% csrf_token %}
                Intensity:
                <input type="number" name="intensity-input"><br>
                Resistance:
                <input type="number" name="resistance-input"><br>
                <button type="submit">Calculate</button>
                <p algin="center">The power of the lamp is: {{ output }}</p>
            </form>
        </body>
</html>

url.py


from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
    path('',views.power, name='home'),
]

views.py

from django.shortcuts import render

def power(request): 
    if request.method == 'POST':
        intensity_value = int(request.POST.get('intensity-input'))
        resistance_value = int(request.POST.get('resistance-input'))
        power = (intensity_value ** 2) * resistance_value
        return render(request, 'math.html', {'output': power})
    return render(request, 'math.html')



```
# SERVER SIDE PROCESSING: 

![alt text](<Screenshot 2025-04-11 160241.png>)
![alt text](<Screenshot 2025-04-11 160308.png>)



# HOMEPAGE:
![alt text](<Screenshot 2025-04-11 145258.png>)

# RESULT:
The program for performing server side processing is completed successfully.
