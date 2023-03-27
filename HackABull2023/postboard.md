# Postboard

### Overview
Postboard was an 100 point web exploit challenge at Hack-a-bull 2023. This challenge was solved on March 25th at 4:32 PM. This challenge was created by Austin.

### The problem
My friends and I made our own blog! However, one of our friends didn't do a great job handling the database... can you figure out what they did wrong?

hackabullwcsc-too-many-posts.chals.io

### The solution
Navigating to the website gives us some posts about the website, but one post in particular interested me:

https://hackabullwcsc-too-many-posts.chals.io/4

This post told us that they replaced the robots.txt directory to robotsnotcool. So now I go to the robotsnotcool directory.

https://hackabullwcsc-too-many-posts.chals.io/robotsnotcool

After navigating here, the web page informed us of an "__info" sub directory that uses similar database entries as the main page, so I added numbers at the end of the info directory, like "/__info/01"
The I navigated across those unsanitized sub-directories until I came across this web page with the flag:

https://hackabullwcsc-too-many-posts.chals.io/__info/07

### TL;DR
The web page had unsanitized database entries that we were able to exploit to get the flag

### Flag
WCSC_HackaBull23{N33dB3tt3rC0d3}
