# 🏛️ ระบบรวบรวมขั้นตอนการอบรม (Training Workflow Portal Hub)
### กลุ่มงานนิเทศ ติดตาม และประเมินผลการจัดการศึกษา สำนักงานศึกษาธิการจังหวัดเชียงใหม่
**ออกแบบและพัฒนานวัตกรรมโดย:** ศน.รัชภูมิ สมสมัย

---

## 📌 ภาพรวมระบบ (System Overview)
ระบบรวบรวมขั้นตอนการอบรม (Training Workflow Portal Hub) เป็น Web Application สไตล์ **Minimal เชิงวิชาการ (Academic Minimal)** พัฒนาขึ้นเพื่อให้บริการและบริหารจัดการขั้นตอนการจัดอบรมสำหรับครูและบุคลากรทางการศึกษาในจังหวัดเชียงใหม่ ครอบคลุม 5 บริการหลัก:

1. **📋 หลักสูตร / ลิงก์สมัครอบรม (Training Course & Registration):** แสดงรายการหลักสูตรอบรม สถานะการรับสมัคร รูปแบบ (Online / Onsite / Hybrid) วันเวลา และพิกัดสถานที่จัดผ่าน Google Maps (Column I: `Link registration`)
2. **👥 ลิงก์รายชื่อผู้สมัคร (Applicant List):** ลิงก์ตรวจสอบรายชื่อผู้สมัครเข้ารับการอบรม (Column J: `Link name`)
3. **📚 ลิงก์เอกสารประกอบการบรรยาย (Training Materials - 2 URLs):** เชื่อมโยงเอกสาร สื่อ Canva หรือไฟล์ประกอบการอบรม (Column H: `Link materials`)
4. **✅ ลิงก์ตรวจสอบความถูกต้องของรายชื่อ (Recheck List):** ลิงก์ตรวจสอบและยืนยันความถูกต้องของรายชื่อผู้เข้ารับการอบรม (Column L: `Link recheck`)
5. **🏅 ดาวน์โหลดเกียรติบัตรออนไลน์ (E-Certificate):** เชื่อมโยงระบบค้นหาและพิมพ์เกียรติบัตรอัตโนมัติ (Column K: `Link certificated`)
6. **📑 ผลการอบรม & การถอดบทเรียน (Post-Training Outcomes):**
   - **📝 สรุปความคิดเห็นเพื่อนครู (Padlet):** ลิงก์เอกสารสรุปข้อคิดเห็นและข้อเสนอแนะจาก Padlet (Column M: `Link padlet`)
   - **🎙️ ถอดเทปและสรุปภาพรวมการอบรม:** ลิงก์เอกสารถอดบทเรียนและสรุปภาพรวมจากการอบรมออนไลน์/ไฮบริด (Column N: `Link summary`)

---

## 🚀 ฟีเจอร์เด่น (Key Features)
- **🎨 สไตล์ Minimal เชิงวิชาการ:** ดีไซน์สะอาด สบายตา ลำดับข้อมูลชัดเจน พร้อม 3 โทนสีวิชาการ (Classic Academic 🏛️, Forest Academic 🌿, Warm Minimal ☕)
- **🔠 ปรับขนาดตัวอักษร:** รองรับการปรับขนาดฟอนต์ (ก-, ก, ก+) เพื่อความสะดวกในการอ่าน
- **🔍 ระบบค้นหาและตัวกรอง:** ค้นหาหลักสูตรตามชื่อ กลุ่มเป้าหมาย หรือกรองตามรูปแบบการจัด
- **🗺️ แผนที่ Interactive (Leaflet Map):** ปักหมุดพิกัดสถานที่จริงพร้อมระบบ Reverse Geocoding อัตโนมัติ
- **🛡️ โหมดผู้ดูแลระบบ (Admin Mode):** เข้าสู่ระบบด้วย PIN พร้อมระบบ **Auto-Sync** ข้อมูลหลักสูตรไปยังแท็บเอกสารและรายชื่ออัตโนมัติ
- **⚡ รองรับ 2 ระบบการติดตั้ง:** ใช้งานได้ทั้งบน **Google Apps Script** โดยตรง และ Host บน **Vercel / GitHub Pages**

---

## 📁 โครงสร้างไฟล์ในโครงการ

```text
├── index.html        # หน้าเว็บหลัก (Academic Minimal UI - ใช้งานบน Vercel / GitHub / GAS)
├── index.txt         # ไฟล์ HTML สำหรับคัดลอกลง Google Apps Script (Index.html)
├── code.txt          # โค้ด Google Apps Script Backend (Code.gs) พร้อมระบบ REST API
├── vercel.json       # ไฟล์คอนฟิกสำหรับการ Deploy บน Vercel
├── .gitignore        # ไฟล์ละเว้นที่ไม่จำเป็นขึ้น Git
└── README.md         # คู่มือและเอกสารประกอบโครงการ
```

---

## 🌐 ขั้นตอนการนำขึ้น GitHub & Vercel

### 1. นำขึ้น GitHub
1. เปิด Terminal ในโฟลเดอร์โครงการนี้ แล้วรันคำสั่ง:
   ```bash
   git init
   git add .
   git commit -m "feat: Academic Minimal UI for Training Workflow Portal"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo-name>.git
   git push -u origin main
   ```

### 2. นำขึ้น Vercel
1. เข้าสู่เว็บไซต์ [vercel.com](https://vercel.com) แล้วเข้าสู่ระบบด้วย GitHub
2. กด **Add New Project** > เลือก Repository ที่เพิ่ง Push ขึ้นไป
3. ในส่วน **Framework Preset** ให้เลือกเป็น `Other`
4. กดปุ่ม **Deploy**
5. เว็บไซต์จะพร้อมใช้งานทันที และได้ URL สำหรับแชร์ใช้งาน (เช่น `https://your-app.vercel.app`)

---

## ⚙️ การตั้งค่า Google Apps Script (Backend)
1. นำโค้ดใน [`code.txt`](file:///code.txt) ไปวางใน **Apps Script (Code.gs)**
2. นำโค้ดใน [`index.txt`](file:///index.txt) ไปวางใน **Apps Script (Index.html)**
3. กด **Deploy (การทำให้ใช้งานได้)** > **New Deployment (การทำให้ใช้งานได้ใหม่)**
   - เลือกประเภท: **Web App (เว็บแอป)**
   - Execute as: **Me (ฉัน)**
   - Who has access: **Anyone (ทุกคน)**
4. คัดลอก **Web App URL** ที่ได้ มาใส่ในหน้าเว็บ (กดไอคอนฟันเฟือง ⚙️ ในโหมดผู้ดูแลระบบ) เพื่อเชื่อมต่อ API ระหว่าง Vercel และ Google Sheet
