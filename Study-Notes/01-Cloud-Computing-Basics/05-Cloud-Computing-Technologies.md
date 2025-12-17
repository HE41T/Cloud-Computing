# Cloud Computing Technologies – In‑Depth Guide

เอกสารนี้อธิบาย **Cloud Computing Technologies** แบบ *เชิงลึก* ตั้งแต่ระดับ Hardware abstraction ไปจนถึงระดับ Application Architecture พร้อมเหตุผลว่าแต่ละเทคโนโลยีจำเป็นต่อ Cloud อย่างไร เหมาะสำหรับ

* การเรียนเชิงลึก
* การสอบ
* การออกแบบระบบจริง

---

## 1. Cloud Computing Technologies คืออะไร (Deep Understanding)

Cloud Computing ไม่ได้เกิดจากเทคโนโลยีเดียว แต่เกิดจาก **การบูรณาการหลายเทคโนโลยี** เพื่อให้ได้คุณสมบัติหลักของ Cloud ได้แก่

* On‑Demand
* Scalability
* Resource Sharing
* Automation
* High Availability

> ถ้าไม่มีเทคโนโลยีเหล่านี้ Cloud จะกลายเป็นแค่ Data Center ธรรมดา

---

## 2. Virtualization Technology (รากฐานของ Cloud)

### 2.1 Virtual Machine (VM)

VM คือการจำลอง “คอมพิวเตอร์ทั้งเครื่อง” บน Hardware เดียว

**โครงสร้างการทำงาน**

```
Hardware
 └─ Hypervisor
     ├─ VM1 (OS + App)
     ├─ VM2 (OS + App)
     └─ VM3 (OS + App)
```

<img width="560" height="413" alt="image" src="https://github.com/user-attachments/assets/1a1d9493-d7a5-4028-bd1d-08ec3c706ae2" />

**ทำไม Cloud ต้องใช้ VM**

* แยกผู้ใช้ออกจากกัน (Isolation)
* ใช้ Hardware ร่วมกันได้อย่างปลอดภัย
* รองรับ Legacy Application

**ข้อแลกเปลี่ยน (Trade‑off)**

* ปลอดภัยสูง แต่ใช้ Resource มาก
* Boot ช้ากว่า Container

---

### 2.2 Hypervisor (ตัวควบคุม VM)

Hypervisor คือ Software ที่แบ่ง Hardware ให้หลาย VM

| ประเภท | ใช้ใน Cloud จริง | เหตุผล                  |
| ------ | ---------------- | ----------------------- |
| Type 1 | ✔                | Performance สูง, Stable |
| Type 2 | ✘                | ใช้เพื่อทดลองเท่านั้น   |

---

## 3. Container Technology (Cloud‑Native Era)

### 3.1 Containers ต่างจาก VM อย่างไร

| VM              | Container             |
| --------------- | --------------------- |
| มี OS แยก       | แชร์ OS Kernel        |
| หนัก            | เบา                   |
| เหมาะกับ Legacy | เหมาะกับ Cloud‑Native |

**เหตุผลที่ Cloud สมัยใหม่ใช้ Container**

* Deploy เร็ว
* Scale เร็ว
* ใช้ Resource คุ้มกว่า

---

### 3.2 Kubernetes (หัวใจของ Modern Cloud)

Kubernetes คือระบบควบคุม Container จำนวนมาก

**ความสามารถสำคัญ**

* Auto‑scaling
* Self‑healing
* Rolling Update
* Service Discovery

> Kubernetes ทำให้ Cloud “ดูแลตัวเองได้”

---

## 4. Networking Technologies (เส้นเลือดของ Cloud)

### 4.1 Software‑Defined Networking (SDN)

แยก Network ออกเป็น 2 ส่วน

* Control Plane (Policy)
* Data Plane (Traffic)

**ประโยชน์**

* เปลี่ยน Network ได้โดยไม่ต้องจับ Hardware
* เป็นพื้นฐานของ NaaS, SD‑WAN

---

### 4.2 Network Virtualization

Cloud สร้าง Network เสมือน เช่น

* VPC
* Subnet
* Security Group

**เหตุผลที่จำเป็น**

* แยก Network ของแต่ละลูกค้า
* ควบคุม Security ได้ละเอียด

---

## 5. Storage Technologies (การจัดเก็บแบบ Cloud)

### 5.1 Block Storage

* ใช้กับ VM
* Performance สูง

### 5.2 Object Storage

* Scale ได้แทบไม่จำกัด
* ใช้กับ Big Data / Backup

### 5.3 File Storage

* ใช้ร่วมกันหลายเครื่อง

> Cloud แยก Storage ตาม “ลักษณะงาน” ไม่ใช่แบบเดียวใช้ทุกอย่าง

---

## 6. Automation & Orchestration (Cloud ต้องอัตโนมัติ)

### 6.1 Infrastructure as Code (IaC)

กำหนด Cloud ด้วย Code แทนการคลิก

**ข้อดีเชิงลึก**

* ทำซ้ำได้ 100%
* Audit ได้
* รองรับ CI/CD

