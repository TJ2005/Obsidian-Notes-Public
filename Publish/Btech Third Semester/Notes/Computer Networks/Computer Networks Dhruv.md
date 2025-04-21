---
Title: Computer Networks Dhruv
Status: 
marker: 
tags: 
Date: 2024.08.20
Time: 11:34
---
# Computer Networks Dhruv

# Main note

Stop-Wait protocol

It is a simple protocol
Reliabilty is 100%

Rules of stop-wait protocol

Sender Side : sends one packet at a time
			 Sends the next packet after receiving ack for the previous one

Receiver Side : Receives and accepts data packets
		      After receiving packets ack needs to be send


Stop-Wait-ARQ

ARQ: Automatic Repeat Request

Pros:

Working is simple
After receiving one frame, the sender waits for an ack before transmitting the next frame
If the ack does not arrive after a certain period of time, the sender timesout and retransmits the orignal frame.


Stop-n-wait ARQ = Stop-n-Wait + Timeout timer + Sequence number

![[Pasted image 20240820115636.png]]


Go-back NARQ

This protocol uses pipelining of packet mechanism, sender can send multiple frames before receiving the ack for the first time



# References


###### Information
- date: 2024.08.20
- time: 11:34