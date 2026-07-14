Cane Next+ — ทดลองจำกัดข้อมูลตาม User จริง

จากภาพปัจจุบัน:
- extension ที่ zone=2, subzone ว่าง จะเห็นทั้งเขต 2
- extension ที่ zone=2, subzone=2002 จะเห็นเฉพาะเขตย่อย 2002
- admin จะเห็นทุกข้อมูล
- manager ที่ zone เป็น NULL ต้องกำหนด zone ก่อนทดลอง มิฉะนั้นจะไม่เห็นข้อมูล

ขั้นตอน:
1. สำรองฐานข้อมูลหรือทดลองใน Project ทดสอบก่อน
2. Supabase > SQL Editor > New query
3. เปิด zone_subzone_rls_live.sql คัดลอกทั้งหมด วาง แล้ว Run
4. เปิด New query ใหม่ และ Run verify_before_live_test.sql
5. ตรวจ user_profiles:
   - role ต้องถูกต้อง
   - status = active
   - manager/extension ต้องมี zone
   - กำหนด subzone เฉพาะคนที่ต้องเห็นเขตย่อยเดียว
6. อัปโหลด index.html และ config.js ขึ้น GitHub Pages
7. Ctrl+F5, Logout แล้ว Login ใหม่

การทดลอง:
A. Login Admin
   - เห็นทุกเขต
   - Data Management และจัดการผู้ใช้งานแสดง

B. Login Extension zone=2, subzone=NULL
   - เห็นชาวไร่ทุกเขตย่อยในเขต 2
   - ไม่เห็นเขตอื่น

C. Login Extension zone=2, subzone=2002
   - เห็นเฉพาะชาวไร่เขต 2 เขตย่อย 2002
   - ไม่เห็นเขตย่อยอื่นและเขตอื่น

การเพิ่ม User ในอนาคต:
- สร้างบัญชี Authentication
- เพิ่ม/แก้ user_profiles ให้มี auth_uid, role, zone, subzone, status
- ไม่ต้องแก้ SQL หรือ HTML ใหม่
- Policy เดิมจะใช้กับ User ใหม่ทันที

หมายเหตุ:
เขต 2 และ 02 จะถือว่าเป็นเขตเดียวกัน
เขตย่อย 2002 และ 20-02 จะเปรียบเทียบจากตัวเลขและถือว่าเป็นค่าเดียวกัน
