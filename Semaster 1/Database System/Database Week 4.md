
# Entity

- บุคคลกับเหตุการณ์
- Strong Entity
	- เกิดขึ้นได้ด้วยตัวเอง ไม่เกี่ยวกับ entity ตัวอื่น มีคุณสมบัติ identity ได้ด้วยตัวเอง
- Weak Entity 
	- การคงอยู่ ขึ้นอยู่กับ Strong Entity อื่น  


# Attribute

- ข้อมูลที่แสดงคุณสมบัติหรือคุณลักษณะของ Entity หรือ ความสัมพันธ์
- Simple Attribute
	- ไม่สามารถแยกย่อยลงไปได้อีก
- Composite Attribute
	- สามารถแยกย่อยลงไปได้อีก

- Key Attribute
	-  attribute หรือกลุ่ม attribute ที่มีค่าข้อมูลในแต่ละสมาชิกของ Entity ไม่ซ้ำกัน
	- Primary Key

- Derived Attribute
	- ค่าข้อมูลที่ได้จากการนำ ค่าของข้อมูลใน Attribute อื่นทำการคำนวณ 
	- เช่นนำ วันเดือนปีเกิดมา คำนวณอายุ

# ความสัมพันธ์ Relationship

- หมายถึง Entity ที่แสดงความสัมธ์ระหว่าง 2 Entity (ตาราง) ขึ้นไป
- ความสัมพันธ์ระหว่าง Entity ใดๆ อาจมี relation มากกว่า 1 ได้
- Entity ที่เกี่ยวกับความสัมพันธ์ เรียกว่า Participant

- Total Participation
	เป็นความสัมพันธ์ที่ทุกสมาชิกใน Entity หนึ่งมีความสัมพันธ์กับข้อมูลในอีก Entity หนึ่ง

- Partial Participation
	เป็นความสัมพันธ์ที่บางสมาชิกใน Entity หนึ่งเท่านั้นจะข้อมูลใน Attribute หนึ่งที่มีความสัมพันฑ์ธ์บข้อมูลในอีกหนึ่ง Entity


- One to One Relationship
- One to Many Relationship
- Many to Many Relationship


- Existence Dependency 
	- ความสัมพันธ์ระหว่าง Entity ปกติและอ่อนแอ

- ความสัมพันธ์แบบ Recursive
	- ความสัมพันธ์ที่เกิดจาก Entity เพียง Entity เดียว
- Composite Entity
	- เป็น Entity ที่ถูกสร้างขึ้นมาเพื่อใช้ในการแปลงวความสัมพันธ์ระหว่าง Entity แบบกลุ่มต่อกลุ่ม ให้เป็นความสัมพันธ์แบบหนึ่งต่อกลุ่ม
	- M:M ไม่สามารถทำได้ด้วยตัวเอง ต้องพึ่ง Composite

- ความสัมพันธ์แบบ Binary
	- 2 Entity
- ความสัมพันธ์แบบ N-ary
	- สอง Entity ขึ้นไป


Chen
\
Crow's Foot


Week ต่อไปเขาให้ออกแบบ ER-Diagram ละ ไม่มีสไลด์

