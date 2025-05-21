# Performance-Analysis-of-Resource-Allocation-in-5G-Systems
MATLAB, OFDMA, 5G, Resource Allocation, Wireless Communication, Signal Processing

performance analysis of resource allocation techniques in multi-user OFDMA systems for 5G networks. Compared the Water-Filling and Round Robin algorithms in terms of Bit Error Rate (BER), sum capacity, throughput, fairness, and power efficiency using MATLAB simulations. Demonstrated that the Water-Filling algorithm significantly improves throughput and system capacity, while Round Robin offers better fairness. The project highlights trade-offs in designing efficient and fair 5G communication systems.

Key Technologies: MATLAB, OFDMA, 5G, Resource Allocation, Wireless Communication, Signal Processing

OFDM System

3.1 INTRODUCTION

Orthogonal Frequency Division Multiplexing (OFDM) is a highly efficient and widely adopted digital modulation technique that forms the backbone of many modern communication systems. It is designed to transmit large amounts of data over a wideband channel by dividing the available bandwidth into multiple narrow subcarriers, which are orthogonal to each other in the frequency domain. This orthogonality ensures that the subcarriers can overlap without causing interference, leading to highly efficient use of the spectrum. The core principle of OFDM lies in converting a high-rate data stream into multiple parallel lower-rate streams, each modulated onto its own subcarrier. By spreading the data across many subcarriers, OFDM reduces the impact of frequency-selective fading and inter-symbol interference (ISI), which are common in wireless communication due to multipath propagation. To further combat ISI, a cyclic prefix (CP) is appended to each OFDM symbol, effectively absorbing channel distortions caused by delayed reflections. One of the standout features of OFDM is its ability to simplify equalization at the receiver. Unlike traditional single-carrier systems, where complex equalizers are needed to counteract channel distortions, OFDM enables straightforward equalization using Fast Fourier Transform (FFT) and Inverse FFT (IFFT) operations. This computational efficiency makes it well- suited for high-speed data transmission over complex channels. Additionally, OFDM supports flexible modulation schemes, such as Quadrature Amplitude Modulation (QAM) and Phase Shift Keying (PSK), allowing dynamic adaptation to varying channel conditions. The system can adjust the modulation and coding schemes to optimize data rates and maintain robust communication, even in environments with significant interference or noise. OFDM is also highly scalable, accommodating varying bandwidths and data rates by simply adjusting the number of subcarriers. This adaptability makes it an ideal choice for a wide range of applications, from broadband wireless systems like Wi-Fi (802.11a/g/n/ac/ax) to cellular networks such as LTE and 5G. It is also the foundation of digital broadcasting standards like DVB-T and DAB. By combining spectral efficiency, robustness against multipath fading, and computational simplicity, OFDM has become the gold standard for modern wireless communication. Its versatility and reliability have made it indispensable for meeting the growing demand for high-speed, high-capacity data transmission in today’s interconnected world.

Fig 3.1 OFDM signal

The fig 3.1 illustrates the concept of orthogonal subcarriers in an OFDM system, where each waveform represents a subcarrier. These subcarriers overlap in the frequency domain, yet do not interfere with one another due to their orthogonality. Orthogonality ensures that the integral of the product of any two subcarriers over a symbol period equals zero, allowing the receiver to distinguish between them without mutual interference. Each subcarrier exhibits a sinc-shaped spectrum, with its main lobe centered on a specific frequency and nulls aligning with the frequencies of adjacent subcarriers. This property enables efficient spectrum usage by eliminating the need for guard bands, achieving high spectral efficiency. The overlapping structure, combined with advanced modulation techniques like QPSK or QAM, allows data to be transmitted on each subcarrier independently, making the system robust against multipath fading and frequency-selective interference. This visualization highlights the fundamental efficiency and resilience of OFDM in modern communication systems.
 
