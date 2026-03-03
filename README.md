
# Experiment-3-Correlation-and-Regression-for-Data-Analysis

# Aim: 
	To analyse given data using co-efficient of correlation and regression line 
  
  <img width="1180" height="120" alt="image" src="https://github.com/user-attachments/assets/62ba8618-34f6-4718-9233-b36f6ca975ff" />
  
# Software Required: Python 

# Theory
1. Correlation measures the strength and direction of the relationship between two variables (say, X and Y).
  
2. If one variable changes, correlation tells us how the other variable changes on average.
   
3. The correlation coefficient (r) ranges from –1 to +1: +1 means perfect positive correlation, –1 means perfect negative correlation, and 0 means no correlation.
   
4. Regression shows how one variable (Y) depends on another variable (X). It provides a line (equation) that best fits the data.
   
5. The regression line of Y on X is expressed as:  Y = a + bX,  where a is the intercept and b is the regression coefficient (slope).
   
# Algorithm 

<img width="1143" height="477" alt="image" src="https://github.com/user-attachments/assets/d3d41b8d-bee6-4b5f-a6fe-ef6997126cf2" />

# Program
**_Name : SRIDHAR C<br>
 Reg No : 212225040425 <br>
 Slot Name : T1-I5<br>
 [colab link](https://colab.research.google.com/notebooks/intro.ipynb#scrollTo=VFUkzd183Wif&line=39&uniqifier=1)_**  

```py
import numpy as np
import math
import matplotlib.pyplot as plt


x=[int(i) for i in input("Enter x values with space seperated:").split()]
y=[int(i) for i in input("Enter y values with space seperated:").split()]

if len(x) != len(y):
  raise SystemExit("Length of x and y should be same")

N=len(x)

Sum_x=0
Sum_y=0
Sum_xy=0
Sum_x2=0
Sum_y2=0

for i in range(N):
  Sum_x+=x[i]
  Sum_y+=y[i]
  Sum_xy+=x[i]*y[i]
  Sum_x2+=x[i]*x[i]
  Sum_y2+=y[i]*y[i]

den=math.sqrt((N*Sum_x2-Sum_x**2)*(N*Sum_y2-Sum_y**2))
if den==0:
  raise SystemExit("Denominator is zero")

r=(N*Sum_xy-Sum_x*Sum_y)/den
print(f"The correlation coefficient is {r:.3f}")

m=(N*Sum_xy-Sum_x*Sum_y)/(N*Sum_x2-Sum_x**2)

xmean=Sum_x/N
ymean=Sum_y/N

c=ymean-m*xmean

print(f"The equation of line is y={m:.3f}x+{c:.3f}")

plt.scatter(x,y)

def Reg(xv):
  return ymean+m*(xv-xmean)

x_plot=np.linspace(min(x),max(x),51)
y_plot=Reg(x_plot)

plt.plot(x_plot,y_plot,'r')

plt.xlabel('x')
plt.ylabel('y')
plt.legend(['Regression Line','Data points'])
plt.grid()
plt.show()
```
# Output
<img width="711" height="628" alt="image" src="https://github.com/user-attachments/assets/862a75c4-93f8-491e-a699-6d8f58b30da1" />


# Result
  The correlation and regression for data analysis of objects from feeder using probability distribution are calculated.
