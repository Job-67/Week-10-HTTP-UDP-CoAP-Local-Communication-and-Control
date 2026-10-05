# แบบบันทึกผลการทดลองที่ 10.1
## mDNS Discovery และ HTTP RESTful API Server บน ESP-IDF

> อ้างอิงใบงาน: [06-Labsheet-10-1-mDNS-Discovery-and-HTTP-REST-Server.md](../06-Labsheet-10-1-mDNS-Discovery-and-HTTP-REST-Server.md)
> โค้ดโปรเจกต์: `Code/Lab10-1_HTTP_REST_Server/`

| รายการ | ข้อมูล |
| :--- | :--- |
| ชื่อ–นามสกุล | |
| รหัสนักศึกษา | 67030098 |
| วันที่ทำการทดลอง | |
| เวอร์ชัน ESP-IDF | |
| รุ่นบอร์ดที่ใช้ | |
| SSID เครือข่ายที่ทดสอบ | |
| IP Address ของ ESP32 | |

---

## ส่วนที่ 1 บันทึกผลการทดลอง (กิจกรรมที่ 10-1.5)

### 1.1 ผลการตรวจสอบ mDNS ด้วยคำสั่ง `ping esp32-node.local`

**คำสั่งที่ใช้**
```powershell
ping esp32-node.local
```

**ผลลัพธ์ที่ได้** *(วางข้อความจาก Terminal หรือแนบภาพหน้าจอ)*
```text

```

| รายการ | ผลที่บันทึกได้ |
| :--- | :--- |
| ชื่อโฮสต์ที่ประกาศผ่าน mDNS | |
| IP Address ที่ Resolve ได้ | |
| Round-trip time เฉลี่ยจาก ping (ms) | |
| ต้องแก้ปัญหา Troubleshooting หรือไม่ (Private Network / ถอดสาย LAN) | |

---

### 1.2 ผลการอ่านค่าเซนเซอร์ผ่าน `GET /api/status`

**คำสั่งที่ใช้**
```powershell
curl.exe -i -X GET http://esp32-node.local/api/status
```

**ผลลัพธ์แบบ verbose (`curl -i`) รวม HTTP Response Header** *(สำหรับตอบคำถามข้อ 2.1)*
```text

```

| รายการ | ผลที่บันทึกได้ |
| :--- | :--- |
| HTTP Status Code | |
| ค่า `pot_raw` ที่อ่านได้ | |
| ค่า `free_heap` (ไบต์) | |
| ค่า `led` | |

---

### 1.3 ผลการสั่งเปิด–ปิด LED ผ่าน `POST /api/led`

**คำสั่งที่ใช้**
```powershell
# สั่งเปิดไฟ LED (GPIO 2)
curl.exe -s -X POST http://esp32-node.local/api/led -H "Content-Type: application/json" -d '{\"state\": true}'

# สั่งปิดไฟ LED (GPIO 2)
curl.exe -s -X POST http://esp32-node.local/api/led -H "Content-Type: application/json" -d '{\"state\": false}'
```

| คำสั่งที่ส่ง | JSON Body | ข้อความตอบกลับ | สถานะ LED บนบอร์ด (ติด/ดับ) |
| :--- | :--- | :--- | :--- |
| `POST /api/led` (เปิด) | `{"state": true}` | | |
| `POST /api/led` (ปิด) | `{"state": false}` | | |

**บันทึกเพิ่มเติม / ปัญหาที่พบระหว่างทดลอง**
```text

```

---

## ส่วนที่ 2 คำถามท้ายการทดลอง

### คำถามข้อ 1
**นำผลการรัน `curl -i` (โหมด verbose เพื่อดู HTTP Response Header) มาแปะในรายงาน พร้อมวิเคราะห์ว่า HTTP Header มีขนาดกี่ไบต์ และข้อมูล JSON มีขนาดกี่ไบต์**

**ผลการรัน `curl -i`**
```text

```

**ตารางวิเคราะห์ขนาดข้อมูล**

| ส่วนของข้อมูล | เนื้อหาที่นับ | ขนาด (ไบต์) |
| :--- | :--- | :---: |
| HTTP Response Header | | |
| JSON Payload (Response Body) | | |
| ขนาดรวมทั้งหมด | | |
| สัดส่วน Payload ต่อข้อมูลรวม (%) | | |

**คำอธิบายและวิเคราะห์**
```text

```

---

### คำถามข้อ 2
**หากในเครือข่ายมีคอมพิวเตอร์ที่ไม่รองรับ mDNS หรือปิดกั้นพอร์ต UDP 5353 จะเกิดผลกระทบอย่างไร และแก้ไขได้อย่างไร?**

**ผลกระทบที่เกิดขึ้น**
```text

```

**แนวทางการแก้ไข**
```text

```

---

### คำถามข้อ 3
**เหตุใดจึงต้องเรียกคำสั่ง `cJSON_Delete(root)` และ `cJSON_free(resp)` เสมอหลังจากประมวลผลเสร็จสิ้น?**

**คำตอบ**
```text

```

---

## ส่วนที่ 3 สรุปผลการทดลอง

```text

```
