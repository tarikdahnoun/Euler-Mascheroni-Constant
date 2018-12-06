#Kemper Exam 3 Question 3
#Euler-Mascheroni Constant

import numpy as np

nts=5000
    
def fA(X,Y):
    return (X-1)/((1-X*Y)*(np.log(X*Y)))

def fB(X):
    return np.tanh(X)/X
    
def midpointA(nts): #first integral
    xi=0
    xf=1
    x=np.linspace(xi,xf,nts)
    dx=x[1]-x[0]
    
    yi=0
    yf=1
    y=np.linspace(yi,yf,nts)
    dy=y[1]-y[0]
    
    I_a=np.zeros((nts,nts))
    for i in range(0,nts-1):
        for j in range(0,nts-1):
            I_a[i,j]=fA(x[i]+dx/2,y[j]+dy/2)*dx*dy
    Ia=sum(I_a)
    Ia=sum(Ia)
    return Ia
     
IA=midpointA(nts) #Value of first integral
print "The value of the first integral is",IA

def midpointB(nts,b): #second integral
    xi=0
    x=np.linspace(xi,b,nts)
    dx=x[1]-x[0]
    
    I_b=np.zeros(nts)
    for i in range(0,nts-1):
        I_b[i]=fB(x[i]+dx/2)*dx
    Ib=sum(I_b)    
    return Ib
    
def fb_largeB(b):
    return np.log(b)
    
#I could have done this by comparing arrays, but thought this work work quicker
#E-M constant is 0.5772156649015328
#Using Algebra, C2 should be about 0.818774 (Gamma-ln(pi/4))
count=1
tol=.00000001
# while abs(midpointB(nts,count)-fb_largeB(count)-(0.5772156649015328-np.log(np.pi/4)))>=tol:
while (abs((midpointB(nts,count)-fb_largeB(count))-(midpointB(nts,count+1)-fb_largeB(count+1))))>=tol:
    count+=1
print "A b value of tolerance",tol,"is b=",count

IB=midpointB(nts,count)
print "The value of the second integral is",IB  
    
FB=fb_largeB(count)
print "The value of the large B integral is", FB

C=IB-FB
print "The value of the C2 is",C
