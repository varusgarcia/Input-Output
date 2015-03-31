#Eingabe Ausgabe
#####Alvaro Garcia ID Fh-Potsdam WS 2014/15

In the course Eingabe-Ausgabe (Input-Output) we made a series of assigments over the semester to come closer to the pragramming lenguage. As a final assigmant we had to make a compilation of them all. This is it.

The coures was divided in three parts:

* [**1.Analog VS. Digital**](#analogvsdigital)
* [**2.Web**](#web)
* [**3.Arduino**](#arduino)

##<a name ="analogvsdigital"></a>1. Analog VS. Digital

The first part was ment to be an introduction to the digital power. For that we made an exercise that was repeated over three weeks. We had to think about a simple task involving drawing on a paper. It had to consist in simple steps that everyone could follow. This commands had to be given out, in the best cases in person, to friends and family. The results had to be collected and compared. We repeated the process each week, presented the results, and based on them, refined our steps.

My first task consisted of:

```
On a Paper: 
   
   1. draw two vertical lines parallel to eachother
   2. between the two, draw three circles
   3. in the middle circle, draw an rectangle
```
  
  The results I became back were diverse, some had done the task in a few seconds and others took more than a minute to complete it:
  
![1](http://i.imgur.com/QKQHPBJ.png?1)

For the next week I decided to complicate things more, adding complexer steps:

```
On a Paper: 
   
   1. draw a big circle, help yourself with a compass
   2. inside the circle, draw more geometrical forms. They have to cross 
      eachother. Not too many, you should still be able to recognise each one. 
   3. With this crossover, other forms have been created. Now you have to
      fillout the ones that haven't been crated by any  (the big
      circle)or by 2,4,6... overlappings.
```

Here the results. They were made more or less in the same time:

![2](http://i.imgur.com/vxsHUAt.jpg?1)


Except one, everybody understood what needed to be done.

For the next week, we had to try to convert the analog commands into digital code. For that, we used Processing, a Java based programming plattform, which allows the user to instantly see the result of what he has written. 

I structured my code the same way I did with the analog steps, instead of three, here I did it in two parts, merging step 1 and 2 of the analog indications.
So, basically, in the `setup()`, the program draws the different geometrical forms and in the `draw()` he fills them out in balck or white depending if they have been created by 0,2,4,6... overlappings or not.

in the `setup()`, the program generates a black background and on top  all the geometrical forms in random position  and rotation filled out in white with a 19% transparency:

![3](http://i.imgur.com/j6DAQ6x.png?1)

in the `draw()` the program uses this image to generate the result. How? As you can observe, each time a form overlaps, the color changes to a lighter tone. The exact color codes are:

| No. of overlappings | Color code  | filled out in |
|:------------- |:---------------:| :---------------: |
|none(black)| -16777216 | white |
| 1     |  -13487566 | black
| 2 | -10855846 | white |
| 3  | -8750470  | black
|4 |-7039852| white |
| 5| -5658199 | black
| 6| -4539718 | white |
| 7 | -3618616 | black

Now, the program does look at each individual pixel of the image generated and tell witch color it is, then, he fills out he pixel in black or withe color based on  the color. From the image above, he can generate this:

![4](http://i.imgur.com/3vStZqw.png?1)

Here a comparison between both:

![5](http://i.imgur.com/SlTovX3.png?1)
 
 
  [Here][link1] you can find the code.

 The first program I wrote was inneficient (on the rendering time), so I made some other versions, all based on this  principal. 
 
 In the forth week we had to find a practical implementation of this code in the analog world. I began thinking about a way to make my drawing more interesting, and came across the idea of making an animation of it, the different geometrical forms moving and rotating in the circle. 
 
This made it more interesting but was still digital. I thought, as I have some experience in Timelapse photography, to merge this animation with the photographic technique. I finished finding a theorical way of mixing both together. The idea is simple, to draw each frame using a selfmade printer, take a photo of each frame and put it togeter into a video. The selfmade printer would be placed somewhere in a City, or in a landscape, so that you would see movment in the final video (people, cars, clouds passing by...).
 
 
 This is how the selfmade printer would look like:
 
 ![6](http://i.imgur.com/yvS02aE.png)
 
It would consist of four motorized sliders, one short and three longer ones. that would be positioned on top of a whiteboard. 

The pen would be able to move in a three dimensional space. Two dimensions for positioning it on the right point, and the third to mark with it on the whiteboard.
  
 ![7](http://i.imgur.com/wPF2uru.png)
 
 Everything would be driven by an Arduino, which would control the four motors and trigger the camera. When the drawing is printed, The Camera is triggered and takes a photo. Then, the printer erases the drawing with an eraser placed under the pen's mechanism.
 
 ![8](http://i.imgur.com/vt8KJE7.png?1)
 
 
 

##<a name ="web"></a>2. Web

In this part we were intoduced to the power of code in the web and data visualisation. For that, we had to collect data ourselves and find a way of  visualising it on a website. 

We were also intoduced to [P5.js](http://p5js.org), that works similar to Processing, but allows to visualise the result in a website.

For the data visualisation topic I picked a guess game. It consisted of five white images with black poits on them (generated in Processing). This was the first one:

![9](http://i.imgur.com/Tty1ZvR.jpg?1)

The participants would have to guess the number of points on them and intoduce them in the form. Also, they had to give me basic information about them, like The continent they were living in, thier age, gender and if they would consider themselves a more artistic or scientific person.

[Here][link2] you can see the form.

As I didn't have that much experience programming, I chose to make it with P5.js. The idea for the web was that the user could choose between each possible option. So, for example, he could choose North America and would see, first, the average guess of all north americans, and then, the average for each guess:

![10](http://i.imgur.com/MVvf4rK.png)

In this case, we can see that the total average is just under the perfect guess,but really noly the first one was near.

Like this, we can click on each option and it would show the result as here. If we click on the total or the individual guesses, we get to see each option compared:

![10](http://i.imgur.com/T6Ls94c.png)

In this case, the user has clicked on "Guess1", and now he can compare the first guess for each option given in the form.

[Here][link3] you can see it for yourself.

The coding part resulted to be a little bit of a hustle, as I intended the transitions between each selection to be animated.
I finished with lots of variables and almost 2000 lines of code. [Here][link4] you can check it out.



##<a name ="arduino"></a>3. Arduino

The arduino block was ment to be an introduction to the phisical computing. We started doing some simple projects that showed us the potential of this little processor.
We played around with all kind of sensors, resistors, switches, LED's...

For the end of this block, we had to build an interacting object. The output of this interaction had to be a flipdot[^flipdot]. First, we had to choose a binary process for the object to show. 

In my case, my first idea was to build a indicator of whether it is safe or not to leave the house. It would be placed next to the door from the inside.
and would directly comunicate with some household items, such as the oven, lights,... Someone who leaves the house, could actually be sure that everithing is turned off only by looking at the flipdot. 

My second idea was based on the game "chinese whispers" in which a spoken message has to pass through a group of people. While it's passing through, the message changes, because of misinterprtation.
In my project, I replaced the spoken messages by rythms, the player could introduce a rythm by touching a capacitive sensor with his finger and see it been played by the flipdot. In Chinese whispers, you would need a group of people for it to work, In my project, you would still need people, but not necesarily as a group, because between each player, it could hold up with the rythm as log as you want. I had the idea of storing each rythm in an Sd card, so that maybe tey could later be compared to eachother or visualized with Processing.

I decidet to realie the second idea, as it was more original and more fun to do.
Here is the circuit:

![10](http://i.imgur.com/aYH1kDb.png)

And some photos of the process:

![10](http://i.imgur.com/BJA2bXx.jpg)
![10](http://i.imgur.com/GkKHdmk.jpg)
![10](http://i.imgur.com/rn0b2Dt.jpg)

[Here][link5] you can see the final product in action and [here][link6] you can find the arduino code.

I hope this was a good overview of what the course covers.



[link1]: https://github.com/varusgarcia/Input-Output/blob/master/Algorythm/Algorythm.pde
[link2]: https://docs.google.com/forms/d/1PAwjxJQz2l65CJPxiWn2zA7Dtr0jKwkhc1Q2Oo37FoQ/edit
[link3]: https://varusgarcia.github.io
[link4]: https://github.com/varusgarcia/Input-Output/tree/master/Crowdsourcing
[link5]: https://vimeo.com/123615966
[link6]: https://github.com/varusgarcia/Input-Output/blob/master/Arduino/Arduino_code.ino

[^flipdot]: What is a FLipdot? Well, it is an object that allows you to flip a circular shape, that can rotate 180º. How? the shape is magnetized and underneath there are two electomagnets with contrary polarities. When you change the  polarities (we used a h-bridge for that) the "dot" flips.
