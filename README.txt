Cane Next+ Supabase Search Fix

แก้ไข:
- Business Partner ค้นหาจาก farmers ตาม farmer_code หรือชื่อ
- โหลด production_history, guarantees และ debt_summary ตาม farmer_code
- ข้อมูลแปลงจริงค้นหาจาก plots ตาม farmer_code
- ตัวกรองปีใช้เฉพาะข้อมูลแปลงของชาวไร่ที่ค้นหา
- Scenario Setup ใช้ข้อมูลแปลงจริงที่โหลดจาก Supabase
- รองรับกด Enter เพื่อค้นหา

อัปโหลด index.html และ config.js ขึ้น GitHub Pages ในโฟลเดอร์เดียวกัน
จากนั้นกด Ctrl+F5 และ Login ใหม่