Orthogonal Frequency Division Multiplexing (OFDM) is a key technology in the IEEE 802.11 standards, especially in high-speed Wi-Fi networks. It is used in several versions of Wi-Fi, including 802.11a, 802.11n, 802.11ac, and 802.11ax, providing a robust solution to address the challenges of wireless communication. OFDM works by splitting the available radio frequency spectrum into multiple narrower subcarriers, each carrying a portion of the data in parallel. These subcarriers are orthogonal, meaning they do not interfere with each other despite being closely spaced. This enables efficient use of the frequency spectrum and reduces the risk of interference from  neighbouring channels. In the context of Wi- Fi, this translates to improved data transmission rates and more reliable performance, even in crowded frequency bands. One of the key advantages of OFDM is its ability to combat multipath interference, which occurs when signals take multiple paths to reach the receiver due to reflections from objects in the environment. By transmitting data over multiple subcarriers simultaneously, OFDM can minimize the negative impact of multipath fading, which is particularly important in wireless networks where signal conditions are often dynamic and unpredictable. This property makes OFDM well-suited for indoor environments where obstacles and reflections are common. Additionally, OFDM supports high data rates by allowing multiple subcarriers to be used at the same time, each transmitting a lower data rate. This parallel transmission of data results in higher overall throughput, which is essential for modern applications like video streaming, large file transfers, and high-speed internet access. The ability to adapt the number of subcarriers based on the available bandwidth further enhances the flexibility of OFDM in different environments, allowing Wi-Fi networks to scale according to the required capacity. The integration of Multiple Input, Multiple Output (MIMO) technology with OFDM further enhances its capabilities. MIMO utilizes multiple antennas to send and receive several data streams simultaneously, effectively increasing the network's capacity and range. By combining MIMO with OFDM, technologies like 802.11n, 802.11ac, and 802.11ax can achieve even higher data rates and more stable connections, especially in environments with high user density. Overall, OFDM is fundamental to the evolution of IEEE 802.11 standards, enabling faster, more efficient, and more reliable Wi-Fi connections for a wide range of devices and applications.

3.2 OFDM BLOCK DIAGRAM 
OFDM is a digital modulation technique that divides information among several orthogonal subcarriers, enhancing spectral efficiency and robustness against interference. It is commonly utilized in technologies such as Wi-Fi, LTE, and 5G.
Fig 3.2 Block diagram of OFDM


The fig 3.2 represents the signal flow in an OFDM system, a widely used communication technique in modern wireless systems such as Wi-Fi, LTE, and 5G. On the transmitter side, the process begins with raw digital input data, which is first converted from a serial to parallel format. This allows the data to be divided across multiple subcarriers. Each parallel stream is then modulated using Binary Phase-Shift Keying (BPSK), where binary bits are mapped to symbols such as +1 or -1. The modulated data is processed through an Inverse Fast Fourier Transform (IFFT), converting the frequency-domain data into a time-domain OFDM signal while maintaining orthogonality between subcarriers. A cyclic prefix is added to the signal to combat inter-symbol interference caused by multipath effects during transmission. The signal is then transmitted through a channel modelled with additive white Gaussian noise (AWGN), simulating real-world noise and interference. On the receiver side, the process is reversed. The cyclic prefix is first removed, leaving only the useful OFDM symbol. The Fast Fourier Transform (FFT) is applied to convert the time-domain signal back into the frequency domain, recovering the modulated subcarrier symbols. BPSK demodulation is then performed to map these symbols back into binary data. Finally, the parallel data streams are converted back into a single serial stream, reconstructing the original input data. This entire process ensures efficient use of bandwidth and robustness against channel impairments, making OFDM a preferred choice in many communication standards.



 
CHAPTER 4 OFDMA
4.1 INTRODUCTION

