> INITIALISING VARIABLES
%1
h=0;		%height [m]
sl=0;		%step length [m]

%2
avel;		%average velocity [mph]
T;		%total operation time [s]
dt;		%sampling time [s]
mvel;		%momentary velocity [mph]
aveltrue;	%average velocity during exercise (break time reducted)[m/s]

%3
dx;		%distance covered in dt [ft]
totaldis;	%total dinstance covered [ft]

%4
alt		%altitude
elra;		%elevation change rate [m/s] 	

%5
bp;		%number of breaks
bt;		%individual break time 
tbt;		%total break time
bl;		%break location

%6
UV-related variables


%7
weight;		%athlete's weigth [kg]
calb; 		%calories burnt [kcal]
calbrate;	%calories burn rate [kcal/s]
mets;		%metabolic cost, constant


%save
N;		%number of saves
Perfi		%performance array, to be saved into a txt file


The various numbers mentioned above correspond to the number of features, hence every one of them will be analysed seperately.
FEATURE 1:
calculation of number of steps the athlete takes, given the height to average step length ratio


FEATURE 2:
Computation of the momentary and average athlete's velocity 

FEATURE 3:
Computation of the total distance covered by the athlete

FEATURE 4:
Computation of the total altitudinal change during the athlete's exercise session (Useful stat for mountain hikers)

FEATURE 5:
Computation of the combined and individual break times, as well as the locations in which they took place


FEATURE 6:
Computation of the UV index at the location of the athlete. It is based on UV irradiance measurements taken by a station in Athens. It can calculate the exposure time that is required to reach procarious UV doses-thresholds, judging from the final set of measurements aquired by the measuring station, and the skin type inputed by the athlete. While this prototype uses a set data array to achieve that, future versions could access the "https://www.temis.nl/uvradiation/UVarchive/stations_uv.php" site, in order to receive up-to-date UV measurements. 
The location service could be used to cross-check the concentration of airborne pollutants and notify the athlete if the aforementioned values surpass the nominal values.

FEATURE 7:
The sum of calories burnt during exercise is calculated. The 'mets' value have been collected, for a range of walking/running speed of 1.7 to 14 mph. Then, a Taylor polynomial function of 
the collected data set was deducted to compute the mets value for any given momentary speed in that range. Future software versions could incoporate mets values for swimming and biking, hence calories.

FEATURE SAVE:
Saves certain performance-related parameters to a ".dat" file, that can be accessed at a later date for comparison. 





> Sources for the data used:
-Steps vs Height
https://www.scientificamerican.com/article/bring-science-home-estimating-height-walk/

-Mets per running speed
https://www.stylecraze.com/tools/running-pace-calculator/
https://media.hypersites.com/clients/1235/filemanager/MHC/METs.pdf
https://www.omicsonline.org/articles-images/2157-7595-6-220-t003.html

-calories per min formula
https://blog.nasm.org/metabolic-equivalents-for-weight-loss

-UV related info
https://en.wikipedia.org/wiki/Action_spectrum
https://www.temis.nl/uvradiation/UVarchive/stations_uv.php
https://www.temis.nl/uvradiation/UVdose.php

-earth's circumferance
https://imagine.gsfc.nasa.gov/features/cosmic/earth_info.html