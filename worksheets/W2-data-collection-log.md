<!-- workshop-header -->
<img width="1347" height="127" alt="Coding Thailand 2026 header" src="https://github.com/user-attachments/assets/ba5cf267-f460-4fb0-b69b-c461ae061a3b" />

# 📝 Worksheet W2 — Data Collection Log

> **ทำในช่วง 10:30-12:00**
> บันทึก process ของการเก็บข้อมูล

---

## ข้อมูลทีม + Edge Impulse

- **ชื่อทีม:** WNYCS
- **Edge Impulse Project URL:**
  ```
  https://studio.edgeimpulse.com/studio/1011912/acquisition/training
  ```

---

## 1. Setup Log

ก่อนเริ่มเก็บข้อมูล ทีมทำอะไรบ้าง?

| เวลา | ทำอะไร | ผู้รับผิดชอบ |
|---|---|---|
| 10:30 | มีการแฟชรเพื่อพูดเสียงเก็บ Data ลงในโฟรเดอร์ | อิทธินพ/บุณยพัต|
| 10:35 | ได้มีการแยกกันทำ Track1/Track2 เเล้วเริ่มการทำงาน|อิทธินพ/รัชพล |
| | | |

---

## 2. Data Collection Sessions

บันทึกแต่ละ session การเก็บข้อมูล:

### Session 1

- **เวลา:10.50ถึง 11.00
- **Class:** สีเเดง
- **จำนวน samples ที่เก็บ:** 20
- **สภาพแวดล้อม:** มีเสียงนิดหน่อยในการเก็บ
- **ใครเป็น subject?:** บุณยพัต
- **Variation ที่ลอง:** เก็บDataในโฟลเดอร์
- **ปัญหาที่เจอ: มีเสียงคนด้านนอกนิดหน่อย

### Session 2

- **เวลา 11.10 ถึง 11.25
- **Class:**  สีฟ้า
- **จำนวน samples ที่เก็บ: 20
- **สภาพแวดล้อม:** มีเสียงที่ชัดเจนขึ้น
- **ใครเป็น subject?:** อิทธินพ/รัชพล
- **Variation ที่ลอง:** เก็บDataในโฟลเดอร์
- **ปัญหาที่เจอ:** ปัญญาเริ่มน้อยลง

### Session 3

- **เวลา:** 11.30 ถึง 11.45
- **Class:** สีเขียว
- **จำนวน samples ที่เก็บ:** 20
- **สภาพแวดล้อม:** ดี
- **ใครเป็น subject?:** บุณยพัต
- **Variation ที่ลอง:** มีการพูดไกลเเละใกล้
- **ปัญหาที่เจอ:** ปัญหามีเสียงตอนที่เราพูดใกล้ไมค์ดังเกินไป

### Session 4

- **เวลา:** 11.50 ถึง 12.10
- **Class:** ไม่มี
- **จำนวน samples ที่เก็บ:** 20
- **สภาพแวดล้อม:** ดี
- **ใครเป็น subject?:** บุณยพัต
- **Variation ที่ลอง:** ไม่มี
- **ปัญหาที่เจอ:** -

> หาก session มากกว่า 3 ให้ copy template เพิ่ม

---

## 3. Dataset Summary

| Class | จำนวน Train | จำนวน Test | สัดส่วน Train:Test |
|เเดง |7|3|7:3|
| ฟ้า| | 7|3|7:3|
| เขียว | 7| 3|7:3|
| ไม่มัี| | 7| 3|7:3|
| **รวม** | 28| 12| 28:12|

**เป้าหมายตาม W1:** 100% samples × class
**ทำได้จริง: 93% samples × class
**ห่างจากเป้า:** 7%

---

## 4. Quality Check

ตอบทุกข้อก่อนเริ่ม train:

- [ ✓ ] ทุก class มี samples ใกล้เคียงกัน (ไม่ต่างกันเกิน 20%)
- [ ] เก็บใน ≥2 สภาพแวดล้อม
- [ ✓ ] เก็บจาก ≥2 subjects (Vision/Audio/Motion ที่มีคน)
- [ ] มี variation ใน angle/distance/lighting
- [ ✓ ] ไม่มี mislabeled data (เช็คตัวอย่างแล้ว)
- [ ✓] Train:Test split = 80:20

---

## 5. Reflection — สิ่งที่เรียนรู้

### a) สิ่งที่ยากที่สุด: การเอาArdunio uno Qใน Edge implus
```
[เขียนสั้นๆ]
```

### b) ถ้าทำใหม่จะปรับอะไร: ถ้ามีเวลามากพอมีการเก็บDataที่มากขึ้นเเล้วอาจจะเพิ่มความเเม่นยำมากขึ้น
```
[เขียนสั้นๆ]
```

### c) คาดการณ์: model จะ confuse class ไหนกับอะไรมากที่สุด? :อาจไปได้ด้วยดี ด้วยการที่เราเก็บDataเยอะมาก
```
[เขียนการคาดเดา — เราจะมาเช็คตอน Train เสร็จ]
```

---

## 📤 วิธี submit

```bash
git add worksheets/W2-data-collection-log.md
git commit -m "docs: data collection log เก็บได้ครบ X samples ใน Y session"
git push
```

---

## 💡 Best Practices

1. **อย่าเก็บข้อมูลที่ "สมบูรณ์แบบ" หมด** — โลกจริงไม่สมบูรณ์แบบ
2. **เก็บข้อมูล "เหมือนไม่ใช่ class ใดเลย" เป็นอีก class** = noise/background class
3. **สลับคนเก็บ** — กัน bias ของ subject เดียว
4. **เช็คตัวอย่างทุก 20 samples** — กัน mislabel
