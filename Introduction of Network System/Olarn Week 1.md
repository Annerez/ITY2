
Network address --> Broadcast
WAN technologies --> point-to-point

link layer ทำงานอยู่ใน "adaptor"
(เช่น network interface card NIC) หรือบนชิป
- Ethernet card, 802.11 card; Ethernet chipset
- implements link, physical layer


Packet

Header + Payload

Header = Control Information
Payload = Data

application layer packet = message
transport layer packet = segment
network layer packet = datagram
link layer packet = frame

trailer ของ link layer = เก็บ error detection and error correction bit


link layer ทำงานบน NIC เป็นหลัก สำคัญสุด

parity

single bit parity

odd parity --> เลขคี่ --> 1
even prity --> เลขคู่ --> 0

two dimensional bit parity


link แบบ broadcast หรือ shared กับ link แบบ point-to-point


CDMA มี threshold การชนที่ยอมรับได้


Pure (unslotted) ALOHA --> 18%

rdt =  reliable data transfer