Orthogonal Frequency Division Multiple Access (OFDMA) is an advanced digital communication technology derived from Orthogonal Frequency Division Multiplexing (OFDM). It is widely adopted in modern wireless systems, including 4G LTE, 5G NR, and Wi-Fi 6 (802.11ax), due to its ability to enhance spectral efficiency, reduce latency, and ensure reliable communication in diverse network conditions. Unlike OFDM, which allocates all subcarriers to a single user, OFDMA divides subcarriers into groups and assigns them to multiple users, allowing simultaneous data transmission and resource sharing in both the time and frequency domains. One of the key features of OFDMA is orthogonality, which ensures that subcarriers do not interfere with each other despite being closely spaced. This property enables efficient utilization of the available frequency spectrum. Another critical feature is dynamic resource allocation, where subcarriers can be assigned to users based on real-time factors such as channel quality, data demand, and quality of service (QoS) requirements. This flexibility allows OFDMA to adapt to changing network conditions and user needs. Additionally, OFDMA supports multiple users by dividing the available frequency resources among them, facilitating parallel transmissions.
The working principle of OFDMA involves dividing the total frequency band into orthogonal subcarriers, which are grouped into smaller units called Resource Blocks (RBs) or Resource Units (RUs). These RUs are dynamically scheduled to users, allowing efficient sharing of resources. Synchronization between users and the base station ensures that the orthogonality of subcarriers is maintained, which is crucial to minimizing interference. Each user transmits data on their allocated subcarriers, enabling simultaneous communication with the base station. OFDMA offers several advantages. It significantly improves spectral efficiency by allowing multiple users to share the same frequency band. It is highly flexible, supporting both narrowband and wideband communications and adapting to varying channel conditions. Its ability to allocate resources in both time and frequency domains reduces latency, making it suitable for low-latency applications. Furthermore, OFDMA’s robustness to fading and interference makes it ideal for modern wireless environments, and its scalability allows it to support high-density networks, such as urban areas or Internet of Things (IoT) deployments.
Applications of OFDMA span various domains. It is the backbone of downlink communication in 4G LTE and both uplink and downlink in 5G NR. Wi-Fi 6 (802.11ax) employs OFDMA to enhance performance in dense networks by enabling multiple devices to communicate simultaneously. The technology is also used in IoT and machine-to-machine communication, where its efficiency in resource allocation supports large-scale device connectivity. Moreover, it is integral to broadband access technologies like WiMAX, providing reliable wireless internet services. However, OFDMA does face some challenges. Maintaining synchronization among users, particularly in uplink transmissions, can be complex, especially when users are at varying distances from the base station. Like OFDM, OFDMA suffers from a high Peak-to-Average Power Ratio (PAPR), requiring sophisticated power amplifier designs to ensure efficient operation. Additionally, the dynamic resource allocation and scheduling mechanisms increase system complexity compared to traditional multiple-access techniques. OFDMA is a versatile and efficient multiple-access technique that has revolutionized wireless communication. Its ability to dynamically allocate resources, support multiple users, and adapt to diverse conditions makes it a cornerstone of modern communication technologies like LTE, 5G, and Wi-Fi 6. 

4.2 DIFFERNCE B/W OFDM & OFDMA
The evolution of Orthogonal Frequency Division Multiple Access (OFDMA) from Orthogonal Frequency Division Multiplexing (OFDM) represents a major advancement in wireless communication technology. OFDM, a digital modulation technique, divides a frequency band into multiple orthogonal subcarriers, enabling parallel data transmission with high spectral efficiency and robustness to frequency-selective fading. However, OFDM is inherently designed for single-user transmission, which limits its scalability and efficiency in multi- user environments. It allocates all subcarriers to a single user at any given time, leading to underutilization of resources when a user does not require the full bandwidth. Additionally, OFDM lacks the flexibility to dynamically allocate resources based on user needs, making it less suitable for modern networks with high user density and varying data demands.
To address these limitations, OFDMA was developed as an extension of OFDM, enabling multiple users to share the same frequency band simultaneously. In OFDMA, the subcarriers are divided into groups called Resource Blocks (RBs) or Resource Units (RUs), which can be dynamically allocated to users based on their real-time requirements, such as data demand, channel conditions, and quality of service (QoS) needs. This dynamic allocation ensures efficient utilization of resources while supporting multi-user parallelism, where multiple users can transmit data simultaneously. OFDMA also introduces scalability by supporting varying bandwidths, making it adaptable to applications ranging from narrowband IoT devices to high-bandwidth cellular networks. The transition from OFDM to OFDMA has enabled several technological advancements, including improved spectral efficiency, reduced latency, and support for dense user networks. OFDMA is a key enabler of modern wireless standards, such as 4G LTE, where it powers downlink communication, and 5G NR, where it supports both uplink and downlink. It is also integral to Wi-Fi 6 (802.11ax), enhancing performance in congested networks by allowing simultaneous communication between multiple devices. Furthermore, its ability to allocate resources efficiently makes it ideal for IoT applications and broadband access technologies like WiMAX.

