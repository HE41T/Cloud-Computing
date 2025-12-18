<img width="400" height="419" alt="image" src="https://github.com/user-attachments/assets/aee1a6c5-c522-4306-a949-b33634dce79e" /># Virtualization Concept

## ความหมายของ Virtualization

Virtualization คือแนวคิดในการ **สร้างเครื่องเสมือน (Virtual Machine: VM)** ขึ้นมาบนระบบปฏิบัติการและฮาร์ดแวร์ที่มีอยู่เดิม ซึ่งเรียกว่า **Hardware Virtualization**

Virtual Machine จะทำงานในสภาพแวดล้อมที่ **แยกออกจากฮาร์ดแวร์จริงแบบเชิงตรรกะ (Logical Separation)** ทำให้หลายระบบสามารถทำงานบนเครื่องเดียวกันได้อย่างอิสระ

---

## Host Machine และ Guest Machine

* **Host Machine** : เครื่องจริงที่มีฮาร์ดแวร์และระบบปฏิบัติการหลัก
* **Guest Machine (Virtual Machine)** : เครื่องเสมือนที่ถูกสร้างขึ้นมาบน Host

Virtual Machine จะถูกควบคุมและจัดการโดยซอฟต์แวร์หรือเฟิร์มแวร์ที่เรียกว่า **Hypervisor**

---

## Hypervisor

Hypervisor คือซอฟต์แวร์ระดับต่ำหรือเฟิร์มแวร์ที่ทำหน้าที่เป็น **Virtual Machine Manager (VMM)** มีหน้าที่จัดสรรทรัพยากร เช่น CPU, Memory, Storage ให้กับ Virtual Machine แต่ละเครื่อง

### ประเภทของ Hypervisor

Hypervisor สามารถแบ่งออกเป็น 2 ประเภทหลัก

---

### Type 1 Hypervisor (Bare-metal Hypervisor)

Type 1 Hypervisor จะทำงาน **โดยตรงบนฮาร์ดแวร์** โดยไม่ต้องมีระบบปฏิบัติการเป็นตัวกลาง

<img width="400" height="419" alt="image" src="https://github.com/user-attachments/assets/68e0350c-f924-48a7-9ee7-c2f495aa5ab3" />

#### ลักษณะเด่น

* ประสิทธิภาพสูง
* เสถียรและปลอดภัย
* นิยมใช้ใน Data Center และ Cloud

#### ตัวอย่าง

* LynxSecure
* RTS Hypervisor
* Oracle VM
* Sun xVM Server
* VirtualLogic VLX

---

### Type 2 Hypervisor (Hosted Hypervisor)

Type 2 Hypervisor จะทำงานเป็น **ซอฟต์แวร์บนระบบปฏิบัติการอีกชั้นหนึ่ง** และทำการจำลองอุปกรณ์ฮาร์ดแวร์ให้ Virtual Machine ใช้งาน

<img width="400" height="419" alt="image" src="https://github.com/user-attachments/assets/152609d9-b10e-4f91-baea-cc3468ab54a4" />

#### ลักษณะเด่น

* ติดตั้งและใช้งานง่าย
* เหมาะสำหรับการทดสอบและใช้งานทั่วไป

#### ตัวอย่าง

* KVM
* Microsoft Hyper-V
* VMware Fusion
* VMware Workstation
* Virtual Server 2005 R2
* Windows Virtual PC
* Containers

---

## Types of Hardware Virtualization

Hardware Virtualization สามารถแบ่งออกเป็น 3 ประเภทหลัก

* Full Virtualization
* Emulation Virtualization
* Paravirtualization

---

## Full Virtualization

Full Virtualization คือการ **จำลองฮาร์ดแวร์ทั้งหมด** ให้กับ Guest Operating System

<img width="400" height="448" alt="image" src="https://github.com/user-attachments/assets/63a64824-cd48-4262-9bf2-6782d555fb7f" />

### ลักษณะสำคัญ

* Guest OS ไม่จำเป็นต้องแก้ไข
* ทำงานเหมือนรันบนเครื่องจริง

### ตัวอย่างการใช้งาน

* VMware
* VirtualBox

---

## Emulation Virtualization

Emulation คือการ **จำลองสถาปัตยกรรมของฮาร์ดแวร์ทั้งหมด** ทำให้ Virtual Machine ไม่ขึ้นกับฮาร์ดแวร์จริง

<img width="400" height="454" alt="image" src="https://github.com/user-attachments/assets/f51cb326-1a94-4fc4-9e74-7821df51da0c" />

### ลักษณะสำคัญ

* Guest OS ไม่ต้องแก้ไข
* รองรับสถาปัตยกรรมต่างชนิดกัน
* ประสิทธิภาพต่ำกว่า Full Virtualization

### ตัวอย่างการใช้งาน

* QEMU (Emulation Mode)

---

## Paravirtualization

Paravirtualization เป็นการทำงานที่ **ไม่จำลองฮาร์ดแวร์ทั้งหมด** แต่ให้ Guest OS ติดต่อกับ Hypervisor โดยตรง

<img width="400" height="442" alt="image" src="https://github.com/user-attachments/assets/3e68c803-244a-4aee-8e7c-5356b6514f59" />

### ลักษณะสำคัญ

* Guest OS ต้องถูกปรับแต่ง
* ประสิทธิภาพสูง
* ลด Overhead จากการจำลองฮาร์ดแวร์

### ตัวอย่างการใช้งาน

* Xen Paravirtualization

---

## หมายเหตุ: VMware vSphere

**VMware vSphere** เป็นแพลตฟอร์ม Virtualization ระดับองค์กรที่มีความสามารถสูง

### ความสามารถหลัก

* Virtualize ระบบคอมพิวเตอร์ (Compute)
* Virtualize Storage
* Virtualize Network
* มีระบบบริหารจัดการแบบศูนย์กลาง

VMware vSphere นิยมใช้ใน Data Center และระบบ Cloud Infrastructure

---

## สรุป

Virtualization เป็นเทคโนโลยีพื้นฐานของ Cloud Computing ช่วยให้การใช้ทรัพยากรมีประสิทธิภาพสูงขึ้น ลดต้นทุน และเพิ่มความยืดหยุ่นในการบริหารระบบ เหมาะสำหรับทั้งการเรียน การสอบ และการใช้งานจริงในระดับองค์กร
