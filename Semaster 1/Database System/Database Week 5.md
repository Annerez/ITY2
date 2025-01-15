
# Normalization

รูปแบบบรรทัดฐาน (Normalization)

วัตถุประสงค์หลักก็คือ

1. ลดความซ้ำซ้อนขงข้อมูลที่จัดเก็บในแต่ละ relation
	1. ดเนื้อที่ที่ใช้ในการจัดเก็บข้อมูล
2. ลดปัญหาข้อมูลไม่ถูกต้อง รวมทั้งลดปัญหาที่เกิดจากการเพิ่มปรับปรุง และลบข้อมูล


# ความสัมพันธ์ระหว่าง Attribute

- เมื่อทราบค่าของ Attribute หนึ่งจะทำให้ทราบค่าของ Attribute อื่นๆใน row เดียวกันของ relation ได้

1. Functional Dependency
2. Multivalve Dependency
3. Join Dependency


# Functional Dependency

FD

- การที่ค่าของ Attribute หนึ่งหรือมากกว่าหนึ่ง Attribute ขึ้นไปประกอบกันสามารถระบุค่าของ Attribute อื่นๆใน row เดียวกันได้
- ตัวระบุเรียกว่า Determinant
- ตัวที่ถูกระบุเรียกว่า Dependent
	- Ex. ระบุรหัสนศ. ลงไป จะได้ชื่อ นศ. กลับมา
- อาจจะระบุได้มากกว่าหนึ่ง Attribute
	- Ex. รหัสนศ. --> ชื่อ, นามสกุล, วัน เดือน ปี เกิด
- สามารถมีตัวระบุมากกว่าหนึ่ง Attribute ได้ มาผสมกันเป็นคีย์หลัก 

# Fully Functional Dependency 

(ความสัมพันธ์ระหว่าง Attribute แบบทั้งหมด) (ใช้ครบทุก column ในตาราง)

Determinant มีขนาดเล็กสุด และสามารถระบุค่าของ Attribute อื่นๆที่เป็น Dependent ได้อย่างชัดเจน

- กรณี Determinant มีเพียงหนึ่ง Attribute
- กรณี Determinant มีมากกว่าหนึ่ง Attribute

# Partial Dependency 

(ใช้แค่บาง column ในตาราง)

ต้องเป็นบางส่วนของคีย์หลัก ถึงระบุได้ (ต้องมี primary key 2 column+)


# Transitive Dependency

Attribute อื่นที่ไม่ใช่ Primary Key แต่สามารถระบุค่าของ Attribute อื่นๆใน tuple เดียวกันของ relation ได้


# Normalization

การทำ Normalization สามารถดำเนินงานเป็นขั้นตอนได้ดังนี้

1. ขั้นที่ 1 (First Normal Form: 1NF)
2. ขั้นที่ 2 (Second Normal Form: 1NF)
3. ขั้นที่ 3 (Third Normal Form: 1NF)
4. รูปแบบบอยส์และคอดด์ (Boyce/Codd Normal Form: BCNF)
5. ขั้นที่ 4 (Fourth Normal Form: 4NF)
6. ขั้นที่ 5 (Fifth Normal Form: 5NF)

วัตถุประสงค์

- เพื่อลดความซ้ำซ้อน
- ประหยัดเนื้อที่เก็บข้อมูล
- ลดปัญหาข้อมูลข้อมูลขาดความถูกต้อง (data integrity)
- ทำให้ลดปัญหาที่เกิดจากการปรับปรุง เพิ่มเติม และลบข้อมูล


# 1NF

คุณสมบัติ: ทุก Attribute ในแต่ละ cell มีค่าข้อมูลเพีบงค่าเดียว

เช่น นักศึกษาคนหนึงเรียน 3 วิชา ในช่องวิชาจะใส่ วิชาทีเดียว 3 อันเลยไม่ได้

ต้องทำเป็น 3 row แทน

![image1](https://github.com/Annerez/ITY2S1/blob/main/Database%20System/images/Pasted%20image%2020240812153609.png)
![image2](https://github.com/Annerez/ITY2S1/blob/main/Database%20System/images/Pasted%20image%2020240812153410.png)
# 2NF

คุณสมบัติ: 
- อยู่ในรูป 1NF แล้ว
- ไม่มี Partial Dependency เกิดขึ้น

![image3](https://github.com/Annerez/ITY2S1/blob/main/Database%20System/images/Pasted%20image%2020240812153410.png)

![image4](https://github.com/Annerez/ITY2S1/blob/main/Database%20System/images/Pasted%20image%2020240812153416.png)

# 3NF

คุณสมบัติ
- อยู่ในรูป 2NF แล้ว
- ไม่มี Transitive Dependency เกิดขึ้น

![image5](https://github.com/Annerez/ITY2S1/blob/main/Database%20System/images/Pasted%20image%2020240812153540.png)

# Over Normalization

- การแยกเยอะไป ทำให้หาข้อมูลยาก
