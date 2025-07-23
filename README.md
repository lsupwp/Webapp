# 📌 SprintFlow - Project Backlog & Agile Workflow Platform

## 🧾 System Requirements (ฉบับเต็ม)

### 1. Functional Requirements (ความสามารถหลักของระบบ)

#### 🔹 User & Authentication
- ผู้ใช้สามารถสมัครสมาชิก / ล็อกอิน / ล็อกเอาท์
- ระบบรองรับการลืมรหัสผ่าน / รีเซ็ต
- ระบบจัดการสิทธิ์ผู้ใช้ด้วย Role-based Access Control (RBAC)

#### 🔹 Project Management
- ผู้ใช้สามารถสร้างหลายโปรเจกต์ได้
- เจ้าของโปรเจกต์สามารถเชิญสมาชิกเข้าร่วม
- กำหนดบทบาทสมาชิกในแต่ละโปรเจกต์ เช่น Owner, Developer, Tester
- ผู้ใช้ 1 คนสามารถอยู่ได้หลายโปรเจกต์

#### 🔹 State Management (Custom Workflow)
- เพิ่ม ลบ แก้ไข ลำดับของ State ได้ เช่น Backlog, Todo, Doing, Test, Done
- ตั้ง “หัวหน้า” (responsible user) ให้กับแต่ละ State
- ตั้ง State ที่จะเป็น Default หลัง Reject
- เซฟ Workflow Template ไว้ใช้กับโปรเจกต์อื่นได้

#### 🔹 Task Management
- สร้าง แก้ไข ลบ Task ในแต่ละโปรเจกต์
- ตั้งชื่อ, รายละเอียด, วันครบกำหนด, ผู้รับผิดชอบ
- ลาก Task ระหว่าง State ได้ (drag & drop)
- ติด Tag / Label ให้ Task ได้
- แนบไฟล์, คอมเมนต์, mention สมาชิกได้

#### 🔹 Notification System
- แจ้งเตือนเมื่อ Task ถูกมอบหมาย
- แจ้งเตือนเมื่อ Task เข้า State ที่มีผู้รับผิดชอบ
- แจ้งเตือนเมื่อ Task ถูก Reject พร้อมเหตุผล
- แจ้งเตือนในเว็บ (In-app), Email, หรือ Line Notify (optional)

#### 🔹 Reject System
- หัวหน้า State สามารถกด Reject Task ได้
- ต้องใส่เหตุผลประกอบการ Reject
- Task ถูกส่งกลับ State ที่กำหนดไว้ (default หรือเลือกได้)
- บันทึกประวัติการ Reject (reason, เวลา, โดยใคร)

#### 🔹 Comment & Activity Log
- สมาชิกสามารถคอมเมนต์ใต้ Task
- Mention (@username) เพื่อแจ้งเตือน
- Log การกระทำทั้งหมดใน Task เช่น สร้าง, ย้าย, มอบหมาย, Reject

#### 🔹 Dashboard & Summary
- ดูสรุปจำนวน Task ต่อ State
- แสดงความคืบหน้าโปรเจกต์ (เช่น Done %)
- ตัวกรองและค้นหา Task ตามชื่อ, ผู้รับผิดชอบ, วันที่, State

---

### 2. Non-functional Requirements (ความต้องการเสริม)
- รองรับทุกอุปกรณ์ (Responsive Web App)
- รองรับหลายภาษา (optional)
- ระบบมีความปลอดภัย (JWT/OAuth, HTTPS, Access Control)
- ระบบทำงานเร็วแม้ Task เยอะ
- มีระบบ Backup & Recovery (optional)
- รองรับการ Integrate กับ API ภายนอก (optional)

---

## ✅ Feature List (รายการฟีเจอร์ฉบับเต็ม)

| หมวด | รายการฟีเจอร์ |
|------|----------------|
| 👤 **User Management** | - สมัครสมาชิก, ล็อกอิน, รีเซ็ตรหัส <br> - แก้ไขโปรไฟล์ <br> - ดูโปรเจกต์ที่ตนมีส่วนร่วม |
| 📁 **Project Management** | - สร้างโปรเจกต์ <br> - เชิญสมาชิก <br> - กำหนดสิทธิ์ (Owner, Dev, Tester) <br> - ลบ/แก้ไขโปรเจกต์ |
| 🧩 **Custom Workflow / State** | - เพิ่ม/ลบ/แก้ไขชื่อ State <br> - กำหนดลำดับการไหลของงาน <br> - ตั้งหัวหน้าผู้รับผิดชอบใน State นั้น <br> - ตั้ง State Default หลัง Reject <br> - Save เป็น Workflow Template ได้ |
| 📋 **Task Management** | - สร้าง/แก้ไข/ลบ Task <br> - มอบหมายผู้รับผิดชอบ <br> - ตั้งวันครบกำหนด <br> - ลากย้าย Task ข้าม State <br> - ใส่ Label/Tag, แนบไฟล์, คอมเมนต์ |
| 🔁 **Reject Workflow** | - หัวหน้าของ State กด Reject Task ได้ <br> - กรอกเหตุผล Reject <br> - ย้าย Task กลับ State ที่กำหนด <br> - แจ้งเตือนและบันทึกลง Log |
| 🔔 **Notification System** | - แจ้งเตือนผู้รับผิดชอบ Task ใหม่ <br> - แจ้งเตือนเมื่อ Task ถูก Reject <br> - แจ้งเมื่อ Task เข้า State ที่คุณดูแล <br> - แจ้งเตือนในแอป / Email / Line Notify (optional) |
| 💬 **Communication** | - คอมเมนต์ใต้ Task <br> - Mention สมาชิก <br> - แจ้งเตือนผ่านคอมเมนต์ |
| 📊 **Dashboard & Reporting** | - สรุป Task ตาม State <br> - กราฟความคืบหน้า (เช่น Pie Chart / Kanban View) <br> - ตัวกรอง / ค้นหาแบบละเอียด |
| 🔒 **Security & Access** | - Role-based Access (เช่น Test ห้ามลบ Task) <br> - Auth: JWT / OAuth2 <br> - การควบคุมสิทธิ์ต่อ Project |
| 🌐 **Other (Optional)** | - รองรับหลายภาษา (i18n) <br> - ตั้งค่าธีม <br> - API สำหรับเชื่อมกับแอปอื่น <br> - Export ข้อมูล Task เป็น CSV |

---
