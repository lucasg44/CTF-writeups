# Unraveling the past

### Overview
Unraveling the past was an 300 point OSINT challenge at Hack-a-bull 2023. This challenge was solved on March 25th at 7:36 PM. This challenge was created by Lily and Austin.

### Resources
https://archive.org/web/

Thw wayback machine was extremely helpful in getting to the past videos in this challenge

### The problem
It seems like Whitney Hatteras is revamping their online persona. Instead of prioritizing CTF competitions, they have been uploading animal videos and tweeting about their channel. Anyways, the animal videos are not all that ordinary.. there is something cryptic about them. But the odd ones of the bunch may have been deleted by now. Relying purely on GUI will only lead to frustration...

### The solution
This solution is split into 6 seperate parts

#### Part 1: Finding the social media pages
To find the social media pages, I googled the name Whitney Hatteras for the cat videos and twitter channel, which led to these two links

[Twitter channel](https://twitter.com/WhitHatteras) [Youtube channel](https://www.youtube.com/@secretarycomrade)

#### Part 2: Decoding the about page
By traveling to the about page, we see a series of messages in seperate languages. After translating all the information to english, we are left with the following:
``````text
There are web resources that in a sense make time travel possible.

Use it to visit me again

and I will tell you a secret

right here, however, in the past
``````

### Part 3: Wayback machine on the about page
I used the resource provided above to go to the specific directory at "https://www.youtube.com/@secretarycomrade/about" on March 24th, 2023 and got this code provided below
``````text
#############################################################
I'll let you in on a secret... I deleted the video... not this me -- but the other me           #
I remember the majority of the video id, but I forgot the last digit       (|||❛︵❛.)            #
/watch?v=pN9XeSpjkT_                                                                                                      #
                                         ^ figure out the missing number and substitute the..          #
                                         ^ ..underscore with the correct number...                             #
                                         ^ ..try to access the video or find a copy of the video...   #
...believe me, it's out there. Nothing ever gets deleted from the Internet.            #
########################################################
``````



