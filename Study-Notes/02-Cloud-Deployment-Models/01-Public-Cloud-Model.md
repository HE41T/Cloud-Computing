# Public Cloud Model – Complete Guide

เอกสารนี้อธิบาย **Public Cloud Model** ตั้งแต่พื้นฐานจนถึงการใช้งานจริง เหมาะสำหรับผู้เริ่มต้นและการอ้างอิงเชิงเทคนิค

---

## 1. Public Cloud คืออะไร

**Public Cloud** คือรูปแบบ Cloud Computing ที่ผู้ให้บริการ (Provider) ให้บริการ Infrastructure, Platform หรือ Software ผ่าน Internet ให้ผู้ใช้หลายราย (Multi-Tenant) ใช้งานร่วมกัน

> แนวคิดหลัก: **แชร์ Resource บน Cloud โดยไม่ต้องลงทุน Infrastructure เอง**

### ตัวอย่าง Resource ที่ให้บริการ

* Compute: VM, Container
* Storage: Block, Object, File
* Network: VPC, VPN, Load Balancer
* Platform: Runtime, Middleware, Database
* Application: SaaS, Productivity Tools

<img width="560" height="456" alt="image" src="https://github.com/user-attachments/assets/c4fe36b3-ec3d-459d-8d6d-ad28f9605f56" />

---

## 2. ลักษณะของ Public Cloud

* **Hosted by Provider:** Provider ดูแล Hardware และ Data Center
* **Multi-Tenant:** ผู้ใช้หลายองค์กรแชร์ Resource เดียวกันแต่ข้อมูลแยกกัน
* **On-Demand:** Provision Resource ตามความต้องการ
* **Pay-as-you-go:** จ่ายตามการใช้งานจริง
* **Accessible Anywhere:** ใช้งานได้จาก Internet

---

## 3. ประเภทของบริการ Public Cloud

| Cloud Model | บริการหลัก     | ตัวอย่าง                                     |
| ----------- | -------------- | -------------------------------------------- |
| IaaS        | Infrastructure | AWS EC2, Azure VM, GCP Compute Engine        |
| PaaS        | Platform       | Heroku, Google App Engine, Azure App Service |
| SaaS        | Application    | Gmail, Office 365, Salesforce                |

---

## 4. จุดเด่นของ Public Cloud

### 4.1 ลดต้นทุน

* ไม่ต้องลงทุน Hardware เอง
* จ่ายตามการใช้งาน (OPEX)

### 4.2 ความยืดหยุ่นและ Scaling

* เพิ่ม / ลด Resource ได้ทันที
* รองรับ Business Growth และ Peak Traffic

### 4.3 ความเร็วในการ Provision

* Deploy VM, Application, Database ได้ทันที
* ลดเวลาตั้งค่า Environment

### 4.4 การบริหารและความปลอดภัย

* Provider ดูแล Security, Backup, Disaster Recovery
* Monitoring และ Maintenance รวมศูนย์

---

## 5. ข้อจำกัดของ Public Cloud

* **Security / Compliance:** ต้องมั่นใจ Provider ได้มาตรฐาน
* **Performance:** อาจขึ้นกับ Internet Connection และ Resource Shared
* **Customization:** ปรับแต่ง Infrastructure ต่ำกว่าการใช้ Private Cloud
* **Vendor Lock-in:** ขึ้นกับ Provider

---

## 6. Use Case ของ Public Cloud

* Hosting Web Application และ Mobile Backend
* Development / Test Environment
* Big Data / Analytics
* SaaS Applications
* Disaster Recovery / Backup

---

## 7. Public Cloud vs Private Cloud vs Hybrid Cloud

| ประเด็น     | Public Cloud  | Private Cloud  | Hybrid Cloud       |
| ----------- | ------------- | -------------- | ------------------ |
| Ownership   | Provider      | Organization   | Mix                |
| Resource    | Shared        | Dedicated      | Shared + Dedicated |
| Cost        | Lower upfront | Higher upfront | Medium             |
| Control     | Low           | High           | Medium             |
| Scalability | High          | Medium         | High               |

> Hybrid Cloud = รวมข้อดี Public + Private สำหรับบาง Workload

---

## 8. ตัวอย่าง Public Cloud Provider

| Provider              | ประเภทบริการ   | จุดเด่น                                              |
| --------------------- | -------------- | ---------------------------------------------------- |
| AWS                   | IaaS/PaaS/SaaS | Global, ครอบคลุมทุก Layer, Ecosystem ใหญ่            |
| Microsoft Azure       | IaaS/PaaS/SaaS | Integration กับ Microsoft Products, Enterprise Focus |
| Google Cloud Platform | IaaS/PaaS/SaaS | AI/ML, Analytics, High Performance Networking        |
| IBM Cloud             | IaaS/PaaS/SaaS | Enterprise, Hybrid Integration                       |

---

## 9. สรุปภาพรวม

> **Public Cloud = การใช้ Resource บน Cloud ที่แชร์กับผู้ใช้หลายรายโดย Provider ดูแล Infrastructure, Platform และ Software ให้**

จำ 3 คำสำคัญ:

* Multi-Tenant
* On-Demand
* Pay-as-you-go

---

*เอกสารนี้เหมาะสำหรับ Lecture Note, Exam Summary และ Technical Overview ของ Public Cloud*
