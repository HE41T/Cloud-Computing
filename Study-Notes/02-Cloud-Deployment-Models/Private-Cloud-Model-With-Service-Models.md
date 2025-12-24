# Private Cloud Model เมื่อใช้งานร่วมกับ Service Model

อธิบายการให้บริการ การทำงาน และสิ่งที่ลูกค้าจะได้รับจาก **Private Cloud** เมื่อใช้งานร่วมกับ IaaS, PaaS และ SaaS

---

## 1. แนวคิดของ Private Cloud (ในมุมการใช้งานจริง)

**Private Cloud** คือรูปแบบ Cloud ที่โครงสร้างพื้นฐานถูกใช้งานโดย **องค์กรเดียวเท่านั้น** (Single-Tenant)

สามารถติดตั้งได้ทั้ง

* ภายในองค์กร (On-Premise)
* หรือ Hosted อยู่ที่ Data Center ของผู้ให้บริการ (Private Hosted Cloud)

ลักษณะสำคัญของ Private Cloud

* ไม่ใช้ทรัพยากรร่วมกับองค์กรอื่น
* ควบคุม Security และ Policy ได้สูง
* ปรับแต่งระบบได้ตามความต้องการ
* เหมาะกับระบบที่มีข้อกำหนดด้าน Compliance

> Private Cloud ยังคงใช้แนวคิด Cloud (Virtualization, Automation, Self-Service) แต่ความเป็นเจ้าของและการควบคุมสูงกว่า Public Cloud

---

## 2. Private Cloud + IaaS (Infrastructure as a Service)

### รูปแบบการให้บริการ

Private Cloud แบบ IaaS คือการให้บริการโครงสร้างพื้นฐาน **เฉพาะองค์กรเดียว** โดยใช้เทคโนโลยี Virtualization

โครงสร้างพื้นฐานประกอบด้วย

* Data Center (ขององค์กรหรือผู้ให้บริการ)
* Physical Server (Dedicated)
* Storage (SAN / NAS / SDS)
* Network (VLAN / VXLAN)
* Hypervisor (VMware, KVM, Hyper-V)

ลูกค้าใช้งานในรูปแบบ **Virtual Machine (VM)** เช่นเดียวกับ Public Cloud แต่เป็นทรัพยากรเฉพาะ

---

### การทำงาน (เชิงลึก)

1. องค์กรเตรียม Hardware หรือเช่าจาก Provider
2. ติดตั้ง Virtualization Platform
3. สร้าง Resource Pool (CPU / RAM / Storage)
4. ผู้ใช้งานสร้าง VM ผ่าน Portal หรือ Admin
5. ติดตั้ง OS และ Software ตามต้องการ

> การทำงานคล้าย Public Cloud IaaS แต่ทุกอย่างอยู่ภายใต้การควบคุมขององค์กร

---

### สิ่งที่ลูกค้าได้รับ

* Server แบบ Dedicated
* ควบคุม OS และ Network ได้เต็มที่
* ปรับแต่งระบบได้สูง
* รองรับ Compliance และ Policy ภายใน

---

### ความรับผิดชอบ

| ส่วน           | ผู้ดูแล           |
| -------------- | ----------------- |
| Data Center    | องค์กร / Provider |
| Hardware       | องค์กร / Provider |
| Virtualization | องค์กร            |
| OS             | องค์กร            |
| Application    | องค์กร            |
| Data           | องค์กร            |

---

### เหมาะกับการใช้งาน

* ระบบ Core Business
* ระบบที่มีข้อมูลสำคัญ
* องค์กรขนาดใหญ่ / ภาครัฐ / ธนาคาร

---

## 3. Private Cloud + PaaS (Platform as a Service)

### รูปแบบการให้บริการ

Private PaaS คือการสร้าง Platform ภายในองค์กร เพื่อให้ Developer ใช้งานโดยไม่ต้องดูแล OS และ Infrastructure

มักใช้ร่วมกับ

* Container Platform (Kubernetes / OpenShift)
* Application Platform ภายใน

---

