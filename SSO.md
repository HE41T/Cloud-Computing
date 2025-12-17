# Single Sign-On (SSO) Explained

## 1. SSO คืออะไร

**SSO (Single Sign-On)** คือระบบที่ให้ผู้ใช้ **ล็อกอินเพียงครั้งเดียว** แล้วสามารถเข้าใช้งานหลายระบบได้โดยไม่ต้องกรอกรหัสผ่านซ้ำ
<img width="560" height="243" alt="image" src="https://github.com/user-attachments/assets/38e94f49-3751-459b-ba57-e290df7bfc74" />

> แนวคิดหลัก: *Authenticate ครั้งเดียว ใช้ได้หลายบริการ*

---

## 2. ปัญหาก่อนมี SSO

หากไม่มี SSO ผู้ใช้ต้อง:

* มีหลาย Username / Password
* เปลี่ยนรหัสผ่านหลายที่
* IT ต้องปิดบัญชีทีละระบบเมื่อพนักงานออก

ผลลัพธ์คือ:

* เสี่ยงด้านความปลอดภัย
* บริหารจัดการยาก
* ผู้ใช้สับสน

---

## 3. แนวคิดพื้นฐานของ SSO

เปรียบเทียบง่าย ๆ:

* ❌ ไม่มี SSO → กุญแจหลายดอก หลายประตู
* ✅ มี SSO → กุญแจดอกเดียว ทุกประตูเชื่อถือ

"กุญแจ" นี้คือ **ตัวตน (Identity)** ของผู้ใช้

---

## 4. องค์ประกอบหลักของ SSO
<img width="560" height="407" alt="image" src="https://github.com/user-attachments/assets/128b7787-6240-4545-afa6-ce06ada7fbc3" />

```
User → Identity Provider (IdP) → Application
```

### 4.1 User

* ผู้ใช้งานระบบ

### 4.2 Identity Provider (IdP)

* ระบบศูนย์กลางยืนยันตัวตน
* เก็บข้อมูลผู้ใช้ เช่น username, password, role

**ตัวอย่าง IdP**

* Google
* Azure AD / Entra ID
* Keycloak
* Okta

### 4.3 Application (Service Provider)

* ระบบปลายทาง เช่น HR, GitLab, Jira
* ไม่เก็บรหัสผ่านเอง
* เชื่อถือ IdP แทน

---

## 5. ขั้นตอนการทำงานของ SSO (Flow)

### Step 1: ผู้ใช้เข้า Application

* ระบบตรวจสอบว่า user ยังไม่ login

### Step 2: Redirect ไปที่ IdP

* ผู้ใช้กรอก username / password ที่ IdP เท่านั้น

### Step 3: IdP ตรวจสอบตัวตน

* Password
* MFA
* Policy

### Step 4: IdP ออก Token

ตัวอย่างข้อมูลใน Token:

```json
{
  "username": "heartyyy",
  "email": "user@company.com",
  "role": "employee"
}
```

### Step 5: ส่ง Token กลับไปที่ Application

* Application ตรวจสอบลายเซ็น
* สร้าง session
* อนุญาตเข้าใช้งาน

---

## 6. ทำไมเข้าได้หลายระบบโดยไม่ต้อง Login ซ้ำ

เพราะ IdP มี **Session กลาง**

* เมื่อ login ครั้งแรกแล้ว
* ระบบอื่นจะถาม IdP และได้รับการยืนยันทันที

นี่คือหัวใจของคำว่า **Single Sign-On**

---

## 7. Protocol ที่ใช้ใน SSO

### SAML 2.0

* ใช้ XML
* นิยมในองค์กรขนาดใหญ่

### OAuth 2.0

* เน้นการขอสิทธิ์เข้าถึง (Authorization)

### OpenID Connect (OIDC)

* ต่อยอดจาก OAuth 2.0
* ใช้ JSON / JWT
* เป็นมาตรฐาน SSO สมัยใหม่

> SSO ปัจจุบันนิยมใช้ **OIDC** มากที่สุด

---

## 8. SSO ≠ Authorization

* **SSO / Authentication**: คุณคือใคร
* **Authorization**: คุณทำอะไรได้บ้าง

ตัวอย่าง:

* SSO ยืนยันว่าเป็นพนักงาน
* ระบบภายในกำหนดสิทธิ์ตาม role

---

## 9. ข้อดีและข้อเสียของ SSO

### ข้อดี

* ผู้ใช้จำรหัสเดียว
* เพิ่มความปลอดภัย (MFA กลาง)
* Offboard ง่าย
* ลดภาระ IT

### ข้อเสีย

* IdP ล่ม = ทุกระบบเข้าไม่ได้
* ต้องออกแบบความเสถียรให้ดี

---

## 10. ตัวอย่างการใช้งาน SSO จริง

* Google Account → Gmail, YouTube, Drive
* Microsoft Account → Microsoft 365
* Kubernetes → OIDC กับ IdP

---

## 11. สรุปสั้นจำง่าย

> **SSO = ระบบศูนย์กลางยืนยันตัวตนหนึ่งเดียว
> ที่หลายระบบเชื่อถือร่วมกัน**

คำสำคัญที่ควรรู้:

* Identity Provider (IdP)
* Token
* Trust

---

*เอกสารนี้อธิบายเฉพาะ SSO (Single Sign-On) เพื่อเป็นพื้นฐานก่อนต่อยอดไปยัง FIDM, IAM และ Zero Trust*