Fig 4.1 OFDM and OFDMA allocation.
 
The fig 4.1 illustrates about the distribution of resources between OFDM and OFDMA systems. In OFDM, every user is allocated all available sub-carriers for their designated time slot, resulting in only one user transmitting at a time while sequentially accessing the full frequency spectrum. This method is simple but may be less efficient as users must wait for their opportunity to utilize the total bandwidth. On the other hand, OFDMA permits multiple users to share the sub- carriers at the same time by assigning each user a distinct combination of sub- carriers and time slots. This allows for simultaneous transmissions, where users can tap into different segments of the spectrum concurrently. Consequently, OFDMA enhances spectrum efficiency, minimizes latency, and accommodates a greater number of users compared to OFDM, making it better suited for contemporary wireless communication systems that demand adaptable and efficient resource management.



 
CHAPTER 5 
            RESOURCE ALLOCATION

5.1 RESOURCE ALLOCATION
Resource allocation is a critical process in wireless communication systems, where available resources such as bandwidth, subcarriers, time slots, and power are distributed among users to ensure efficient communication, maximize network performance, and meet diverse quality of service (QoS) requirements. It is particularly essential in modern systems like OFDMA, where multiple users share resources dynamically. Proper resource allocation not only improves system efficiency but also enhances user experience by optimizing throughput, minimizing latency, and reducing interference.

5.2 TYPES OF RESOURCE ALLOCATION
Resource allocation in wireless communication optimizes system performance by distributing key resources. Frequency allocation assigns subcarriers to users, power allocation adjusts transmit power for efficient use, and time slot allocation schedules transmission times to avoid interference. Spatial allocation manages antenna resources in MIMO systems.
5.2.1 Frequency Resource Allocation
In systems like OFDMA, the available frequency spectrum is divided into subcarriers. The allocation of these subcarriers to different users or data streams is a key part of resource management. The goal is to allocate subcarriers in a way that maximizes throughput while ensuring fairness among users. This can be done by assigning a higher number of subcarriers to users with better channel conditions (higher Signal-to-Noise Ratio or SNR) and fewer subcarriers to those with poorer conditions. The allocation process can also consider the interference levels, ensuring that users causing or receiving high interference are allocated resources more carefully. Resource allocation algorithms often aim to balance maximizing the throughput for each user while maintaining fairness and avoiding bottlenecks.

Fig 5.1 4G LTE
5.2.2 Power Allocation
Power allocation is another critical aspect of resource management, particularly in systems that aim to minimize power consumption while still achieving efficient communication. Power is allocated to different subcarriers or antennas to achieve the best possible performance in terms of signal strength, quality, and data rate. For example, in an OFDMA system, the water-filling algorithm is a common method for optimal power allocation. It assigns more power to subcarriers with better channel conditions and less power to those with poorer conditions. This allows for a more efficient use of available power, improving overall system capacity without unnecessarily increasing the energy consumption of each user or device.

