Cane Next+ User Management

1) Supabase > SQL Editor
   เปิด user_management_schema.sql แล้ว Run

2) กำหนดบัญชีเดิมให้เป็น Admin
   update public.user_profiles
   set role='admin', status='active'
   where email='อีเมลแอดมินของคุณ';

3) Deploy Edge Function:
   supabase functions deploy manage-users

4) อัปโหลด index.html และ config.js ขึ้น GitHub Pages ในโฟลเดอร์เดียวกัน

5) Login ด้วยบัญชี Admin
   เมนู "จัดการผู้ใช้งาน" จะแสดงเฉพาะ Admin

Roles:
- admin: ทุกสิทธิ์
- manager: ข้อมูลระดับเขต
- extension: ข้อมูลระดับเขตย่อย
- viewer: ดูข้อมูลอย่างเดียว

หมายเหตุ:
Edge Function ใช้ Service Role เฉพาะบน Supabase Server เท่านั้น
ห้ามใส่ Secret/Service Role Key ใน HTML
