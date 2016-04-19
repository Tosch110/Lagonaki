# Waves

**Not working** Please do not run the Software yet.

This is one testnet waves implementation with Nxt consensus on top of Scorex framework.
There might be several development forks at once.

## Installation
# Ubuntu

Ubuntu Server
Install Oracle Java8 JDK:

echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list

echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list

apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886

apt-get update

apt-get install oracle-java8-installer

and agree with license terms

Install SBT(Scala Build Tool):

echo "deb http://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list 

apt-get update 

apt-get install sbt 


## Run a node

For testnet:
Please, put your own walletSeed string into waves-testnet.json

# Ubuntu

//Download deb package from [releases](https://github.com/ScorexProject/PermaScorex/releases), install it, run "perma-windows settings.json".

# Other system

Compile code and run your node by typing `sbt start` 

# Create package

For now it is only possible to create deb package with (sudo) `sbt debian:packageBin` command. 
In order to install waves with the package, pack it first and then run with

sudo sbt debian:packageBin

sudo dpkg -i target/waves_db_package.deb

waves_db_package.deb to be found in /target (look closely the current version)

waves waves-testnet.json


## Run a private local network
---

Run one or two peers on the local machine:


* run "sbt recompile" to (re-)build .jar file
* run "sbt startLocal1" to run first local peer binded to 127.0.0.1:9084 . Edit settings in settings-local1.json
   if needed. Access UI via localhost:9085
* run "sbt startLocal2" to run second local peer binded to 127.0.0.2:9088 . Edit settings in settings-local2.json
   if needed. Access UI via localhost:9086
* run "sbt startLocal3" to run second local peer binded to 127.0.0.3:9084 . Edit settings in settings-local2.json
   if needed. Access UI via localhost:9087
* You can run first & second peers simultaneously by running "sbt startLocal"

You can edit folders / other settings in settings.json file before running commands above.

