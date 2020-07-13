# lorawan-model

This repo will contain an accurate and configurable model to estimate the network performance of a [LoRaWAN](https://lora-alliance.org/about-lorawan) network with a single gateway.

Through multiple configurable parameters, the model allows the user to estimate the performance of LoRaWAN networks applying standard configurations, as well as to test innovative and more efficient options. 

Performances are computed in terms of Packet Delivery Ratio (PDR) and delays. An overview of the model structure, employed assumption and accepted input and outputs are described below.

The analytical model is written in Python, and its results can be easily compared to the simulation outcomes obtained through the ns-3 [lorawan](https://github.com/signetlabdei/lorawan) module.

Further information can be found at [INSERIRE LINK ARXIV]


### Model structure and assumptions
The model makes use of the alternate renewal processes to describe the behavior of the gateway's demodulators availability and the possibility of sending an ACK (or downlink packet) in the reception windows. 

The assumptions are the following:
- Packets are generated at the application level following independent Poisson processes with aggregate packet generation rate lambda (pck/s).
- The generated traffic is equally split into C frequncy channels
- Spreading Factors (SFs) are prefectly orthogonal
- Re-transmissions are independent
- End Devices (EDs) are uniformly spread around the GW, and are in range for any SF
- Each ED can transmit only one type of message, either confirmed or unconfirmed 


### Inputs and configurable parameters

| Parameter        |Description                                                               
| :------------    | :----------:                                                           
|  p               | distribution of SFs
|  alpha           | fraction of devices that uses confirmed traffic
|delta             |  enables (delta = 1) or disables (delta = 0) duty cycle restrictions
| h                | number of re-transmissions for unconfirmed traffic;
| m                | maximum number of transmission attempts for devices employing confirmed traffic;
| tau_1, tau_2     | prioritization flags. If tau_k=0, the GW prioritizes reception operations over transmission during the k-th receive window. In this case, the GW will drop any DL message that needs to be transmitted while a uplink reception is ongoing. Instead, if TX is prioritized (tau_k = 1), the reception of any incoming packet will be interrupted in order to send the ACK.
| C               | number of UL frequency channels.
| T_x,ack_2       | duration of the transmission of the ACK in the second receive window when using SF x. (The standard considers packets transmitted in RX2 to use SF 12 as pre-configured setting, corresponding to T_12,ack2.

### Output



