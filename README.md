# TC1001S_Evidence1
Evidence1_team1

## Authors
- Andrea Ochoa
- Sue Mi Zamarrón

## Snake
Snake, classic arcade game.

Exercises
1. How do you make the snake faster or slower?
2. How can you make the snake go around the edges?
3. How would you move the food?
4. Change the snake to respond to arrow keys.


Changes made in code: 

1. aim = vector(0, -40) #Sue Mi: changed argument of vector from -10 to -40 to make the snake faster
2. if not inside(head):#Sue Mi: This code makes the snake go around without crashing the edges
    head = snake[-1] * -1
	  head.move(aim)
    update()
3. if head == food:
        print('Snake:', len(snake))
        food.x = randrange(-19, 18) * 10 #Sue Mi: change range of coordinates to change food
        food.y = randrange(-19, 18) * 10
4. Snake already responds to arrows keys so we changed food color: 
square(food.x, food.y, 9, 'blue')#Sue Mi:change color


## Cannon 
Cannon game: hitting targets with projectiles.
Exercises
1. Keep score by counting target hits.
2. Vary the effect of gravity.
3. Apply gravity to the targets.
4. Change the speed of the ball.

1. #andrea: display how many targets were hit
   turtle.write(f"You hit: {targethits} targets", move=False, align="left", font=("Arial", 8, "normal"
   print(f"You hit: {targethits} targets!")
2. if inside(ball):
    speed.y -= 0.55 #andrea:varied effect of gravity 
    ball.move(speed)
3. for target in targets:
    target.x -= 0.5
    target.y -= 0.25 #andrea: added target y component ro apply gravity to the targets
4. def tap(x, y):
    "Respond to screen tap."
    if not inside(ball):
        ball.x = -199
        ball.y = -199
        speed.x = (x + 200) / 18
        speed.y = (y + 200) / 18 #andrea: change speed of ball by dividing both components by 18 instead of 25

## Pacman 
Pacman: classic arcade game 
Exercises
1. Change the board.
2. Change the number of ghosts.
3. Change where pacman starts.
4. Make the ghosts faster/slower.
5. Personal changes

1. tiles =[ #andrea: openned up a new path by changing the values of the array
    0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
    0, 1, 1, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0,
    0, 1, 0, 0, 1, 0, 0, 1, 0, 1, 0, 0, 1, 0, 0, 1, 0, 1, 0, 0,
    0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 1, 0, 0,
    0, 1, 0, 0, 1, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0, 1, 0, 0,
    0, 1, 1, 1, 1, 0, 1, 1, 0, 1, 1, 0, 1, 1, 1, 1, 0, 1, 0, 0,
    0, 1, 0, 0, 1, 0, 0, 1, 0, 1, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0,
    0, 1, 0, 0, 1, 0, 1, 1, 1, 1, 1, 0, 1, 0, 0, 0, 0, 1, 0, 0,
    0, 1, 1, 1, 1, 1, 1, 0, 0, 0, 1, 1, 1, 1, 1, 1, 0, 1, 0, 0,
    0, 0, 0, 0, 1, 0, 1, 1, 1, 1, 1, 0, 1, 0, 0, 1, 0, 1, 0, 0,
    0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0, 1, 0, 0,
    0, 1, 1, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0,
    0, 1, 0, 0, 1, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0,
    0, 1, 1, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 1, 1, 0, 1, 0, 0,
    0, 0, 1, 0, 1, 0, 1, 0, 0, 0, 1, 0, 1, 0, 1, 0, 0, 1, 0, 0,
    0, 1, 1, 1, 1, 0, 1, 1, 0, 1, 1, 0, 1, 1, 1, 1, 0, 1, 0, 0,
    0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0,
    0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0,
    0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
] #andrea: changed values in tiles array and added one column to change board.

2.     [vector(-120, 160), vector(5, 5)], #andrea: added another ghost to change number of ghosts
3.     pacman = vector(40, 80)#andrea: changed values from negative to positive to change pacma's position
4.     [vector(100, 160), vector(0, -10],#Sue Mi:Here I change the value of the first and thrid vector to 10 so that the direction is bigger
       [vector(100, -160), vector(-5, 0)],#and the ghost reach more space on the board, making it slower
5. path.dot(2, 'pink') #andrea: changed dot color from white to pink
   dot(20, 'green')#Sue Mi: change color
   def world(): #andrea: changed board's colors
    "Draw world using path."
    bgcolor('purple') #andrea: changed bg color from black to purple
    path.color('orange') #andrea: changed path color from blue to orange




