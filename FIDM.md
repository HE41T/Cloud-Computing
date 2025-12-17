# Federated Identity Management (FIDM) Explained

## 1. FIDM คืออะไร

**FIDM (Federated Identity Management)** คือการจัดการตัวตนที่เปิดให้ **หลายองค์กรหรือหลายโดเมนเชื่อถือกัน** เพื่อใช้ยืนยันตัวตนข้ามระบบได้

> แนวคิดหลัก: *ใช้ตัวตนจากองค์กรต้นทาง ไปเข้าใช้งานระบบขององค์กรอื่นได้*

---

## 2. ปัญหาก่อนมี FIDM

เมื่อยังไม่มี FIDM:

* ต้องสร้างบัญชีผู้ใช้ซ้ำในทุกระบบภายนอก
* ผู้ดูแลระบบต้องจัดการ user จำนวนมาก
* การลบ user เมื่อหมดสัญญาทำได้ยาก

ผลลัพธ์:

* User ซ้ำซ้อน
* เสี่ยงด้าน Security
* Audit และ Compliance ลำบาก

---

## 3. ความแตกต่างระหว่าง SSO กับ FIDM

| ประเด็น   | SSO         | FIDM               |
| --------- | ----------- | ------------------ |
| ขอบเขต    | องค์กรเดียว | หลายองค์กร         |
| Identity  | IdP เดียว   | IdP ของแต่ละองค์กร |
| การใช้งาน | ภายใน       | ภายนอก / Partner   |

> **FIDM คือ SSO ที่ข้ามขอบเขตองค์กร**

---

## 4. องค์ประกอบหลักของ FIDM

<img width="560" height="380" alt="image" src="https://github.com/user-attachments/assets/3d871b7a-4d86-4d82-a962-8466aa5726b9" />

```
User → Home Identity Provider → External Service
```

### 4.1 User

* บุคคลที่ต้องการเข้าใช้งานระบบภายนอก

### 4.2 Home Identity Provider (Home IdP)

* องค์กรต้นทางที่เก็บตัวตนจริง
* ตรวจสอบรหัสผ่าน, MFA และ Policy

ตัวอย่าง:

* Azure AD / Entra ID
* Google Workspace
* Keycloak

### 4.3 Service Provider (SP) / Relying Party

* ระบบปลายทาง
* ไม่เก็บรหัสผ่าน
* เชื่อถือผลการยืนยันจาก Home IdP

---

## 5. ขั้นตอนการทำงานของ FIDM (Flow)

### Step 1: ผู้ใช้เข้า External Service

* ระบบปลายทางตรวจสอบว่ายังไม่ login

### Step 2: เลือกองค์กรต้นทาง

* เช่น "Login with Company A"

### Step 3: Redirect ไป Home IdP

* ผู้ใช้กรอกข้อมูลที่องค์กรต้นทาง

### Step 4: Home IdP ตรวจสอบตัวตน

* Password
* MFA
* Policy

### Step 5: Home IdP ออก Assertion / Token

ตัวอย่างข้อมูล:

```json
{
  "user": "heartyyy",
  "email": "user@company-a.com",
  "org": "CompanyA",
  "role": "partner"
}
```

### Step 6: ส่ง Token ไปยัง External Service

* ตรวจสอบลายเซ็น
* สร้าง session
* อนุญาตเข้าใช้งาน

---

## 6. หัวใจของ FIDM: Trust

FIDM ทำงานได้เพราะ **ความเชื่อถือ (Trust)** ระหว่างองค์กร

Service Provider ต้องเชื่อว่า:

* Home IdP ตรวจสอบตัวตนถูกต้อง
* มีมาตรฐานความปลอดภัย
* มี MFA และ Policy ที่เหมาะสม

---

## 7. Protocol ที่ใช้ใน FIDM

### SAML 2.0

* นิยมมากใน Enterprise Federation
* ใช้ XML

### OpenID Connect (OIDC)

* ใช้ JSON / JWT
* เหมาะกับ Cloud และ SaaS

### OAuth 2.0

* ใช้ควบคู่ แต่ไม่ใช่ Identity โดยตรง

---

## 8. FIDM ≠ Account Sharing

❌ ใช้บัญชีเดียวกันหลายคน
❌ แชร์รหัสผ่าน

✅ FIDM:

* ผู้ใช้แต่ละคนมี identity ของตัวเอง
* ตรวจสอบย้อนหลังได้
* รองรับ Audit และ Compliance

---

## 9. ตัวอย่าง FIDM ที่ใช้จริง

| กรณีใช้งาน                  | FIDM |
| --------------------------- | ---- |
| Login Google → SaaS         | ✔    |
| Login Microsoft → Cloud     | ✔    |
| Partner เข้าใช้ระบบลูกค้า   | ✔    |
| นักศึกษาใช้บัญชีมหาวิทยาลัย | ✔    |

---

## 10. ความสัมพันธ์ FIDM กับ IAM

```
IAM
 ├─ Authentication
 │   ├─ SSO
 │   └─ FIDM
 └─ Authorization
```

* IAM เป็นภาพรวมทั้งหมด
* FIDM เป็นส่วนหนึ่งของการยืนยันตัวตน

---

## 11. ข้อดีและข้อจำกัดของ FIDM

### ข้อดี

* ไม่ต้องสร้าง user ซ้ำ
* ลดภาระผู้ดูแลระบบ
* ปลอดภัยกว่า account sharing

### ข้อจำกัด

* ต้องมีข้อตกลง Trust ระหว่างองค์กร
* การ Debug ยากกว่า SSO ปกติ

---

## 12. สรุปสั้นจำง่าย

> **FIDM = การใช้ตัวตนจากองค์กรหนึ่ง
> ไปยืนยันตัวกับระบบของอีกองค์กรหนึ่ง**

คำสำคัญ:

* Federation
* Trust
* Assertion / Token

---

*เอกสารนี้ต่อยอดจาก SSO เพื่ออธิบายการทำ Identity ข้ามองค์กร*
