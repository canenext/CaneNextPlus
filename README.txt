Cane Next+ Direct Excel Import

สิ่งที่ต้องทำ:
1. Supabase > SQL Editor
   Run ไฟล์ direct_import_policies.sql
2. ตรวจใน user_profiles ว่าบัญชีของคุณ role=admin และ status=active
3. อัปโหลด index.html และ config.js ขึ้น GitHub Pages
4. Login ด้วยบัญชี Admin
5. Data Management > เลือก Excel > ตรวจสอบ > Import

ระบบใช้ Upsert:
- farmers: farmer_code
- plots: farmer_code + production_year + plot_id
- production_history: farmer_code + production_year
- guarantees: farmer_code + production_year
- debts: farmer_code
- harvests: farmer_code + production_year

ข้อมูลเดิมจะถูกอัปเดต ข้อมูลใหม่จะถูกเพิ่ม และไม่สร้างรายการซ้ำ
