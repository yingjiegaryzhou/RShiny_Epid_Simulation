---
title: "README"
author: "Amos Okutse, Yingjie(Gary) Zhou, Kyla Finlayson"
date: "12/15/2021"
output: html_document
    
---

# Modeling Infectious Disease Dynamics

## Objective
The goal of this app is to provide users with a tool to create interactive and visual simulations of infectious disease dynamics. Under the current COVID-19 landscape, we felt that providing a means to model trends in disease spread and recovery over time may be beneficial for researchers and the general public. Features include the ability to adjust parameters manually and download the resulting simulation tables. The models we provided are commonly used in epidemiological research. In particular, we adopted the SIR equations found in Cooper (2020) and borrowed our intervention functions from an R package created by Andreas Handel.


## General Description

In our shiny application, the user is able to simulate and visualize the infectious disease dynamics for a number of different models. Under the "Simulate Disease Dynamics" tab, the user has the option of creating one of three different models: the SEIR model, the SIR model, or the SI model. In the "Analyze Intervention Effect" tab, we have created a version of the SIR model which also accounts for the intervention effect of a vaccine. More information about each tab is found in the sections below.

## Getting Started

In order to open our application, you must have R or R Studio downloaded on your computer, and you must download and expand the zip file labeled "modeling-main". Then, you will need to open three files using R or R Studio: "idmodelling.R", "load_packages.R", and "simulation_functions.R". Next, you will need to click "Run App", and the application should show up on your screen. You can then explore our different models in the "Simulate Disease Dynamics" and "Analyze Intervention Effect" tabs, or you can learn more about the equations and parameters behind them in our "About" tab. 


## Simulate Disease Dynamics

In the "Simulate Disease Dynamics" tab, you can simulate and visualize each of the "SEIR", "SIR", and "SI" disease dynamic models with customizable inputs. You can also download your simulated data in a .csv file. Below are the parameters and equations explained for each model:



### The SEIR Model

The "SEIR" model simulates the change between states for populations that are experiencing an infectious disease. The four states, also known as compartments, are abbreviated as follows: "S" is for the susceptible population, "E" is for the exposed population, "I" is for the infected population, and "R" is for the recovered population. Over time, individuals in the population will move from susceptible to exposed, from exposed to infected, and from infected to recovered (we have chosen not to include deaths in our project). If time continues infinitely and there is no intervention that creates immunity (e.g., a vaccine), then eventually every individual within the population will move from the "susceptible" status all the way to the "recovered" status. The parameters for our model and the ordinary differential equations describing the rate of change for each state are outlined below:

#### User-Specified Parameters
<img src="https://github.com/yinggz/epid_simulation/raw/main/ReadMe_Images/Latex_Github_Epid1.png" alt="Definitions" width="50%" height="50%">
When you enter customizable parameters S(t), E(t), I(t), and R(t), you will be entering their values at time point t=0. 

#### Equations
<img src="https://github.com/yinggz/epid_simulation/raw/main/ReadMe_Images/Latex_Github_EpidEqn.png" alt="Definitions" width="40%" height="40%">

### The SIR Model
The "SIR" model simulates the change between states for populations that are experiencing an infectious disease. There are three states: "S" is for the susceptible population, "I" is for the infected population, and "R" is for the recovered population. Over time, individuals in the population will move from susceptible to infected, and from infected to recovered. As in the SEIR model, if time continues infinitely and there is no intervention that creates immunity (e.g., a vaccine), then eventually every individual within the population will move from the "susceptible" status all the way to the "recovered" status. The parameters for our model and the ordinary differential equations describing the rate of change for each state are outlined below:

#### User-Specified Parameters
<img src="https://github.com/yinggz/epid_simulation/blob/main/ReadMe_Images/Latex_Github_SIR_Param.png" alt="Definitions" width="50%" height="50%">
When you enter customizable parameters S(t), I(t), and R(t), you will be entering their values at time point t=0. 

#### Equations
<img src="https://github.com/yinggz/epid_simulation/blob/main/ReadMe_Images/Latex_Github_SIR_Eqn.png" alt="Definitions" width="50%" height="50%">

### The SI Model
The "SI" model simulates the change between the susceptible population ("S") compartment and the infected population ("I"). Over time, individuals in the population will move from susceptible to infected. Given infinite time and no intervention, every individual will eventually become infected. The parameters for our model and the ordinary differential equations describing the rate of change for each state are outlined below:

#### User-Specified Parameters
<img src="https://github.com/yinggz/epid_simulation/blob/main/ReadMe_Images/Latex_Github_SI_Param.png" alt="Definitions" width="50%" height="50%">
When you enter customizable parameters S(t) and I(t), you will be entering their values at time point t=0. 

#### Equations
<img src="https://github.com/yinggz/epid_simulation/blob/main/ReadMe_Images/Latex_Github_SI_Eqn.png" alt="Definitions" width="50%" height="50%">

## Analyze Intervention Effect
In the "Analyze Intervention Effect" tab, we have created an adaptation of the SIR model that also accounts for the intervention effect of a vaccine, and visualizes how the number of those susceptible, infected, or recovered will change over time as a result of a number of different parameters. The parameters for our intervention model and the ordinary differential equations describing the rate of change for each state are outlined below:

#### User-Specified Parameters
<img src="https://github.com/yinggz/epid_simulation/blob/main/ReadMe_Images/Latex_Github_Interven_Param.png" alt="Definitions" width="50%" height="50%">
When you enter customizable parameters S(t) and I(t), you will be entering their values at time point t=0. 

#### Equations
<img src="https://github.com/yinggz/epid_simulation/blob/main/ReadMe_Images/Latex_Github_Interven_Eqn.png" alt="Definitions" width="50%" height="50%">

## Citations
Cooper, I., Mondal, A., & Antonopoulos, C. G. (2020). A SIR model assumption for the spread of COVID-19 in different communities. Chaos, solitons, and fractals, 139, 110057. 
https://doi.org/10.1016/j.chaos.2020.110057
<br>
<br>
Keeling, Matt & Rohani, Pejman & Pourbohloul, Babak. (2008). Modeling Infectious Diseases in Humans and Animals. Clinical infectious diseases : an official publication of the Infectious Diseases Society of America. 47. 864-865. 10.1086/591197.
