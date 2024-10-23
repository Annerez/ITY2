
# CSMA

- ฟังก่อน transmit
- ถ้า channel ว่าง, ส่งไปแม่งทั้ง frame เลย
- ถ้า channel ไม่ว่าง, เลื่อนเวลาส่ง


- เกิดการชนกันได้ ผ่าน propagation delay ก็คือทั้งสองคนไม่รู้ว่าอีกฝ่ายกำลังจะส่ง
- ถ้าชนกัน หายไปทั้ง packet เลย

# CSMA/CD

- มี carrier sensing
- ลดเวลาการชน
- ถ้าชนกันจะหายไปอย่างรวดเร็ว ไม่เสียทรัพยากรเท่า CSMA

wired LAN วัดสัญญาณจากสาย
wireless LAN มี shadow node หาไม่ได้ว่ามี

CA collision avoidance

- มี backoff รอ K*512 bit times, ค่า K อยู่ในระหว่าง 2^m - 1
- ประสิทธิภาพของ CSMA/CD = 1 / (1 + 5tprop / ttrans)


# "Taking turns" MAC protocols

- channel partitioning MAC protocol (แบ่งช่องด้วย Time หรือ Code)
	- Time Division, Frequency Division
	- แบ่งช่องเท่าๆกัน
	- ไม่ดีสำหรับ load น้อยๆ, bandwidth 1/N ถูกใช้แม้ว่าจะมีแค่ 1 node !
- random access MAC protocol
	- ประสิทธิภาพดีสำหรับ load น้อยๆ: ใช้ bandwidth ได้คุ้ม
	- ไม่ดีใน high load: เกิด collision ได้
	- ALOHA, S-ALOHA, CSMA, CSMA/CD
	- CSMA/CD ใช้ใน Ethernet
	- CSMA/CA ใช้ใน 802.11
- taking turns protocol
	- เอาข้อดีทั้งคู่มารวมกัน
	- polling
		- master node เชิญ slave node transmit เป็น turnๆ
	- token passing
		- ส่ง token ให้แต่ละ node ใช้ในการส่งข้อมูล

# Ethernet

- first widely used LAN technology
- 10 Mbps - 10 Gbps
- เมื่อก่อน bus ตอนนี้ star มี switch อยู่ตรงกลาง ใช้ Ethernet protocol แต่ละตัวต่างกัน
- มี hub กับ switch
- CRC
- Premable
- Hub --> repeater, ขยายการเชื่อมต่อ
- Switch --> Repeater, filtering ตรวจสอบ MAC address ที่เข้ามา, สร้าง switch table ลด traffic, broadcast ลดปริมาณ traffic ลง

- unreliable, connectionless
- Ethernet's MAC protocol: unslotted CSMA/CD with binary backoff

# LANs

- MAC address กำหนดที่อยู่ของ LAN
- ARP กระบวนการ mapping ให้รู้ว่า IP ใน segment มี MAC address อะไรบ้าง

IPv4
Fragmentation --> กรณี payload ใหญ่เกิน

การสื่อสารบน LAN มัน broadcast


Ethernet hub --> layer 1