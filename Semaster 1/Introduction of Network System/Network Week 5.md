

tracert

ส่ง ICMP ไปยัง IP ปปลายทาง แล้วส่ง TTL ไป

TTL = จำนวน hop, router ที่จะกำหนดให้ packet ผ่านได้ก่อนโดน drop
TTL ป้องกันการติดลูป


ข้อมูลที่ใช้encapsulateใน transport port, network ip address, link mc

reverse, forward proxy

url http host name และก็ที่อยู่ มันรู้ได้ไงว่า

Dst. Port Number
Dst. IP Address
Dst. MAC Address

DNS give IP address
ARP give MAC address (ถ้าอยู่คนละ subnet ต้องผ่าน gateway)

ARP gateway ก่อน แล้วเอา mac address ของ gateway  มาเป็น header ของ link layer


Forward proxy อยู่ใกล้ฝั่ง client เวลาขอหน้าเว็ป client จะดู proxy ก่อนถ้ามีหน้าเว็ปใน cache จะเอามาให้เลย

Reverse Proxy จะอยู่ใกล้ฝั่ง Server เวลา request จะไป reverse proxy ก่อนและค่อยไป Server เพื่อช่วยทำ load balancing กรณีมี server หลายตัว