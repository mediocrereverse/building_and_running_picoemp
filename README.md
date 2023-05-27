# building_and_running_picoemp
Fun with the PICOEMP - Mediocre Reverser
This Repo will be about how I built and ran the picoemp at home for under 60$. For a proof of concept and to ball on a budget I highly recommend this option for all electrical engineers before investing into BADFET or the CHIPSHOUTER/CHIPWHISPERER. This great alternative took me around 3 days total and was a hell of a lot of fun to build. My friends who build them alongside me would agree that it was a super cool project and the end product was well worth it to build. 
# PCB and Parts
The PICOEMP was designed by world renound engineer Colin O Flynn/NewAE. It was built as a cheap alternative for the chip shouter and for engineers looking to put an EMP/EMFI into a chip. BTW this is so fkn cool. Also Colin big shoutout to you and thank you for doing this <3. 
To order the PICOEMP PCP you have to pull down the gerber files from https://github.com/newaetech/chipshouter-picoemp/tree/main/hardware/gerbers/rev04_normal]. Download all of the gerber files then zip them all into a zip folder. For example on linux: 

git clone https://github.com/newaetech/chipshouter-picoemp.git    
zip -r chipshouter-picoemp/hardware/gerbers/rev04_normal.zip chipshouter-picoemp/hardware/gerbers/rev04_normal
cp chipshouter-picoemp/hardware/gerbers/rev04_normal.zip .

Now that you have the zipped files, you can upload them to a fabhouse. It should be noted that windows users just download the files in the git at that directory then zip them. The fab house will combine your digital art into reality. For reference as well, you can design these PCB's with software like eaglecad or kicad. I have built numerous projects with kicad. So now we can upload our project to a place like: 

https://cart.jlcpcb.com/quote

It should cost under 10$ if you adjust the shipping. And you have to make an account. 

Now we have to get the components. This is the critical parts that actually direct and run the emp. It is all controlled by a RP2040. Also known as a raspberry pico. More projects with this in the future. To order these parts we have to go to the excel spreadsheet in hardware/BOM for ChipShouter-PicoEMP.xls The xls file will have our info for what parts we need. Get as close to the part description that is humanly possible. I did and my devices worked perfectly. Go to mouser or digikey for parts. You can find them on google quite easy by searching mouser or digikey respectivly. And then searching for the part number from the bom file.

![IMG_1045](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/44afed04-2135-431a-b11c-42f96cbb9a4c)

After recieving, time to solder! 

![IMG1](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/aed5866d-ee8d-4f92-8b29-2692fd8fc52e)

![IMG_1047](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/5c15e16f-702b-4dbc-83f5-8c00251ac225)

I like to label my bags before I start. It speeds up the process. Highly recommend cross checking the BOM file with your parts!

![IMG_1050](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/8947ce33-6b58-454f-8d61-be97b978ec5a)

Some action of fault conception at work with me! 

![IMG_1050](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/c43e3206-2169-493d-b4e2-e1d1b0019b34)

![IMG_1048](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/f5a0d22e-c9c1-439e-a8b0-a5f4b09172a4)

![IMG_1046](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/bea3e67d-ab14-450b-bed0-75d46e311606)

Wow These are small!

Lastly you need the firmware to run the pico. We just said Fu^kit and threw the micropython script on it. To do that you need to download thonny with linux or windows. Apt has thonny and windows ... here is the link. https://thonny.org/. After download, connect your pico while holding the bootsel button for like 5 sec. Then release and get into thonny. Now in most cases you are going to have a brand new pico. So in the bottom right, click com port or python or whatever comes up. Click on pico. And install the py interperter. After that, open the cspico_simple.py from the git repository into thonny. click the save button or file save and click save to pico. name the file main.py. You should now be ready to roll. 

To diagnose, it should be 270kOhm over chg header to gnd. And when you press the arm button, the jumper port should jump to 240-250V respectively. If it is 0 or your resistance is over 270kOhm, you most certianly have an electrical issue. I found that the small parts sometimes dont solder the best and had to go back thru with a meter to find what the hell was going on. Luckly my first go around it was just one resistor that was not soldered on correctly. 

Have fun and hope you enjoy! 
-MediocreReverser

