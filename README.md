# HLF-VotingSystem

1.installation (date 20/Feb/2019)
installation of fabric is easy using vagrant and other way is to install all fabric tools then use cygwin to run the cmd
i have installed using vagrant and problem is face are
a.g++ and build-essential install error ==>> solved using link "https://gist.github.com/application2000/73fd6f4bf1be6600a2cf9f56315a2d91"
b.  error in "composer network start " due to incompatible version of composer and fabric version ==> solved by set env variable:
 FABRIC_VERSION=hlfv12
 c. encoding error due to platform difference(wrong on unix files using windows platform) in files ==>solved using cmd :
 sed -i -e 's/\r$//' youFileName.sh
