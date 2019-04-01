---
title:  form 1
description:111 description
primary_tag: tutorial>HANA
tags: [Tutorial > advanced, Tutorial > License ,tutorial:product/sapHana, tutorial:product/hana_studio]
time: 123
qrcode: true
---

[ACCORDION-BEGIN [STEP 1]( test)] 
   
[Done]
 
 
  **Example:code** 
```
let apples = 3
class TriangleAndSquare {
    var triangle: EquilateralTriangle {
        willSet {
            square.sideLength = newValue.sideLength
        }
```
***14Example:shell code** 
```shell
$ chmod a+x name.sh
$ ./name.sh Hans-Wolfgang Loidl
My first name is Hans-Wolfgang
My surname is Loidl
Total number of arguments is 2
```
***13Example: r code** 
```r
w = rnorm(500,0,1)  # 500 N(0,1) variates
v = filter(w, sides=2, rep(1/3,3))  # moving average
par(mfrow=c(2,1))
plot.ts(w, main="white noise")
plot.ts(v, ylim=c(-3,3), main="moving average")

# now try this (not in text):  
dev.new()  # open a new graphic device
ts.plot(w, v, lty=2:1, col=1:2, lwd=1:2)
```
***12Example:Python code** 
```python
"""This is a 
multiline docstring."""
print("Hello, World!")
```
