
# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
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
