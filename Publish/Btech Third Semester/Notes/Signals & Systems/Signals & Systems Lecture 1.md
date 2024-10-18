---
Title: Signals & Systems
Status: 
marker:
  - "[[btech]]"
tags:
  - BTech
Date: 2024.07.30
Time: 12:16
---
# Signals & Systems

# Main note

## Nyquist Theorem
Refer old lectures [[]]

## Formula derived from Nyquist Theorem.
Maximum Data or noiseless = $2B Log_2 V~bits/sec$
What is the max data on noiseless channel frequency bandiwdth = 2F Log_2 V where f is frequency

The formula \( C = 2B \log_2 V \) represents the maximum data rate (channel capacity) of a noiseless channel, where:

- \( C \) is the channel capacity in bits per second (bps).
- \( B \) is the bandwidth in hertz (Hz).
- \( V \) is the number of discrete signal levels.

### Key Points:

1. **Bandwidth (\( B \))**: Determines the range of frequencies the channel can transmit.
2. **Signal Levels (\( V \))**: Number of discrete levels used for encoding data.
3. **Logarithmic Relationship**: \( \log_2 V \) indicates the bits represented by each symbol.
4. **Nyquist Rate**: \( 2B \) is the maximum number of symbols per second in a noiseless channel.

### Formula Explanation:

- The Nyquist rate is \( 2B \), representing the maximum symbol rate.
- Each symbol can represent \( \log_2 V \) bits.
- The product of the symbol rate and bits per symbol gives the maximum data rate.

### Example:

For a bandwidth of 3 kHz and 8 signal levels (\( V = 8 \)):
- Bits per symbol: \( \log_2 8 = 3 \).
- Nyquist rate: \( 2 \times 3000 = 6000 \) symbols/sec.
- Maximum data rate: \( C = 6000 \times 3 = 18000 \) bps (18 kbps).

This formula shows the dependence of channel capacity on both bandwidth and signal levels.

The Shannon theorem, also known as the Shannon-Hartley theorem, defines the maximum data rate (channel capacity) that can be achieved over a communication channel with a given bandwidth in the presence of noise. It provides a theoretical upper bound on the information rate that can be transmitted with a negligible probability of error.

The formula is:
\[ C = B \log_2 (1 + \frac{S}{N}) \]

where:
- \( C \) is the channel capacity in bits per second (bps).
- \( B \) is the bandwidth of the channel in hertz (Hz).
- \( S \) is the average signal power.
- \( N \) is the average noise power.
- \( \frac{S}{N} \) is the signal-to-noise ratio (SNR), often denoted as \( SNR \).

## Shannon Theorem
### Explanation of Shannon Theorem

1. **Bandwidth (\( B \))**: This is the range of frequencies that the channel can transmit. The wider the bandwidth, the higher the potential data rate.

2. **Signal-to-Noise Ratio (\( S/N \))**: This is a measure of signal strength relative to background noise. A higher SNR indicates a clearer signal with less noise interference, which allows for higher data rates.

3. **Logarithmic Relationship**: The \( \log_2 (1 + \frac{S}{N}) \) term quantifies the increase in capacity with respect to the SNR. The logarithm base 2 indicates that capacity grows with the ability to distinguish between more discrete levels, directly tied to SNR.

### Formula Explanation

- **Signal-to-Noise Ratio (SNR)**: As SNR increases, the channel can support more bits per second because the signal can be more clearly distinguished from the noise.
  
- **Bandwidth**: The data rate is directly proportional to the bandwidth. Doubling the bandwidth doubles the capacity, assuming SNR remains constant.

- **Logarithmic Effect**: The logarithmic function reflects the diminishing returns of increasing SNR. While increasing SNR improves capacity, the rate of improvement decreases as SNR becomes very high.

### Example Calculation

Suppose a communication channel has a bandwidth of 3 kHz (3000 Hz) and a signal-to-noise ratio of 30 dB. First, convert the SNR from decibels to a ratio:
$$ 30 \text{ dB} = 10 \log_{10} \left( \frac{S}{N} \right) $$
$$ \frac{S}{N} = 10^{30/10} = 10^3 = 1000 $$
Then apply the Shannon theorem formula: 
$$ C = 3000 \log_2 (1 + 1000) $$
 $$ C = 3000 \log_2 (1001) $$  

Using \( \log_2 (1001) \approx 9.97 \):
$$ C \approx 3000 \times 9.97 \approx 29910 \text{ bps}$$

So, the maximum data rate for this channel is approximately 29.91 kbps.

### Key Insights

- The Shannon theorem sets a fundamental limit on the data rate given bandwidth and noise constraints.
- Increasing bandwidth or improving SNR increases the maximum data rate.
- The logarithmic relationship shows diminishing returns at high SNR values, emphasizing the balance needed between power and bandwidth for efficient communication.

## What are types of Links?

There are 6 major Links
1) Ethernet 802.3
2) Token Ring 802.5
3) 802.11 Wireless
4) Point to Point Protocol
5) Frame Relay
6) AIMC Asynchronous Transfer Mode

## What are functions of Data Link Layer
1) Link access : Media Access Controls protocols Decides Ruels for frame transmission.
![[Link.excalidraw]]
2) Framing Link: This Laye protocol Creates Datalink FRAMI. Data live frame has three parts like header, payload, Traitor
3) Reliability: Datalink Layer should provide Reliable Communication 
	1) ![[Reliability links.excalidraw]]
4) i
# Problems
### Statement 1
If channel is working on 6 khz and noise is 20 decibel
# References


###### Information
- date: 2024.07.30
- time: 12:16