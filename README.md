# Performance testing

Performance Testing is a software testing process used for testing the speed, response time, stability, reliability, scalability and resource usage of a software application under particular workload. The main purpose of performance testing is to identify and eliminate the performance bottlenecks in the software application.
It should be done to improve and based on user experience.

Types of performance testing:

- **Load testing**: is the application able to perform under anticipated user loads
- **Stress testing**: is the application able to perform under extreme workloads? How does it handle high traffic or data processing.
- **Endurance testing**: is the application able to handle the expected load over a long period of time
- **Spike testing**: software's reaction to sudden large spikes in the load
- **Volume testing**: is the application able to perform under varying database volumes
- **Scalability testing**: determines how effective is an application when scaling up to support an increase in user load

## Gatling

Gatling is an open-source load- and performance-testing framework based on Scala, Akka and Netty. The software is designed to be used as a load testing tool for analyzing and measuring the performance of a variety of services, with a focus on web applications.

### Scala

Scala is an object-oriented programming language used with Gatling performance testing.

### Intellij

ntelliJ IDEA is an integrated development environment (IDE) written in Java for developing computer software.

## How to run simulations in Gatling?

### Gatling File Structure

![alt text](https://github.com/ioanan11/Deloitte_SRE_Performance_Testing/blob/main/images/Screenshot%202021-09-21%20151609.png)


### A. Basic Simulation

![alt text](https://github.com/ioanan11/Deloitte_SRE_Performance_Testing/blob/main/images/Screenshot%202021-09-20%20170352.png)

First of all, we need to make sure everything is installed properly

- **Java** (version 8 and up) can be downloaded from here: https://www.oracle.com/java/technologies/downloads/#jdk17-windows
- **IntelliJ** can be downloaded from here: https://www.jetbrains.com/idea/download/#section=windows
- **Gatling** can be downloaded from here:  https://gatling.io/get-started/

Then open Intellij, and download **Scala** plugin (ctrl+alt+s and install plugin). 

Open **File** -> **New Project** and select the folder where you have downloaded Gatling (C:\Users\ioana11\gatling-charts-highcharts-bundle-3.6.1).

While in the **bin** folder run `./gatling.bat` and select the number corresponding to the test you want to run. 

![alt text](https://github.com/ioanan11/Deloitte_SRE_Performance_Testing/blob/main/images/Screenshot%202021-09-20%20170111.png)

The test is then run and will return a file path that can be copy pasted into the browser.

![alt text](https://github.com/ioanan11/Deloitte_SRE_Performance_Testing/blob/main/images/Screenshot%202021-09-21%20093236.png)

These results can be found in **results** directory. Copy paste the path found in **index.html** into the browser and we get the same thing.

### B. Custom Simulations with HAR files

#### Step 1: Inspect

- On the page you want to record the simulation, right-click `Inspect`
- On the **Network** tab ensure the **Preserve log** is checked
- Make sure you are recording (from the red button)

#### Step 2: Export HAR

- When you are done doing the stuff you needed to record, download the HAR file

#### Step 3: Run `recorder.bat`

A window will pop up. You need to write the following:

- select **HAR Converter** from the right side corner
- select the HAR file you have downloaded
- for **Class Name** enter a name (that's how the simulation will be named)
- select a simulations folder where the simulation will be saved
- press **Start**

![alt text](https://github.com/ioanan11/Deloitte_SRE_Performance_Testing/blob/main/images/Screenshot%202021-09-21%20145157.png)

The simulation will now be available when we run `gatling.bat`.

#### Extra: Let's increase the numbers of users!

We can change the number of users from the **Scala Simulation File**. This can be found in `user-files/simulations/`. Edit the last line in the script from 1 to 10, 100, 1000 etc.
`setUp(scn.inject(atOnceUsers(1))).protocols(httpProtocol)`

### C. Custom Simulations with Proxy
