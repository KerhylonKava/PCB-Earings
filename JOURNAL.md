---
title: "PCB Earrings"
author: "Esther (@Star)"
description: "A pair of stylish PCB earrings I can wear to school!"
created_at: "2025-06-02"
---
# Project Overview

Last spring, one of the judges for a robotics competition had these really cool PCB earrings. I don't remember if they actually did something or if they were just for show, but I have wanted to make some ever since then. Now's my chance! I hope to make several versions for different use cases, and maybe some for my friends!

<details>
  <summary>Brainstorm</summary>
  <br>
  Earrings with...
  
  - green, yellow, and red LEDs, with ability switch which one is on to display my mood/social battery level
  - ~~tiny programable e-ink display with a *small* quote of the day or something else~~
  - ~~e-ink display with buttons that flash different screens~~ no b/c all e-ink displays are too large
  - morse code something?
  - USB thumb (ear) drive
  - UV sensor and bar display for the index range
  
Note for future me: make a hair clip that doubles as a mini game console! Or with the e-ink ideas above

  -------
</details>

# Contents
<details>
  <summary>Expand</summary>
  
  - [June 2nd](#-june-2nd-getting-started-with-research)
  - [June 4th](#-june-4th-schematic-design)

</details>


# June 2nd: Getting Started with Research!

Started out the morning (11 am really) by putting in some non-silver-or-gold plated earrings I made to see if I would react to them. If I don't, I will use the hooks I already have from the set for my earrings, but if I do react, I will have to get 925 sterling silver hooks.

<details>
<summary>Possible hooks</summary>
<br>
  
  [925 Sterling Silver Hooks: 120 pcs for $8.99](https://www.amazon.com/Sterling-Hypo-allergenic-Findings-Silicone-Stoppers/dp/B0829NMGQ5?source=ps-sl-shoppingads-lpcontext&ref_=fplfs&smid=A3BONGPFEG4RER&gQT=1&th=1)
  Probably the best option, and pretty cheap as well.

  [Stainless Steel Leverbacks: 50 pcs for $8.99](https://www.amazon.com/Stainless-leverback-Hypoallergenic-findings-Earrings/dp/B0D9XQXQY7/ref=sr_1_2_sspa?dib=eyJ2IjoiMSJ9.q-V-bW8sUKY4ZOsY64ggnMj5QjPc2V1JRmffpzr2vmFGTZCUDeVmVPF-VsDDO3B0N4BX_VDuU6dh_5ZMcKU7E4lWgv5Qde2mLxo7_sQFe8H7lA67Ggsw0gqW4Tp-JCl54wB8PbZjUPt3gBrOZ6owBacb1X7lB2KMJQ2iy9HAKrTp9isU-bKmRXUk62wVSWRc8KCu_lpxKnYhUA77LcLWG7uE-k3SnElzejy_RRHb2ry1vHJmWeWC442y-WCsE9i86o87QEixBv_gR8XsEkerxEyvSnQITBNdSuiYereexKM.HujwfjhyNfCZU_Kg5dsYzhsSb79r4kCvr0RwFLgu8Kg&dib_tag=se&keywords=sterling+silver+leverback+findings&qid=1748896022&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1#averageCustomerReviewsAnchor)
  Not 925 silver, but leverbacks are more secure than normal hooks. Also more expensive...

  --------------------
</details>

I was hoping to make the earrings turn the movement from your head shaking into energy to light up an LED, but it seems like there aren't exactly _small_ components that do that, and most usually use a spinning motion (ex: turbine) not a pendulum like motion.

I could also use small solar panels like [these](https://www.tindie.com/products/questwise-ventures/miniature-solar-panel-cell-breakout-board/)

I also looked online to see what else similar has been done... There seem to be lots of non-functional/fake circuit boards, but only a few that actually do something.

Inspo below 
![image](https://github.com/user-attachments/assets/9ba4f308-24f5-4e50-abc4-3e598afefcff)
These of course use coin batteries, but there are smaller ones if I do end up having to use batteries.

The best batteries seem to be SR626SW button batteries or other similarly small batteries. I need to use something smaller than a coin battery because I want the earrings to be skinny and long, which does not accomidate for 20mm coin batteries. Coin batteries are also just heavier than I would really like (my ears are pretty sensitive).

**Total time spent: 3h**

# June 4th: Schematic Design

Started by designing the edge cut for the earrings in Adobe Illustrator. That way I knew what shape the circuit would have to fit in.

I decided to make the earrings a diamond shape. After importing to KiCad I used the measure tool to figure out the rough scale of what I wanted it. The earring has a hole for a jump ring, so I also measured that. It was actually too small (around 1.2mm) to begin with, and the buffer between the hole and the edge of the board was about 0.6mm, which was also far too little. 

After some redisigning, the hole is now 2.1mm and the buffer is 1.2mm. The length is around 40mm and the width is around 24mm.

This is the final result: ![image](https://github.com/user-attachments/assets/eed4c447-8495-4e7f-8304-0f7cf24a93fd)

After that I found a footprint for a 6.8mm battery (the size of a SR626SW) and made sure it fit comfortably in the edge cut. Then I started and finished the schematic for the circut of the first version.

![image](https://github.com/user-attachments/assets/02362bab-b819-4e46-a846-91c99d5172e7)

It has an on/off switch and a three option switch with each output powering an LED. The three LEDs will be green, yellow, and red, which can correspond to how I'm feeling (or something else I guess). When it came to assign footprints, I got stuck on the footprint for the three option switch
<details>
  <summary>SW_DP3T Details</summary>
  
  Switch, three position, dual pole triple throw, 3 position switch, SP3T
  Keywords: switch dp3t ON-ON-ON
  
  ------
</details>

Of course, I did not find the correct footprint, but tomorrow is another day...

**Total time spent: 2h**

# Winter Break; Dec 2025 - Jan 2026: Found suitable switch

Tomorrow was indeed another day... But I did not work on it then, or again for many months :(

I wasn't able to find a "three option switch" (aka, as I know now, a single pole, triple throw switch). Instead, I'll replace it with two single pole, double throw switches. It took a lot of digging, and I had to look through parts catalogs and all that, but I think I found one that will work: the SW Nidec CAS-120A. Also there is an availible footprint to use, so yay! I can actually get to arranging stuff since I have the footprints!
Well before that, I actually updated the schematic to acommodate the two single pole, double throw switches (and got rid of the triple throw switch), but you know, onward!

Schematic:
<img width="785" height="543" alt="image" src="https://github.com/user-attachments/assets/7cdccc53-e991-4822-8efd-6777d9424ef8" />



**Total time spent: 4h**

# Winter Break; Dec 2025 - Jan 2026 cont: Edge Cuts (again) and board layout

It took an embarrassing amount of troubleshooting, but I eventually figured out that you can't have holes in the edge cut you import (see June 4th entry). Instead you have to make a hole once it's imported to KiCad... So yeah, did that, and no more edge cut errors!

After that, I arranged all the footprints on there. I still need to route it though.

PCB:

<img height="500" alt="image" src="https://github.com/user-attachments/assets/4fbaeb57-1c7d-4d01-a6ab-180fb07c779b" />

Front:

<img height="500" alt="image" src="https://github.com/user-attachments/assets/3601b6a0-54b0-45dc-9a2a-85dfcb76da34" />

Back:

<img height="500" alt="image" src="https://github.com/user-attachments/assets/78f65e85-049e-4d3a-83db-5e3179b784f0" />


With hope, I will not need to make any more large-scale changes, but I also wonder if I should make the PCB have 2 earrings stuck together on the same thing, since I can fit two in 10cm, so it won't cost more... We shall see. I may also want to add some silkscreen designs.

**Total time spent: 4h**

#Jan 24: Routing and Silkscreen

Finished routing! Footprint:

<img height="500" alt="image" src="https://github.com/user-attachments/assets/503108e2-6b51-4a3c-80a4-e7805b9d55e4" />

Used Adobe Illustrator to make the silkscreen and applied it to front and back of earring. I also added a little smiley face to fill space.

Front:

<img height="500" alt="image" src="https://github.com/user-attachments/assets/323821e2-0996-4a6f-a547-5de6bb8834f2" />

Back:

<img width="669" height="1041" alt="image" src="https://github.com/user-attachments/assets/367998f0-c5e2-4e44-aa5f-b17a91affcea" />

For the back, I also edited the silkscreen so it did not overlap with the footprints for the switches and battery holder.

**Total time spent: 1.5h**
