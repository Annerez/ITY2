
1. Network Layer's responsibility
	- ส่งข้อมูลจาก source ไปถึง Destination ที่ถูกต้อง
	- หาเส้นทางที่จะใช้ส่งข้อมูลไป Destination ที่ต้องการ โดยจะเลือกใช้เส้นทางที่ดีที่สุด ในเวลานั้น --> Active - Passive (ใช้แค่อันเดียว ถ้ามีปัญหาเอา backup มาใช้)
	- 1 เส้นทางทำงานไม่ได้ ต้องมีมากกว่า 1 เส้น (ทำได้ แต่ไม่พอ)
	- Highly Available (พร้อมใช้งานมากๆ)


	- Network Layer Protocol -> IP (internet protocol) -> Best effort service (ถ้าหาได้จะหาเส้นทางดีสุด ถ้าไม่ได้จะ feedback กลับ )
	- IP ไม่ได้ส่ง feedback กลับ
	- ICMP เป็นตัวตรวจสอบปัยหาของ network layer ว่า error  มันเกิดที่อะไร (ping, trace roue ให้ ICMP หมด)


	- ข้อมูล layer 3 เรียกว่า packet, datagram

- Router อ่าน IP header แล้วตัดสินใจได้ไงว่าจะต้อง forward ไปไหน
	- ทำ routing หาเส้นทางที่ดีที่สุด, router แต่ละตัวจะมี routing table


Summary: Network Layer มีสอง function หลักๆ
1. Forwarding --> Data Plane --> Local Process
2. Routing --> Control Plane --> Global Process
Control Plane จะต้องคุยกัน เป็น Distribute Process

SDN Controller ใช้แทนเป็น control plane ได้เลย คอยควบคุม router ที่เหลือเป็น data plane


การจะ Forwarding ได้อย่างถูกต้อง

- มีการ assign ค่าตำแหน่ง ( address ) ของ host ใน Network ที่มี Address ไม่ซ้ำซ้อนกัน (unique) กับ host อื่น 
- (ต้องมี address ที่ unique) จึงต้องมี IP address


# IPv4 Addressing

- public IP address (เชื่อมเน็ตได้)
- private IP address --> คุยกันใน Network ที่อยู่ในการดูแลของหน่วยงานเดียวกัน



การส่งข้อมูลข้าม Network ใช้อุปกรณ์ L3 9Router, L3 Switch)

ถ้าจะคุยใน network เดียวกันใช้ อุปกรณ์ L2 (Switch)



# IPv4 จะแบ่ง address เป็น 2 ส่วน


Network bits + Host bits

IP address อะไรที่มี network bits เหมือนกัน แสดงว่าเป็น IP address ที่อยู่ network เดียวกัน

- ในแต่ละ IP address, เราจะต้องรู้ว่า IP นี้มี Network bits กี่บิต ( host bits = 32 - network bits )


# Classful IP address

ดูที่ octet  แรก 

0 - 127.x.x.x --> Class A; Network bits = 8
128 - 191.x.x.x --> Class B; Network bits = 16
192 - 223.x.x.x --> Class C; Network bits = 24

Class A = 0.x.x.x --> 01111111.x.x.x
Class B = 10.x.x.x --> 10111111.x.x.x
Class C = 110.x.x.x --> 11011111.x.x.x

# Classless IP address

ต้องมีตัวบอกจำนวน bits ของ IP address

-> subnet mask

- มีขนาด 32 bits
- 1 --> Network bits
- 0 --> Host bits

11111111.11111111.00000000.00000000 --> Network 16 bits, Host 16 bits --> 255.255.0.0

![[Pasted image 20241022234902.png]]


Unicast -- ส่งไปแล้วให้ทุกคนแต่ถึง Destination เดียว
Broadcast -- ส่งให้ทุกคนใน subnet


Network address --> Host bits ทุกตัวเป็น 0 หมด
Broadcast address --> Host bits ทุกตัวเป็น 1 หมด


![[Pasted image 20241023135622.png]]

![[Pasted image 20241023140654.png]]

![[Pasted image 20241023163711.png]]

![[Pasted image 20241023164603.png]]

Default Gateway --> เส้นทาง default ในการเดินทางไปยัง router

![[Pasted image 20241023171058.png]]

ถ้ามี subnet เยอะกว่าจะอยู่ข้างบน และเช็คข้างบนก่อน (subnet จะอยู่ข้างบนเสมอ)