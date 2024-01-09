# Pub-Sub System
This is a pub-sub E-commerce system that aims to provide an event-driven service

## Project Overview
Our goal for this project is to design a system for e-commerce companies to manage their order, packaging, shipping, and notification service separately in different containers as an event-driven distributed system. First, we will use **Golang**, an efficient and accessible language for a distributed system, to build the basic pub-sub system. The second is to design topics in the **broker** for subsystems to send/receive events correctly. For deployment, we use **Docker** containers to maintain five subsystems (order + package + shipping + notification + broker). Also, we will create and run a **docker-compose** file to define **multi-containers**.

## Key Design Choices
**Programming language**: Go 
-Reason: Best way to handle concurrency 
        Features in multithreaded programming
**Deployment**: Docker	
**Network protocol**: MQTT (by Mosquitto Server)
  1. There are some Quality of Service (**QoS**) options that can be used to guarantee delivery (**Reliability**)
  2. The publish/subscribe model scales well in a power-efficient way. (**Scalability**)
  3. There are several elements to the design that decouple the device and the subscribing server, which results in a more robust communication strategy 
     (**Decoupled design**)


## Algorithm
**Vector Timestamp**
 Assign the partial ordering  of publish and subscribe
 Identify concurrent events and ensure publisher/subscriber causality
**Mutual Exclusion** 
 Utilize go libraries mutual exclusion syntax  “sync.Mutex”
 Include two mechanisms: lock and unlock
**Concurrency Control**
 Apply to Go built-in primitive by Golang goroutine and channel
 Keep communication between several publishers/subscribers at the same time


![截圖 2024-01-08 下午5 35 01](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/b65b35e4-9fd7-45c5-9f7f-bcacc42f59d0)

## Architecture
![image](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/bc3c1819-0756-486c-83bb-ba3f483bff25)

**Order client**
![image](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/54397899-6357-4989-82ac-d06699a30ffa)

**Packaging client**
![image](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/c812cbea-de58-4a5d-ac55-8c5a563e451e)

**Shipping client**
![image](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/d7a4e928-0683-43c1-8e13-ca2a6118121b)

**Topic Tree Architecture**
![image](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/40767c7e-fde3-42d6-a6cd-4ac51cd2ab5e)
![image](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/2eb9b8fb-60f2-47cb-b3c7-026df7674dcb)
![image](https://github.com/angelahuang3/Pub-Sub-system/assets/123219721/729698bf-588a-4096-94cf-0fa756bfa4fc)







