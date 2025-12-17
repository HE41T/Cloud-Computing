# Network as a Service (NaaS) – Complete Guide

เอกสารนี้สรุป **NaaS (Network as a Service)** ตั้งแต่แนวคิดพื้นฐานจนถึงการใช้งานจริง โดยปรับภาษาและโครงสร้างให้อ่านง่าย เหมาะสำหรับเรียน สอบ และใช้อ้างอิงเชิงเทคนิค

---

## 1. NaaS คืออะไร

**NaaS (Network as a Service)** คือการให้บริการโครงสร้างเครือข่ายในรูปแบบ *Service* ผ่าน Cloud หรือ Provider กลาง

> แนวคิดหลัก: **Network ไม่จำเป็นต้องสร้างและดูแลเอง แต่สามารถเรียกใช้งานได้เหมือน Software**

### บทบาทของแต่ละฝ่าย

**ผู้ใช้งาน (Customer)**

* กำหนด Policy การใช้งานเครือข่าย
* เลือกรูปแบบการเชื่อมต่อ
* จ่ายค่าใช้จ่ายตามการใช้งานจริง

**ผู้ให้บริการ (Provider)**

* ดูแล Hardware และโครงสร้างพื้นฐาน
* ดูแล Routing, Security และ Availability

---

## 2. ปัญหาของ Network แบบเดิม

### Network แบบ Traditional

* ต้องลงทุนซื้อ Router / Switch / Firewall
* ต้องมีทีม Network ดูแลเฉพาะทาง
* ขยายระบบ (Scale) ทำได้ยาก
* เปลี่ยน Configuration เสี่ยงเกิด Downtime

### ปัญหาที่พบบ่อย

* ใช้เงินลงทุนเริ่มต้นสูง (CAPEX)
* Provision ช้า (ระดับสัปดาห์หรือเดือน)
* บริหารจัดการหลายสาขามีความซับซ้อน

---

## 3. NaaS เข้ามาแก้อะไร

NaaS เปลี่ยนแนวคิดการทำ Network จาก

> **Hardware-centric → Software-centric**

### ผลลัพธ์ที่ได้

* Provision ระบบได้รวดเร็ว
* เพิ่มหรือลดขนาดระบบได้ทันที
* ควบคุมและบริหารจากศูนย์กลาง

### เปรียบเทียบแบบชีวิตจริง

* ❌ **Network แบบเดิม**: ต้องซื้อเสาไฟ เดินสายไฟ และซ่อมเอง
* ✅ **NaaS**: เสียบปลั๊ก ใช้ไฟ และจ่ายตามหน่วยที่ใช้

---

## 4. แนวคิดหลักของ NaaS

### 4.1 Software-Defined Network

* Control Plane อยู่บน Cloud
* อุปกรณ์ปลายทางทำหน้าที่ Forward Traffic เป็นหลัก

### 4.2 Policy-Based Management

* กำหนดกฎจากศูนย์กลาง
* ไม่ต้องตั้งค่าอุปกรณ์ทีละตัว

### 4.3 Pay-as-you-go

* ใช้เท่าไร จ่ายเท่านั้น
* ลดต้นทุนที่ไม่จำเป็น

---

## 5. องค์ประกอบของ NaaS

```
[ User / Branch / Application ]
              ↓
        Edge / Internet
              ↓
        NaaS Platform
     (Control + Security)
              ↓
      Cloud / DC / SaaS
```

### องค์ประกอบหลัก

* Edge Device หรือ Agent
* Control Plane
* Data Plane
* Management Portal / API

---

## 6. NaaS ทำงานอย่างไร (Flow)

1. สมัครใช้งาน NaaS Provider
2. ติดตั้ง Edge Device หรือ Software Agent
3. เชื่อมต่อ Internet หรือ Mobile Network
4. สร้าง Virtual Network
5. กำหนด Policy (Routing, Security, Access)
6. Traffic ทั้งหมดถูกควบคุมผ่าน NaaS Core

---

## 7. บริการที่อยู่ภายใต้ NaaS

### Connectivity

* VPN (Client-to-Site / Site-to-Site)
* SD-WAN
* Interconnect ระหว่าง Cloud หรือ DC

### Network Function

* Firewall
* Load Balancer
* NAT
* DNS
* DDoS Protection

### Management

* Monitoring
* Logging
* Automation ผ่าน API

---

## 8. Mobile NaaS

**Mobile NaaS** คือรูปแบบหนึ่งของ NaaS ที่ใช้เครือข่ายมือถือ (4G / 5G) เป็นโครงสร้างหลัก

### จุดเด่นของ Mobile NaaS

* ไม่ต้องพึ่งพาสาย LAN
* ใช้ SIM / eSIM เป็นตัวตนของอุปกรณ์
* เหมาะกับ IoT และ Mobile Workforce

```
[ Device ] → 4G/5G → Mobile NaaS Core → Cloud / Application
```

---

## 9. NaaS Benefits (ข้อดี)

### 9.1 ด้านต้นทุน

* ลดการลงทุนเริ่มต้น (CAPEX)
* เปลี่ยนเป็นค่าใช้จ่ายตามการใช้งาน (OPEX)

### 9.2 ด้านความเร็วและความยืดหยุ่น

* Provision ระบบได้รวดเร็ว
* รองรับธุรกิจที่เปลี่ยนแปลงตลอดเวลา

### 9.3 ด้านการบริหารจัดการ

* ควบคุมจากศูนย์กลาง
* ลดความผิดพลาดจากมนุษย์ (Human Error)

### 9.4 ด้านความปลอดภัย

* Security รวมศูนย์
* รองรับแนวคิด Zero Trust

---

## 10. Use Case ของ NaaS

* องค์กรที่มีหลายสาขา (Multi-Branch)
* Hybrid / Multi-Cloud Environment
* Remote Work
* Dev / Test Environment
* IoT / Smart Factory

---

## 11. NaaS เทียบกับเทคโนโลยีอื่น

### NaaS vs MPLS

| ประเด็น | MPLS | NaaS     |
| ------- | ---- | -------- |
| Cost    | สูง  | ยืดหยุ่น |
| Scale   | ยาก  | ง่าย     |
| Control | ต่ำ  | สูง      |

### NaaS vs VPN

* VPN เป็นเพียงส่วนหนึ่งของ NaaS
* NaaS ให้การควบคุมและกำหนด Policy ได้มากกว่า

---

## 12. NaaS กับ Zero Trust / SASE

* NaaS เป็นโครงสร้างพื้นฐานด้าน Network
* Zero Trust เป็นนโยบายด้านความปลอดภัย
* **SASE = NaaS + Security Services**

---

## 13. ข้อจำกัดของ NaaS

* ขึ้นกับความเสถียรของ Provider
* ต้องพึ่งพา Internet เป็นหลัก
* การปรับแต่งระดับ Low-level ทำได้จำกัด

---

## 14. ตัวอย่าง NaaS Provider

| ประเภท       | ตัวอย่าง        |
| ------------ | --------------- |
| Cloud Native | AWS, Azure, GCP |
| Enterprise   | Cisco Meraki    |
| Global Edge  | Cloudflare      |

---

## 15. สรุปภาพรวม

> **NaaS คือการเปลี่ยน Network ให้กลายเป็น Service ที่ควบคุมได้ด้วย Software**

จำ 3 คำสำคัญนี้:

* Software-defined
* Policy-based
* On-demand

---

*เอกสารนี้เหมาะสำหรับใช้เป็น Lecture Note, Exam Summary และ Technical Overview ด้าน NaaS*
