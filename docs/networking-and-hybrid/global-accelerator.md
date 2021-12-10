### Overview
AWS Global Accelerator is designed to improve global network performance by offering entry point onto the global AWS transit network as close to customers as possible using ANycast IP addresses

- **Anycast IP's** allow a **single IP** to be in **multiple locations**. Routing moves traffic to **closet location**
- **2 anycast IP Addresses**
- All location of global accelerator edge locations wil use the pair of anycast IP addresses
- Traffic initially uses **public internet** before **entering a Global Accelerator edge location**
    - from the edge, data transits globally across the **AWS global backbone network**
    - increases the performance substantially

### Global Accelerator vs Cloudfront
|Global Accelerator| Cloudfront|
|:---:|:---:|
| Doesnot support caching | Cache the http content using edge location|
| Move AWS network closer to the customer|  Move content closer to the customer by caching|
| Network product which supports **TCP/UDP** (deos not understand http protocol) | Only supports **HTTP/HTTPS** content caching|
