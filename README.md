global x, y
global vx, vy 
global contador
h, w = 500, 500
x, y = random(0, w), random(0, h)
vx, vy = 5, 3

def draw_bar(cx, cy):
    fill(20, 255, 188)
    rect(cx, cy, 60, 15)
     
    
def draw_pikachu(cx, cy, s):
    #yellow part
    fill(255, 232, 20)
    ellipse(cx, cy, 150*s, 150*s)
    ellipse(cx, cy, 150*s, 150*s)
 
    #cheeks: 
    fill(235, 115, 177)
    ellipse(cx - 50*s, cy + 15*s, 40*s, 40*s)
    ellipse(cx + 50*s, cy + 15*s, 40*s, 40*s) 
 
    #eyes:
    fill(0)
    ellipse(cx - 30*s, cy - 20*s, 20*s, 20*s)
    ellipse(cx + 30*s, cy - 20*s, 20*s, 20*s)
    fill(255)
    ellipse(cx - 25*s, cy - 20*s, 5*s, 5*s)
    ellipse(cx + 35*s, cy - 20*s, 5*s, 5*s)
    
    #nose:
    fill(0)
    ellipse(cx, cy + 10*s, 5*s, 5*s)
      
    #mouth
    fill(235, 124, 97)
    ellipse(cx, cy + 40*s, 25*s, 30*s )
    
    

def setup():
    size(h, w)
    background(25, 159, 255)
    noStroke()
    
    
def draw():
    global x, y
    global vx, vy
    
    s = 0.15
    r = 75 * s

    background (25,159, 225)
    cx, cy = w // 2, h // 2
    
    # cx, cy = mouseX, mouseY
    x, y = x + vx, y + vy
 
    draw_pikachu(x, y, s)
    if not 0 < x < w-r: 
        vx = -vx
    if not 0 < y < h-r:
        vy = -vy

    draw_bar(mouseX, h - 35)
