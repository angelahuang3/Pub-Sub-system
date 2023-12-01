# Pub-Sub-system
This is a pub-sub E-commerce system that aims to provide an event-driven service
## Project Idea
Our goal for this project is to design a system for e-commerce companies to manage their order, packaging, shipping, and notification service separately in different containers as an event-driven distributed system. First, we will use **Golang**, an efficient and accessible language for a distributed system, to build the basic pub-sub system. The second is to design topics in the broker for subsystems to send/receive events correctly. For deployment, we use Docker containers to maintain five subsystems (order + package + shipping + notification + broker). Also, we will use Docker Compose to define and run multi-containers.
