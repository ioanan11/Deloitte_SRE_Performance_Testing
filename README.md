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

## How to do performance testing?

First of all, we need to make sure everything is installed properly

- **Java** (version 8 and up) can be downloaded from here: https://www.oracle.com/java/technologies/downloads/#jdk17-windows
- **IntelliJ** can be downloaded from here: https://www.jetbrains.com/idea/download/#section=windows
- **Gatling** can be downloaded from here:  https://gatling.io/get-started/

Then open Intellij, and download **Scala** plugin (ctrl+alt+s and install plugin). 

Open **File** -> **New Project** and select the folder where you have downloaded Gatling (C:\Users\ioana11\gatling-charts-highcharts-bundle-3.6.1).

While in the **bin** folder run `./gatling.bat` and select the number corresponding to the test you want to run. 