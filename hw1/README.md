# VP1: Simple Start for Vpython, Projectile \[the basic of Python, while\]  

## python3 x vpython7 Installation  
Follow the steps in “安裝” at http://tcjd71.wixsite.com/vpython/install to install (choose one of the following ways):  
(1) python3 + vpython7  
(2) anaconda + vpython http://tcjd71.wixsite.com/vpython/copy-of-python-2-vpython-6  
(3) both(1) + (2)  

Video: https://goo.gl/6F8uZp  

## Free Fall  
Type (type instead of “cut-and-paste” can help you learn coding) and then run the codes. *** Hold the right mouse button and move mouse to change view angle. Hold both buttons and move the mouse to zoom in or out.  

```python
from vpython import *
g=9.8           # g = 9.8 m/s^2
size = 0.25     # ball radius = 0.25 m
height = 15.0   # ball center initial height = 15 m

scene = canvas(width=800, height=800, center =vec(0,height/2,0), background=vec(0.5,0.5,0))   # open a window
floor = box(length=30, height=0.01, width=10, color=color.blue)                               # the floor
ball = sphere(radius = size, color=color.red, make_trail = True, trail_radius = 0.05)         
# the ball
msg =text(text = 'Free Fall', pos = vec(-10, 10, 0))

ball.pos = vec( 0, height, 0)         # ball center initial position
ball.v = vec(0, 0 , 0)                # ball initial velocity

dt = 0.001                            # time step
while ball.pos.y >= size:             # until the ball hit the ground
    rate(1000)                        # run 1000 times per real second
    
    ball.pos = ball.pos + ball.v*dt 
    ball.v.y = ball.v.y - g*dt
 

msg.visible = False
msg =text(text = str(ball.v.y), pos = vec(-10, 10, 0)) 
print(ball.v.y)
```


## Arrow


## Homework
