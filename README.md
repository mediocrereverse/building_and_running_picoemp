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

![IMG_1050](https://github.com/mediocrereverse/building_and_running_picoemp/assets/133725400/c43e3206-2169-493d-b4e2-e1d1b0019b34)
