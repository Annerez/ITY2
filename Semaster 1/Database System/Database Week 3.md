

Key

- เอกลักษณ์ของแถวในความสัมพันธ์
- ทำให้เข้าถึงฐานข้อมูลได้รวดเร็ว
- แยกแยะ ข้อมูลในฐานข้อมูลได้ถูกต้อง

# Primary Key

- อ้างถึง Entity ในฐานข้อมูล
- ไม่ซ้ำ, ไม่ว่าง
- เข้าถึงข้อมูลได้รวดเร็ว

# Secondary Key

- ไม่จำเป็นต้องเป็น เอกลักษณ์
- ใช้ในการหาความสัมพันธ์ของข้อมูลมากกว่า 1 record
- ได้ผลลัพธ์มากกว่า 1 record ได้

# Foreign Key

- ตัวเชื่อมต่อความสัมพันธ์

# Algebra Rule

 - การใช้งานขั้นพื้นฐาน
	 - Selection
	 - Projection
	 - Cross Product
	 - Set Difference
	 - Union

 - การใช้งานขั้นสูง
	 - join
	 - intersection, division

# ประเภทการกระทำ

- Unary Operators 
	- ความสัมพันธ์เดียว

- Binary Operators 
	- ต้องการ 2 ความสัมพันธ์


Union, Intersect, Difference คงไม่ต้องเขียน...

# Cartesian Product
- มี 2 ตาราง
- ทำให้ 2 ตาราง เชื่อมกันทุกตัว
- งงอยู่ไป search google เอา

# Join

- รวมข้อมูลหลายความสัมพันธ์ ตามเงื่อนไข
- Theta-Join  คือ การทำ cartesian product โดยมีเงื่อนไขไปเปรียบเทียบ
- Equi-Join คือ การ join แบบมีเงื่อนไข "=" เท่านั้น เป็นส่วนนึงของ Theta Join
- Natural-Join คือ Equi-join ที่ join ทุก column ที่ซ้ำกัน จะถูกขจัดออกไป # Database ส่วนใหญ่เป็นงี้


# ประเภทของเงื่อนไข Constraints

- Key constraints 2 รูปแบบ คือ
	- primary key จะไม่เป็น null และเป็น index ในการเรียงลำดับเสทอ
	- Unique เป็น key เอกลักษณ์

- Referential Integrity
	- เป็นการอ้างอิงข้อมูลจากความสัมพันธ์อื่น
	- attribute ที่ถูกอ้างอิงเรียกว่า Foreign Key
	- attribute ที่ถูกอ้างอิงมา จะต้องเป็น primary key เสมอ

