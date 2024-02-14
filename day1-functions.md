# Day 1 - Functions

Here are some of the codes I came across during my learning, which helped me to understand python functions better.

### Calculating number of days, based on given time period in years, months and days.
```python
# This function calculates the number of days in a variable number of
# years, months, and days. These variables are provided by the user and
# are passed to the function through the function’s parameters.
def find_total_days(years, months, days):
year= days * 365
month= days * 30
my_days = (years*365) + (months*30) + days
# Use the "return" keyword to send the result of the "my_days"
# calculation to the function call.
return my_days
# Function call with user provided parameter values.
print(find_total_days(2,5,23))
```

### Conversion of volume
```python
# Calculate value of the "ml" variable using the parameter variable 
# "fluid_ounce". There are approximately 29.5 milliliters in 1 fluid
# ounce.
    ml = fluid_ounce * 29.5  
# Return the result of the calculation.  
    return ml
 
# Call the conversion from within the print() function using 2 fluid 
# ounces. Convert the return value from a float to a string.  
print("The volume in milliliters is " + str(convert_volume(2)))
 
# Call the function again and double the 2 fluid ounces from within
# the print function.
print("The volume in milliliters is " + str(convert_volume(2)*2))
# Alternative calculation:
# print("The volume in milliliters is " + str(convert_volume(4))

```

Convert a given time from hours, minutes and seconds to seconds.
```python
    def convert_seconds(seconds):
        hours = seconds // 3600
        minutes = (seconds - hours * 3600) // 60
        remaining_seconds = seconds - hours * 3600 - minutes * 60
        return hours, minutes, remaining_seconds
     
    hours, minutes, seconds = convert_seconds(5000)
    print(hours, minutes, seconds)

```

### Calculation of area of triangle
```python
    def area_triangle(base, height):
        return base*height/2
    area_a = area_triangle(5,4)
    area_b = area_triangle(7,3)
    sum = area_a + area_b
    print("The sum of both areas is: " + str(sum))
```

### Calculate the area of circle
```python
import math  
def area\_of\_the\_circle (Radius):   
	area = Radius\*\* 2 \* math.pi  
    return area  
Radius = float (input ("Please enter the radius of the given circle: "))  
print (" The area of the given circle is: ", area\_of\_the\_circle (Radius))

```