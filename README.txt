Cane Next+ Stable Farmer Context

แก้ปัญหา Page Unresponsive:
- ลบ wrapper ซ้อนของ searchBusinessPartner และ showMainMenu
- ลบ event click ที่ re-wrap ฟังก์ชันซ้ำไม่สิ้นสุด
- ใช้ CustomEvent canenext:farmer-changed เพียงครั้งเดียว
- Query Farmer และ Plot ครั้งเดียวหลังค้นหา Business Partner
- เมนูอื่นอ่านข้อมูลจาก Context/LocalStorage โดยไม่ค้นหาซ้ำ
- ปุ่มค้นหากลับเป็นปกติใน finally เสมอ

อัปโหลด index.html และ config.js ขึ้น GitHub
กด Ctrl+F5 แล้ว Login ใหม่
