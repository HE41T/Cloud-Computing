# Infrastructure as a Service (IaaS) – Complete Guide

เอกสารนี้อธิบาย **IaaS (Infrastructure as a Service)** ตั้งแต่พื้นฐานจนถึงการใช้งานจริง โดยปรับให้เหมาะกับผู้เริ่มต้นและการอ้างอิงเชิงเทคนิค

---

## 1. IaaS คืออะไร

**IaaS (Infrastructure as a Service)** คือการให้บริการโครงสร้างพื้นฐานคอมพิวเตอร์ เช่น Server, Storage, Network, Virtualization ผ่าน Cloud

> แนวคิดหลัก: **ไม่ต้องซื้อ Hardware เอง แต่ใช้บริการตามต้องการ**

### บทบาทของแต่ละฝ่าย

**ผู้ใช้งาน (Customer)**

* Provision VM, Storage, Network
* ติดตั้ง OS และ Software
* จ่ายตามการใช้งานจริง

**ผู้ให้บริการ (Provider)**

* จัดหาและดูแล Hardware
* จัดการ Virtualization Layer
* ดูแล Availability และ Security

---

## 2. ปัญหาของ Infrastructure แบบเดิม

### แบบ Traditional

* ต้องซื้อ Server, Storage, Network
* ต้องมีทีม Data Center ดูแล
* Scale ยากและใช้เวลา
* Maintenance บำรุงรักษายาก

### ปัญหาที่พบบ่อย

* CAPEX สูง
* Provision ช้า (เป็นสัปดาห์หรือเดือน)
* อัพเกรด Hardware ต้องหยุดระบบบางส่วน

---

## 3. IaaS แก้ปัญหาอย่างไร

IaaS เปลี่ยนแนวคิดจาก:

> **Physical Infrastructure → Virtualized / Cloud Infrastructure**

### ผลลัพธ์

* Provision Server, Storage, Network ได้ทันที
* Scale ขึ้นลงตามต้องการ
* จัดการและบริหารจากศูนย์กลาง

### เปรียบเทียบแบบชีวิตจริง

* ❌ แบบเดิม: ซื้อคอมพิวเตอร์ตั้ง Data Center เอง
* ✅ IaaS: กดสร้าง VM บน Cloud ใช้ได้ทันที จ่ายตามชั่วโมง

---

## 4. แนวคิดหลักของ IaaS

### 4.1 Virtualization

* Hardware ถูกแยกเป็น Virtual Machines (VM)
* สามารถสร้าง / ลบ / ย้าย VM ได้ง่าย

### 4.2 On-Demand Provisioning

* สร้าง Server, Storage, Network ตามต้องการ
* เพิ่มหรือลดขนาดทรัพยากรได้ทันที

### 4.3 Pay-as-you-go

* จ่ายตามปริมาณการใช้จริง
* ลดค่าใช้จ่ายที่ไม่จำเป็น

---

## 5. องค์ประกอบของ IaaS

```
[ User / Admin ]
       ↓
   IaaS Portal / API
       ↓
  Virtualization Layer
       ↓
[ Compute | Storage | Network ]
       ↓
     Physical Data Center
```

### องค์ประกอบหลัก

* Compute (VM, CPU, RAM)
* Storage (Block, Object, File)
* Network (VPC, VPN, Load Balancer)
* Management / API

---

## 6. IaaS ทำงานอย่างไร (Flow)

1. ผู้ใช้สมัครใช้ IaaS Provider
2. สร้าง VM, Storage, Network ผ่าน Portal หรือ API
3. ติดตั้ง OS และ Software บน VM
4. Config Network, Security, Firewall
5. Traffic และ Resource ถูกจัดการโดย Provider

---

## 7. บริการที่อยู่ภายใต้ IaaS

### Compute

* Virtual Machine (VM)
* Container (บางกรณี)

### Storage

* Block Storage
* Object Storage
* File Storage

### Network

* Virtual Network / VPC
* VPN, Load Balancer, NAT
* Security Groups / Firewall

### Management

* Monitoring, Logging
* Backup / Snapshot
* Automation / API

---

## 8. IaaS Benefits (ข้อดี)

### 8.1 ลดต้นทุน

* ลดการลงทุน Hardware เริ่มต้น
* เปลี่ยนเป็น OPEX จ่ายตามการใช้งาน

### 8.2 ความเร็วและยืดหยุ่น

* Provision VM และ Storage ได้ทันที
* Scale ขึ้นลงตามความต้องการ

### 8.3 การบริหารและความปลอดภัย

* Management รวมศูนย์
* Security และ Backup ทำได้ง่าย
* รองรับ Disaster Recovery

---

## 9. Use Case ของ IaaS

* Web Hosting / Application Hosting
* Development / Test Environment
* Big Data / Analytics
* Disaster Recovery / Backup
* Hybrid Cloud Deployment

---

## 10. IaaS เทียบกับ PaaS / SaaS

| ประเภท | ผู้ควบคุม                     | ตัวอย่าง                                     |
| ------ | ----------------------------- | -------------------------------------------- |
| IaaS   | OS / Application / Middleware | AWS EC2, Azure VM, GCP Compute Engine        |
| PaaS   | Application / Middleware      | Heroku, Google App Engine, Azure App Service |
| SaaS   | แค่ใช้งาน Application         | Gmail, Office 365, Salesforce                |

> IaaS จะให้ผู้ใช้ควบคุม Infrastructure มากที่สุด

---

## 11. ตัวอย่าง IaaS Provider

| ประเภท     | ตัวอย่าง                |
| ---------- | ----------------------- |
| Global     | AWS, Azure, GCP         |
| Enterprise | IBM Cloud, Oracle Cloud |
| Regional   | DigitalOcean, Linode    |

---

## 12. ข้อจำกัดของ IaaS

* ต้องมีความรู้ด้าน OS / Middleware
* ความรับผิดชอบบางส่วนยังอยู่กับผู้ใช้
* Performance ขึ้นกับ Resource และ Provider

---

## 13. สรุปภาพรวม

> **IaaS = การให้บริการ Infrastructure แบบ Virtualized บน Cloud ที่ผู้ใช้สามารถ Provision, Scale และบริหารจัดการเองได้**

จำ 3 คำสำคัญ:

* Virtualized
* On-Demand
* Pay-as-you-go

---

*เอกสารนี้สามารถใช้เป็น Lecture Note, Exam Summary และ Technical Overview สำหรับ IaaS ได้*
