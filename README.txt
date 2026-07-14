Cane Next+ Admin-only access fix

แก้ไข:
- Data Management แสดงและเปิดได้เฉพาะ Admin ที่ status=active
- จัดการผู้ใช้งาน แสดงและเปิดได้เฉพาะ Admin ที่ status=active
- Extension / Manager / Viewer ถูกส่งกลับไป Business Partner
- ป้องกันการเรียก Preview, Import และ User Management actions โดยตรงจาก JavaScript
- ตรวจสิทธิ์ใหม่ทุกครั้งเมื่อ Login/Logout เปลี่ยน

ติดตั้ง:
1. อัปโหลด index.html และ config.js ขึ้น GitHub Pages
2. กด Ctrl+F5
3. Logout แล้ว Login ใหม่

ความปลอดภัยฝั่ง Server:
- manage-users Edge Function ในแพ็กเกจตรวจ role=admin อยู่แล้ว
- สำหรับ import-cane-excel ต้องตรวจ Admin ใน Edge Function เช่นเดียวกัน หากใช้ Service Role
