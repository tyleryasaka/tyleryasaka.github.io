---
layout: post
title:  Makerspace Workshop
date:   2019-07-30
---

Today, I just finished running a little workshop to introduce some middle school kids to code during their summer break. The idea was to give them a project that would be minimally challenging and maximally rewarding. I wanted to, you know, make coding fun. Or at least not scary.

### Prep

To make the project rewarding, I knew it would need to be something hands-on. I remember how I felt when I first learned how to print "hello world" to a console... unimpressed. I settled on a cool idea I found on the [Adafruit](https://www.adafruit.com/) website. You can actually create wearable electronics by sewing little computers onto your clothing and connecting various components, such as LEDs, via conductive thread. Hell yeah.

So I ordered the supplies and began practicing myself. This was easier said than done. The coding, as it turns out, was a piece of cake. Just using alligator clips to connect my LED and my micro computer, my project was up and running in minutes. The problems arose when I tried to create a more permanent connection with the conductive thread. I by no means am an experienced seamster, but I have wielded a needle and thread before. Even my third attempt resulted in less than stellar results. If my jacket folded in the wrong way, the light cut out. I decided this would have to be good enough.

![Alligator clips](/assets/img/alligators.jpg){: .small}

My next task was to tone down the scariness factor of coding. I didn't want the kids to be freaked out by the (parentheses), semicolons; camelCaseNotation, and [square brackets]. Adafruit apparently does have a graphical programming interface, but sadly my Flora model was not supported. So I decided to make my own. I spent the better part of a weekend hacking together a very rudimentary web interface that would allow the kids to create basic instructions using buttons and dropdown menus. The web page would automatically convert their instructions into [arduino](https://www.arduino.cc/) code, and at the press of a button they could have the code sent to my inbox so that I could upload it to their micro computers.

![Code interface](/assets/img/flora-interface.png)

The interface can be seen [here](http://floracode.tyleryasaka.me/).

### Session 1: Alligator clips

We spent the first session hooking up the LED to the micro computer with alligator clips and testing out the code using the interface I built. I intentionally made a certain aspect of the interface unintuitive to give the kids just a little taste of having to "be the computer". I gave them instructions for setting light colors. However, I did not put in any built in delays. There was a separate pause instruction for this. Of course, looking at the interface, you might naturally want to set the light red, then yellow, then blue (or whatever your favorite colors are). When we uploaded this code, the light would just flash a continuous white color. I used the opportunity to explain that the computer is really fast and was actually following the instructions, but it was too quick to for humans to see. To actually *see* the colors, the kids needed to also insert pause instructions.

### Session 2: Conductive tape

By this point I realized my conductive thread idea was not going to realistically work. It was just too difficult of a project to undertake in a 2-hour session for kids who were experienced in neither electronics nor embroidery. I found [conductive tape](https://www.amazon.com/gp/product/B01ALDR0D0/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1) on Amazon.com and some translucent boxes at Target. Instead of electronic suits, we would make crude nightlights. We spent most of this session trying to connect the LED and micro computer with the thin conductive tape. We had some success, but it never lasted more than 10 minutes. The tape was just too finicky with our sloppy craftsmanship. At the end of this session, I promised the kids that if they returned next week I would have a fading effect available for them to use, rather than abrupt blinking.

### Session 3: Back to Alligator Clips

An hour before the last session was to start, I still had not addressed the problem of fading the lights. I sat down at a coffee shop and managed to hack together a rather primitive solution that got the job done. I showed up to the workshop with my updated code generator and more alligator clips which I had ordered since the last session. Since we were using boxes, there really wasn't a problem with just using alligator clips as a permanent connection. In fact, they were very well suited for this project. They allowed the electronics to function a bit like legos. You could take things apart and re-assemble them at will, without too much of a hassle. All of the kids updated their code to use my new fader, and were able to successfully create their boxes. One kid decided to place two lights in his box and have them cycle through different colors. Nice.

![Fading light box](/assets/img/lightbox.gif)
