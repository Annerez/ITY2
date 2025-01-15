

#ดาวเทียม bandwidth เยอะสุด แต่ latency/delay ก็สูงเช่นกัน

# 1.1 Internet คืออะไร ?
Internet แบบรวบๆ

- hosts / end systems หลายพันล้านอันเชื่อมเข้าด้วยกัน
- มี communication links (ตัวเชื่อมการสื่อสาร)
	- ไฟเบอร์, ทองแดง, วิทยุ, ดาวเทียม
	- transmission rate เป็น bandwidth
- มี packet switches (routers หรือ switches) ในการส่ง data เป็น chunkๆ


- Internet คือ "network ของ networks" อีกที
	- ISPs (Internet Service Providers) ที่เชื่อมต่อกันอีกที
- protocols ควบคุมการ ส่ง, รับ ข้อมูล
	- เช่น TCP, IP, HTTP, Skype, 802.11
- Internet standards
	- RFC: Requests for comments
	- IETF: Internet Engineering Task Force
- Internet ในมุมมองของ service
	- infra ที่ให้บริการต่างๆแก่ application (web, email, game, etc.)
	- ให้ programming interface กับ app



- Protocol คืออะไร
	- format และ order ในการรับส่งข่อมูล ระหว่าง network และ action ที่ทำกับข้อมูลระหว่างการรับ-ส่ง


# 1.2 Network Edge
End Systems, Access Networks, Links

DSL
Access Network
Ethernet
Wireless
Host

- Physical Media
	- bit
		- เผยแผ่ไปตาม transmitter/receiver pairs
	- physical link
		- link 
		- ที่อยู่ระหว่าง transmitter กับ receiver\
	- guided media
		- สัญญาณชัดเจน ไปตามสาย
		- copper, fiber, coax
	- unguided media
		- ไม่มีทิศทางชัดเจน
		- signal ที่แผ่สัญญาณกระจายไปทั่ว เช่นสัญญาณวิทยุ
	- Twisted Pair (TP)
		- มีแบบมี shield (STP) กันฉนวน กับไม่มี shield (UTP)
		- 99% เป็น UTP ไม่จำเป็นต้องมี shield เราไม่ได้ใช้ในที่สัญญาณเยอะ ใช้แค่ LAN
		- ทองแดงหุ้มฉนวน 2 เส้น
			- Cat 5: 100 Mbps, 1Gbps Ethernet
			- Cat 6: 10 Gbps
	
- สายไฟ
	- Coaxial cable
		- ตัวนำทองแดงสองตัวมีตัวกลางร่วมกัน
		- มีแบบหักงอได้กับหักไม่ได้ (copper อื่นงอได้ปกติ)
		- bidirectional (ส่งสองทิศทาง)
		- broadband (source genrated สัญญาณ modulate ไปที่ความถี่อื่น (คนละ band) แล้วส่ง ทำให้ source อื่นส่งข้อมูลเดียวกันได้ โดยที่ไม่ตีกัน)
			- Multiple channels on cble
			- HFC
	- Fiber Optic Cable
		- แก้วใยนำแสง pulse หนึงนับเป็น1 bit
		- Encode ด้วย On-Off Keying (0 คือปิดไฟ 1 เปิดไฟ)
		- โครตเร็วระดับ the flash ในการส่งจุดต่อจุด (e.g. 10's-100's Gbps transmission rate)
		- งอได้เต็มที่
		- Error Rate ต่ำ
			- ทนต่อ electromagnetic noise (คลื่นแม่เหล็กไฟฟ้า, คลื่นวิทยุ)
			- repeaters แต่ละตัวอยู่ห่างกัน
		- แพงกว่า copper (ปัจจุบันไมา่แพงมากละ)
		- เครื่องวัดไฟแพง (ใช้ส่องตาแทน แต่อย่าหาทำ 5555)
	- Radio
	- อากาศเป็น median คลื่นไฟฟ้าเป็นตัวนำ
	- bidirectional
	- ผลกระทบการของสิ่งแวดล้อมในการแผ่สัญญาณ
		- โดน reflect
		- obstructions by object โดน object มาบดบัง
		- interference สัญญาณอื่นมาโดน
	- Radio link types:
		- terrestrial microwave --> up to 45 Mbps channel
		- LAN --> 54 Mbps
		- Wide-Area (e.g. cellular) --> 4G cellular: ~ 10 Mbps
		- Satellite
			- Kbps to 45 Mbps channel (or multiple smaller channels)
			- 270 msec end-end delay
			- geosynchronous versus low altitude

