
![cs](https://github.com/Annerez/ITY2S1/blob/main/Introduction%20of%20Network%20System/Network%20Images/Pasted%20image%2020241003093605.png)

ถ้าคอมใน cs ย้ายมา ee และต้องการคุยกับ CS

ก็ต้อง broadcast เพราะอยู่นอกวง LAN ซึ่งมีปัญหา security, privacy

จึ่งเกิด VLANs ขึ้นมา

# VLANs

เครือข่าย LAN ที่อยู่ภายใต้ switch เดียวกันแต่คนละ segment สามารถทำให้เหมือนอยู่ LAN เดียวกันได้ผ่าน VLANs

![idk](https://github.com/Annerez/ITY2S1/blob/main/Introduction%20of%20Network%20System/Network%20Images/Pasted%20image%2020241003094009.png)

![idk2](https://github.com/Annerez/ITY2S1/blob/main/Introduction%20of%20Network%20System/Network%20Images/Pasted%20image%2020241003094017.png)


traffic isolation:

frame ส่งจาก 1-8 ไปถึง 1-8 ก็จะคุยได้แค่กับ 1-8

จึงๆเรากำหนด VLAN ผ่าน mac address  ของ Endpoint แทน port ได้ด้วย

dynamic membership:
port สามารถ assign แบบ dynamic ได้เลย

![idk3](https://github.com/Annerez/ITY2S1/blob/main/Introduction%20of%20Network%20System/Network%20Images/Pasted%20image%2020241003094458.png)
forwarding between VLANs

คุยกับข้าม switch ได้ผ่านการ routing (ต้องมี switch หรือ router)

![idk6](https://github.com/Annerez/ITY2S1/blob/main/Introduction%20of%20Network%20System/Network%20Images/Pasted%20image%2020241003094520.png)



# trunk port

![idk7](https://github.com/Annerez/ITY2S1/blob/main/Introduction%20of%20Network%20System/Network%20Images/Pasted%20image%2020241003094708.png)

802.1q --> ปรับปรุง header ของ 802.3 เพื่อทำให้ใช้ใน VLANs ได้



# เชื่อม internet

(IP static ทำยากต้องมี DHCP)
หา DHCP ก่อนเพื่อเอา IP ด้วยการ broadcast IP, Ethernet address ไป


TCP ใช้ socket binding ผ่าน IP
ต้องรู้ DNS ก่อนพิมพ์ url ได้เพื่อรู้ address


ตอนนี้ไป wireless ละ
# WLANs

- Mobiles Communication Domain
	- โทรศัพท์ เน้นเคลื่อนที่
	- มื่อก่อน 2G ใช้ cellular ได้ผ่าน GPRS, EDGE
- Data Communication Domain
	- ไม่ได้เน้นการเคลื่อนที่
	- ใช้แค่ให้คอมเชื่อมแบบไร้สายได้
	- ต่อมามี laptop มีฯลฯจึง mobility ได้ 
- เมื่อ technology ผ่านไป ทั้งสองก็รวมกันเป็น Wireless Communications and Networks
	- ตอนนี้เราสามารถเชื่อมได้ทั้ง cellular และ Wi-Fi


Wireless link

มีสอง link

backbone (point-to-point) กับ shared

Multiple Access Protocol ของ wireless

2G --> FDMA/TDMA
3G --> CDMA
4G/5G --> OFDM

802.11 (Wi-Fi) --> CSMA/CA

DSSSS (-> CDMA)
OFDM
OFDMA

Access point มีหน้าที่ทำการเปลี่ยน protocol

Access point แบบใหม่สามารถทำให้ handoff ได้ (ปกติทำไม่ได้)

ad hoc mode


# Wireless Link Characteristics

- interference: เกิด noise
- multipath propagation: เกิด collision

SNR = Ps/Pn

SNR = 10.log(Ps/Pn) dB


# 802.11 Wireless LAN

802.11b --> DSSS

802.11a --> OFDM

802.11g

802.11n --> มี MIMO ใช้ประโยชน์จาก multipath

802.11ac --> MIMO

- all use CSMA/CA for multiple access
- all have base-station and ad-hoc networks version

QoS ใช้กับ service real time เช่น streaming



Channels, association

การเชื่อม Wi-Fi
1. beaming
2. Joining
3. Transmitting
4. Remain Connect


active scanning

ขอ SSID จาก APs
