# แบบบันทึกผลการทดลองที่ 10.3
## CoAP Server สำหรับระบบฝังตัวและการควบคุมอุปกรณ์ด้วยโปรโตคอลน้ำหนักเบา

> อ้างอิงใบงาน: [08-Labsheet-10-3-CoAP-Server-and-Lightweight-IoT-Control.md](../08-Labsheet-10-3-CoAP-Server-and-Lightweight-IoT-Control.md)
> โค้ดโปรเจกต์: `Code/Lab10-3_CoAP_Server/`

| รายการ | ข้อมูล |
| :--- | :--- |
| ชื่อ–นามสกุล | |
| รหัสนักศึกษา | 67030098 |
| วันที่ทำการทดลอง | |
| IP Address ของ ESP32 | |
| พอร์ต CoAP | 5683 (UDP) |
| เวอร์ชันคอมโพเนนต์ `espressif/coap` | |
| Stack Size ของ `coap_server_task` | |

---

## ส่วนที่ 1 บันทึกผลการทดลอง (กิจกรรมที่ 10-3.5)

### 1.1 ผลการทดสอบ Resource Discovery — `GET /.well-known/core`

**ผลลัพธ์ดิบที่ได้รับ (CoRE Link Format)**
```text

```

**ตารางถอดความ Resource Directory** *(สำหรับตอบคำถามข้อ 1)*

| Resource URI | Attribute ที่ประกาศ (`rt=`, `if=`, `ct=` ฯลฯ) | ความหมาย |
| :--- | :--- | :--- |
| | | |
| | | |

---

### 1.2 ผลการอ่านค่าเซนเซอร์ — `GET /sensor/pot`

| รายการ | ผลที่บันทึกได้ |
| :--- | :--- |
| Response Code | |
| Payload ที่ได้รับ | |
| ขนาด Payload (ไบต์) | |
| Content-Format (`ct`) | |

**ผลลัพธ์จาก Terminal**
```text

```

---

### 1.3 ผลการสั่งเปิด–ปิด LED — `PUT /actuator/led`

| คำสั่งที่ส่ง | Payload | Response Code | สถานะ LED บนบอร์ด (ติด/ดับ) |
| :--- | :---: | :--- | :--- |
| `PUT /actuator/led` (เปิด) | `1` | | |
| `PUT /actuator/led` (ปิด) | `0` | | |

---

### 1.4 ผลการทดสอบ CON (Confirmable) เทียบกับ NON (Non-confirmable)

| รายการเปรียบเทียบ | CON (Confirmable) | NON (Non-confirmable) |
| :--- | :--- | :--- |
| Message Type ใน Header | | |
| มีการตอบ ACK กลับหรือไม่ | | |
| จำนวนแพ็กเก็ตต่อ 1 คำสั่ง | | |
| RTT เฉลี่ยที่วัดได้ (ms) | | |
| ผลเมื่อทดสอบในสภาวะสัญญาณปกติ | | |
| ผลเมื่อทดสอบในสภาวะสัญญาณรบกวน/อ่อน | | |
| พฤติกรรมการ Retransmission | | |

**วิธีจำลองสัญญาณรบกวนที่ใช้** *(เช่น ย้ายบอร์ดออกห่าง AP, ปิดกั้นสัญญาณ, โหลดเครือข่ายหนัก)*
```text

```

---

### 1.5 ผลการทดสอบ CoAP Observe (RFC 7641)

| รายการ | ผลที่บันทึกได้ |
| :--- | :--- |
| Resource ที่ Observe | |
| จำนวน Notification ที่ได้รับในช่วง 30 วินาที | |
| เงื่อนไขที่ทำให้เกิด Notification | |
| ค่า Observe Option ที่เพิ่มขึ้นในแต่ละ Notification | |

**ผลลัพธ์จาก Terminal**
```text

```

**บันทึกเพิ่มเติม / ปัญหาที่พบระหว่างทดลอง**
```text

```

---

## ส่วนที่ 2 คำถามท้ายการทดลอง

### คำถามข้อ 1
**นำผลการ Query `/.well-known/core` มาแสดงในรายงาน พร้อมอธิบายรูปแบบ CoRE Link Format (RFC 6690) ว่าแสดงข้อมูลทรัพยากรอย่างไร**

**ผลการ Query**
```text

```

**อธิบายรูปแบบ CoRE Link Format**
```text

```

---

### คำถามข้อ 2
**อธิบายความแตกต่างของแพ็กเก็ต CoAP ระหว่าง CON (Confirmable) และ NON (Non-confirmable) เมื่อทดสอบในเครือข่ายที่มีการรบกวนสัญญาณ**

**คำตอบ** *(อ้างอิงผลที่บันทึกในตารางข้อ 1.4)*
```text

```

---

### คำถามข้อ 3
**ทำไม CoAP จึงเหมาะสมกับโปรโตคอลการสื่อสารบนเครือข่ายเช่น Thread, Zigbee IP หรือ NB-IoT มากกว่า HTTP?**

**คำตอบ** *(พิจารณาขนาด MTU ของ 6LoWPAN, พลังงานแบตเตอรี่, Radio Airtime, Header 4 ไบต์ เทียบกับ Plaintext Header ของ HTTP, และการไม่ต้องทำ TCP Handshake)*
```text

```

---

## ส่วนที่ 3 สรุปผลการทดลอง

```text

```
