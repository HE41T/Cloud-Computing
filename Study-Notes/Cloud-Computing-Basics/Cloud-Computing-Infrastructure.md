# Cloud Computing Infrastructure – Complete & In-Depth Guide

เอกสารนี้อธิบาย **Cloud Computing Infrastructure** แบบละเอียด ตั้งแต่โครงสร้างพื้นฐานจริง (Physical) ไปจนถึง Infrastructure เสมือน (Virtual / Software-defined) เพื่อให้เข้าใจว่า Cloud ทำงานได้อย่างไรในระดับลึก

---

## 1. Cloud Computing Infrastructure คืออะไร

**Cloud Computing Infrastructure** คือชุดของทรัพยากรพื้นฐานที่ทำให้ Cloud สามารถให้บริการได้ ได้แก่

* Compute
* Storage
* Network
* Virtualization
* Data Center Facilities

> Infrastructure คือ “ฐานราก” ของ Cloud ถ้าฐานไม่ดี Cloud จะไม่เสถียร ไม่ปลอดภัย และ Scale ไม่ได้

---

## 2. Physical Infrastructure (ชั้นล่างสุด)

### 2.1 Data Center

Data Center คือสถานที่ที่เก็บ Hardware ทั้งหมดของ Cloud

**องค์ประกอบหลัก**

* อาคารและพื้นที่
* ระบบไฟฟ้า (UPS, Generator)
* ระบบระบายความร้อน
* ระบบป้องกันไฟไหม้
* Physical Security

> Cloud ระดับโลกใช้ Data Center หลายแห่งเพื่อความทนทาน (Resilience)

---

### 2.2 Physical Servers

* CPU, RAM
* Disk (SSD / HDD)
* Network Interface Card (NIC)

**ลักษณะสำคัญ**

* ออกแบบเพื่อทำงาน 24/7
* รองรับ Virtualization และ Workload หนัก

---

### 2.3 Physical Storage Systems

* SAN (Storage Area Network)
* NAS (Network Attached Storage)

ใช้เป็นฐานให้ Block / File / Object Storage บน Cloud

---

### 2.4 Physical Network

* Core Switch
* Router
* Firewall
* Load Balancer

> เป็นโครงข่ายหลักที่เชื่อม Server และ Data Center เข้าด้วยกัน

---

## 3. Virtualization Infrastructure

Virtualization คือหัวใจที่เปลี่ยน Data Center ธรรมดาให้กลายเป็น Cloud

---

### 3.1 Compute Virtualization

* Hypervisor (VMware ESXi, KVM, Hyper-V)
* สร้าง Virtual Machine (VM)

**ประโยชน์**

* แยกผู้ใช้ (Isolation)
* ใช้ Hardware ร่วมกัน
* Provision เร็ว

---

### 3.2 Storage Virtualization

* รวม Disk หลายชุดให้เป็น Pool เดียว
* จัดสรร Storage แบบ Dynamic

> ผู้ใช้ไม่ต้องรู้ว่า Disk จริงอยู่ที่ไหน

---

### 3.3 Network Virtualization

* Virtual Network
* Virtual Switch
* Virtual Firewall

ตัวอย่าง: VPC, Subnet, Security Group

---

## 4. Software-Defined Infrastructure (SDI)

Cloud Infrastructure สมัยใหม่ถูกควบคุมด้วย Software

### 4.1 Software-Defined Compute

* VM
* Container

### 4.2 Software-Defined Storage (SDS)

* Ceph
* vSAN

### 4.3 Software-Defined Networking (SDN)

* ควบคุม Network ด้วย Policy
* แยก Control Plane / Data Plane

> SDI ทำให้ Infrastructure กลายเป็น Code

---

## 5. Compute Infrastructure

### 5.1 Virtual Machines

* เหมาะกับ Legacy Application
* Control OS ได้เต็มที่

### 5.2 Containers

* เบา
* Deploy เร็ว
* เหมาะกับ Cloud-Native

### 5.3 Serverless Infrastructure

* ไม่ต้องดูแล Server
* Scale อัตโนมัติ

---

## 6. Storage Infrastructure

### 6.1 Block Storage

* ใช้กับ VM / Database

### 6.2 Object Storage

* Scale สูงมาก
* ใช้กับ Backup, Big Data

### 6.3 File Storage

* ใช้ร่วมกันหลายระบบ

---

## 7. Network Infrastructure

### 7.1 Cloud Network Components

* Virtual Network (VPC / VNet)
* Subnet
* Routing Table
* Load Balancer
* VPN / Direct Connect

---

### 7.2 Connectivity Models

* Internet-based
* VPN-based
* Dedicated Link

---

## 8. Management & Control Infrastructure

### 8.1 Management Plane

* Provision Resource
* Monitor Health
* Control Policy

### 8.2 Monitoring & Logging

* Metrics
* Logs
* Alerts

---

## 9. Security Infrastructure

Security ฝังอยู่ใน Infrastructure ทุกระดับ

* IAM
* Network Segmentation
* Encryption
* Key Management (KMS)
* Compliance & Audit

---

## 10. High Availability & Resilience Infrastructure

* Redundant Hardware
* Multi-AZ / Multi-Region
* Backup & Disaster Recovery

---

## 11. Infrastructure as Code (IaC)

Infrastructure ถูกสร้างและจัดการด้วย Code

* Terraform
* CloudFormation

**ข้อดี**

* ทำซ้ำได้
* ลด Human Error
* รองรับ Automation

---

## 12. Infrastructure Responsibility Model

| Layer          | Responsibility  |
| -------------- | --------------- |
| Physical DC    | Cloud Provider  |
| Virtualization | Cloud Provider  |
| OS / App       | Customer (IaaS) |

---

## 13. Common Infrastructure Challenges

* Over-Provisioning
* Underutilized Resource
* Network Bottleneck
* Misconfiguration

---

## 14. Summary

> **Cloud Computing Infrastructure คือการรวม Physical + Virtual + Software-Defined Infrastructure เข้าด้วยกัน**

### จำ 3 แกนหลัก

1. Compute
2. Storage
3. Network

ทั้งหมดถูกควบคุมด้วย Software และ Automation

---

*เอกสารนี้เหมาะสำหรับ Lecture Note, Exam Summary และ Cloud Infrastructure Reference*
