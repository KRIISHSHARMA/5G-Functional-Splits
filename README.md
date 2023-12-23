# 5G-Functional-Splits
## WHY DO WE NEED RAN FUNCTIONAL SPLITS ?
- More flexible and easier to fit to specific deployment constraints
- Some splits implementations allow more centralization hence bring performance gains and improving hardware utilization (ex: split 8)
- Some splits are better suited for virtualization though it is challenging to virtualize some lower level functions whereas high level ram functions can be more easily virtualized
- Virtualization brings down costs of hardware
- More variety of vendors , a key factor with open brand deployments as this enables flexibility of choice and the ability to avoid vendor lock in

## HAUL 
- Fronthaul refers to the link between the RU and DU, while Midhaul refers to the link between the DU and CU, and lastly the Backhaul is representing the link between the CU and the core network
- The Midhaul or the F1 interface is standardized by 3GPP and it is a new interface that exists in 5G due to the RAN split technique which allows the BBU (Baseband Unit) to be divided into two parts which are DU and CU that can deployed in different locations.
- Also, the Backhaul refers to the NG interface which is also standardized by the 3GPP. However, the Fronthaul was implemented by large equipment vendors in a proprietary fashion which limits the operators to a single-vendor approach as you can’t connect RU and DU from different vendors.
- But if you are going to implement 5G using Open RAN, then O-RAN Alliance was responsible for standardizing Fronthaul using option 7-2x and also the Small Cell Forum using split option 6 for small cells.
- [reference](https://www.telecomhall.net/t/what-is-fronthaul-midhaul-and-backhaul-in-5g/16985)

![image](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/643b4d89-7846-4681-9031-3c584980ad00)
![image](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/46d91f08-3c77-4975-9166-8ce4506e4aae)


## FUNCTIONAL SPLITS
- Split 2: RRC/PDCP split : Radio resource control and packet data convergence control are split from the Layer 2 radio link control (RLC)
  1. Variant 1: RRC, service data adaptation protocol (SDAP) & PDCP in the same central unit as one entity; no control and user split. RLC, medium access control (MAC), and high physical layer will be part of the DU, and the low physical layer along with the RF are in the DU.
  2. Variant 2: In addition to Variant 1, this split option comes with control and user split like in a CU-CP and CU-UP. RRC along with PDCP-C will be part of CU-CP, and the SDAP/PDCP-U will be associated with CU-UP.
  3. [more](https://www.rcrwireless.com/20210317/5g/exploring-functional-splits-in-5g-ran-tradeoffs-and-use-cases-reader-forum)
  4. Split 2 – use cases: Ideal use cases include scenarios where a low fronthaul bitrate is necessary to be transported over a less ideal fronthaul interface, where higher security and resiliency is obtained by CP/UP separation.
    
- Split 6: MAC/PHY layer split. The MAC, RLC and upper layers will be part of the central unit (CU). There is no Low PHY/High PHY split; instead the full stack of the PHY layer and the RF are in the DU/RU.
- Split 6 – use cases: The ideal use cases are scenarios where only centralized scheduling is required. It is best suited for small cell fem-to-cell like deployment as well as where heterogeneous backhaul and fronthaul with variable performance is available and the cost to cater for different small cells is needed.

- Split 7.2x: Low PHY/High PHY split. The Low PHY/High PHY split is the most acceptable approach for it is less complex and it supports various fronthaul requirements and most importantly it has high virtualization benefits. This split has been further optimized by the O-RAN Alliance into two variants: split 7.2a and split 7.2b. Split 7.2x comes with fronthaul compression techniques like BFP IQ compression and de-compression to further reduce transport bandwidth.

![image](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/3f9047ba-8fce-45c6-87a7-11d58d84d244)

- Split 7.2x – use cases: Scenarios where an ideal fronthaul is possible for URLLC and carrier aggregation, presence of [eCPRI](https://www.5gworldpro.com/blog/2022/12/21/what-is-the-importance-of-ecpri-in-5g/) and common scheduler for deployment like virtualized local data centers. It supports use cases where efficient resource utilization from multi-RAT and multi-connectivity is needed.

![Parallel_Fig07-768x362](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/233ad1bc-93d4-4a0d-aee8-6361e56222dc)
![image](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/213037af-e8f6-42e3-bf6d-47096f819994)
![image](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/1b786efd-273c-4425-afb5-f7b8afa8fcd7)

## WHAT TO CHOOSE ?
- When you have something like split 8  you need more real time and an ideal backhaul (fiber)
- wheras if your looking at split 2 you can have non-ideal delay so you could have something like a microwave and dont need to have fiber

![Screenshot from 2023-12-23 17-57-46](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/7276305e-3477-47a7-94a8-975d5dcf14eb)

## MMWAVE
![image](https://github.com/KRIISHSHARMA/5G-Functional-Splits/assets/86760658/68b18fdb-1ec2-428e-ae09-010714064d15)

