# Cloud Data Storage

## ความหมายของ Cloud Data Storage

Cloud Data Storage คือบริการจัดเก็บข้อมูลบนระบบ **Storage ที่อยู่นอกสถานที่ (Offsite Storage)** ซึ่งถูกดูแลโดยผู้ให้บริการบุคคลที่สาม (Cloud Provider) และสามารถเข้าถึงข้อมูลได้ผ่าน **Web Services API** หรือเครือข่ายอินเทอร์เน็ต

ผู้ใช้งานไม่จำเป็นต้องดูแล Hardware เอง แต่สามารถใช้งานพื้นที่จัดเก็บข้อมูลได้ตามต้องการ

---

## ประเภทของอุปกรณ์จัดเก็บข้อมูล (Storage Devices)

อุปกรณ์จัดเก็บข้อมูลสามารถแบ่งออกได้เป็น 2 ประเภทหลัก

* Block Storage Devices
* File Storage Devices

---

## Block Storage Devices

Block Storage เป็นรูปแบบการให้บริการ **พื้นที่จัดเก็บข้อมูลแบบดิบ (Raw Storage)** แก่ผู้ใช้งาน

### ลักษณะสำคัญ

* ผู้ใช้สามารถแบ่ง Partition ได้เอง
* สามารถ Format และเลือก File System ได้เอง
* มักใช้กับระบบที่ต้องการประสิทธิภาพสูง

### ตัวอย่างการใช้งาน

* Disk สำหรับ Virtual Machine
* Database Storage
* ระบบที่ต้องการ I/O สูง

---

## File Storage Devices

File Storage ให้บริการจัดเก็บข้อมูลในรูปแบบ **ไฟล์ (File-based)** โดยมี File System ให้พร้อมใช้งาน

ลักษณะของ File Storage จะเป็นแบบ **Network Attached Storage (NAS)**

### ลักษณะสำคัญ

* เข้าถึงข้อมูลผ่านเครือข่าย
* มีโครงสร้างโฟลเดอร์และไฟล์
* ใช้งานง่าย ไม่ต้องจัดการ Disk เอง

### ตัวอย่างการใช้งาน

* File Sharing
* Home Directory ของผู้ใช้งาน
* ระบบที่หลายเครื่องต้องใช้ไฟล์ร่วมกัน

---

## Cloud Storage Classes

Cloud Storage สามารถแบ่งออกเป็น 2 ประเภทหลัก

* Unmanaged Cloud Storage
* Managed Cloud Storage

---

## Unmanaged Cloud Storage

Unmanaged Cloud Storage คือพื้นที่จัดเก็บข้อมูลที่ **ถูกตั้งค่ามาเรียบร้อยแล้วโดย Provider**

### ลักษณะสำคัญ

* ผู้ใช้งานไม่สามารถ Format ได้เอง
* ไม่สามารถติดตั้ง File System เอง
* ไม่สามารถปรับแต่งคุณสมบัติของ Drive ได้

### ตัวอย่างการใช้งาน

* Object Storage บางประเภท
* Storage สำหรับ Backup แบบสำเร็จรูป

---

## Managed Cloud Storage

Managed Cloud Storage เป็นบริการจัดเก็บข้อมูลที่ให้ผู้ใช้งาน **ควบคุมการจัดการ Storage ได้เอง**

### ลักษณะสำคัญ

* มองเห็น Storage เสมือนเป็น Raw Disk
* สามารถ Partition และ Format ได้เอง
* ยืดหยุ่นและรองรับการใช้งานหลากหลาย

### ตัวอย่างการใช้งาน

* Block Storage สำหรับ VM
* ระบบที่ต้องการปรับแต่ง File System เอง

---

## การสร้างระบบ Cloud Storage (Creating Cloud Storage System)

ระบบ Cloud Storage จะจัดเก็บข้อมูลหลายชุด (Multiple Copies) ไว้บน

* หลาย Server
* หลายตำแหน่งที่ตั้ง (Multiple Locations)

หากระบบใดระบบหนึ่งล้มเหลว จะเพียงแค่เปลี่ยน **Pointer** ไปยังตำแหน่งของข้อมูลที่ยังใช้งานได้

---

## Storage Virtualization และ StorageGRID

เพื่อรวมทรัพยากร Storage หลายแหล่งให้เป็นระบบเดียว Cloud Provider จะใช้ **Storage Virtualization Software** เช่น **StorageGRID**

### ความสามารถของ StorageGRID

* สร้าง Virtualization Layer
* รวม Storage จากหลายอุปกรณ์เข้าด้วยกัน
* จัดการ Storage ผ่านระบบศูนย์กลาง
* รองรับ CIFS และ NFS ผ่านอินเทอร์เน็ต

<img width="560" height="395" alt="image" src="https://github.com/user-attachments/assets/fec83f67-a54c-48f0-b1d8-a2910eb7aacb" />

---

## Virtual Storage Containers

Virtual Storage Container คือกลไกที่ช่วยให้ Cloud Storage มีประสิทธิภาพสูง

### ลักษณะสำคัญ

* สร้าง Logical Unit Number (LUN)
* รองรับ Device, Files และ Objects
* ใช้กำหนดขอบเขตของ Cloud Storage Domain

Virtual Storage Containers ช่วยให้การจัดการ Storage มีความยืดหยุ่นและเป็นระบบมากขึ้น

<img width="560" height="420" alt="image" src="https://github.com/user-attachments/assets/68cbabf2-0b00-4e3e-aada-d17b590b6fbf" />

---

## Challenges (ความท้าทายของ Cloud Data Storage)

แม้ Cloud Storage จะมีความยืดหยุ่นและสะดวก แต่ก็มีความท้าทายที่ผู้ใช้งานต้องพิจารณา

ผู้ใช้งานควรมีความสามารถในการ:

* Provision พื้นที่จัดเก็บข้อมูลเพิ่มเติมได้ตามต้องการ
* รู้และควบคุมตำแหน่งที่ตั้งทางกายภาพของข้อมูล
* ตรวจสอบว่าข้อมูลถูกลบอย่างถูกต้อง (Data Erasure Verification)
* มีเอกสารยืนยันกระบวนการกำจัดอุปกรณ์จัดเก็บข้อมูล
* ควบคุมสิทธิ์การเข้าถึงข้อมูลของผู้ดูแลระบบ (Administrator Access Control)

---

## สรุป

Cloud Data Storage เป็นองค์ประกอบสำคัญของ Cloud Computing ที่ช่วยให้การจัดเก็บข้อมูลมีความยืดหยุ่น ปลอดภัย และขยายได้ง่าย แต่ผู้ใช้งานต้องเข้าใจประเภทของ Storage การจัดการ และความท้าทาย เพื่อเลือกใช้งานได้อย่างเหมาะสม
