import time
import turtle
import math

t = turtle.Turtle()
c = turtle.Turtle()
t.hideturtle()
t.speed(10)  # for hands
c.speed(10)  # for drawing clock


# turtle.Screen().bgcolor(0,0,0)
def polygon(s, l):
    for _ in range(s):
        c.fd(l)
        c.rt(360 / s)


def circle(r):
    c = math.pi * 2 * r
    polygon(int(c), 3)


def outer():
    c.penup()
    c.goto(-300, 300)
    c.pendown()
    c.begin_fill()
    c.fillcolor(0, 0, 0)
    polygon(4, 600)
    c.end_fill()


def draw_clock():
    outer()
    c.penup()
    c.goto(0, 300)
    c.pendown()
    c.begin_fill()
    c.fillcolor(1, 1, 1)
    circle(100)
    c.end_fill()
    c.penup()
    c.goto(0, 0)
    c.setheading(90)
    for x in range(13):
        c.fd(299)
        c.pendown()
        # c.bk(10) # to revert back to lines you need to go back 5 again to write the number
        c.rt(90)  # for triangle
        c.bk(5)  # for triangle
        c.begin_fill()
        c.fillcolor(0, 0, 0)
        polygon(3, 10)
        c.end_fill()
        c.penup()
        c.fd(5)  # for triangle
        c.lt(90)  # for triangle
        c.bk(20)  # for triangle
        if x == 0:
            h = 12
        else:
            h = x
        c.write(str(h), align='center', font=('Arial', 12, 'normal'))
        c.fd(20)
        c.goto(0, 0)
        c.rt(360 / 12)
    c.hideturtle()


def reset_turtle():
    t.pensize(2)
    t.penup()
    t.goto(0, 0)
    t.setheading(90)
    t.pendown()


def clockface(h, m, s):
    t.speed(0)
    reset_turtle()
    h = h + (m / 60)
    t.rt(h * 30)
    t.fd(190)
    reset_turtle()
    t.rt(m * 6)
    t.fd(260)
    reset_turtle()
    t.rt(s * 6)
    t.pensize(1)
    t.fd(300)


def clock():
    draw_clock()
    tm = time.localtime()
    while True:
        t.clear()
        tm = time.localtime()
        # turtle.tracer(1,100)
        clockface(tm.tm_hour, tm.tm_min, tm.tm_sec)
        turtle.update()
        time.sleep(0.7)


clock()
