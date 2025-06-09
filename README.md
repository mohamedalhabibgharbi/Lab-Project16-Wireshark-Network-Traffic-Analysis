# 🔍 Network Traffic Analysis with Wireshark – A TryHackMe Lab Walkthrough

In this lab, hosted on TryHackMe, I explored the fundamentals of Wireshark, one of the most powerful and widely used network traffic analysis tools. The lab provided hands-on practice with live packet captures and deep-dived into techniques used by security analysts to inspect, filter, and dissect network data. Here's a summary of the most important insights and takeaways.

---

## 🛠️ Objectives

- Load and analyze packet captures  
- Understand packet structure based on the OSI model  
- Use filtering and stream reconstruction  
- Extract embedded data and spot anomalies  

---

## 📊 Understanding the Wireshark Interface

Wireshark's interface is structured into multiple panes:

- **Packet List Pane**: Summary of all captured packets.  
- **Packet Details Pane**: Layered dissection of each packet.  
- **Packet Bytes Pane**: Raw hexadecimal and ASCII view.  
- **Toolbar & Filter Bar**: Tools for capture, filtering, exporting, and navigation.  

> Color coding helps quickly distinguish protocols and traffic types—green often indicates HTTP, blue for TCP, etc.

---

## 📁 Loading and Investigating PCAP Files

Upon loading `Exercise.pcapng`, I analyzed the file properties and noted:

- 🏷️ **File Comment (Flag)**: TryHackMe_Wireshark_Demo <br> <br>
  ![Screenshot1](https://i.imgur.com/SHMuhAM.png)
  <br> <br> <br>

- 📦 **Total Packets**: 58,620 <br> <br>
  ![Screenshot2](https://i.imgur.com/9d3XosJ.png)
  <br> <br> <br>

- 🔑 **SHA256 Hash**: `f446de335565fb0b0ee5e5a3266703c778b2f3dfad7efeaeccb2da5641a6d6eb` <br> <br> 
  ![Screenshot3](https://i.imgur.com/1lE72dX.png)
  <br> <br> <br>

---

## 🧬 Packet Dissection & OSI Layers

Wireshark allows deep inspection of each packet across the OSI model:

- **Layer 2 (Data Link)**: MAC addresses  
- **Layer 3 (Network)**: IP addresses  
- **Layer 4 (Transport)**: TCP/UDP headers, ports  
- **Layer 5–7 (Application)**: Protocol-specific data (e.g., HTTP/XML)

---

## 📌 Example Insight

As part of the exercise using the `Exercise.pcapng` file, I conducted my own analysis of packet 38 and extracted the following specific insights:
 
  - Markup Language: XML <br> <br>
    ![Screenshot4](https://i.imgur.com/73sarV8.png)
    <br> <br> <br>
  - Arrival Date: 05/13/2004  <br> <br>
    ![Screenshot5](https://i.imgur.com/mbXB8dz.png)
    <br> <br> <br>
  - TTL Value: 47 <br> <br> 
    ![Screenshot6](https://i.imgur.com/vHKoxJ6.png)
    <br> <br> <br>
  - TCP Payload Size: 424 bytes <br> <br>
    ![Screenshot7](https://i.imgur.com/wJ8G8o3.png)
    <br> <br> <br>
  - E-tag Value: `9a01a-4696-7e354b00` <br> <br>
    ![Screenshot8](https://i.imgur.com/MkGh88E.png)
    <br> <br> <br>

---

## 🔎 Advanced Analysis Techniques

### ✅ Search & Commenting

- I searched for `"r4w"` and found artist name: `r4w8173`  <br> <br>
  ![Screenshot9](https://i.imgur.com/HTwxdWs.png)
  <br> <br> <br>

- **Packet #12** had a hidden comment revealing an MD5 hash: `911cd574a42865a956ccde2d04495ebf` <br> <br> 
  ![Screenshot10](https://i.imgur.com/RQ1S6FC.png)
  <br> <br> <br>
  ![Screenshot11](https://i.imgur.com/rZFLzfx.png)
  <br> <br> <br>
  ![Screenshot12](https://i.imgur.com/4zuFeVi.png)
  <br> <br> <br>

---

### 📄 File Extraction

I extracted a `.txt` file embedded in HTTP traffic, and found that the 🛸 "Alien name" was `PACKETMASTER` <br> <br>
![Screenshot13](https://i.imgur.com/chu8hiD.png) 
<br> <br> <br>
![Screenshot14](https://i.imgur.com/8yz1cO5.png) <br> <br>
<br> <br> <br>

---

### ⚠️ Expert Info Section

Wireshark flagged **1636 warnings**, highlighting potential anomalies for closer inspection. <br> <br> 
![Screenshot15](https://i.imgur.com/TkcN4p7.png)
<br> <br> <br>

---

## 🔍 Filtering & Stream Analysis

Wireshark's filtering capability is crucial in real-world traffic analysis.

- I Applied `http` Filter  <br> <br>
  ![Screenshot16](https://i.imgur.com/3Y2vfp9.png)
  <br> <br> <br>
  ![Screenshot17](https://i.imgur.com/9aFTlNe.png) <br> <br>
  <br> <br> <br>

- After applying the Filter, I found out that the Filtered Packets Count was 1,089  <br> <br>
  ![Screenshot18](https://i.imgur.com/h4oBvh1.png)
  <br> <br> <br>


---

## 💡 What I Learned

This lab was essential for building a strong foundation in network security analysis:

- Navigating and customizing Wireshark’s interface  
- Interpreting the structure of network packets  
- Performing targeted searches and stream reconstructions  
- Extracting and analyzing files from network traffic  
- Leveraging expert info for spotting protocol anomalies  

---

## 📸 Portfolio Bonus

To support this write-up, I’ve included annotated screenshots demonstrating:

- GUI layout and filtering  
- Extracted file objects  
- Expert Info window  
- Followed HTTP streams  
- Packet layer analysis  

---

## 🧠 TryHackMe Room: Wireshark - The Basics

**Skills Gained**:  
`Network forensics`, `protocol analysis`, `traffic filtering`, `stream reconstruction`

---

## ⚠️ Disclaimer

This is a hands-on lab from the TryHackMe website. It is created for training purposes only.
