Cane Next+ Master v2.1.1

ไฟล์สำหรับอัปโหลดขึ้น GitHub Pages:
- index.html
- config.js

ไฟล์สำหรับ Supabase:
- sql/manager_multizone_schema.sql
- supabase/functions/manage-users/index.ts

ขั้นตอนติดตั้ง:
1. อัปโหลด index.html และ config.js ไว้ในโฟลเดอร์เดียวกันบน GitHub Pages
2. Supabase > SQL Editor > New query
   Run sql/manager_multizone_schema.sql
3. Supabase > Edge Functions > manage-users
   แทนที่โค้ดด้วย supabase/functions/manage-users/index.ts แล้ว Deploy
4. เปิดหน้าเว็บ กด Ctrl+F5 แล้ว Logout/Login ใหม่

ข้อควรระวัง:
- config.js ใช้ Publishable Key เท่านั้น
- ห้ามนำ SUPABASE_SERVICE_ROLE_KEY ไปใส่ใน config.js หรือ index.html
- Service Role Key ต้องอยู่ใน Supabase Edge Function environment เท่านั้น