Fig 5.2 Power Allocation
5.2.3 Time Slot Allocation
In Time Division Multiple Access (TDMA) or OFDMA systems, time slots are allocated to users or data streams to avoid conflicts and ensure fair access to the medium. Time slot allocation determines how long each user can transmit and at what time. This is particularly important in systems with multiple users, as the total transmission time must be shared effectively. Dynamic time slot allocation methods can adjust the transmission times based on the network conditions, such as the number of active users and their data demands.
 

Fig 5.3 2G GSM

5.2.4 Spatial allocation
Spatial allocation in wireless communication systems refers to the distribution of available spatial resources, such as antennas, channels, and frequency bands, to multiple users or devices. This is especially important in multi-user and multi-antenna systems like MIMO (Multiple Input, Multiple Output) and massive MIMO, as well as in systems that use beamforming or other spatial techniques. Space allocation plays a key role in improving network efficiency, throughput, and coverage while minimizing interference. It ensures that spatial resources are used optimally to support high-quality communication for multiple users or devices simultaneously.


Fig 5.4 5G Massive MIMO

5.3 OFDMA SYSTEM WITH OPTIMIZE RESOURCE ALLOCATION
OFDMA efficiently allocates subcarriers to multiple users in a wireless communication system. This improves data rates, reduces interference, and enhances spectral efficiency in systems like LTE and 5G.

Fig 5.5 Block diagram of OFDMA system with optimize Resource Allocation

The fig 5.1 illustrates input data undergoes power allocation, followed by BPSK modulation. The modulated data is converted to parallel format and processed using an IFFT before being transmitted through an AWGN channel. On the receiving side, the signal is processed using a FFT, converted back to serial format, and demodulated. Finally, the BER is calculated to evaluate the performance of the system under noisy conditions.

5.4 RESOURCE ALLOCATION ALGORITHMS

Resource allocation algorithms play a vital role in contemporary communication systems, facilitating the effective utilization of scarce resources such as power, bandwidth, and time slots. Power allocation in wireless communication is the process of distributing available transmission power among various channels, users, or subcarriers to optimize network performance while meeting constraints like energy efficiency, data rate, fairness, and interference management. It is crucial for maximizing system efficiency, reducing energy consumption, managing interference, ensuring fairness among users, and adapting to dynamic wireless conditions. Various algorithms are used for power allocation, including optimization-based approaches like the water-filling algorithm and convex optimization for maximizing throughput under constraints, and game-theoretic models for multi-user environments. Heuristic methods, such as greedy algorithms and genetic algorithms, provide near-optimal solutions with lower complexity. Machine learning techniques, including reinforcement learning and deep learning, enable dynamic and adaptive power allocation in complex systems. Iterative algorithms refine power distribution through repeated adjustments, while simpler rule-based approaches like equal or priority-based allocation are used in specific scenarios. Additionally, frameworks like proportional fair scheduling and weighted sum rate maximization are commonly applied in cellular standards such as LTE to balance fairness and efficiency. To achieve optimal power distribution in our system, we are currently using the Water-Filling algorithm and Round-Robin algorithm.
5.5 WATER-FILLING ALGORITHM
The Water-Filling Algorithm plays a crucial role in solving resource allocation issues, especially in communication systems like wireless networks. These systems require efficient distribution of resources such as power, bandwidth, or data rate among various channels or users. The algorithm's name is derived from the way water fills up containers of varying levels, prioritizing lower areas. In the context of communication, these containers represents different channels or subchannels, while water represents the allocation of power or other resources. The Water-Filling Algorithm finds application in systems with multiple communication channels that have varying capacities due to noise or interference. Its aim is to optimize resource allocation to maximize overall performance, such as data rate or signal quality. Its applications include power allocation in multi- user MIMO systems, resource allocation in OFDM systems, and maximizing channel capacity in wireless networks. It also contributes to noise minimization in signal processing.
Step 1: Initialize system parameters the number of users N, the number of subcarriers M, and the SNR range.
     Step 2: Compute channel gains for each user and subcarriers
     Step 3: Calculate water level λ based on average channel gains
      Step 4: Allocate power using water-filling 
          P_(U,K)^WF= max(0,λ - σ2/(h_(u,k)^2 ))                            
     Step 5: Simulate transmission over AWGN channel and perform BPSK modulation 
     Step 6: Compute BER, throughput, and power efficiency metrics.  
     Step 7: Repeat for varying SNR values and aggregate results. 


