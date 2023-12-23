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
