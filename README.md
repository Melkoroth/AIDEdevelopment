#  Ambient Intelligence Development Environment for People with Neurodegenerative Diseases
[![Build Status](https://travis-ci.com/Melkoroth/AIDEdevelopment.svg?branch=master)](https://travis-ci.com/Melkoroth/AIDEdevelopment)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)
[![OpenJDK Version](https://img.shields.io/badge/openjdk-v1.8-red.svg)](http://openjdk.java.net/)
[![Maven Version](https://img.shields.io/badge/maven-v3.1.1-orange.svg)](http://maven.apache.org/)
[![Ant Version](https://img.shields.io/badge/ant-v1.8.2-yellow.svg)](http://ant.apache.org/)

This site shows how to use the [AIDE](http://grasia.fdi.ucm.es/aide/) toolset for the development of AAL solutions for people with neurogenerative diseases (NDD).

It first briefly explains what is [AIDE](http://grasia.fdi.ucm.es/aide/), how to install it, and then a set of case studies that illustrate what can be done with it.

This has been developed in the context of the project [ColoSAAL](http://grasia.fdi.ucm.es/colosaal/) (TIN2014-57028-R), whose purpose is to facilitate the co-creation of AAL solutions for people with NDD. 

The [ColoSAAL](http://grasia.fdi.ucm.es/colosaal/) project proposes a process that involves different actors: end-users, relatives, care-givers, health experts, sociologists, software engineers, and other relevant stakeholders.

They will co-create AAL solutions in an iterative process, where the interaction artifacts are simulations of scenarios of the solutions in daily activities of the end-users (in this case, the people with NDD).

These simulations can be seen and analysed by the different actors, who can comment on them, and such information is taken to provide a refined solution.

In order to do this, several tools from the [**AIDE Framework**](http://grasia.fdi.ucm.es/aide/) are used, mainly [**SociAALML Editor**](http://grasia.fdi.ucm.es/sociaal/) and [**PHAT Simulator**](https://github.com/Grasia/phatsim).

![workflow](https://github.com/Melkoroth/AIDEdevelopment/raw/master/documentation/workflow.png)

## Introduction to the Framework:

[**AIDE**](http://grasia.fdi.ucm.es/aide/) stands for **A**mbient **I**ntelligence **D**evelopment **E**nvironment and is a set of tools to model, simulate and rapid prototype Ambient Intelligence systems. For more information please visit [this link.](http://grasia.fdi.ucm.es/aide/)

1. [**SociAALML Editor**](https://github.com/Grasia/sociaalml) is a graphical editor to model the elements for the simulation. The editor is based on [INGENME](https://github.com/Grasia/ingenme) framework.

2. [**PHAT Framework**](https://github.com/Grasia/phatsim) is a set of tools (coded using Java) to model and simulate activities of daily living.
The main components are:

    2.1 [**PHAT Generator**](https://github.com/Grasia/phatsim) is a tool that transforms the model defined with SociAALML into java code which can then be executed to see the simulations in action.

    2.2 [**PHAT Simulator**](https://github.com/Grasia/phatsim) is a simulator developed from scratch using jMonkeyEngine, which makes the entire framework [FOSS](https://en.wikipedia.org/wiki/Free_and_open-source_software).

## Getting Started:

### Installation:
#### Java 1.8 at least (set variable JAVA_HOME). 

Under GNU/Linux you can install it by typing these into the console:
```bash
sudo apt install openjdk-8-jre
sudo apt install openjdk-8-jdk-headless
```
You can check the java version with:
```bash
java -version
javac -version
```
To change between java versions:
```bash
sudo update-alternatives --config java
```

#### Maven 3.1.1+ at least (set variable M2_HOME).

```bash
sudo apt install maven
```
If you need to set M2 variables add the following lines to your .bashrc or .zshrc or whatever you use:
```bash
export M2_HOME="/usr/share/maven"
export M2="$M2_HOME/bin"
export PATH="$M2:$PATH"
```

#### Ant (set variable ANT_HOME)

```bash
sudo apt install ant
```

### Usage:
1. To **generate** the java code for the **editor and simulations**:
```bash
mvn clean compile
```
    
2. To **open SociAALML Editor** you go to a project's folder and type:
```bash
ant edit
```

3. To **run a simulation**
```bash
ant runSimName
```

*NOTE:* Bash completion for ant is useful when searching for simulations: <http://ingenias.sourceforge.net/blog/2012/12/04/a-useful-bashcompletion-extension-for-ant/>

### Case Study Usage Example:
Download full repository
```bash
git clone git@github.com:Melkoroth/AIDEdevelopment.git
cd AIDEdevelopment
```
Enter project directory, compile and run a simulation
```bash
cd e18interview
mvn clean compile 
ant runSimTalkToTV
```
If you get an error message complaining about encoding you should call maven with the following line:
```bash
mvn clean compile -Dfile.encoding=UTF8
```
This should launch a PHATSIM window with the simulation. It should be similar to this one:
![phatsim example](https://github.com/Grasia/AIDEdevelopment/raw/master/documentation/phatSim.gif)

If you are interested in the modelling part:
```bash
cd e18interview
mvn clean compile 
ant edit
```
This will laund the SociAALML editor, which is similar to this capture:
![sociaalml example](https://github.com/Grasia/AIDEdevelopment/raw/master/documentation/sociaalExample.png)

## Acknowledgements

This development is part of [ColoSAAL](http://grasia.fdi.ucm.es/colosaal/) project (TIN2014-57028-R) which is funded by Spain's [Ministerio de Economía y Competitividad](http://www.mineco.gob.es). Developed at [GRASIA](https://grasia.fdi.ucm.es/) research group in the [Universidad Complutense de Madrid](https://ucm.es/).

[![logo saal](http://grasia.fdi.ucm.es/colosaal/img/logo_colosaal.png)](http://grasia.fdi.ucm.es/colosaal/)
[![logo grasia](http://grasiagroup.fdi.ucm.es/aidendd/wp-content/uploads/GRASIA_logotipo2B.png)](https://grasia.fdi.ucm.es/)
[![logo ucm](http://grasiagroup.fdi.ucm.es/aidendd/wp-content/uploads/logo_ucm-e1537792345349.jpg)](https://ucm.es/)
