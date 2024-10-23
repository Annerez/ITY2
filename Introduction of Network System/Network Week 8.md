
TCP Connection Management, Congestion, QUIC


# TCP Connection Management

TCP -> Connection Oriented Protocol
UDP -> Connectionless -> ผู้ส่งพร้อมส่ง สามารถส่งได้เลย

Phase 1 

A: Connection establish (Initial)
B: ทำให้ทั้งสองฝ่ายพร้อมรับส่งข้อมูล

Phase 2

A: Data Transmission (Sequence Number, ขนาด Buffer ของผู้รับ / Window, HTTP version)
B: ARQ (Stop-and-wait, Go-back-N, Selective-Repeat)

Phase 3

A: Connection Terminate
B: คืน Resource ให้ระบบ


# Connection Establishment

3 Ways Handshake

- A request connection to B sending SYN
	- (SYN มีแต่ header)

- B send SYN / ACK back

- A send ACK to B\


A สามารถส่งข้อมูลให้ ได้แล้ว

B ส่ง A:

A SYN B
B ACK A
B SYN Request B-> A
A ACK B

End Phase 1


# 3 Ways Handshake with Sequence Number (SN), ACK Number (AN)

A สุ่ม 10
B สุ่ม 99

A SYN (SN = 10, AN = NULL) B

B SYN / ACK (SN = 99, AN = 11) A

A ACK (AN = 100, SN = 11) 

SN = เลขของ byte sequence ที่เราจะส่ง
AN = บอก ACK ไปว่าต้องส่ง SN ตำแหน่งไหนมาต่อ

# Connection Terminate

A -> B Phase 2 Finished


B FIN A ปิด B->A

A ACK B

A FIN B

B ACK A คืน resource

ถ้าปิดฝั่งเดียวเรียก half-closed แต่ปกติปิดหมด




เราจะต้องคำนวณและ update ค่า RTO

อยู่ใกล้ RTO ไม่ต้องเยอะ
อยู่ไกล RTO เยอะตาม


Round Trip Time Estimation

Original TCP RTT estimator
- RTT estimated as a moving average
- new_rtt = a(old_rtt) + (1 - a)(new_sample)
- Recommended a: 0.8-0.9 (0.875 for most TCP)

RTO = 2 * new_rtt (i.e. TCP is conservative)


RTT Sample Ambiguity

Karn's Algorithm
ไม่สนใจ sample ที่มีการ retransmitted

# Congestion


# QUIC

