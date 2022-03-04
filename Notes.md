### 4-layer model
sdf
d
fs
df
sd


### IP service model
To use internet, we must use **Internet Protocol (IP)**.

Recall that each layer provides the "service" to the layer above. Lets see what service provided by Internet Protocol.

![IMG_5690(20220304-174152)](https://user-images.githubusercontent.com/72336341/156739313-40d79901-b74a-457d-a55e-a7c6051a8591.PNG)
When the transport layer sends data, it hands a Transport Segment to the Network layer below. The network layer puts the transport segement inside a new IP datagram. 

IP need to deliver the datagram to the other end. 
IP datagram has to make it over the first link to the first router. IP sends the datagram to the Link Layer that puts it inside a Link frame, such as an Ethernet packet and ships it off to the first router.

IP service can be characterized by four properties below:
![image](https://user-images.githubusercontent.com/72336341/156741612-b6025903-3c27-4af0-a3b4-a7ceb03db884.png)

* **datagram**

  IP is a datagram service, which sends Datagrams from end host to end host; it is unreliable, but makes a best-effort to deliver the datagrams. The network maintains no per-flow state associated with the datagrams.

  Recall: datagram is a packet that is routed individually and hop-by-hop through the network from one router to the next, all the way from the IP source address to the IP destination address, based on the information in its header. 

  In the image, "IP DA" means IP destination address. The forwarding decision at each router is based on the IP DA.

  IP source address, or "IP SA" indicates where the packet came from, so the receiver knows where to send any response.

  **How router works? more later...**

  For now, enough to know that each router contains a forwarding table that tells it where to send packets matching a given destination address. The router doesn’t know the whole path, it uses the destination address to index into its forwarding table so that it can forward the packet to the next hop along the path towards its final destination. Hop by hop, step by step the packet makes its way from the source to the destination using only the destination address in the datagram.

* **Unreliable**

  IP makes no promise that packets will be delivered to the destination. They could be delivered late, out of sequence, or never delivered at all. 

  It’s possible that a packet will be duplicated along the way, for example by a misbehaving router. 
* **Best effort**

  However, it won’t drop datagrams arbitrarily. **IP does make the promise to only drop datagrams if necessary.**

  For example, the packet queue in a router might fill up because of congestion, forcing the router to drop the next arriving packet. IP won’t make any attempt to resend the data and in fact, IP doesn’t tell the source that the packet was dropped.
  
  Another example, a faulty routing table might cause a packet to be sent to the wrong destination. Or cause a packet to be duplicated by mistake.
  
* **Connectionless**

  IP is an extremely simple, minimal service. It maintains no state at all related to a communication. We say that a communication service is “connectionless” because it doesn’t start by establishing some end to state associated with the communication. In other words, when we make a Skype call lasting several minutes and consisting of many IP datagrams, the IP layer maintains no knowledge of the call, and simply routes each datagram individually and independently of all the others
#### Why keep IP service simple?
 


#### IPv4 Datagram

![image](https://user-images.githubusercontent.com/72336341/156746310-7aa80332-18d8-49f1-8337-02cbc0724a41.png)