5.6 ROUND-ROBIN ALGORITHM

The Round Robin (RR) scheduling algorithm is a commonly utilized method for CPU management in operating systems that promotes both fairness and efficiency in environments where multitasking occurs.  It works by giving each process a fixed duration or time slice, known as a quantum, to execute. If a process does not finish within the given quantum, it is interrupted and placed at the end of the ready queue, while the next process in line is assigned the CPU. This repetitive scheduling continues until all processes have been completed. Round Robin is a preemptive method, which prevents any single process from dominating CPU usage, and its straightforward implementation makes it a favoured option in time-sharing systems. However, its effectiveness is influenced by the size of the time quantum: a smaller quantum can heighten context-switching overhead, while a larger one may result in unsatisfactory response times. In spite of these limitations, RR is appreciated for its equitable allocation of CPU time among processes. 
Step 1: Initialize system parameters the number of users N, the number of subcarriers M, and the SNR range.
     Step 2: Allocate power equally across all users and subcarriers
                             P_(u,k)^RR=P_total/(N×K)                                                      
     Step 3: Simulate transmission over AWGN channel and perform BPSK modulation 
     Step 4: Compute BER, throughput, and power efficiency metrics.  
     Step 5: Repeat for varying SNR values and aggregate results.   






CHAPTER 6
       RESULTS & DISCUSSION

6.1 SIMULATION PARAMATERS

Table 1 Simulation parameters
 	
Modulation scheme	BPSK
Channel model	AWGN & Rayleigh
FEC scheme	Repetition
Number of users	4
Number of subcarriers	64
SNR values in dB	0 to 10
Number of information bits per user	10^6
Fairness control factor for Round Robin allocation	10
Repetition factor for error correction	3

6.1.1 BER Calculation

BER quantifies the ratio of erroneously received bits to the total transmitted bits. It serves as a measure of system reliability.
The Bit Error Rate (BER) for every user u is defined as follows:
            〖BER〗_u = (Number of Bit Errors)/(Total number of Bits)            
A lower BER signifies greater system dependability, especially in situations with                                                  low Signal-to-Noise Ratios (SNR).




6.1.2 Throughput   

Throughput evaluates the rate of successful data transmission. It reflects system efficiency under different power allocation schemes. 
The overall throughput of the system is,
             〖Throughput〗_total=∑_(u=1)^numUsers▒〖(1- 〖BER〗_u) 〗× 〖infoBitsLength〗^                                                         
Increased throughput indicates improved use of system resources and effective data transmission among users.

6.1.3 Fairness Index
Fairness Index quantifies the fairness of resource allocation among users, where a value close to 1 indicates high fairness.
         Fairness Index = □(〖(∑_(u=1)^N▒T_u )〗^2 )/(N .∑_(u=1)^N▒T_u^2 )         

6.1.4 Sum Capacity       
The sum capacity represents the total achievable rate of the system. It depends on the channel gains and allocated power per subcarrier.
               C_(sum =) ∑_(u=1)^N▒  ∑_(k=1)^K▒〖log〗_(2 ) (1+□(〖h_(u,k)^2 P〗_(u,k) )/σ2)        
6.1.5 Water level
The water level λ is determined by computing the inverse of the average channel gain. 
The water level λ can be defined as,
            λ = 1/(E[h_(u,k)])             

6.1.6 Power Usage in Water-Filling

In the Water-Filling allocation scheme, power is adaptively distributed based on the channel gain of each subcarrier. Subcarriers with better channel conditions receive more power.
The power usage in water-filling is defined as follows,
               P_(U,K)^WF= max(0,λ - σ2/(h_(u,k)^2 ))       