# 1.3 Network Core

 - packet switching message จาก user มาหาร เป็น packages ชิ้นเล้กๆ และส่งให้ ตัวอื่น (share bandwidth)
 -  circuit switching สร้างเส้นทางต้นถึงปลาย แล้วส่ง ไม่หารเป็น package (dedicate bandwidth)

- Routing --> forwarding
- circuit --> มี resource คือ bandwidth, เวลาการใช้งาน ***แบ่ง bandwidth เอา***

โจทย์ มี bandwidth อยู่ 1mbps ต้องมี bandwidth >= 100kbps ถึงจะส่งข้อมูลได้แบบไม่ fail
โดยมีโอกาสที่เครื่องนั้นจะ active อยู่ 10% ของช่วงเวลา

circuit --> รับได้แค่ 10 คน
package switching --> ที่ 35 คนมีเสี่ยงแค่ 0.04% ที่เกิน 10 เครื่องจะ active พร้อมกัน


```
import math

n = 35
cal = 0
for k in range(11):
    cal += (math.factorial(n) / (math.factorial(k) * math.factorial((n - k)))) * (0.1**k) * ((1-0.1)**(35-k))
    print(cal)
    
cal = 1 - cal
print(cal)
```

packet switching --> เหมาะสำหรับ data ที่ไหลเยอะๆ เพราะมี resource sharing และ ง่ายไม่ต้อง call setup

- ต้องการ protocols สำหรับการส่งข้อมูลที่ reliable และ congestion (ความแออัด) control
- How to provide circuit-like behavior?
	- bandwidth guarantee needed for audio/video apps
- Human analogies of reserved resourced (circuit switching) vs on-demand allocation (packet switching)


- End system เชทื่อมอินเตอร์เน็ตผ่าน ISPs (Internet Service Providers)
	- residential, company, university ISPs
- Access ISPs must be interconnected so that two hosts can send packets to each other


![[Pasted image 20240718100622.png]]

# 1.4 Delay, Loss, Throughput in Networks

Performance

1) Reliability: Success rate, Loss rate
2) Throughput (bit per second (bps.), Byte per second (Bps.), Pulse per second (PPS))
3) Bandwidth 
	1) Analog Bandwidth (Hz)
	2)  Digital Bandwidth (bps, Bps, PPS) : Maximum Throughput (ทฤษฎี)
4) Latency, Delay, Time


Loss --> Collision, Noise, Congestion 
- Congestion (ความคับคั่ง)
	- Buffer Overflow  (ข้อมูลล้น buffer)
	- Timeout
![[Pasted image 20240718102158.png]]

![[Pasted image 20240718102706.png]]
![[Pasted image 20240718102659.png]]

Queueing Delay มีความ swing สูงมาก น่ากลัวสุด

![[Pasted image 20240718103254.png]]

End to End Delay --> link delay มาบวกกัน (d donal)
RTT (Routing Time) = End to End ขาไป + End to End ขากลับ = (2 * End to End)

ping คือ echo request ส่งมาต้องส่งกลับ
ping คือ routing time (RTT)
assume ว่า End to End คือ RTT / 2  ยังพอรับได้
แต่เอาไปบอก link delay, d donal ไม่ได้

![[Pasted image 20240718104540.png]]

trace route มันหา router ยังไง???


Throughput อัตราการส่งข้อมูล

![[Pasted image 20240718105117.png]]

![[Pasted image 20240718105128.png]]

![[Pasted image 20240718105722.png]]

link ที่มี bandwidth น้อยที่สุด คือ คอขวด

เอา link ที่มี bandwidth น้อยที่สุดมายึดเป็น throughput


# 1.5 Protocol layers, Service models

![[Pasted image 20240718112512.png]]

	
WiFi = 802.11 not 111
physical media นำทางด้วยไฟฟ้าจะเป็น ทองแดง ไม่ใช่แสง

![[Pasted image 20240718112619.png]]

presentation --> เราจะนำเสนอข้อมูลยังไง

![[Pasted image 20240718112841.png]]

Encapsulation --> การห่อหุ้มข้อมูลให้มันไปถึงปลายทางได้อย่างเรียบร้อย

แต่ละ header คืออะไร มีประโยชน์อย่างไร

Ht --> port number --> บอกว่าต้องใช้ webserver ใด ส่งไปไหน อะไรอย่างไง
- HTTP --> TCP port 80
- HTTPs --> TCP port 443 etc.
Hn --> Logical Address --> IP Address --> กำหนด end point ดูว่าส่งถูกไหม ใครเป็นคนรับ
Hl --> Physical Address --> MAC Address (Ethernet Address) (802.3)

# 1.6 Network Under Attack: Security

DDoS โง่ๆ