### การทำงาน (อธิบายกรณี “ไม่ต้องดูแล OS”)

เมื่อใช้งาน Private PaaS:

* Developer ไม่ต้องสร้าง VM
* ไม่ต้องติดตั้งหรือ Patch OS
* ไม่ต้องดูแล Runtime

ฝ่าย Infrastructure จะเป็นผู้ดูแล

* OS Image มาตรฐาน
* Patch Security
* Cluster และ Platform

Developer มีหน้าที่

* เขียน Code
* Build / Deploy Application
* จัดการ Logic และ Data

---

### Flow การทำงาน

1. Infra Team เตรียม Platform (K8s / PaaS)
2. Developer Push Code
3. Platform สร้าง Container / Runtime
4. ระบบจัดการ Load Balancing และ Scaling
5. Application ให้บริการภายในองค์กร

---

### สิ่งที่ลูกค้าได้รับ

* ลดภาระงาน Infra สำหรับ Developer
* มาตรฐานเดียวกันทั้งองค์กร
* ควบคุม Security ภายใน
* รองรับ DevOps

---

### ความรับผิดชอบ

| ส่วน             | ผู้ดูแล    |
| ---------------- | ---------- |
| Infrastructure   | Infra Team |
| OS               | Infra Team |
| Platform         | Infra Team |
| Application Code | Developer  |
| Data             | องค์กร     |

---

### เหมาะกับการใช้งาน

* องค์กรที่มี Dev Team ขนาดใหญ่
* ระบบภายใน (Internal Application)
* ระบบที่ต้องควบคุมข้อมูลสูง

---

## 4. Private Cloud + SaaS (Software as a Service)

### รูปแบบการให้บริการ

Private SaaS คือ Software ที่พัฒนาและใช้งาน **เฉพาะภายในองค์กร**

เช่น

* ระบบ HR ภายใน
* ระบบ ERP ภายใน
* ระบบ Workflow ภายใน

---

### การทำงาน

1. องค์กรพัฒนา Software เอง หรือจ้างพัฒนา
2. Deploy บน Private Cloud
3. Infra / IT Team ดูแล OS, Application และ Security
4. ผู้ใช้งานภายใน Login ใช้งาน

> ผู้ใช้งานไม่ต้องดูแลระบบ แต่ IT ภายในยังต้องดูแลทั้งหมด

---

### สิ่งที่ลูกค้าได้รับ

* ควบคุมข้อมูล 100%
* ปรับแต่งระบบได้ตามองค์กร
* สอดคล้อง Compliance ภายใน

---

### ความรับผิดชอบ

| ส่วน           | ผู้ดูแล     |
| -------------- | ----------- |
| Infrastructure | องค์กร      |
| OS             | องค์กร      |
| Application    | องค์กร      |
| Security       | องค์กร      |
| การใช้งาน      | ผู้ใช้ภายใน |

---

### เหมาะกับการใช้งาน

* องค์กรที่มีข้อกำหนดด้านข้อมูลสูง
* หน่วยงานรัฐ / การเงิน / สุขภาพ

---

## 5. เปรียบเทียบภาพรวม (Private Cloud)

| Service Model | ลูกค้าดูแล OS | ระดับการควบคุม |
| ------------- | ------------- | -------------- |
| IaaS          | ดูแลเอง       | สูงมาก         |
| PaaS          | ไม่ต้องดูแล   | สูง            |
| SaaS          | ผู้ใช้ไม่ดูแล | สูงสุด         |

---

## 6. สรุปแนวคิดแบบเข้าใจง่าย

* **Private IaaS**: Cloud ภายในองค์กร ควบคุมทุกอย่าง
* **Private PaaS**: มี Platform กลางให้ Dev ใช้
* **Private SaaS**: ระบบภายใน ใช้งานเฉพาะองค์กร

---

เอกสารนี้เหมาะสำหรับ

* อธิบาย Cloud Architecture ภายในองค์กร
* ใช้เทียบ Public vs Private Cloud
* ใช้เป็นเอกสาร Training / Policy
