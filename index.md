# lorawan-model

This repo will contain an accurate and configurable model to estimate the network performance of a [LoRaWAN](https://lora-alliance.org/about-lorawan) network with a single gateway.

Through multiple configurable parameters, the model allows the user to estimate the performance of LoRaWAN networks applying standard configurations, as well as to test innovative and more efficient options. 

Performances are computed in terms of Packet Delivery Ratio (PDR) and delays. 

The analytical model is written in Python, and its results can be easily compared to the simulation outcomes obtained through the ns-3 [lorawan](https://github.com/signetlabdei/lorawan) module. This repo provides the user with a *Jupyter notebook* that allows to run model and simulations smoothly and with no effort, to replicate the findings of out paper.


## References
- D. Magrin, M. Capuzzo, A. Zanella and M. Zorzi, "A Configurable Mathematical Model for Single-Gateway LoRaWAN Performance Analysis," in *IEEE Transactions on Wireless Communications*, doi: 10.1109/TWC.2021.3136029. [Link](https://ieeexplore.ieee.org/document/9662201)