6.1.7 Power Usage in Round Robin  
In the Round Robin allocation scheme, power is uniformly distributed among all users and subcarriers, regardless of channel quality.        
The power usage in Round Robin is defined as follows,
〖                  P〗_(u,k)^RR=P_total/(N×K)                                                                                                       
 
 
 








 
	RESULTS & OUTPUT
6.2.1 Comparison of BER Vs SNR
BER (Bit Error Rate) measures the number of bit errors in a transmission, while SNR (Signal-to-Noise Ratio) quantifies the strength of the signal relative to noise. As SNR increases, BER typically decreases, indicating better communication quality.
	

Fig 6.1 Comparison of BER Vs SNR

The fig 6.1 shows the BER versus SNR performance for four users using WF and RR algorithms. At an SNR of 0 dB, the BER for all users is approximately 10−2. As the SNR increases, the BER reduces noticeably. At 2 dB, WF users achieve a BER near 10−4, while RR users remain closer to 10−3. By 4 dB, WF User 4 achieves a BER below 10−6, while RR users stay around 10−5, demonstrating the better efficiency of WF compared to RR for all users.

6.2.2 Comparison of Sum Capacity vs. SNR
Sum Capacity vs SNR refers to the total data transmission capacity of a communication system as a function of the Signal-to-Noise Ratio (SNR). As SNR increases, the sum capacity (total throughput) generally increases, meaning the system can support higher data rates and more users with better signal quality.

Fig 6.2 Comparison of Sum Capacity Vs SNR

The fig 6.2 depicts the sum capacity comparison between Water-Filling (WF) and Round-Robin (RR) algorithms as a function of SNR. At an SNR of 0 dB, both WF and RR achieve a sum capacity of approximately 50 bps/Hz. As SNR increases, the sum capacity improves. At 6 dB, WF reaches about 200 bps/Hz, while RR lags behind at around 150 bps/Hz. At 10 dB, WF achieves nearly 300 bps/Hz, significantly outperforming RR, which remains close to 250 bps/Hz, highlighting the superior efficiency of WF in maximizing sum capacity.
 
 6.2.3 Comparison of Total Throughput Vs SNR
Total Throughput vs SNR refers to the relationship between the overall data transmission rate (throughput) and the Signal-to-Noise Ratio (SNR) in a communication system. As the SNR increases, the signal quality improves, allowing for higher data rates and more efficient use of the available bandwidth, resulting in increased total throughput. Essentially, higher SNR enables more reliable communication, which leads to better overall system performance and greater throughput.


Fig 6.3 Comparison of Total Throughput Vs SNR

The fig 6.3 illustrates the total throughput comparison between Water-Filling (WF) and Round-Robin (RR) algorithms as a function of SNR. At 0 dB, both methods achieve a throughput of approximately 3.99 × 106 bits. As SNR increases, throughput slightly improves. At 6 dB, WF achieves around 3.996 × 106 bits, while RR lags behind at about 3.994 × 106 bits. At 10 dB, WF reaches close to 3.999 × 106 bits, marginally outperforming RR, demonstrating its better throughput efficiency across higher SNR levels.
 
6.2.4 Comparison of Fairness index Vs SNR
A Fairness Index vs. SNR graph shows how equally resources are allocated among users as the Signal-to-Noise Ratio (SNR) changes. A higher fairness index (closer to 1) means resources are distributed more equally, while a lower value indicates unfair allocation. The graph helps evaluate scheduling algorithms like Round Robin, Proportional Fair, and Water-Filling in wireless networks.
Fig 6.4 Comparison of Fairness index Vs SNR

