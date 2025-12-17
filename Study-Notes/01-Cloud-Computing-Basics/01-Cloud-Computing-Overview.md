# Cloud Computing Overview – Complete Guide

เอกสารนี้อธิบาย **Cloud Computing** แบบละเอียด ตั้งแต่พื้นฐานจนถึงแนวคิดเชิงเทคนิค พร้อม Markdown Rendering / Preview

---

## 1. What is Cloud?

**Cloud** คือ **การเข้าถึง Resource หรือ Service ผ่าน Internet** โดยไม่จำเป็นต้องมี Hardware หรือ Software บนเครื่องของเราเอง

> ตัวอย่าง: Storage, Application, Compute, Database

---

## 2. What is Cloud Computing?

**Cloud Computing** คือการให้บริการ **Computing Resource และ Services ผ่าน Internet** ในรูปแบบ On-Demand และ Pay-as-you-go

* ผู้ใช้ไม่ต้องลงทุน Hardware เอง
* ผู้ให้บริการจัดการ Infrastructure Platform และ Software
* Resource สามารถ Scale ได้ทันทีตามต้องการ

<img width="560" height="346" alt="image" src="https://github.com/user-attachments/assets/f652b406-9fd5-43d0-88f1-eaf055f999b0" />

---

## 3. Basic Concepts

* **Virtualization:** การสร้าง Virtual Machine / Container แยกจาก Hardware จริง
* **Resource Pooling:** รวม Resource ใช้ร่วมกันระหว่างผู้ใช้หลายราย
* **Scalability / Elasticity:** เพิ่มหรือลด Resource ได้ตามต้องการ
* **On-Demand Self-Service:** ผู้ใช้ Provision Resource ได้ด้วยตัวเอง
* **Metered Service / Pay-as-you-go:** จ่ายตามการใช้งานจริง

---

## 4. Deployment Models

| Model           | Description                             | Examples                                           |
| --------------- | --------------------------------------- | -------------------------------------------------- |
| Public Cloud    | Resource ถูกแชร์หลายองค์กร              | AWS, Azure, GCP                                    |
| Private Cloud   | Resource เฉพาะองค์กรเดียว               | VMware vSphere, OpenStack                          |
| Hybrid Cloud    | ผสม Public + Private Cloud              | VMware Cloud on AWS, Azure Stack                   |
| Community Cloud | Resource แชร์ระหว่างองค์กรกลุ่มเดียวกัน | IBM Cloud for Financial Services, Azure Government |

<img width="560" height="281" alt="image" src="https://github.com/user-attachments/assets/7a26f2a8-fe51-4503-a2a6-3977aaffbd08" />

---

## 5. Service Models

| Model | Description                            | Examples                                     |
| ----- | -------------------------------------- | -------------------------------------------- |
| IaaS  | Infrastructure as a Service            | AWS EC2, Azure VM, GCP Compute Engine        |
| PaaS  | Platform as a Service                  | Heroku, Google App Engine, Azure App Service |
| SaaS  | Software as a Service                  | Gmail, Office 365, Salesforce                |
| NaaS  | Network as a Service                   | Cisco Meraki, Cloudflare, AWS VPC            |
| FIDM  | Federated Identity & Access Management | Okta, Auth0, Ping Identity                   |
| SSO   | Single Sign-On Service                 | Google Workspace SSO, Microsoft SSO          |

<img width="400" height="357" alt="image" src="https://github.com/user-attachments/assets/a7480bd2-f17e-4d57-a1e8-311308da5a27" />

---

## 6. History of Cloud Computing

1. **1960s:** Concept of Utility Computing (John McCarthy)
2. **1990s:** Virtualization technologies (VMware)
3. **2000s:** Emergence of SaaS (Salesforce 1999), IaaS (AWS 2006)
4. **2010s:** PaaS, Mobile Cloud, Hybrid Cloud
5. **2020s:** Multi-Cloud, Edge Computing, AI Cloud Services

<img width="560" height="317" alt="image" src="https://github.com/user-attachments/assets/38e89819-df95-43ad-91a3-ad69f46f1f5c" />

---

## 7. Benefits

* **Cost Savings:** ลด CAPEX, จ่ายตาม Usage
* **Scalability & Flexibility:** เพิ่ม / ลด Resource ได้ทันที
* **Accessibility:** ใช้งานจากทุกที่ทุกเวลา
* **Fast Provisioning:** Deploy VM, App, Database ได้ทันที
* **Maintenance & Updates:** Provider ดูแล Software / Infrastructure
* **Collaboration:** รองรับ Remote Work และ Multi-user Access

<img width="560" height="399" alt="image" src="https://github.com/user-attachments/assets/874833ea-8f5c-4dbd-b39c-5397f7a2650c" />

---

## 8. Risks related to Cloud Computing

* **Data Security & Privacy:** ข้อมูลถูกเก็บบน Cloud Provider
* **Vendor Lock-in:** ย้าย Service Provider ยาก
* **Downtime / Availability:** Service อาจมี Outage
* **Compliance & Legal Issues:** ต้องปฏิบัติตามกฎหมายและมาตรฐาน
* **Network Dependency:** ต้องพึ่งพา Internet
* **Misconfiguration / Human Error:** การตั้งค่าผิดพลาดอาจทำให้เกิดปัญหา

---

## 9. Characteristics of Cloud Computing

* **On-Demand Self-Service:** Provision Resource ได้เอง
* **Broad Network Access:** ใช้ได้จาก Device ใดก็ได้ที่เชื่อม Internet
* **Resource Pooling:** Shared Resource สำหรับหลายผู้ใช้
* **Rapid Elasticity:** Scale Resource ขึ้นลงอัตโนมัติ
* **Measured Service:** Usage Monitor & Billing
* **Multi-Tenancy:** Resource ใช้ร่วมกันแต่ข้อมูลแยกกัน
* **Resiliency & Reliability:** มี Backup, Redundancy และ Disaster Recovery

<img width="560" height="428" alt="image" src="https://github.com/user-attachments/assets/276c0c52-56e4-422d-878c-b34d5d274a00" />

---

*เอกสารนี้เหมาะสำหรับ Lecture Note, Exam Summary และ Technical Overview ของ Cloud Computing และสามารถใช้เชื่อมโยงกับ Deployment Models และ Service Models อื่น ๆ ได้*
