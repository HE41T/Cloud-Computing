# Cloud Computing Planning – Complete Guide

เอกสารนี้อธิบาย **Cloud Computing Planning** ตั้งแต่แนวคิดพื้นฐานจนถึงการวางแผนใช้งานจริง เหมาะสำหรับผู้เริ่มต้น ผู้ดูแลระบบ และการอ้างอิงเชิงเทคนิค

---

## 1. Cloud Computing Planning คืออะไร

**Cloud Computing Planning** คือกระบวนการวางแผนก่อนย้ายหรือเริ่มใช้งาน Cloud เพื่อให้ระบบมี **ประสิทธิภาพ ปลอดภัย คุ้มค่า และสอดคล้องกับธุรกิจ**

> แนวคิดหลัก: *ไม่ใช่แค่ย้ายขึ้น Cloud แต่ต้องย้ายอย่างถูกวิธี*

---

## 2. เป้าหมายของการวางแผน Cloud

* รองรับ Business Requirement
* ควบคุมต้นทุน
* เพิ่ม Performance และ Availability
* ลดความเสี่ยงด้าน Security และ Compliance
* รองรับการ Scale ในอนาคต

---

## 3. ขั้นตอนการวางแผน Cloud Computing

<img width="560" height="441" alt="image" src="https://github.com/user-attachments/assets/6566c1b9-72d0-440b-a307-fab344fa9fed" />

### 3.1 Assess Current Environment (Assessment)

ประเมินระบบปัจจุบัน (On-Premise / Legacy)

* Application ไหนใช้งานอยู่
* Dependency ระหว่างระบบ
* Workload Pattern (Peak / Normal)
* Security & Compliance Requirement

> Output: Application & Infrastructure Inventory

---

### 3.2 Define Business & Technical Requirements

* ต้องการลดต้นทุน หรือเพิ่มความเร็วในการ Deploy
* SLA / Availability ที่ต้องการ
* Security Level (Data Sensitivity)
* Compliance (PDPA, GDPR, ISO)

---

### 3.3 Choose Cloud Deployment Model

| Model           | เหมาะกับ                       |
| --------------- | ------------------------------ |
| Public Cloud    | Workload ทั่วไป, Dev/Test      |
| Private Cloud   | ข้อมูลสำคัญ, Control สูง       |
| Hybrid Cloud    | ค่อย ๆ ย้าย, มี On-Premise     |
| Community Cloud | องค์กรที่มี Compliance ร่วมกัน |

---

### 3.4 Choose Cloud Service Model

| Service Model | ใช้เมื่อ                      |
| ------------- | ----------------------------- |
| IaaS          | ต้องการ Control OS / Network  |
| PaaS          | เน้น Dev เร็ว ไม่ดูแล Infra   |
| SaaS          | ใช้ Application สำเร็จรูป     |
| NaaS          | ต้องการ Network แบบ On-Demand |

---

### 3.5 Architecture Design

ออกแบบโครงสร้างระบบบน Cloud

* Network (VPC, Subnet, Firewall)
* Compute (VM, Container)
* Storage (Block, Object, Backup)
* Security (IAM, Encryption)
* DR & Backup Strategy

```
User → Internet → Cloud Network → Application → Database
```

---

### 3.6 Security & Compliance Planning

* Identity & Access Management (IAM)
* Data Encryption (At Rest / In Transit)
* Logging & Monitoring
* Compliance Policy & Audit

> Security ต้องวางแผนตั้งแต่ต้น ไม่ใช่เพิ่มทีหลัง

---

### 3.7 Cost Planning & Optimization

* Estimate Cost (Compute, Storage, Network)
* เลือก Pricing Model (On-Demand, Reserved)
* Budget Alert & Cost Monitoring
* Right-sizing Resource

---

### 3.8 Migration Strategy

เลือกกลยุทธ์การย้ายระบบ (6R Model)

| Strategy   | Description              |
| ---------- | ------------------------ |
| Rehost     | Lift & Shift             |
| Replatform | ปรับเล็กน้อย             |
| Refactor   | แก้โค้ดให้เหมาะกับ Cloud |
| Repurchase | เปลี่ยนเป็น SaaS         |
| Retire     | ยกเลิกระบบ               |
| Retain     | ใช้ On-Premise ต่อ       |

---

### 3.9 Testing & Validation

* Performance Test
* Security Test
* Failover / DR Test
* User Acceptance Test (UAT)

---

### 3.10 Operation & Governance

* Monitoring & Alerting
* Backup & DR Operation
* Access Control & Policy Enforcement
* Change Management

---

## 4. Cloud Planning Best Practices

* เริ่มจาก Small Workload ก่อน
* ใช้ Automation (IaC)
* ออกแบบ Security แบบ Zero Trust
* Monitor Cost อย่างสม่ำเสมอ
* Document Architecture และ Process

---

## 5. Common Mistakes in Cloud Planning

* ย้ายขึ้น Cloud โดยไม่ประเมินระบบเดิม
* ไม่วางแผนค่าใช้จ่าย
* Security เป็นเรื่องรอง
* เลือก Service Model ไม่เหมาะกับ Workload

---

## 6. Summary

> **Cloud Computing Planning คือกุญแจสำคัญของการใช้งาน Cloud อย่างประสบความสำเร็จ**

จำ 4 คำนี้:

* Assess
* Design
* Secure
* Optimize

---

*เอกสารนี้เหมาะสำหรับ Lecture Note, Exam Summary และ Technical Overview ของ Cloud Computing Planning*
