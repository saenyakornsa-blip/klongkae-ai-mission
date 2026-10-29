# 🏫 Klongkae AI Mission: ภารกิจกู้ชีพครูไทย (โรงเรียนบ้านคลองแค)

เว็บแอปพลิเคชันเกมกระดานภารกิจ Workshop 10 สถานการณ์จริงของครูไทย (ธีมสดใส สบายตา) พร้อมระบบล็อกอินด้วยบัญชี **Gmail (Firebase Authentication)** ระบบเก็บสถิติเรียลไทม์ (**Cloud Firestore Free Tier**) และระบบออกรายงานผลราชการ 1 หน้า (One-Page Official Report)

---

## 🚀 วิธีอัปโหลดขึ้น GitHub Pages เพื่อใช้งานจริง (ฟรี 100%)

### ขั้นตอนที่ 1: สร้าง Repository บน GitHub
1. ลงชื่อเข้าใช้บัญชี GitHub (เช่น `saenyakornsa-blip`)
2. กดปุ่ม **New repository** ตั้งชื่อ например `klongkae-ai-mission`
3. เลือกเป็น **Public** แล้วกด **Create repository**

### ขั้นตอนที่ 2: อัปโหลดไฟล์จากชุดติดตั้งนี้
1. แตกไฟล์ซิป `klongkae-ai-mission-github-pages.zip`
2. ในหน้า Repository บน GitHub กด **Add file ➔ Upload files**
3. ลากไฟล์ทั้งหมด (`index.html`, `firestore.rules`, `.nojekyll`, `README.md`) ลงไป
4. กดปุ่มสีเขียว **Commit changes**

### ขั้นตอนที่ 3: เปิดใช้งาน GitHub Pages
1. ไปที่แถบเมนู **Settings** ของ Repository ➔ เลือกเมนู **Pages** ทางซ้ายมือ
2. ในหัวข้อ **Build and deployment (Branch)** เปลี่ยนจาก `None` เป็น **`main`** (โฟลเดอร์ `/ (root)`) แล้วกด **Save**
3. รอประมาณ 1–2 นาที เว็บไซต์จะพร้อมใช้งานที่ลิงก์:
   `https://<ชื่อผู้ใช้-github>.github.io/klongkae-ai-mission/`

---

## 🔥 วิธีเชื่อมต่อฐานข้อมูล Firebase Free Tier (Spark Plan) และการล็อกอิน Gmail

1. ไปที่ [Firebase Console](https://console.firebase.google.com/) แล้วกด **Add project** สร้างโปรเจกต์ใหม่ (ใช้แผน **Spark Plan ฟรี 100%**)
2. **เปิดระบบล็อกอิน Gmail:**
   - ไปที่เมนู **Authentication ➔ Sign-in method**
   - กดเปิดใช้งาน **Google** แล้วกด Save
   - ไปที่แท็บ **Authentication ➔ Settings ➔ Authorized domains** แล้วกด **Add domain** เพิ่มโดเมนของ GitHub Pages ของคุณ เช่น:
     `saenyakornsa-blip.github.io`
3. **เปิดฐานข้อมูลเก็บสถิติ (Cloud Firestore):**
   - ไปที่เมนู **Firestore Database ➔ Create database**
   - เลือก Location เป็น `asia-southeast1 (Singapore)` และเริ่มในโหมด **Test mode** (หรือใช้กฎในไฟล์ `firestore.rules`)
4. **นำโค้ด `firebaseConfig` มาใส่ในเว็บ:**
   - ไปที่ **Project Settings (รูปเฟือง) ➔ Your apps ➔ เลือกไอคอนเว็บ `</>`**
   - คัดลอกค่า `firebaseConfig` (เป็นรูปแบบ JSON) มาวางในปุ่ม **⚙️ ตั้งค่า Firebase** บนหน้าเว็บ หรือวางค่าเริ่มต้นลงในไฟล์ `index.html` ได้เลย
