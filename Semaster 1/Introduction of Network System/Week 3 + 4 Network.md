

TCP Service:

- flow control --> ตควบคุมขนาดของ data transfer ไม่ให้ใหญ่ไป

UDP Service:


# 2.2 Web and HTTP

HTTP -> Hypertext Transfer Protocol
![[Pasted image 20240725102209.png]]

uses TCP:


HTML is stateless

non-persistent HTTP
- เปิดปิดๆ
- ส่งแค่ object เดียว ผ่าน  TCP connection แล้วค่อยปิด connection
- ส่งหลาย object ก็ต้องทำหลายรอบ
- http ปัจจุบันใช้ non persistent
- multithread ดีกว่า (parallel request)

persistent HTTP
- object หลายอันส่งผ่าน TCP connectionรอบเดียว
- ทำครั้งเดียว


![[Pasted image 20240725104539.png]]

![[Pasted image 20240725104544.png]]


Cookie เก็บตอน user เข้าครั้งแรก ไว้เก็บข้อมูล ทำ authentication, shopping cart, user data ฯลฯ

Cache เก็บข้อมูลเว็บไว้ทำให้เรียกดูเว็บได้ไวขึ้นในครั้งถัดไป

![[Pasted image 20240725111824.png]]

![[Pasted image 20240725111830.png]]


# 2.3 Electronic Mail


Electronic Mail มี 3 components หลักๆ

- user agents
- mail servers
- simple mail transfer protocol: SMTP

- User Agent
	- aka "mail reader"
	- composing, editing, reading mail messages
	- Outlook, Thunderbird, iPhone Mail Client
	- outgoing, incoming message stored on a server
- ![[Pasted image 20240725111345.png]]

- Mail servers
	- mailbox contains incoming message for user
	- message queue of outgoing mail message
	- SMTP protocol between mail server to send email message 
		- cilent send server recieved

- SMTP [RFC 2821]


# 2.4 DNS


![[Pasted image 20240725111950.png]]


local DNS server ดูแค่คนในองค์กร

ถ้าใช้ recursive root DNS มันดูทั้งโลก เกิดคอขวด delay ได้


# 2.5 Peer to Peer Application



![[Pasted image 20240725114534.png]]

![[Pasted image 20240725114548.png]]

P2P scalable as it's not increasing as N user increase

NF(us + Sigma ui)

= lim N-> infinity (NF / us + Nu) -> d(NF)/df / d(us+Nu) / dN = F/u



Midterm
1. Circuit + Packet Switicng
2. Proxy (  เขียนเป็นตัวเลข )
3. Scalability