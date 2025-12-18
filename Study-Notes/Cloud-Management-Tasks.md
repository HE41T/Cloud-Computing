# Cloud Management Tasks

## ความหมายของ Cloud Management Tasks

Cloud Management Tasks คือชุดของงานและกระบวนการที่ **Cloud Provider** และ **ผู้ดูแลระบบ (Cloud / System Administrator)** ต้องดำเนินการ เพื่อให้การใช้งานทรัพยากรบน Cloud มีความ **เสถียร ปลอดภัย มีประสิทธิภาพ และคุ้มค่า** มากที่สุด

งานเหล่านี้ครอบคลุมตั้งแต่การสำรองข้อมูล การจัดการการไหลของข้อมูล ความปลอดภัย ไปจนถึงการตรวจสอบและวางแผนการขยายระบบ

---

## 1. Audit System Backups (การตรวจสอบระบบสำรองข้อมูล)

เป็นการตรวจสอบว่า **ระบบ Backup ทำงานถูกต้องและสามารถกู้คืนข้อมูลได้จริง**

### วัตถุประสงค์

* ป้องกันข้อมูลสูญหาย (Data Loss)
* รองรับเหตุการณ์ไม่คาดคิด เช่น ระบบล่ม, ข้อมูลถูกลบ, Cyber Attack

### ตัวอย่าง

* ตรวจสอบว่า VM / Database มีการ Backup ตามรอบเวลาที่กำหนด
* ทดสอบการ Restore ข้อมูลจาก Backup

---

## 2. System's Data Flow Management (การจัดการการไหลของข้อมูลในระบบ)

คือการควบคุมและออกแบบเส้นทางการไหลของข้อมูลระหว่างระบบต่าง ๆ บน Cloud

### วัตถุประสงค์

* ลดความซับซ้อนของระบบ
* เพิ่มประสิทธิภาพการส่งข้อมูล
* ลดความเสี่ยงด้านความปลอดภัย

### ตัวอย่าง

* กำหนด Network Flow ระหว่าง Frontend → Backend → Database
* ใช้ Load Balancer เพื่อกระจายทราฟฟิก

---

## 3. Ensuring No Vendor Lock-in (ป้องกันการผูกติดกับผู้ให้บริการรายเดียว)

Vendor Lock-in คือสถานการณ์ที่ **ย้ายระบบออกจาก Cloud Provider เดิมได้ยากหรือมีค่าใช้จ่ายสูง**

### แนวทางป้องกัน

* ใช้เทคโนโลยีมาตรฐาน เช่น Docker, Kubernetes
* ออกแบบระบบให้รองรับ Multi-Cloud / Hybrid Cloud

### ตัวอย่าง

* ใช้ Kubernetes แทนบริการ Container เฉพาะของ Provider
* ใช้ Database แบบ Open Source

---

## 4. Provider's Security Procedures (ขั้นตอนความปลอดภัยของผู้ให้บริการ)

เป็นการตรวจสอบและปฏิบัติตามมาตรการความปลอดภัยที่ Cloud Provider กำหนดไว้

### ประเด็นสำคัญ

* Identity & Access Management (IAM)
* Network Security (Firewall, Security Group)
* Data Encryption (At-rest / In-transit)

### ตัวอย่าง

* กำหนดสิทธิ์ผู้ใช้งานตาม Principle of Least Privilege
* เปิดใช้งาน MFA (Multi-Factor Authentication)

---

## 5. Monitor Capacity Planning and Scaling Capabilities

(การติดตามการวางแผนทรัพยากรและความสามารถในการขยายระบบ)

คือการตรวจสอบการใช้ทรัพยากร และวางแผนการขยายระบบให้รองรับการใช้งานในอนาคต

### วัตถุประสงค์

* ป้องกันระบบล่มจาก Resource ไม่เพียงพอ
* ควบคุมค่าใช้จ่าย

### ตัวอย่าง

* Monitor CPU / Memory / Disk Usage
* ใช้ Auto Scaling เพิ่ม-ลดจำนวน Instance อัตโนมัติ

---

## 6. Monitor Audit-Log Use (การตรวจสอบการใช้งาน Audit Log)

Audit Log คือบันทึกเหตุการณ์การใช้งานระบบ เช่น ใครทำอะไร เมื่อไหร่

### ความสำคัญ

* ใช้ตรวจสอบเหตุการณ์ผิดปกติ
* รองรับการตรวจสอบด้าน Compliance และ Security

### ตัวอย่าง

* ตรวจสอบ Log การ Login ของผู้ดูแลระบบ
* ตรวจสอบการเปลี่ยนแปลง Configuration

---

## 7. Solution Testing and Validation (การทดสอบและตรวจสอบความถูกต้องของโซลูชัน)

เป็นการทดสอบว่าโซลูชันที่นำขึ้น Cloud **ทำงานได้ถูกต้อง ตรงตามความต้องการ และพร้อมใช้งานจริง**

### ประเภทการทดสอบ

* Functional Testing
* Performance Testing
* Security Testing
* Disaster Recovery Testing

### ตัวอย่าง

* ทดสอบ Load ว่าระบบรองรับผู้ใช้งานพร้อมกันได้กี่คน
* ทดสอบ Failover เมื่อระบบหลักล่ม

---

## สรุปภาพรวม Cloud Management Tasks

Cloud Management Tasks เป็นหัวใจสำคัญของการใช้งาน Cloud อย่างมืออาชีพ ช่วยให้ระบบมีความ

* เสถียร (Reliability)
* ปลอดภัย (Security)
* ขยายตัวได้ง่าย (Scalability)
* ควบคุมต้นทุนได้ดี (Cost Efficiency)

เหมาะสำหรับใช้อ้างอิงในการเรียน วิชา Cloud Computing และการทำงานด้าน Cloud / DevOps
