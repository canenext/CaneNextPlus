# Cane Next+ — Supabase Integration

ไฟล์ในชุดนี้
- `index.html` — เว็บ Cane Next+ พร้อมเมนู Data Management และการตรวจสอบ Excel 6 Sheets
- `config.js` — Project URL และ Publishable Key
- `supabase/functions/import-cane-excel/index.ts` — Edge Function สำหรับ Import อย่างปลอดภัย

## เปิดเว็บ
อัปโหลด `index.html` และ `config.js` ไว้ในโฟลเดอร์เดียวกันบน GitHub Pages

## สิ่งที่ใช้งานได้ทันที
1. ตรวจสอบการเชื่อมต่อ Supabase
2. เลือกไฟล์ Excel
3. ตรวจชื่อ Sheet และคอลัมน์ทั้ง 6 Sheets
4. แสดงจำนวนแถวและ Preview 10 แถวแรก
5. มีตัวช่วย `CaneDB.getFarmerBundle(farmerCode)` สำหรับเชื่อม Business Partner

## ก่อนกด Import จริง
ต้องดำเนินการเพิ่ม:
1. เปิดใช้ Supabase Auth และสร้างบัญชี Admin
2. Deploy Edge Function `import-cane-excel`
3. เพิ่มการตรวจ role ของ Admin ใน Edge Function
4. ห้ามนำ Secret/Service Role Key ไปใส่ใน HTML หรือ config.js

## Deploy Edge Function ด้วย Supabase CLI
```bash
supabase login
supabase link --project-ref ibydxfuootlidzpaxdxp
supabase functions deploy import-cane-excel
```

Supabase จะจัดเตรียม `SUPABASE_URL`, `SUPABASE_ANON_KEY` และ
`SUPABASE_SERVICE_ROLE_KEY` ให้ Edge Function ในระบบโดยอัตโนมัติ
