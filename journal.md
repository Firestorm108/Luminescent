# August 4th 2026

I started out deciding which laser diode to use.
My two options are NUBB23 and NUBM38. Both diodes are usually either test parts or taken out of old projectors. This means there is not that much documentation on them.
NUBB23 is a lower power 25W diode, much easier to drive and requires less cooling. NUBM38 is much harder to drive, 75W, and requires tons of cooling. I decided to go with the NUBM38 because I was interested in the challenge.
Usually, we drive these diodes with linear voltage regulators rigged to operate in constant current mode. However, this massive diode array is driven at 60V! This is much too high for these linear regulators.
It is possible to run them as two seperate strings at around 30V each, but that is still at the upper limit of these regulators and would most likely generate tons of heat.
I found that Styropyro used the HV9910C IC in his build and looked at the datasheet. Using that, I calculated the components and drew up a schematic of the main laser driver. 

<img width="3024" height="4032" alt="IMG_6718" src="https://github.com/user-attachments/assets/2cdfd693-a2ab-4e2a-8433-4ece21cc0737" />

I just finished designing the ESP32, USB, 3.3V reg, and the entire laser driver (which doesn't look like much but since no one on the internet has used this before I had to figure it myself with a datasheet and a calculator). As I was working on designing the BMS, where there will be 4, 4s LiPos in series to get 16S and around 60V, I realized there was a problem with this approach. Well, a few. These batteries are expensive, designing a BMS would make the board massive, etc. etc. etc.

.<img width="1537" height="1072" alt="Screenshot 2026-08-04 at 6 36 17 PM" src="https://github.com/user-attachments/assets/b9268a1c-05e9-40a9-b2cd-99cba59aeab8" />

This is the part where we pivot direction

I just got the CRAZIEST deal on ebay for laser arrays. It's a new model, and literally just solved all my problems. 
I just dropped $140 on this so im PRAYING i can get reimbursed because I'm broke asl now. But basically it has 4 channels instead of 2, and it can take like 22V instead of 60V. 
This means a few things, like I only need one battery. The BMS isn't gonna be insanely massive, I can use a different constant current circuit, less heating, everything! This is amazing.

Time Spent: 5 Hours
# August 5th 2026

Soo the laser arrays don't have lenses on them. Since they're straight from like the factory and not from the NUBARU modules and stuff. So I gotta make my own lens array which might be doable???
Anyways I finished up the schematic. Added tonsss of fun lil features. Like pseudo BMS stuff because I think the ESP32 can handle it lol.

<img width="1721" height="1168" alt="Screenshot 2026-08-06 at 10 12 23 AM" src="https://github.com/user-attachments/assets/9a042e0f-7fcc-439b-8fdd-a5dd7d72eb7f" />

Time Spent: 2 Hours

# August 6th 2026

Woke up bright and early for this. I actually asked gemini what time to wake up and it gave hella good advice.
But I started out by assigning footprints. I also was recording myself doing all of this since I intend to try to turn it into an insta reel.
 <img width="819" height="507" alt="Screenshot 2026-08-06 at 10 51 36 AM" src="https://github.com/user-attachments/assets/43398fd8-0b12-43c6-b79f-13a5a70b0244" />

The layout I decided to go with + mostly power routing
<img width="1189" height="972" alt="Screenshot 2026-08-06 at 12 17 46 PM" src="https://github.com/user-attachments/assets/2a0776e2-7534-47e4-9d4d-93885266ee6b" />

Routing absolutely everything

<img width="973" height="943" alt="Screenshot 2026-08-06 at 12 56 36 PM" src="https://github.com/user-attachments/assets/5e75e1dd-7461-453a-b0fe-63712a9ee426" />

<img width="833" height="775" alt="Screenshot 2026-08-06 at 1 08 01 PM" src="https://github.com/user-attachments/assets/a34d36b0-d689-4701-8a43-73a9cd7641d2" />

Overall it looks super good. I'm hoping it works especially since I want other people with similar arrays to be able to use it. It'd be cool to contribute to a niche open source community.

Time Spent: 10 Hours

# August 7th 2026

I thought it'd be super cool to make this into a portal gun. Since you would literally be able to see a massive beam of laser light coming out of it as if it was a real working portal gun.
So I modified a little housing for the PCB, toggle switches for safety and trigger, as well as a voltmeter.


<img width="1108" height="933" alt="Screenshot 2026-08-07 at 10 01 19 AM" src="https://github.com/user-attachments/assets/8a6fd039-1619-4198-afa3-f44a1b5f9d97" />

<img width="1240" height="817" alt="Screenshot 2026-08-07 at 10 01 26 AM" src="https://github.com/user-attachments/assets/efa91bb8-68c2-40cb-9833-74d5776b1e3d" />

After that I adapted the front part of the inner portal gun to fit in front of the circuit board. The decorative parts of the portal gun aren't in the model, this is just the core. I found this off just some random website, since I'm not that great at artistic modeling, and it wasn't worth redoing it from scratch since it'd perform worse.

<img width="1354" height="733" alt="Screenshot 2026-08-07 at 10 02 37 AM" src="https://github.com/user-attachments/assets/09fafad3-8ee8-4e09-87d4-7b3847eeedcd" />


There's one last part to do now. Since the arrays I bought don't come with lenses, I have to make my own lens array. The problem is that these arrays have most likely never gotten to the public before until now. They're surplus from a company called NUBARU, and they make extreme high power blue laser industrial machines. I believe I bought it off a dude who worked there. But since these are fresh out of the box from OSRAM, they don't have any lenses on them because they do that in the assembly line where they build their modules. I asked him what lenses they used, and he said a bunch of FACs and SACs. However, I don't know where to buy these. 

Ok, so after looking at the datasheet, I think I found some decent collimating lenses. I talked with some people who know a bit more than optics than me and they said that since each individual laser diode in the array has an output power of less than 4 watts, I don't need a super specialized lens made of some crazy type of glass or something since the power isn't too high relatively. So I did some research and found a good part on ebay that should work.

Time Spent: 5 Hours