---

### 6.2 Configuration Management

จัดการ Configuration ของ OS / App แบบรวมศูนย์

> Cloud ขนาดใหญ่ “ห้าม” ตั้งค่าด้วยมือ

---

## 7. Security Technologies (Security by Design)

### 7.1 IAM

* ใครเข้าถึงอะไรได้
* Principle of Least Privilege

### 7.2 Encryption

* ป้องกันข้อมูลแม้ถูกขโมย

### 7.3 Monitoring & SIEM

* ตรวจจับความผิดปกติ
* Audit & Compliance

---

## 8. Management & Observability

Cloud ต้องมองเห็นระบบตลอดเวลา

* Metrics
* Logs
* Traces

> ถ้ามองไม่เห็น = ควบคุมไม่ได้

---

## 9. Application Architecture Technologies

### 9.1 Service-Oriented Architecture (SOA)

**SOA (Service-Oriented Architecture)** คือแนวคิดการออกแบบระบบที่แบ่งระบบใหญ่ให้เป็นบริการย่อย (Service) ที่สื่อสารกันผ่านมาตรฐานกลาง เช่น API, SOAP, REST

<img width="560" height="425" alt="image" src="https://github.com/user-attachments/assets/47e047a2-f5a7-4f69-8c15-c50800d1dce7" />

**แนวคิดหลักของ SOA**

* แต่ละ Service ทำหน้าที่ชัดเจน
* Service สามารถนำกลับมาใช้ซ้ำได้ (Reusable)
* เชื่อมต่อกันแบบ Loose Coupling

**ตัวอย่าง**

* ระบบธนาคาร: Service ลูกค้า, Service บัญชี, Service ชำระเงิน

**ความสัมพันธ์กับ Cloud**

* SOA เป็นรากฐานของ Microservices
* Cloud ทำให้ SOA Scale ได้ง่ายและคุ้มค่า

> SOA = แนวคิดเชิงสถาปัตยกรรมที่ทำให้ Cloud และ Microservices เกิดขึ้นได้จริง

---

### 9.2 API-Driven Architecture

* ทุกอย่างใน Cloud ควบคุมผ่าน API
* รองรับ Automation และ Integration

---

### 9.3 Microservices

* แยก App เป็น Service ย่อย
* Scale และ Deploy แยกกันได้

### 9.1 API‑Driven Architecture

* ทุกอย่างควบคุมด้วย API

### 9.2 Microservices

* แยก App เป็นบริการย่อย
* Scale ได้อิสระ

---

## 10. Distributed & Pre-Cloud Computing Technologies

### 10.1 Grid Computing

**Grid Computing** คือการนำคอมพิวเตอร์หลายเครื่องมารวมพลังประมวลผลเพื่อทำงานเดียวกัน

<img width="560" height="418" alt="image" src="https://github.com/user-attachments/assets/603e2216-ecff-49ca-aa70-7386a112f346" />

**ลักษณะสำคัญ**

* ใช้ Resource จากหลายองค์กรหรือหลายสถานที่
* เน้นงานคำนวณหนัก (High Performance Computing)

**ตัวอย่าง**

* งานวิจัยทางวิทยาศาสตร์
* Simulation

**ความแตกต่างจาก Cloud**

| Grid          | Cloud        |
| ------------- | ------------ |
| เน้น Compute  | เน้น Service |
| ไม่ยืดหยุ่น   | Elastic      |
| ไม่ On-Demand | On-Demand    |

> Grid Computing คือบรรพบุรุษของ Cloud Computing

---

### 10.2 Utility Computing

**Utility Computing** คือแนวคิดการใช้ทรัพยากร IT แบบจ่ายตามการใช้งาน เหมือนค่าน้ำค่าไฟ

**แนวคิดหลัก**

* Pay-per-use
* Metering

**ความสัมพันธ์กับ Cloud**

* เป็นแนวคิดทางธุรกิจของ Cloud
* Cloud คือการทำ Utility Computing ให้ใช้งานได้จริง

> Utility Computing = Business Model ของ Cloud

---

## 11. Emerging Cloud Technologies

* Serverless (FaaS)

* Edge Computing

* AI / ML Cloud

* Multi-Cloud Management

* Serverless (ไม่ต้องดูแล Server)

* Edge Computing (ใกล้ผู้ใช้)

* AI / ML Cloud

* Multi‑Cloud Management

---

## 12. Big Picture Summary

**Cloud Computing Technologies = เทคโนโลยีที่ทำให้**

* Resource ถูกแชร์อย่างปลอดภัย
* ระบบ Scale ได้อัตโนมัติ
* บริหารด้วย Software & Automation

### จำเป็นต้องเข้าใจ 3 ชั้น

1. Infrastructure (VM, Network, Storage)
2. Platform (Container, Kubernetes)
3. Operation (Automation, Security, Monitoring)

---

*เอกสารนี้เป็นระดับ "เข้าใจ Cloud จริง" ไม่ใช่แค่จำคำจำกัดความ*
