Cane Next+ User Management

เพิ่มให้แล้ว:
- เมนูจัดการผู้ใช้งาน แสดงเฉพาะ Admin
- เพิ่มผู้ใช้
- แก้ไขชื่อ รหัสพนักงาน Role เขต เขตย่อย และสถานะ
- รีเซ็ตรหัสผ่าน
- เปิด/ปิดการใช้งาน
- ค้นหาผู้ใช้

ขั้นตอนติดตั้ง:
1. Supabase > SQL Editor
   Run ไฟล์ user_management_schema.sql

2. กำหนดบัญชีเดิมเป็น Admin:
   update public.user_profiles
   set role='admin', status='active'
   where email='อีเมลแอดมินของคุณ';

3. Deploy Edge Function ชื่อ manage-users
   ใช้ไฟล์ supabase/functions/manage-users/index.ts

4. อัปโหลด index.html และ config.js ขึ้น GitHub Pages

5. Logout และ Login ใหม่
   เมนูจัดการผู้ใช้งานจะแสดงเฉพาะ Admin