The fig 6.4 shows the fairness index comparison between the Water-Filling (WF) and Round-Robin (RR) algorithms across varying SNR levels. At 0 dB, both WF and RR start with a fairness index of around 0.98. As SNR increases, RR consistently achieves a slightly higher fairness index than WF. By 6 dB, RR reaches nearly 0.995, while WF remains close to 0.985. At 10 dB, RR maintains a fairness index close to 1.0, outperforming WF, which approaches 0.99. This demonstrates RR's superior ability to maintain fairness as SNR increases.

 
6.2.5 Comparison of Total power allocation Vs SNR
A Total Power Allocation vs. SNR graph shows how the total transmitted power varies with Signal-to-Noise Ratio (SNR). In water-filling algorithms, more power is allocated to users with better SNR, while low-SNR users receive less power. This graph helps analyze power efficiency in wireless communication systems.
Fig 6.5 Comparison of Total power allocation Vs SNR

The fig 6.5 compares the total power allocation between the Water-Filling (WF) and Round-Robin (RR) algorithms as a function of SNR. At an SNR of 0 dB, both WF and RR start with a total power allocation of approximately 2 Watts. As SNR increases, the total power allocation for both algorithms rises, with WF consistently requiring more power than RR. By 6 dB, WF allocates nearly 10 Watts, while RR allocates about 8 Watts. At 10 dB, WF reaches approximately 18 Watts, surpassing RR, which allocates around 14 Watts. This indicates that WF uses higher power to achieve its performance gains compared to RR.

Table 2 Water-Filling Vs Round Robin Comparison    

Metric	Best Algorithm
Bit Error Rate	Both Water-Filling and Round Robin
Sum Capacity	Water-Filling
Throughput	Water-Filling
Fairness	Round Robin
Power allocation	Water-Filling

The table 2 compares Water-Filling and Round Robin algorithms across key metrics. Water-Filling outperforms in terms of sum capacity, throughput, and power allocation due to its efficient resource distribution. Round Robin performs better in fairness, ensuring equal access for all users. Both algorithms deliver similar performance in bit error rate under the given conditions.

Water-Filling maximizes sum capacity but consumes more power. Round-Robin ensures fairness but lacks efficiency. The choice depends on whether throughput or fairness is prioritized. The comparative analysis highlights key trade-offs between the Water-Filling and Round-Robin algorithms. Water-Filling achieves superior sum capacity and throughput by dynamically allocating power based on channel conditions. However, this advantage comes at the cost of higher power consumption. In contrast, Round-Robin ensures fairness among users by distributing resources equally but does not optimize sum capacity. The choice of algorithm depends on network priorities—whether maximizing throughput or ensuring fair access.



  CHAPTER 6 CONCLUSION
This paper presents a performance analysis of the Water-Filling (WF) and Round-Robin (RR) algorithms for resource allocation in multi-user OFDMA systems. The study evaluates key performance metrics, including sum capacity, throughput, fairness, and power efficiency, to determine the effectiveness of each algorithm. The simulation results indicate that the Water-Filling algorithm significantly improves system efficiency by dynamically allocating power to subcarriers with superior channel conditions. As a result, it maximizes sum capacity and throughput, making it a preferred choice for scenarios where system performance and efficiency are the primary objectives. However, this improvement comes at the cost of higher power consumption, which may not always be desirable, especially in energy-constrained networks.

On the other hand, the Round-Robin algorithm ensures equal resource distribution among users, making it an excellent choice for applications where fairness is critical. Unlike the WF algorithm, which prioritizes efficiency, RR focuses on maintaining a balanced allocation of resources across all users, preventing any single user from monopolizing the available bandwidth. Despite its advantages in fairness, the RR algorithm does not optimize sum capacity or throughput, which can be a limiting factor in high-performance wireless networks. The findings of this study highlight the importance of selecting an appropriate resource allocation strategy based on specific network requirements. If the primary goal is to maximize system efficiency and throughput, the WF algorithm is the optimal choice. Conversely, if fairness among users is the main concern, then the RR algorithm is more suitable. Ultimately, network designers must carefully consider the trade-offs between performance and fairness to achieve the best possible balance for their specific applications.

