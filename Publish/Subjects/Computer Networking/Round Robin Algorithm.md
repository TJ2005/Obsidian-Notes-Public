---
Title: Computer Networks Round Robin
Status: 
marker:
  - "[[Algorithm]]"
  - "[[Round Robin]]"
  - "[[Computer Networks]]"
  - "[[Serialization of tasks]]"
  - "[[Task Management"
tags: 
Date: 2024.10.07
Time: 07:09
---
# **Round Robin Scheduling**
**Round Robin** is a **scheduling algorithm** used in various systems such as operating systems, networking, and computer science in general. Its main purpose is to ensure **fairness** by giving each process or task equal opportunity to execute.

In the context of networking and resource management, **Round Robin** is a technique where a central controller or system assigns **equal, fixed time slices** or **turns** to each task or device, ensuring that no single process or device monopolizes the resource.

#### Key Features:
- **Time Sharing**: Each device or process is assigned a **time slice** (also called a time quantum). After its turn is over, the next device or process gets its turn.
- **Fairness**: Every task or device gets an equal chance to use the resource (e.g., CPU, network bandwidth).
- **Cyclic Order**: Once every device or process gets a turn, the scheduling starts over from the first one, forming a **cycle**.

### How Round Robin Works:
- A list of devices, processes, or tasks is maintained.
- The system goes through the list one by one, allocating a fixed **time quantum** or allowing the devices to perform their tasks.
- If the task finishes before its time quantum, the system immediately moves on to the next task in the list.
- If the task is not completed in the time slice, it goes to the back of the queue and will be resumed in the next cycle.
  
### Example in Networking:
In **[[Computer Networks Controlled Access Protocol#2. **Polling Protocol**|Polling Protocol]]** (a type of **controlled access protocol**), **Round Robin** is often used to **poll** devices in a network. The controller polls each device in sequence, giving each one a chance to transmit data.

#### Steps in Round Robin Polling:
1. The **polling controller** (or central device) maintains a list of all devices connected to the network.
2. The controller **polls** each device one by one in a fixed, repeating order.
3. Each device is given a chance to transmit data for a certain amount of time or until it has no more data to send.
4. Once every device has been polled, the cycle repeats from the first device again.

#### Advantages of Round Robin:
- **Fairness**: Ensures that all devices or processes get an equal opportunity to use the resource.
- **Simplicity**: Easy to implement and understand.
- **Prevents Starvation**: No device or process is left out, unlike some other scheduling algorithms.

#### Disadvantages of Round Robin:
- **Performance Issues with Large Time Slices**: If the time quantum is too large, it can lead to long waiting times for other devices or tasks, reducing responsiveness.
- **Inefficiency with Short Time Slices**: If the time quantum is too short, frequent context switching can introduce overhead, reducing overall efficiency.

#### Use Cases:
- **CPU Scheduling**: In operating systems, Round Robin is used to schedule tasks on the CPU. Each process is given a fixed time to execute, and then the next process is executed.
- **Network Polling**: In networking, Round Robin is used to poll devices for data transmission. It ensures all devices get equal access to the network.
- **Load Balancing**: In web servers or distributed systems, Round Robin is used to distribute incoming requests evenly across servers or resources.

### Example of Round Robin in a Polling System:

Assume there are three devices on a network: **Device A**, **Device B**, and **Device C**. The polling controller uses Round Robin to give each device a chance to send data. Here’s how it works:
1. **Device A** is polled and allowed to transmit data.
2. Once **Device A** is done or its time slice ends, **Device B** is polled next.
3. After **Device B** finishes or its time slice ends, **Device C** is polled.
4. After **Device C**, the polling cycle restarts with **Device A**.

This continues in a cyclic manner, ensuring fairness in data transmission for all devices.

### Summary:
- **Round Robin** is a scheduling technique that provides equal time slices to tasks or devices in a cyclic order.
- It ensures fairness by preventing any single task or device from monopolizing the resource.
- It's widely used in networking (polling protocols), CPU scheduling, and load balancing systems due to its simplicity and fairness. However, its performance can vary depending on the size of the time quantum used.

Let me know if you'd like more details or examples!


# References


###### Information
- date: 2024.10.07
- time: 07:09